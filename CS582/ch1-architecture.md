# Architecture of a Distributed System

- [Architecture of a Distributed System](#architecture-of-a-distributed-system)
  - [Architectural Styles](#architectural-styles)
    - [Layered Architecture](#layered-architecture)
      - [Layered Communication Protocols](#layered-communication-protocols)

## Architectural Styles

- The organization of distributed systems is mostly about the software components that constitute the system. 
- These software architectures tell us how the various software components are supposed to be organized and how they should interact. 
- An important goal of distributed systems is to separate applications from underlying platforms by providing a so-called middleware layer. The main purpose of doing so is to provide distribution transparency which is not simple to achieve and there is an inherent trade-off. 
- The actual realization of a distributed system requires that we instantiate and place software components on real machines.
- The logical organization of a distributed system is also termed as its software architecture.
- An architectural style is formulated in terms of components, the way that components are connected to each other, the data exchanged between components, and finally how these elements are jointly configured into a system. 
- A component is a software unit that encapsulates certain functionality and whose interfaces conform to a prescribed protocol. These **well designed** interfaces allow components to be replaceable in times of an upgrade or a failure.
- Special measures may need to be taken when a part of the distributed system does need to be restarted to let the updates take effect. Such measures may include having replicated standbys
that take over while the partial restart is taking place.
- The most important architectural styles for a distributed system are as follows:
  - Layered Architecture
  - Service-oriented Architecture
  - Publish-subscribe Architecture

Now, let us look at each of these architectural styles in detail.

### Layered Architecture

- The basic idea of such an architecture is to organize the system into layers, where each layer provides a set of services to the layer above it.
- The components are organized in a way that the layer above uses the services of the layer below. In other words layer $L_{A}$ can make a **downcall** to layer $L_{B}$. In some cases, the layer $L_{B}$ may also be able to make an **upcall** to layer $L_{A}$.
- Since making an upcall is an exception, I'd like to provide an example. When an operating system signals the occurrence of an event, to which end it calls a user-defined operation for which an application had previously passed a reference (typically refered to as a **handle**).
  
#### Layered Communication Protocols

This section provides only a global picture of how the **communication-protocol stacks work** since a detailed discussion will be in the upcoming chapters. 