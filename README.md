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

We will use the mediator pattern to facilitate the command dispatching in our CQRS architecture.
- The mediator pattern is a behavioural design pattern.
- It promotes loose coupling by preventing objects from referring to each other explicitly.
- It is used to simplify communication between objects in an application by introducing a single object known as the mediator that manages the distribution of messages among other objects.
