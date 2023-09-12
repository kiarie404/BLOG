# Communication

## Protocols
Which communication protocols get used? Why? Why not?
### HTTPS
- [undone] read about HTTPS. This is HTTP, but the passed messages get encrypted.  
- HTTPS in request-response based, the client sends a request to the server, the server returns a response. Communication is bi-directional.  
- this protocol is mostly used by browsers to website servers.  

#### When to use https
- when communication is not meant to be continuous BUT initiated by client.  
- when communication is meant to be Bi-directional.
- When data is NOT time critical

#### Why avoid Https
1. encryption is processor and RAM expensive.
2. encryption is memory expensive, extra bytes to the frame. The HTTPS protocol adds some overhead to each data packet due to encryption and additional headers. In applications with limited bandwidth, this overhead can be a concern.
3.  HTTPS connections can introduce additional latency, especially when establishing the secure connection. For applications where real-time responsiveness is essential, such as industrial automation or remote control systems, this latency can be problematic. 
4.   IoT devices often need to maintain persistent connections to servers. HTTPS connections, by nature, are request-response-based, which means they are not ideal for continuous streaming or push-type communication. This can lead to inefficiencies when devices need to send or receive data frequently.
5.    IoT devices often send data that doesn't require a response from the server. In these cases, HTTPS can be seen as overkill because it establishes a bidirectional connection, which consumes more resources than necessary.


To address these challenges, IoT implementations may consider alternative communication protocols and strategies:

    MQTT (Message Queuing Telemetry Transport): MQTT is a lightweight publish-subscribe messaging protocol designed for IoT. It is often more efficient and less resource-intensive than HTTPS for certain IoT scenarios.

    CoAP (Constrained Application Protocol): CoAP is a lightweight protocol designed for resource-constrained IoT devices. It's efficient for low-power, low-latency applications.

    WebSocket: WebSocket provides full-duplex communication channels over a single TCP connection and is more suitable for real-time, bidirectional communication.

    Edge Computing: Some IoT applications benefit from processing data at the edge (i.e., on the device or a local gateway) before sending it to a central server. This can reduce the need for continuous HTTPS connections.

    Hybrid Approaches: In some cases, a hybrid approach may be suitable, where critical real-time data is sent over a low-latency protocol like MQTT, while less critical data is sent over HTTPS.

