# Cloud PubSub

Message queue service (cf kafka)

- Write message.
- Another application reads service.
- Topic stores messages
- Subscription enabled application to read messages in queue.

Decoupling applications, making them asynchronous.

````
Publisher->Message->Topic->Subscription->Message
                    Topic->Message Storage
                           Subscription->Message<-Subscriber->Ack to Subscription when done.
````