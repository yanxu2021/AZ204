# Connect your services together
## 1 Choose a messaging model in Azure to loosely connect your services
### 1.1 Choose whether to use messages or events
- Communication strategies in Azure (APIs)
- What is a message?In the terminology of distributed applications, messages have the following characteristics:

A message contains raw data, produced by one component, that will be consumed by another component.
A message contains the data itself, not just a reference to that data.
The sending component expects the message content to be processed in a certain way by the destination component. The integrity of the overall system may depend on both sender and receiver doing a specific job.

- What is an event? Events are lighter weight than messages, and are most often used for broadcast communications. The components sending the event are known as publishers, and receivers are known as subscribers.
- How to choose messages or events? For each communication, consider the following question: Does the sending component expect the communication to be processed in a particular way by the destination component? If the answer is yes, choose to use a message. If the answer is no, you may be able to use events.
### 1.2 Choose a message-based delivery with queues
- What is Azure Queue Storage? Queue storage is a service that uses Azure Storage to store large numbers of messages that can be securely accessed from anywhere in the world using a simple REST-based interface. Queues can contain millions of messages, limited only by the capacity of the storage account that owns it.
- What is Azure Service Bus Queues? Service Bus is a message broker system intended for enterprise applications. These apps often utilize multiple communication protocols, have different data contracts, higher security requirements, and can include both cloud and on-premises services. Service Bus is built on top of a dedicated messaging infrastructure designed for exactly these scenarios.

Both of these services are based on the idea of a queue, which holds sent messages until the target is ready to receive them.
- What are Azure Service Bus Topics? Azure Service Bus topics are like queues, but can have multiple subscribers. When a message is sent to a topic instead of a queue, multiple components can be triggered to do their work.Internally, topics use queues. When you post to a topic, the message is copied and dropped into the queue for each subscription. The queue means that the message copy will stay around to be processed by each subscription branch even if the component processing that subscription is too busy to keep up.
- Benefits of queues: Increased reliability, Message delivery guarantees, Transactional support
- Which service should I choose? Having understood that the communication strategy for this architecture should be a message, you must choose whether to use Azure Storage queues or Azure Service Bus, both of which can be used to store and deliver messages between your components. Each has a slightly different feature set, which means you can choose one or the other, or use both, depending on the problem you are solving.
### 1.3 Choose Azure Event Grid
- What is Azure Event Grid? Azure Event Grid is a fully-managed event routing service running on top of Azure Service Fabric.
- What is an event? Events are the data messages passing through Event Grid that describe what has taken place. 
- Types of event sources
- Event handlers
- Should you use Event Grid? Use Event Grid when you need these features:Simplicity, Advanced filtering, Fan-out, Reliability, Pay-per-event.
### 1.4 Choose Azure Event Hubs
- What is Azure Event Hubs?Event Hubs is an intermediary for the publish-subscribe communication pattern. Unlike Event Grid, however, it is optimized for extremely high throughput, a large number of publishers, security, and resiliency.
- Using Event Hubs
- Which service should I choose? Event Hubs lets you build a big data pipeline capable of processing millions of events per second with low latency. It can handle data from concurrent sources and route it to a variety of stream-processing infrastructures and analytics services. It enables real-time processing and supports repeated replay of stored raw data.
### 1.5 Knowledge check
1. Suppose you have a distributed application with a web service that authenticates users. When a user logs on, the web service notifies all the client applications so they can display that user's status as "Online". Is the login notification an example of a message or an event?
```
**Event**
The login notification is an event: it contains only a simple piece of status data and there is no expectation by the authentication service for the client applications to react to the notice in any particular way.
```
2. Suppose you have a distributed application with a web service that lets users manage their account. Users can sign up, edit their profile, and delete their account. When a user deletes their account, your web service notifies your data layer so the user's data will be removed from the database. Is the delete-account notification an example of a message or an event?
```
**Message**
The delete-account notification is a message. The key factor is that the web service has an expectation about how the data layer will process the message: the data layer must remove the user's data from the database for the system to function correctly. Note that the message itself contains only simple information so this aspect of the communication could be considered an event; however, the fact that the web service requires the data layer to handle the notification in a specific way is sufficient to make this a message.
```
## 2
