# API Architectural Designs

## REST
### Representational State Transfer
Uses standard HTTP methods for resouce manipulation, making it stateless and efficient.
It promotes a client-server relationship with separation of concerns.
* Simple, resource oriented applications
* Utilizes standard HTTP methods (GET, POST, PUT, DELETE). Perfect for CRUD ops.
-> General purpose

## SOAP
### Simple Object Access Protocol
A protocol for exchanging XML data between web services. Both stateful and stateless activities
are supported. Iths highly scure.
* High securoity, enterprise applications
* XML based
-> Secure data transfers

## gRPC
### Google Remote Procedure Call
A high-performance RPC framework from Google. Uses protocol buffers for data serialization and
strongly-typed contract for services.
* Best for high performance, low latency distributed systems
* gRPC leverages HTTP/2 and protocol buffers(Protobufs)
* Supports bidirectional streaming
* Microservices where speed is critical
-> Microservice, real-time applications

## Web Sockets
A communcation protocol provoding full-duplex, bidirectional, real time communication over a single,
long-lived connection.
* persistent, two way communciation client server architecture
* ultra low latency, high interactivity
-> live, interactive applications

## MQTT
### Message Queueing Telemetry Transport
A lightweight and efficient messaging protocol designed for low-bandwidth. It uses a publish-subscribe
model for async communciation. Popular with IoT.
* lightweight, low bandwidth, power constraint
-> IoT and connected devices

#### reference: blog.amigoscode.com