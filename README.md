# nats--knative-messaging

NATS messaging enables the exchange of data that is segmented into messages among computer applications and services. 
These messages are addressed by ``` subjects ``` and do not depend on network location. This provides an abstraction 
layer between the application or service and the underlying physical network. Data is encoded and framed as a message and sent by a publisher. 
The message is received, decoded, and processed by one or more subscribers.

NATS core offers an at most once quality of service. 
- If a subscriber is not listening on the subject (no subject match), or is not active when the message is sent, the message is not received. This is the same level of guarantee that TCP/IP provides. 
- By default, NATS is a fire-and-forget messaging system. 
- If you need higher levels of service, you can use ```NATS Streaming``` or build additional reliability into your client applications with proven and scalable reference designs such as acks and sequence numbers.

NATS is a pub-sub model. But publishing and consuming messages depends on ``` subjects```. ```Subject``` is a string that provides a identifier or name that is used by publishers and consumers to identify each other. 

### Subject formats

- Subject can only contain alpha numeric string with dot.
- Subjects are case-sensitive and cannot contain whitespace
- For safety across clients, ASCII characters should be used, although this is subject to change in the future.


#### Subject Hierarchies

For example, there's an application named CBS. It has hrm, crm microserives. A subject that points to employee resource may be represented as ``` cbs.hrm.emaployee ``` for ```hrm``` microservice and ``` cbs.crm.emaployee ``` for ```crm``` microservice.

#### Wildcards
NATS provides two wildcards that can take the place of one or more elements in a dot-separated subject. Subscribers can use these wildcards to listen to multiple subjects with a single subscription but ``` Publishers will always use a fully specified subject, without the wildcard.```

##### Matching A Single Token

The first wildcard is * which will match a single token. For example if a subscriber want to listen from ``` cbs.hrm.emaployee ```  and  ``` cbs.crm.emaployee ```, it can simply supscribe tp  ``` cbs.*.emaployee ```








