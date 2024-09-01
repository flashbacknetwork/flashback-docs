# Light Node

A Light Node is a lightweight version of a blockchain node that does not store the entire blockchain but relies on other full nodes to access the data. This tutorial will guide you through setting up a Light Node using Nethermind as the execution client and Lighthouse as the consensus client.\
\
<mark style="color:red;">**WARNING: This tutorial is incomplete and only illustrates the process. Additional information related to the network version (testnet/mainnet) will be documented and added to this tutorial.**</mark>

## Step 1: Setting Up Your Environment

Before running the node, make sure your system is up to date.

```bash
bash sudo apt update && sudo apt upgrade -y
```

#### **Install Required Dependencies**

You need to install Docker and Docker Compose to manage your clients easily.

1.  **Install Docker**:

    ```bash
    bash sudo apt install docker.io -y
    sudo systemctl enable docker --now
    ```
2.  **Install Docker Compose**:

    ```bash
    bash sudo apt install docker-compose -y
    ```
3.  **Add Your User to the Docker Group**:

    ```bash
    bash sudo usermod -aG docker $USER
    ```

    Log out and back in to apply the changes.

## Step 2: Installing Nethermind Execution Client

Nethermind is a fast and flexible Ethereum execution client. To run Nethermind as a Light Node, we'll configure it to minimize resource usage.

1.  **Pull the Docker Image**:

    ```bash
    bash docker pull nethermind/nethermind
    ```
2.  **Run Nethermind as a Light Node**:

    Create a Docker Compose file named `docker-compose-nethermind.yml`:

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
        command: >
          --config goerli
          --Network.DiscoveryPort=30303
          --Network.P2PPort=30303
          --Sync.FastSync=true
          --JsonRpc.Enabled=true
          --JsonRpc.Host=0.0.0.0
          --JsonRpc.Port=8545
    ```

    Save the file and run:

    ```bash
    bashCopier le codedocker-compose -f docker-compose-nethermind.yml up -d
    ```

    This command will start Nethermind in a Light Node mode, configured to run on the Goerli testnet. You can replace `goerli` with `mainnet` for the main network.

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
3.  **Run Lighthouse as a Light Client**:

    Create a Docker Compose file named `docker-compose-lighthouse.yml`:

    ```yaml
    yaml version: '3.8'
    services:
      lighthouse:
        image: sigp/lighthouse:latest
        container_name: lighthouse
        restart: always
        ports:
          - 9000:9000/tcp
        command: >
          lighthouse bn
          --network goerli
          --http
          --http-address 0.0.0.0
          --http-port 5052
    ```

    Save the file and run:

    ```bash
    bash docker-compose -f docker-compose-lighthouse.yml up -d
    ```

    This command runs Lighthouse as a beacon node configured to connect to the Goerli testnet.

## Step 4: Connecting the Execution and Consensus Clients

To connect Nethermind and Lighthouse, you need to configure the consensus client (Lighthouse) to use the execution client (Nethermind).

1.  **Update Lighthouse Configurations**:

    Edit `docker-compose-lighthouse.yml` to add the `--execution-endpoint` parameter:

    ```yaml
    yaml command: >
      lighthouse bn
      --network goerli
      --http
      --http-address 0.0.0.0
      --http-port 5052
      --execution-endpoint http://nethermind:8545
    ```
2.  **Restart Lighthouse**:

    ```bash
    bash docker-compose -f docker-compose-lighthouse.yml up -d
    ```

This will ensure that Lighthouse uses Nethermind as its execution layer, enabling them to work together seamlessly.

## Step 5: Monitoring and Maintenance

* **Logs**: Use `docker logs -f nethermind` and `docker logs -f lighthouse` to monitor the logs for each client.
* **Health Check**: Ensure both clients are syncing properly and that the Light Node is functioning as expected.

## Step 6: Keeping Your Node Updated

Both Nethermind and Lighthouse are actively developed. It’s essential to keep your node up to date to avoid any network issues or vulnerabilities:

```bash
bash docker pull nethermind/nethermind
docker pull sigp/lighthouse:latest
docker-compose -f docker-compose-nethermind.yml up -d
docker-compose -f docker-compose-lighthouse.yml up -d
```
