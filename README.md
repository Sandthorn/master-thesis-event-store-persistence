# Evaluation of Riak as a persistence mechanimsm for events in an Event Sourcing System

## Background

An Event Store (ES) is a database for storing events in an [Event Sourcing System][5] (ESS). 
Instead of storing current state, a very common way to persist data, an ESS captures all changes to an application state as a sequence of events - not only delta of state, but when and why the state was changed. Event Sourcing is considered a part of [Domain Driven Design][7].

One of the advantages when using ESS is projections. 
A projection listens to events and constructs a read-only view of desired data, for example a database table only containing specific information for a particular view in the GUI. This separation of concerns is called Command Query Responsibility Segregation, [CQRS][6].
In ESS, the commands are creating events and queries reads from projections.

The ES persists all events in the domain, and is therefore an append-only database. 
Usually the ES is a relational database that has the advantage of transactions when writing events. 
Scaling a relational database is not trivial.

To improve scalability, fault tolerance and performance, our thesis is that using Riak would improve all of these points compared to using a relational database as an Event Store.

## Project goal

The overall goal is to evaluate the Open Source database [Riak][3] as a viable Event Store.

1. Getting a thorough understanding of how a Event Sourcing System works.
2. Understanding how the Open Source project [Sandthorn][1] implements ESS, including the [SQL Event Store][2].
3. Studying the NoSQL database [Riak][3] and understanding the differences to relational databases.
4. Creating a [Sandthorn][1] Event Store using [Riak][3] in the Ruby language.
5. Evaluate differences in performance, scalability and fault tolerance between the [SQL Event Store][2] and the created [Riak][3] Event Store.
6. The evaluation methods should be reusable when evaluating other persistance mechanimsm in the future.

## Requirements

Good knowledge of Ruby and relational databases are mandatory.

## Contact

Lars Krantz
[lars.krantz@upptec.se](mailto:lars.krantz@upptec.se)
Tel: +46709468080
UpptecOn AB
Stortorget 13A
216 20 Malmö

### UpptecOn AB

[Upptec][4] supplies a SaaS for valuations in the insurance industry. 
We are based in Malmö, Sweden and have seven employees.

[1]: https://github.com/Sandthorn/
[2]: https://github.com/Sandthorn/sandthorn_driver_sequel
[3]: https://github.com/basho/riak
[4]: http://upptec.se
[5]: http://martinfowler.com/eaaDev/EventSourcing.html
[6]: http://martinfowler.com/bliki/CQRS.html
[7]: http://en.wikipedia.org/wiki/Domain-driven_design

