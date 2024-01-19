#### Microservices
	- Small
	- Loosely coupled
	- They can fail independently
	

#### Principles
	- They should not share code or data
		○ Independence and Autonomy is more important than code reusability in Microservices
	- Microservices do not communicate directly to each other (decoupling)
		○ Instead use asynchronous event bus communication (producer-consumer)

#### CQRS
##### Command and Query Responsibility Segregation
	- Pattern that separates read and update operations for a data store.
	- Commands = writes (create-update-delete)
	- Query = reads (read)
	- It allows you to scale the command and query APIs independently from each other
	- Separation of concerns
	- Better optimization
	- Improve data security

#### Event Sourcing
	- The event store contains a complete auditable log with all the changes applied, instead of just storing the latest or current state
	- It improves write performance, since all events are simply appended to the event store. We never do any updates/deletes on the event store
	- In case of failure, the event store can be used to restore the read database.

#### Messages 
	1. Command
	2. Event
	3. Query


#### Mediator Pattern
The Mediator pattern is a behavioral design pattern that is used to reduce the complexity of communication between multiple objects or classes. This pattern provides a mediator class, which normally handles all the communications between different classes and supports easy maintenance of the code by loose coupling. The Mediator pattern is particularly useful in scenarios where an application has multiple components that interact with each other in complex ways, but you want to manage these interactions in a centralized or organized manner.

In a typical scenario using these components, when a command needs to be processed, it is sent to the CommandDispatcher. The dispatcher then determines which CommandHandler is appropriate for handling the command and forwards it accordingly. This way, the CommandHandlers don't need to know about each other, reducing the dependencies between them and making the system easier to maintain and extend.

#### Aggregate Root
AggregateRoot is an abstract class that forms the foundation of an Aggregate. In DDD, an Aggregate Root is the primary entry point to an Aggregate—a cluster of domain objects that should be treated as a single unit for the purpose of data changes.

#### Aggregate
An Aggregate is a pattern that encapsulates a group of related objects - entities and value objects - and treats them as a single unit for data modification. The root of the aggregate is the only member of the aggregate that outside objects are allowed to hold references to.

#### Event Store
An Event Store is a type of database designed specifically for storing event records in an event-sourcing system. Unlike traditional databases that store the current state of data, an event store retains a log of all changes (events) that have occurred over time. Each event represents a state change in the system. This allows you to reconstruct the state of an application by replaying these events.

- Immutable Log: Events are typically stored immutably, meaning once an event is stored, it cannot be changed or deleted.
- Sequential Order: Events are stored in the order they occurred, which is crucial for accurately reconstructing the state.
- Query Support: Many event stores also provide mechanisms to query events and aggregate data.