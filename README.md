# Client-Server Communication using IPC Techniques and Threads

## Overview
This project establishes a connection between requesting clients, processing clients, and the server using Inter-Process Communication (IPC) techniques and threads. The server accepts requests from multiple requesting clients, forwards them to the appropriate processing clients, and then sends the processed results back to the respective requesting clients.

## Directory Structure
- `clients/`: Contains client-related code and scripts.
- `server/`: Contains server-related code and scripts.
- `vendor/`: Contains dependencies or additional libraries.
- `README.md`: Project documentation.

## IPC Techniques Used
- **FIFOs**: Used to send requests (addition, subtraction, and multiplication operations) from requesting clients to the server.
- **Pipes**: Used by the server to forward requests to the appropriate processing clients. Threads are created to handle the data processing.
- **Shared Memory**: Used for writing processed data back to the server from processing clients. Synchronization is achieved using thread semaphores.
- **Message Queues**: Used by the server to send the processed data back to the requesting clients.

## Features
- Multi-client support: Handles multiple requesting clients simultaneously.
- Thread-based processing: Utilizes threads for processing client requests efficiently.
- Synchronization: Ensures data consistency using thread semaphores.

## Getting Started

### Prerequisites
- Linux-based system
- C/C++ compiler
- Basic understanding of IPC mechanisms and thread programming

### Compilation and Execution
1. **Compile the Server and Client Programs**:
    Navigate to the `server` directory and run:
    ```sh
    cd server
    make
    ```

    Navigate to the `clients` directory and compile the clients as needed:
    ```sh
    cd clients
    make
    ```

2. **Run the Server**:
    ```sh
    ./server/main
    ```

3. **Run the Requesting Clients**:
    For example, to run the first requesting client:
    ```sh
    ./clients/rc1
    ```

4. **Run the Processing Clients**:
    For example, to run the processing client for request type 1:
    ```sh
    ./clients/rc2
    ```

## Example Usage

### Example 1: Sending a Request
1. Start the server:
    ```sh
    ./server/main
    ```

2. Start a requesting client and send a request (e.g., addition):
    ```sh
    ./clients/rc1
    ```

3. Start a processing client to process the request:
    ```sh
    ./clients/rc2
    ```

4. The server will forward the request to the processing client, receive the processed result, and send it back to the requesting client.

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

## License
This project is licensed under the MIT License.
