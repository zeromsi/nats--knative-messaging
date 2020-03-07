# nats--knative-messaging

NATS messaging enables the exchange of data that is segmented into messages among computer applications and services. 
These messages are addressed by ``` subjects ``` and do not depend on network location. This provides an abstraction 
layer between the application or service and the underlying physical network. Data is encoded and framed as a message and sent by a publisher. 
The message is received, decoded, and processed by one or more subscribers.

NATS core offers an at most once quality of service. 
- If a subscriber is not listening on the subject (no subject match), or is not active when the message is sent, the message is not received. This is the same level of guarantee that TCP/IP provides. 
- By default, NATS is a fire-and-forget messaging system. 
- If you need higher levels of service, you can use ```NATS Streaming``` or build additional reliability into your client applications with proven and scalable reference designs such as acks and sequence numbers.
