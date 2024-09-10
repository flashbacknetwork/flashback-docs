# Command Lines

<mark style="color:red;">**WARNING: This tutorial is incomplete and only illustrates the process. Additional information related to the network version (testnet/mainnet) will be documented and added to this tutorial.**</mark>

## Step 1: Setting Up Your Environment

Before running the node, make sure your system is up to date.

```bash
bash sudo apt update && sudo apt upgrade -y
```

### **Install Required Dependencies**

You need to install Docker and Docker Compose to manage your clients easily.

**Install Docker**:

```bash
bash sudo apt install docker.io -y
sudo systemctl enable docker --now
```

**Install Docker Compose**

```bash
bash sudo apt install docker-compose -y
```

**Add Your User to the Docker Group**:

```bash
bash sudo usermod -aG docker $USER
```

Log out and back in to apply the changes.

***

## Step 2: Installing Nethermind Execution Client

Nethermind is a fast and flexible Ethereum execution client. To run Nethermind as a Light Node, we'll configure it to minimize resource usage.

**Pull the Docker Image**

```bash
bash docker pull nethermind/nethermind
```

**Run Nethermind**

Create a Docker Compose file named `docker-compose-nethermind.yml`:

{% tabs %}
{% tab title="Full" %}
```yaml
yaml version: '3.8'
services:
  nethermind:
    image: nethermind/nethermind
    container_name: nethermind
    restart: always
    ports:
      - 30303:30303/tcp
      - 30303:30303/udp
      - 8545:8545/tcp
    volumes:
      - ./nethermind-data:/nethermind/data
    command: >
      --config mainnet
      --Sync.FullNode=true
      --Init.VerifiedSync=true
      --JsonRpc.Enabled=true
      --JsonRpc.Host=0.0.0.0
      --JsonRpc.Port=8545
```
{% endtab %}

{% tab title="Archive" %}
```yaml
yaml version: '3.8'
services:
  nethermind:
    image: nethermind/nethermind
    container_name: nethermind
    restart: always
    ports:
      - 30303:30303/tcp
      - 30303:30303/udp
      - 8545:8545/tcp
    volumes:
      - ./nethermind-data:/nethermind/data
    command: >
      --config mainnet
      --Sync.FullNode=true
      --Sync.Archive=true
      --Init.VerifiedSync=true
      --JsonRpc.Enabled=true
      --JsonRpc.Host=0.0.0.0
      --JsonRpc.Port=8545
```

The `--Sync.Archive=true` flag enables the Archive Node mode, allowing the client to store all historical states.
{% endtab %}
{% endtabs %}

This configuration sets up Nethermind as a Full Node on the mainnet. It also enables JSON-RPC for client interactions.

Save the file and run:

```bash
bash docker-compose -f docker-compose-nethermind.yml up -d
```

This command will start Nethermind in a Node mode, configured to run on the Goerli testnet. You can replace `goerli` with `mainnet` for the main network.

## Step 3: Installing Lighthouse Consensus Client

Lighthouse is a fast, secure, and efficient Ethereum consensus client. It’s written in Rust and optimized for performance.

1.  **Install Rust** (if not already installed):

    ```bash
    bash curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
    source $HOME/.cargo/env
    ```
2.  **Download and Build Lighthouse**:

    ```bash
    bash git clone https://github.com/sigp/lighthouse.git
    cd lighthouse
    make
    ```
3.  **Create a Docker Compose File for Lighthouse**:

    Create a file named `docker-compose-lighthouse.yml`:

    ```yaml
    yaml version: '3.8'
    services:
      lighthouse:
        image: sigp/lighthouse:latest
        container_name: lighthouse
        restart: always
        ports:
          - 9000:9000/tcp
          - 5052:5052/tcp
        volumes:
          - ./lighthouse-data:/root/.lighthouse
        command: >
          lighthouse bn
          --network mainnet
          --http
          --http-address 0.0.0.0
          --http-port 5052
          --execution-endpoint http://nethermind:8545
          --metrics
    ```

    This configuration will set up Lighthouse as a beacon node, connect it to the mainnet, and link it with Nethermind as the execution client.
4.  **Run Lighthouse**:

    Start the Lighthouse container using Docker Compose:

    ```bash
    bash docker-compose -f docker-compose-lighthouse.yml up -d
    ```

## Step 4: Connecting Execution and Consensus Clients

To ensure that Nethermind and Lighthouse work seamlessly together:

1.  **Update Lighthouse Configurations**:

    Ensure the `--execution-endpoint` is correctly set to the URL of your Nethermind client. This connects the execution client (Nethermind) to the consensus client (Lighthouse).
2.  **Restart Lighthouse**:

    ```bash
    bash docker-compose -f docker-compose-lighthouse.yml restart
    ```

## Step 5: Monitoring and Logging

* **Monitor Logs**: Use `docker logs -f nethermind` and `docker logs -f lighthouse` to view the logs for each client.
* **System Resource Monitoring**: Use tools like `htop`, `docker stats`, and `du` to monitor CPU, memory, and disk usage.

## Step 6: Maintaining Your Node

* **Regular Updates**: Keep both Nethermind and Lighthouse updated to ensure compatibility and security.
*   **Update Commands**:

    ```bash
    bash docker pull nethermind/nethermind
    docker pull sigp/lighthouse:latest
    docker-compose -f docker-compose-nethermind.yml up -d
    docker-compose -f docker-compose-lighthouse.yml up -d
    ```
* **Backup Data**: Regularly backup the data directories (`nethermind-data` and `lighthouse-data`) to prevent data loss.
