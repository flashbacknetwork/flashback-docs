# AddPiece (AP)

The initial stage of the sealing pipeline in the Filecoin network, known as AddPiece (AP), involves preparing data for cryptographic processing. Here's a detailed breakdown of the AddPiece process, essential for understanding how data is managed before it enters the cryptographic phases of Filecoin’s storage protocol.

## Overview

* **Function**: AddPiece is responsible for taking data, formatting it into the Content Addressed aRchive (CAR) file format, and organizing it within the sealing scratch space in preparation for the next stage, PreCommit 1 (PC1).
* **Data Representation**: In Filecoin, a "Piece" refers to data structured as an IPLD Directed Acyclic Graph (DAG) with associated PayloadCID and PieceCID, which uniquely identify the content.
* **Size Constraints**: The maximum size of a Piece aligns with the sector sizes available on the network—either 32 GiB or 64 GiB. If the original data exceeds the sector size, it must be divided into multiple Pieces, each with its own PieceCID.

## Technical Considerations

* **CPU Usage**: The AddPiece process is not computationally intensive regarding GPU requirements but utilizes several CPU cores. Despite this, it's a data-heavy operation that involves significant read/write operations on the storage volume.
* **Concurrency Management**: Given the high I/O demand during this process, limiting the number of concurrent AddPiece operations is advised. This is typically managed through setting an environment variable, such as `AP_32G_MAX_CONCURRENT=1`, to control the number of active instances, reducing the risk of overloading the system’s I/O capabilities.

## System Configuration and Optimization

* **Co-location with PC1**: Since AddPiece directly feeds into the PreCommit 1 (PC1) stage, running these processes on the same server is logical to minimize data transfer delays and streamline the workflow.
*   **Resource Allocation**: To prevent any single process from monopolizing system resources, which could lead to inefficiencies or slowdowns, you can use the `taskset` command to specify CPU core allocation for the AddPiece process:

    ```arduino
    arduino taskset -c <xx-xx> lotus-worker run ...
    ```

    Replace `<xx-xx>` with the specific range of CPU cores you wish to allocate, ensuring balanced resource usage across the server.

This setup helps maintain an efficient flow within the sealing pipeline, ensuring that each process stage is optimally configured to handle the demands placed upon it. By managing resources carefully and understanding the technical requirements of each stage, storage providers can enhance their operational efficiency and maintain high throughput in their Filecoin operations.
