# TCP (Transmission Control Protocol) – Overview

TCP stands for Transmission Control Protocol. It is a transport layer protocol that operates at Layer 4 of the OSI model.

TCP is a reliable and connection-oriented protocol. This means a connection must be established between sender and receiver before any data is transmitted. This connection is created using the three-way handshake.

## Key Characteristics of TCP

- Reliable delivery of data  
- Connection-oriented communication  
- Ordered data transmission  
- Error detection using checksum  
- Flow control using window size  
- Congestion control mechanisms  
- Full-duplex communication  

TCP ensures that data is delivered accurately, in order, and without duplication.

## Basic TCP Header Fields (High-Level)

- **Source Port:** Identifies the application on the sender's device.

- **Destination Port:** Identifies the application or service on the receiving device.

- **Sequence Number:** Represents the byte number of the first data byte in the current segment. It is used to maintain ordered delivery.

- **Acknowledgment Number:** Represents the next byte the receiver expects to receive. It confirms that all previous bytes have been successfully received.

- **Flags:**
  - **SYN:** Used to initiate a connection.
  - **ACK:** Used to acknowledge received data.
  - **FIN:** Used for graceful connection termination.
  - **RST:** Used to immediately terminate a connection.
  - **PSH:** Pushes buffered data to the application immediately.

- **Window Size:** Indicates how many bytes the receiver is currently able to accept. It is used for flow control.

- **Checksum:** Used to detect corruption in the TCP segment during transmission.
