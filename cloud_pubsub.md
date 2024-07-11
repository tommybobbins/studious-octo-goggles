# Cloud PubSub

Message queue service (cf kafka)

- Write message.
- Another application reads service.
- Topic stores messages
- Subscription enabled application to read messages in queue.

Decoupling applications, making them asynchronous. Each application needs it's own subscription.

````
Publisher->Message->Topic->Subscription->Message
                    Topic->Message Storage
                           Subscription->Message<-Subscriber->Ack
                                <-----------------------------Ack
````
Subscription can be a push if required. Without an Ack the message remains on the queue.

Dataflow jobs can read from pubsub and publish to BigQuery or Cloud Storage (Text or Avro)