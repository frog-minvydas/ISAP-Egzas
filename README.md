**<h1>Domain Driven Design</h1>**

### 1. What is DDD?
- An approach to software development enabling teams to more effectively manage the construction and maintenance of software for complex problem domains.

## 2. What is Big Ball of Mud?
- Is a haphazardly structured, sprawling, sloppy, duct-tape-and-baling-wire, spaghetti-code system that **lacks a perceivable architecture**.

## 3. What issues does DDD attempt to solve?
- **Cost-centric vs Profit-centric development**  
  ▸ Projects often prioritize minimizing costs rather than maximizing long-term value.

- **Technology-First mentality**  
  ▸ Solutions are driven by technology rather than a deep understanding of the domain and its needs.

- **Database-Centric thinking**  
  ▸ Overemphasis is placed on database design rather than modelling the domain properly.

- **Improper naming**  
  ▸ Poor naming of objects and operations leads to misunderstanding and miscommunication across the team.

- **Rushed delivery leads to poor quality**  
  ▸ Fast delivery often sacrifices design quality, which leads to fragile systems.

- **Business logic spread across UI and persistence layers**  
  ▸ Violating separation of concerns, making systems hard to change and understand.

- **Inefficient database operations**  
  ▸ Queries that are slow, poorly optimised, or lock unnecessarily.

- **Wrong abstractions**  
  ▸ Misrepresentation of business logic results in models that don’t reflect reality.

- **Tight coupling between services**  
  ▸ Strong dependencies between modules hinder scalability and flexibility.

## 4. What values does DDD provide?

- **Rich and precise domain models**  
  ▸ DDD leads to the development of models that clearly reflect real-world business processes and rules.

- **Improved understanding of the business**  
  ▸ By engaging domain experts in the modelling process, teams build software aligned with business goals.

- **Enhanced User Experience**  
  ▸ Well-designed models lead to better software usability and functionality, as they map closely to user needs.

- **Clear Architecture boundaries**  
  ▸ Bounded contexts isolate models and prevent the spread of conflicting concepts, increasing clarity and maintainability.

- **Better Enterprise Architecture**  
  ▸ The entire system becomes easier to organize and evolve through defined domains and subdomains.

- **Agile and Iterative modelling**  
  ▸ DDD supports continuous improvement through flexible design that evolves with changing business needs.

- **Strategic and tactical toolsets**  
  ▸ DDD introduces practical tools and patterns for long-term success, including aggregates, repositories, services, and context maps.

## 5. What are the main principles of DDD?

- **Exploration and Experimentation**  
  ▸ Modelling is a learning process. Teams should explore domain ideas through continuous experimentation.

- **Challenging assumptions**  
  ▸ Developers must critically evaluate domain knowledge, asking questions and refining.

- **Continuous modelling**  
  ▸ The models evolve over time, driven by insights gained during development and collaboration.

- **Problem solver first, technologist second**  
  ▸ The goal is to solve business problems, not just apply technical solutions for their own sake.

- **Do not try to solve all the problems at once**  
  ▸ Focus on the core domain and tackle complex areas incrementally.

- **Good is good enough**  
  ▸ Striving for perfect models can lead to overengineering. Aim for models that are accurate enough to be useful and maintainable.

## 6. What are the main concerns of strategic modelling in DDD?

- **Identifying Domains and Subdomains**
- **Defining Bounded Contexts**
- **Establishing Ubiquitous Language**
- **Context Mapping**
- **Mapping Context Relationships**
- **Avoiding The Big Ball of Mud**

## 7. What is the Context map?

- Is a global view that illustrates how different Bounded Contexts in a system relate and interact with each other.

## 8. What is the value of good domain boundaries?

- Good domain boundaries are essential for building well-structured, maintainable, and scalable systems.  
  They ensure that each part of the system is focused, cohesive, and evolves independently.

## 9. What are the context mapping patterns?

- **Shared Kernel**  
  ▸ Teams share a small, explicitly defined subset of the domain model  
  ▸ Requires close collaboration and coordination

- **Partnership**  
  ▸ Two teams with dependent goals collaborate closely  
  ▸ They share schedules, integration, and planning to succeed — to fail together  
  ▸ Regular synchronization and continuous integration are essential

- **Customer-Supplier**  
  ▸ One team provides functionality to another  
  ▸ Downstream needs influence upstream plans  
  ▸ Agreements are negotiated for prioritization and delivery

- **Conformist**  
  ▸ Downstream conforms to the upstream model without negotiation  
  ▸ Common when the upstream is off-the-shelf or uncooperative  
  ▸ Downstream gives up autonomy for simplicity

- **Anticorruption Layer (ACL)**  
  ▸ Downstream team creates a translation layer to protect its own model from upstream influence  
  ▸ Ensures isolation and maintains model integrity

- **Open Host Service (OHS)**  
  ▸ Upstream exposes a standard protocol for integration  
  ▸ Open to all consumers via a well-documented interface

- **Event Publisher**  
  ▸ Upstream context publishes its domain events via a messaging system  
  ▸ Downstream contexts can subscribe to the relevant events, adapting or transforming them to fit their models

- **Published Language**  
  ▸ A shared information exchange language between contexts  
  ▸ Can be used with OHS for easier translation

- **Separate Ways**  
  ▸ When two contexts have no valuable integration, they operate independently  
  ▸ Reduces unnecessary complexity and coupling

## 10. Tactical modelling concepts and patterns

- **Aggregate**  
  ▸ A cluster of associated objects that are treated as a unit for the purpose of data changes  
  ▸ Only the Aggregate Root is accessible from the outside  
  ▸ Ensures consistency rules within its boundary

- **Entity**  
  ▸ An object with a distinct identity that persists over time, regardless of its attribute changes

- **Value Object**  
  ▸ An object that describes some characteristics or attributes but carries no concept of identity

- **Whole Value**  
  ▸ An object that models a single, complete concept

- **Repository**  
  ▸ A mechanism for encapsulating storage, retrieval, and search behaviour which emulates a collection of objects

- **Service**  
  ▸ An operation offered as an interface that stands alone in the model, with no encapsulated state

- **Factory**  
  ▸ A mechanism for encapsulating complex creation logic and abstracting the types of a created object for the sake of a client

- **Domain Event**  
  ▸ Captures a significant occurrence in the domain  
  ▸ Enables event-driven communication inside and outside the domain

- **Invariants**  
  ▸ Rules that enforce consistency in the domain model

- **Event Sourcing**  
  ▸ State changes in the domain are not stored as current values, but rather as a sequence of events that represent all the changes leading to the current state

## 11. Domain model implementation patterns: domain model, transaction script, table module, active record, anemic domain model

- **Domain model**  
  ▸ A rich, object-oriented model where business logic and data are encapsulated together in Entities, Value Objects, and Aggregates.  
  ▸ Focuses on the domain not the database.  
  ▸ Follows model-driven design.  
  ▸ Suited for complex domains with evolving business rules.

- **Transaction Script**  
  ▸ A procedural approach where each use case is handled by a single script or method that coordinates all steps.  
  ▸ Business logic is placed directly inside methods.  
  ▸ Logic is grouped by transaction, not domain concept.  
  ▸ Suitable for simple or CRUD-heavy systems.  
  ▸ Quick to implement but hard to maintain at scale.

- **Table module**  
  ▸ A single object that represents a database table or view, combining persistence logic and business rules.  
  ▸ One object per table.  
  ▸ Often used in UI-heavy applications.  
  ▸ Good for simple domain or bounded contexts with low complexity.

- **Active Record**  
  ▸ An object that wraps a row in a database, containing both data access logic and some business logic.  
  ▸ Common in ORMs.  
  ▸ Couples domain logic with persistence.  
  ▸ Easy to use in basic apps, but hard to scale and test in complex domains.

- **Anemic domain model**  
  ▸ A domain model where objects contain no behavior, only data (getters/setters) and is an anti-pattern.  
  ▸ Violates object-oriented design.  
  ▸ Logic lives outside the domain in services or controllers.

## 12. Domain-Driven Design Pros and Cons

### Advantages
- Eases communication  
- Improves flexibility  
- Emphasizes domain over interface  
- Maintainability

### Disadvantages
- Requires robust domain experts  
- High cost  
- Time-consuming

**<h1>Introduction to Software Architecture</h1>**

## 1. What is Software Architecture and why is it important?

- The fundamental organization of a software system embodied in its components, their relationships to each other and to the environment, and the principles guiding its design and evolution.

- **Shapes system quality**  
  ▸ Directly influences attributes like performance, security, scalability, and maintainability.

- **Guides change management**  
  ▸ Helps adapt the system to new requirements or technologies over time.

- **Embeds critical design decisions**  
  ▸ Captures decisions that are hard to change once implemented.

- **Influences organizational structure**  
  ▸ System structure often reflects the communication structure of the organization.

- **Enables incremental development**  
  ▸ Supports modularity and phased delivery.

## 2. Common Software Architectural patterns and styles

### Architectural Pattern  
- A named collection of architectural design decisions that are applicable to a recurring design problem, parameterized to account for different software development contexts in which that problem appears.

### Architectural Style  
- A named collection of architectural design decisions.  

### A style is a blueprint of the overall system structure, while a pattern is a blueprint of a specific part of the system.

### Common architectural patterns

- **Big Ball of Mud**  
  ▸ Absence of any architecture structure.

- **Unitary Architecture**  
  ▸ Hardware and software as a single unit (mainframe, embedded).

- **Peer-to-peer**  
  ▸ Acting as both client and server.

- **Publish-Subscribe**  
  ▸ Announcing events to multiple interested consumers asynchronously.

- **Sense-Compute-Control**  
  ▸ Structuring embedded control applications.

- **Client/Server**  
  ▸ Application types: Desktop, Mobile, Web (MPA, SPA, PWA).  
  ▸ Structure Types: N-Layer, Clean, Vertical.  
  ▸ Interaction and Presentation: MVC, MVA, MVP, MVVM.

### Common architectural styles

#### **Monolith**

- **Layered architecture**  
  ▸ Divides systems into layers (UI, business, persistence, database).  
  ▸ Easy to start with, good separation of concerns.

- **Modular architecture**  
  ▸ Modularizes a monolith using Bounded Contexts or modules.  
  ▸ Easier to evolve into microservices.

- **Pipeline architecture**  
  ▸ Uses chained filters (components) and pipes (connectors).  
  ▸ Ideal for data transformation (ETL, analytics).

- **Microkernel architecture**  
  ▸ Core system + plug-ins.  
  ▸ Common in product platforms like IDEs.

#### **Distributed**

- **Service-based architecture**  
  ▸ Application composed of several coarse-grained services.  
  ▸ Easier to manage than microservices but still scalable.

- **Event-driven architecture**  
  ▸ System reacts to events asynchronously.  
  ▸ Highly scalable and reactive.

- **Space-based architecture**  
  ▸ Eliminates traditional database bottlenecks using in-memory data grids.  
  ▸ Designed for high-concurrency and scalable systems.

- **Service-oriented architecture (SOA)**  
  ▸ Distributed architectural style where business functionality is decomposed into modular, loosely coupled services that communicate over the network using standardized protocols.  
  ▸ Each service is independently deployable, reusable, and exposes well-defined interfaces.

- **Microservices architecture**  
  ▸ Highly decoupled services organized by domain.  
  ▸ Enables independent development and deployment.

## 3. Common types of Client/Server applications

### Desktop applications
- **Examples**: Windows (WPF, WinForms), macOS apps, JavaFX, Qt, Electron
- **Installed locally**
- **Full access to device hardware and OS**
- **Rich UI and performance**
- **Typically uses some MV* framework**

#### Pros
- Offline mode  
- Privacy/security  
- Better performance  
- Optimal use of computer resources

#### Cons
- Not portable  
- Hard drive space  
- Installation  
- Updates

---

### Mobile applications

#### Native (iOS, Android)
#### Hybrid (Flutter, React Native)

#### Pros
- Fast graphics  
- Better performance  
- Access to native APIs in phone’s OS  
- UI components and libraries

#### Cons
- Distribution via Stores  
- Longer development cycle  
- Rules and frameworks by native platforms  
- Phones/tablets defined separately, different layout

---

### Web applications

#### Multi-page application (MPA)
- Traditional web apps (Spring MVC, ASP.NET)
- Reloads the page on navigation

##### Pros
- SEO-friendly  
- More secure  
- Easier to scale  
- Can be built using single technology

##### Cons
- Slower due to page reloads  
- UI/Backend coupling  
- No offline  
- Expensive maintenance

---

#### Single-page application (SPA)
- Uses frameworks like React, Angular, Vue  
- Loads once and dynamically updates the UI  
- Fast user experience, but also SEO-friendly

##### Pros
- Fast response  
- Easy debugging  
- Linear content flow  
- Caching capabilities

##### Cons
- SEO readiness  
- Browser history  
- Security

##### Common rendering methods:
- **Client-side rendering**  
  ▸ In SPA, the server only generates the very first page that the user requests, leaving all subsequent pages to be rendered by the browser.

- **Server-side rendering**  
  ▸ Dynamic generation of the HTML page that is sent from web server to browser.

- **Static-site generation**  
  ▸ SPA is generated on build and hosted via static web sites/blob storages.

---

#### Progressive web application (PWA)
- Web apps with native-like features  
- Works offline, supports push notifications  
- Installed via browser

##### Pros
- Connectivity/notifications  
- Self-updates  
- Safety  
- Easy installation  
- Dev savings

##### Cons
- Search traffic  
- Cannot support native-app typical features

## 4. Difference between Multi-page and Single-page Web Applications

- MPA does full page reload on each action, whereas SPA loads once and updates dynamically.
- SEO is strong on MPA (server-side rendered HTML), while SPA is weaker unless using server-side rendering (SSR).
- MPA has slower user experience compared to fast and seamless interactions in SPA.
- MPA is simpler to build and manage compared to SPA routing and state management.
- MPA is used in content-heavy sites (blogs, news), whereas SPA is used in app-like interfaces (dashboards, tools).

## 5. Common structural patterns of Software Architecture

### N-Tier Architecture
- Divides an application into multiple layers or tiers. Each tier is responsible for specific functionality and communicates with others through well-defined interfaces.
- Commonly used in large-scale enterprise applications.

#### Typical layers
- **Presentation layer (UI)**:  
  ▸ Responsible for presenting information and receiving user input. Includes web pages, desktop apps, or mobile apps.

- **Services layer**:  
  ▸ Includes services interfaces and message types to interact with PL or external systems.

- **Application/Business layer**:  
  ▸ Contains business logic and handles data processing, workflow, validation, and transformation.

- **Data layer**:  
  ▸ Handles accessing, persisting, and transforming data.

- Other tiers may include integration, security, authentication, or authorization.

#### Pros
- **Scalability**:  
  ▸ Each tier can be scaled independently for high traffic/data.

- **Maintainability**:  
  ▸ Clear separation of concerns enables easier updates and changes.

- **Reusability**:  
  ▸ Modular code can be reused across multiple apps.

- **Security**:  
  ▸ Separating presentation and data tiers can improve security.

#### Cons
- **Complexity**:  
  ▸ Can be difficult to design and implement.

- **Performance**:  
  ▸ Communication between tiers can cause overhead.

- **Cost**:  
  ▸ Development and maintenance may be expensive for small apps.

---

### The Clean Architecture

#### Based on:
- Hexagonal Architecture  
- Cockburn  
- Domain-Context-Interaction  
- Boundary-Control Entity

#### Motivation
- Create systems that are:
  - **Independent of frameworks**  
  - **Testable**  
  - **Independent of the UI**  
  - **Independent of the database**  
  - **Independent of any external agency**

#### Pros
- **Maintainability**  
- **Testability**  
- **Flexibility**:  
  ▸ Easily swap frameworks, UI, or DBs.

- **Scalability**:  
  ▸ Layered structure supports growth.

#### Cons
- **Complexity**:  
  ▸ Can be harder to design and implement.

- **Learning curve**:  
  ▸ Requires understanding new architectural ideas.

- **Time and cost**:  
  ▸ More resource-intensive than simpler architectures.

---

### Vertical Slice Architecture
- Built around distinct requests (features or use cases).
- Encapsulates everything from front-end to back-end needed for a feature.
- Goal is to **minimize coupling between slices**, and **maximize cohesion within** a slice.

## 6. Data management design patterns: CRUD and CQRS — Principles, purposes, differences

### CRUD (Create, Read, Update, Delete)
- A simple and commonly used design pattern in managing data in databases.

#### Pros
- **Simple**: Easy-to-understand design pattern.
- **Widely used**: Supported by most databases and ORM frameworks.
- **Fast development**: Can be quickly implemented, reducing time and cost.

#### Cons
- **Limited scalability**: Not suitable for high concurrency applications.
- **Limited flexibility**: May not fit complex data models or custom business logic.

---

### CQRS (Command Query Responsibility Segregation)
- A design pattern that separates read and write operations into separate models or services.

#### Pros
- **High scalability**: Designed for high concurrency and load.
- **Flexibility**: Supports complex models and custom business logic.
- **Improved performance**: Allows specialized databases for read/write operations.

#### Cons
- **Complexity**: Requires more design and implementation effort.
- **Higher cost**: Needs more infrastructure and resources.
- **Learning curve**: Involves new concepts and approaches.

---

### CRUD vs CQRS

- **Data management**:  
  ▸ CRUD provides a unified model, CQRS splits read/write logic.

- **Data storage**:  
  ▸ CRUD typically uses one database, CQRS may use separate ones.

- **Scalability**:  
  ▸ CQRS is optimized for high-scale scenarios, CRUD is not.

- **Complexity**:  
  ▸ CQRS is more complex and resource-intensive than CRUD.

## 7. Software Architecture definition principles and techniques

- Architecture is the fundamental organization of a software system embodied in its components, their relationships to each other and to the environment, and the principles guiding its design and evolution.

**<h1>Software Architecture Styles</h1>**

## 1. Laws and characteristics of Software Architecture

- **Everything in software architecture is a trade-off**  
  ▸ Every architectural decision involves compromises.

- **Why is more important than how**  
  ▸ Understanding why a decision is made is more important than knowing how it's implemented.

### Characteristics

#### Operational Architecture Characteristics
- **Performance** – system responsiveness under specific workloads
- **Robustness** – ability to handle errors and edge cases
- **Availability** – system uptime and readiness
- **Continuity** – disaster recovery capabilities
- **Reliability/Safety** – tolerance for failure, especially in mission-critical systems
- **Recoverability** – speed of system restoration after failure
- **Scalability** – how performance holds under increased load

#### Structural Architecture Characteristics
- **Extensibility** – ease of adding new features
- **Installability** – ease of system installation on all necessary platforms
- **Localization** – support for various languages, currencies, and formats
- **Maintainability** – ease of fixing or improving the system
- **Supportability** – ease of debugging and providing technical support
- **Upgradeability** – ability to update components easily
- **Configurability** – customization by end users
- **Reuse** – ability to leverage common components across multiple products
- **Portability** – ability to run on multiple platforms

#### Cross-cutting Architecture Characteristics
- **Accessibility** – support for users with special needs
- **Usability** – ease of use and user experience
- **Archivability** – requirements for storing or deleting old data
- **Authentication** – identity verification of users
- **Authorization** – access control to features and data
- **Legal** – compliance with laws like GDPR
- **Privacy** – data protection from internal misuse
- **Security** – protection against data breaches or malicious use

#### Domain Concerns and Architecture Characteristics
- **Mergers and acquisitions** – interoperability, scalability, adaptability, extensibility
- **Time to market** – agility, testability, deployability
- **User satisfaction** – performance, availability, fault tolerance, testability, deployability, agility, security
- **Competitive advantage** – agility, testability, deployability, scalability, availability, fault-tolerance
- **Time and budget** – simplicity, feasibility

## 2. Common fallacies about distributed Software Architecture

- **The network is reliable**  
  ▸ Systems relying heavily on the network must account for outages and use mechanisms like circuit breakers or retries.

- **Latency is zero**  
  ▸ Even small latencies add up. Avoid long chains of synchronous service calls. Use asynchronous or batch processing where possible.

- **Bandwidth is infinite**  
  ▸ Network bandwidth is limited and can become a bottleneck. Minimize data exchange between services.

- **The Network is Secure**  
  ▸ Inter-service communication can be intercepted or attacked. Secure every endpoint, use encryption, and apply security measures even internally.

- **The Network Topology Doesn’t Change**  
  ▸ Network infrastructure changes (e.g., firewalls, routing rules, subnets). Architects must design for dynamic environments.

- **There is only one network administrator**  
  ▸ In large organizations, multiple admins manage different network parts. Miscommunication can occur without clear coordination.

- **Transport cost is zero**  
  ▸ Distributed systems increase costs (hardware, proxies, gateways, maintenance). Factor in these costs during architectural decisions.

- **The network is homogeneous**  
  ▸ Networks often consist of heterogeneous systems and technologies. Incompatibilities can cause intermittent issues like packet loss or protocol mismatches.

## 3. Principles of Monolith Software Architecture style

- A monolith is a software application where all components are packaged and deployed as a single unit.  
  There are various styles within monolithic architecture, each with its own principles.

### Principles
- **Single deployment unit**  
  ▸ All modules, features, and components are deployed together.

- **Tight integration**  
  ▸ Internal components often share memory and code.

- **Simple deployment and operations**  
  ▸ Easy to build and deploy, especially for small teams or early-stage projects.

- **Low latency communication**  
  ▸ Internal function calls are faster than network calls, offering better performance.

## 4. Principles of Pipeline Architecture style

- The Pipeline Architecture Style organizes processing as a sequence of discrete, independent processing units (filters) connected by unidirectional data channels (pipes).

### Principles
- **Separation of concerns via filters**  
  ▸ Each filter performs a single, well-defined task. Filters are self-contained, typically stateless, and independent of one another.

- **Unidirectional communication via pipes**  
  ▸ Data flows in one direction through pipes between filters.

- **High composability**  
  ▸ Filters can be composed and chained in various ways to create flexible workflows.

- **Loose coupling**  
  ▸ Filters do not know about the logic of upstream or downstream filters. Communication is based solely on data passed through pipes.

- **Efficient performance**  
  ▸ Designed for high performance.

## 5. Principles of Microkernel Architecture style

- Centered around a minimal core system that provides essential services, with plug-in components extending functionality in a modular and isolated way.

### Principles
- **Minimal core functionality (the Kernel)**  
  ▸ The core system contains only the essential capabilities required to run the system.

- **Plug-in extensions for business logic**  
  ▸ Most of the application logic resides in plug-in modules. Plug-ins interact with the core via well-defined contracts or interfaces. New features can be added by simply adding or replacing plugins.

- **Separation of core and custom logic**  
- **Loose coupling and high cohesion**  
- **Extensibility and maintainability**

## 6. Principles of Service-Based Architecture style

- A pragmatic and simplified distributed architecture that combines benefits of microservices with a coarse-grained domain service approach.  
  Designed to balance maintainability and independent deployment while avoiding full microservices complexity.

### Principles
- **Coarse-grained services**  
  ▸ Services are larger and more domain-focused than microservices.

- **Independent deployment**  
  ▸ Each service can be deployed and scaled independently, though they may share a database. Improves reliability and fault isolation.

- **Single database**  
  ▸ Unlike microservices, services often share a database (logically partitioned). Simplifies access and avoids duplication, but needs careful management.

- **Defined interfaces and communication**  
  ▸ Services interact via well-defined interfaces.

- **Domain-Driven design alignment**

## 7. Principles of Event-Driven Architecture style

- A highly decoupled, asynchronous software design style where components communicate by emitting and responding to events rather than making direct calls.

### Principles
- **Asynchronous communication**
- **Decoupled components**
- **High-performance**
- **Highly scalable**
- **Highly adaptable**

## 8. Differences between Broker and Mediator topologies in Event-Driven Architecture

- **Broker** is a simple, decentralized topology compared to **Mediator’s** centralized and coordinated approach.
- Broker topology has no central control, while the Mediator controls the entire event workflow.
- Broker is a looser coupler; events are more tightly coupled to the mediator.
- Broker performance is higher compared to the Mediator.
- Broker is a lightweight, parallel event-processing style, while the Mediator is for complex workflows with coordination and dependencies.

## 9. When is hybrid event-driven architecture typically considered?

A hybrid event-driven architecture is typically considered when:

- There is a need to remove bottlenecks
- There is a need for fault-tolerance and backpressure handling
- There is a need to improve system scalability and responsiveness
- There is a need for real-time processing

## 10. What are the main principles of space-based architecture style?

- Designed for systems with high scalability, elasticity, and concurrent user loads.  
  Achieves this by eliminating traditional bottlenecks like centralized databases.

### Principles
- **In-memory data grids**  
  ▸ Uses in-memory data grids instead of a central database.

- **Processing units**  
  ▸ Self-contained modules with application logic, in-memory data, replication engine.  
  ▸ Deployed and scaled dynamically.

- **Asynchronous persistence**  
  ▸ Updates to the database are done asynchronously using data pumps and writers.  
  ▸ Promotes eventual consistency.

## 11. What are the main principles of microservices architecture style?

- A distributed design style where the system is composed of many small, independent, and deployable services.  
  Each service is focused on a specific business capability.

### Principles
- **Single responsibility / bounded contexts**  
  ▸ Each service models a specific domain or business function.  
  ▸ Services are functionally cohesive and operate within a bounded context.

- **Independent deployment**  
  ▸ Services are developed, deployed, and scaled independently.

- **Decentralized data management**  
  ▸ Each service has its own database (no shared schema).  
  ▸ Enables data isolation and technology independence.

- **Polyglot architecture**  
  ▸ Services can be built using different languages or tools based on needs.

- **Choreography over orchestration**  
  ▸ Services coordinate through events, not centralized orchestration, to reduce coupling.

- **High scalability and fault tolerance**  
  ▸ Services can be independently scaled.  
  ▸ Failures are isolated to prevent system-wide impact.

## 12. What should be considered when selecting an architectural style?

- Choosing an architecture style involves analyzing trade-offs across:
  - Architecture characteristics
  - Domain considerations
  - Strategic goals
  - System constraints

### Key Factors
- **Domain considerations** – How complex is the domain?
- **Data architecture** – Centralized or decentralized?
- **Communication style** – Use async where necessary; avoid unnecessary sync.
- **Organizational structure** – Size and experience of the development team.
- **Ecosystem and technology constraints**
- **Evolution and change** – Anticipated system growth

- Select architecture based on a holistic understanding of goals, constraints, and future needs — not a one-size-fits-all approach.

**<h1>Software Modifiability</h1>**

## 1. How modifiability can be measured?

- **Coupling** – How strongly modules are related based on the number and nature of their relationship.  
  ▸ Goal: Achieve loose coupling.

- **Cohesion** – How strongly the responsibilities of a module are related.  
  ▸ Goal: High cohesion.

- **Connascence (co-existence)** – Degree to which a change in one module requires a change in another to maintain correctness.  
  ▸ Goal: Reduce connascence to reduce cost of change.

## 2. What is coupling, cohesion, and connascence?

- **Coupling** – Degree of interdependence between software modules.

- **Cohesion** – Degree to which elements inside a module belong together.

- **Connascence** – Degree to which one component must change if another changes to maintain correctness.  
  ▸ Reflects hidden dependencies and cost of change propagation.

## 3. General software design principles

- **Abstraction** – Simplify complexity by focusing on essential characteristics.
- **Information hiding** – Hide internal details to reduce interdependency.
- **Encapsulation** – Bundle data and methods together.
- **Sufficiency** – Component includes necessary features for abstraction.
- **Completeness** – Component includes all essential aspects.
- **Primitiveness** – Use simple, easy-to-understand building blocks.
- **Separation of concern** – Different parts should address different concerns.

## 4. What concerns are typically considered in software design?

- **Functional concerns** – What the system should do.
- **Structural concerns** – How the system is organized and structured.

## 5. What is separation of concerns?

- **Separation of concerns** – Divide a system into parts, each addressing a distinct function or responsibility.

## 6. What are the main principles of YAGNI?

- **Build only what is needed** – Avoid speculative design.
- **Simplify code and reduce bloat** – Easier maintenance.
- **Deliver value faster** – Focus on current needs.
- **Embrace change via refactoring** – Evolve design with actual requirements.

## 7. What are the main cohesion principles?

- **Reuse/release equivalence principle** – Reusable modules should be packaged and released together.
- **Common closure principle** – A module should encapsulate related changes.
- **Common reuse principle** – Group functions/classes that are reused together.

## 8. What are the main coupling principles?

- **Acyclic dependencies principle** – No circular dependencies.
- **Stable dependency principle** – Depend only on stable components.
- **Stable abstraction principle** – Stable components should be abstract and extensible.

## 9. What are the SOLID principles?

- A set of design guidelines on object-oriented programming that helps create more modular, maintainable, and scalable software.

### Principles

- **Single Responsibility Principle**  
  ▸ A class/module should do only one thing and encapsulate only one area of responsibility.

- **Open/Closed Principle**  
  ▸ You should be able to extend behaviour without modifying existing code.

- **Liskov Substitution Principle**  
  ▸ Objects of a subclass should behave the same way as objects of their superclass.

- **Interface Segregation Principle**  
  ▸ Break large interfaces into smaller, more specific ones.  
  ▸ Prevents classes from being forced to implement irrelevant functionality.

- **Dependency Inversion Principle**  
  ▸ Abstractions should not depend on details.  
  ▸ Promotes loose coupling and supports testability.

**<h1>Deployability</h1>**

## 1. What is the cloud computing model?

Cloud computing is a model that provides on-demand access to computing resources (like servers, storage, and applications) over the internet. It is defined by five essential characteristics:

- **On-demand self-service** – Users can provision resources automatically without human interaction.
- **Broad network access** – Accessible from a wide range of devices via standard networks.
- **Resource pooling** – Uses a multi-tenant model to dynamically allocate resources.
- **Rapid elasticity** – Can scale resources up or down quickly as needed.
- **Measured service** – Resource usage is monitored and billed accordingly.

## 2. What perspective does cloud computing model cover?

The cloud computing model covers the consumer-provider perspective, detailing how computing resources are provisioned, managed, and consumed. It defines:

- **Service models** – What kind of services are provided and who manages what (IaaS, PaaS, SaaS, FaaS).
- **Deployment models** – Where and how the infrastructure is deployed and who controls it (Public, Private, Hybrid, Community).
- **Essential characteristics** – Operational behavior and expectations from both sides, like scalability and cost transparency.

## 3. What are the possible cloud deployment technology options?  
### What are the common types of `<Resource>`-as-a-Service?  
### What are the differences between them?

- **IaaS**
  - **Bare metal** – Dedicated physical servers without virtualization.
  - **VMs (Virtual Machines)** – Isolated environments using hypervisors.
  - **Unikernels** – Specialized minimal OS images optimized for performance and security.
  - **Containers** – Lightweight, portable environments sharing the host OS kernel.

- **CaaS**
  - Container deployment with options like:
    - Build your own container services
    - Off-the-shelf platforms
    - Managed services (e.g., Kubernetes)

- **PaaS**
  - Provides middleware, language runtimes, and tools in pre-packaged environments for developers.

- **FaaS / Serverless**
  - Runs stateless code triggered by events without server management.

- **SaaS**
  - Fully managed applications accessible via the internet.

## 4. What is the difference between virtualization vs containerization?

### Virtualization
- Uses a hypervisor to create and run multiple VMs on a single physical server.
- Each VM includes a full OS, its own kernel, and virtualized hardware.
- Offers strong isolation but has higher overhead due to full OS instances.

### Containerization
- Uses a shared OS kernel to run multiple containers in isolated user spaces.
- Containers package only the app and its dependencies, not a full OS.
- Offers lightweight, fast, and portable deployments with lower overhead than VMs.

> **Use virtualization** when you need full OS isolation or run legacy systems.  
> **Use containerization** for scalable, modular, modern deployments.

## 5. What are the common cloud deployment models?

- **Private cloud**  
  ▸ Exclusive to a single organization  
  ▸ Managed by the organization or a third party  
  ▸ On-premises or off-premises  
  ▸ High security, control, and regulatory compliance

- **Community cloud**  
  ▸ Shared by organizations with common goals or requirements  
  ▸ Managed by one or more organizations or a third party  
  ▸ On-premises or off-premises  
  ▸ Suited for collaborative projects or shared concerns

- **Public cloud**  
  ▸ Open to the public  
  ▸ Managed and hosted by cloud providers  
  ▸ Providers use their data centers  
  ▸ Scalability, cost-efficiency, low entry barriers

- **Hybrid cloud**  
  ▸ Combination of two or more cloud types  
  ▸ Integrated for workload portability  
  ▸ Balances control with scalability, supports cloud bursting or disaster recovery

- **Multi-cloud**  
  ▸ Use of multiple cloud providers  
  ▸ May or may not be integrated  
  ▸ Vendor independence, best-of-breed services, increased availability

## 6. What are the common deployability tactics?

### Manage Deployment Pipeline
- **Scale rollouts** – Gradually deploy to subsets of users, monitor, and rollback if needed  
- **Rollback** – Revert to a previous version automatically on failure  
- **Script deployment commands** – Automate complex deployments using version-controlled scripts

### Manage Deployed System
- **Service interactions** – Handle compatibility across different versions during rollout  
- **Package dependencies** – Bundle apps with required dependencies  
- **Feature toggle** – Enable/disable features at runtime without redeployment

**<h1>Integrability</h1>**

## 1. What is the common module/service integration styles?

- **File transfer** – Modules exchange files with shared data.  
  ▸ Can be manual, automatic, or hybrid. It is slow.

- **Shared database** – Modules use the same database.  
  ▸ Offers consistent data but leads to very high coupling.

- **Invocation (local method call)** – Modules expose functionality via direct calls.  
  ▸ Requires encapsulation and may need anti-corruption layers.  
  ▸ Synchronous and tightly coupled.

- **Messaging** – Modules exchange events via a message broker.  
  ▸ Promotes loose coupling and eventual consistency, but adds complexity.

- **Integration events** – Used to inform other modules/bounded contexts that an event has occurred.  
  ▸ Consumers process events independently.

## 2. What is API?

An API (Application Programming Interface) is a set of rules and mechanisms that allows applications to exchange data and functionality remotely, simplifying development and enhancement.

### Properties
- **Consumer-centric** – Designed from the perspective of the consumer.
- **Atomic** – Each API call does one thing on one object.
- **Support service evolution** – APIs can evolve without breaking clients.
- **Platform independent** – Any client can call the API regardless of implementation.
- **Simple and intuitive** – Easy to understand and predict.
- **Well-documented** – Clear documentation.
- **Forgiving** – Returns understandable error messages.
- **Secure and compliant** – Proper access control, no data leakage.
- **Performant, scalable, available** – Ensures fast, reliable responses.
- **Reusable and backward-compatible** – Supports multiple clients and versions.

## 3. What different styles of API do you know?

- **REST (Representational State Transfer)**  
  ▸ Resource-based, uses standard HTTP verbs (GET, POST, PUT, DELETE)  
  ▸ Stateless, uses caching, uniform interface

- **SOAP (Simple Object Access Protocol)**  
  ▸ XML-based protocol with strict structure (envelope, rules, conventions)  
  ▸ Extensible, platform-independent, protocol-neutral  
  ▸ Heavier and more complex than REST

- **RPC (Remote Procedure Call)**  
  ▸ Executes functions remotely like local functions  
  ▸ Includes XML-RPC, JSON-RPC, gRPC  
  ▸ gRPC uses protocol buffers, supports streaming & advanced features

- **OData (Open Data Protocol)**  
  ▸ REST-based, standard for querying and updating data via URLs  
  ▸ Supports filtering, sorting, pagination, projection, batch operations

- **GraphQL**  
  ▸ Query language for APIs  
  ▸ Clients request only the exact data needed (efficient)  
  ▸ Supports query, mutation, and subscription operations

## 4. What is REST API?

A REST API is an architectural style for building distributed systems where resources (data or services) are accessed and manipulated using standard HTTP methods.

## 5. What properties does REST API possess?

- **Resource-oriented** – Everything is treated as a resource.
- **Stateless** – Each request contains all information needed; no server-side session state.
- **Uniform interface** – Standard methods like GET, POST, PUT, PATCH, DELETE.
- **Client-server separation** – Frontend and backend are clearly separated.
- **Cacheable** – Responses must define cache-ability to improve performance.

## 6. What are the REST API maturity levels?

### Level 0
- Single endpoint.
- All operations use a single method like POST.
- Essentially a remote procedure call over HTTP.

### Level 1
- API is broken into multiple URIs, each representing a resource.
- Still uses a single HTTP method for all actions.

### Level 2
- Uses standard HTTP methods (GET, POST, etc.).
- Enables semantic clarity and aligns with HTTP conventions.

### Level 3 – HATEOAS (Hypermedia As The Engine Of Application State)
- Responses include hyperlinks to guide clients on next available actions.
- Promotes discoverability and loose coupling.

## 7. How to ensure asynchronicity in REST API design?

### Long-Running Operations

- **Use Resource-based LRO (RELO)**  
  ▸ `POST` a command to initiate an operation  
  ▸ `GET` the status from a resource URI

- **Use Stepwise LRO (SLRO)**  
  ▸ Initial response returns an operation-location URL  
  ▸ Client polls the operation endpoint (optionally using Retry-After header)

### Webhooks (Push Notifications)

- Client registers a callback URL with the server  
- Server pushes updates to that URL when an event occurs  
- Avoids polling; ideal for lightweight, real-time updates

#### Two subscription types:
- **Firehose subscription** – A subscription is manually created in an app registration portal.
- **Per-resource subscriptions** – Subscribing app creates subscriptions at runtime for specific entities.

### Fire-and-forget operations

- The API acknowledges receipt and processes the request in the background  
- No immediate result is returned to the client

## 8. What is message-based communication?

Message-based communication is an integration style where systems exchange asynchronous messages via a **message broker**, instead of making direct requests.

### Key components:
- **Producer** – Sends messages  
- **Consumer** – Receives and processes messages  
- **Broker** – Intermediates  
- **Channel** – Pathway through which messages travel

### Message types:
- **Event** – Something that already happened  
- **Command** – Instructs a specific action  
- **Query** – Asks for information

## 9. What is the purpose of different messaging patterns?

Different messaging patterns are used to solve common challenges in message-based communication.

- **Invalid Message Channel** – Diverts unreadable or bad messages to a separate channel. Ensures the main flow is not disrupted by faulty data.
- **Datatype Channel** – Routes each data type to a specific channel. Consumers know exactly what data to expect.
- **Dead Letter Channel** – Stores undeliverable messages that couldn’t be processed. Helps with debugging and retry mechanisms.
- **Channel Adapter** – Connects applications to the messaging system. Allows apps to send/receive messages without changing core logic.
- **Messaging Bridge** – Connects different messaging systems. Ensures messages flow across systems/platforms.
- **Pseudosynchronicity** – Simulates synchronous request-reply in an async system. Useful for operations needing confirmation or response.
- **Request-reply via Correlation** – Simulates synchronous behavior using correlation IDs. Enables matching responses to requests.
- **Request-reply via Temporary Queue** – Uses a unique temporary queue per client. Prevents interference between different replies.
- **Competing Consumers and Messaging Ordering** – Multiple consumers read from the same queue. Increases parallelism and throughput. Ensures message ordering while scaling consumers using partitioning.
- **Handling Duplicate Messages** – Prevents re-processing the same message. Achieved via idempotent logic or tracking message IDs.
- **Guaranteed Delivery** – Ensures message persistence and eventual delivery. Stores messages on disk until successfully acknowledged by the consumer.

## 10. How sync/async APIs can be documented?

### Synchronous APIs
- Use **OpenAPI Specification (OAS)**.
- Described using **YAML/JSON**.
- Tools: **Swagger UI**, **ReDoc**.

### Asynchronous APIs
- Use **AsyncAPI Specification**.
- Designed for event-driven and message-based systems.
- Works with **Kafka**, **MQTT**, **WebSockets**.

**<h1>Usability</h1>**


<h4><strong>Common Types of UI</strong></h4>

⌨️ Command Line Interface (CLI) \
🖼️ Graphical User Interface (GUI) \
📜 Menu-Driven UI \
📝 Forms-Based UI \
📊 Analytical UI \
💬 Chat-Based UI \
🗣️ Natural Language Interface


<h4><strong>UI/UX Design Concepts and Key Principles</strong></h4>

🎨 Balancing multiple factors for effective interface design. \
⚖️ Compromise Between:
<ul>
  <li>Interaction & Presentation Styles— Choose the most appropriate style (e.g., GUI, CLI, chat-based) based on the system's needs.\</li>
  <li>User Background & Experience— Tailor the interface to the skills and familiarity of the users.</li>
  <li>Available Devices— Design for different platforms (e.g., desktop, mobile, touchscreens, voice assistants).</li>
</ul>


<h4><strong>What Are the Usability Heuristics? Provide Some Examples.</strong></h4>

![image](https://github.com/user-attachments/assets/a9678e23-f585-45b4-8fa1-74bf403db0ea)

Visibility of system status \
💡 Design should always keep users informed about what is going on, through appropriate feedback within a reasonable amount of time. \
🗣️ Communicate ClearlyEnsure the system communicates its state — never act on users' behalf without informing them. \
⚡ Respond QuicklyDeliver feedback as soon as possible — ideally, immediately after the user acts. \
🤝 Build TrustFoster user confidence through open and continuous communication. \

Match between system and the real world \
📌 Use terms and concepts familiar to users and follow real-world conventions to present information in a natural and logical order. \
🔍 Speak the User’s LanguageAvoid jargon — users shouldn't need a dictionary to understand your interface. \
⚠️ Don’t Assume UnderstandingYour interpretation of words or ideas may differ from your users’. \
📊 Research to AlignUse user research to uncover your audience’s terminology and mental models. \

User control and freedom \
🧭 Users should feel in control — provide a clear "emergency exit" to undo mistakes or back out of unintended actions easily. \
↩️ Support Undo/RedoLet users reverse actions without penalty. \
❌ Provide Clear ExitsInclude clearly labeled options like "Cancel" to escape ongoing processes. \
👀 Make It DiscoverableEmergency exits should be clearly labeled and discoverable. \

Consistency and standards \
📖 Users shouldn't have to guess whether actions or terms mean the same thing — follow platform and industry conventions. \
📚 Support LearnabilityUse both internal (within your product) and external (across platforms) consistency. \
🧱 Keep It ConsistentStick to familiar layouts, terminology, and behaviors across screens and features. \
🌐 Respect Jakob’s LawUsers rely on experiences from other products — align with what they already know. \


Error prevention \
🚫 The best error message is one that never needs to appear — prevent problems before they happen. \
⚠️ Prioritize PreventionFocus first on high-cost errors, then address smaller frustrations. \
🧭 Avoid SlipsUse smart defaults, input constraints, and clear layouts to guide users. \
🧠 Prevent MistakesReduce memory load, support undo, and warn users before irreversible actions. \

Recognition rather than recall \
👁️ Minimize memory load — make actions, elements, and options visible so users don’t have to remember them. \
🔍 Support RecognitionPresent relevant information where and when it's needed — don’t rely on memory. \
📎 Contextual HelpOffer help and guidance in the moment, not through long tutorials. \
📉 Reduce Cognitive LoadStreamline the interface to show only what’s necessary at each step. \

Flexibility and efficiency of use \
🧩 Design for both novices and experts — support shortcuts and customization to streamline frequent actions. \
⌨️ Use AcceleratorsEnable keyboard shortcuts, touch gestures, and other time-saving tools for experienced users. \
🎯 Personalize ExperiencesTailor content and functionality to suit individual preferences and usage patterns. \
🛠️ Allow CustomizationLet users configure the interface or workflow to match their habits and needs. \

Aesthetic and minimalist design \
🎯 Interfaces should show only what’s necessary — every extra element competes with the important ones. \
🔬 Focus on EssentialsDesign content and visuals to highlight what truly matters. \
🚫 Avoid DistractionsRemove unnecessary elements that clutter the interface or mislead users. \
🏁 Support Primary GoalsPrioritize features and information that align with users’ main tasks. \

Help users recognize, diagnose, and recover from errors \
💬 Error messages should be clear, informative, and helpful — not cryptic or confusing. \
🔴 Make It NoticeableUse familiar visuals like bold red text or icons to grab attention. \
🗣️ Speak PlainlyAvoid technical jargon — describe the issue in user-friendly language. \
🛠️ Offer SolutionsSuggest actions users can take right away to fix the problem. \

Help and documentation \
🧭 Even the best designs may need support — help should be easy to find, understand, and apply. \
🔎 Make Help SearchableUsers should quickly find the guidance they need without digging. \
📍 Provide Contextual HelpShow relevant instructions right when and where users need them. \
📝 Use Clear, Actionable StepsList steps in plain language — no vague or overly technical instructions. \



<h4><strong>What Is the Purpose of UX/UI Design?</strong></h4>

🎯 Design should ensure effective operation and control of the system and deliver the best  experience for the user.  \
🧠 UX Design — The WHY \
Focuses on strategy, structure, and purpose \
Plans how the product will solve real user problems \
Guided by research, user needs, and business goals \
🎨 UI Design — The HOW \
Focuses on visuals, interactivity, and accessibility \
Brings UX plans to life through layout, colors, and components \
Ensures consistency, clarity, and responsiveness in the interface \


<h4><strong>What Is Information Architecture? What Value It Provides?</strong></h4>
📦 IA defines the full structure of a product, helping users find what they need with clarity and ease.  \
🎯 Main Goal  \
Organize and classify content so users can navigate efficiently and understand the structure.  \

📐 Common IA Patterns:  \
🔽 Hierarchical — From most to least important  \
➡️ Sequential — Step-by-step, ordered flow  \
🔲 Matrix — User decides how to navigate  \
🔤 Alphabetical — A to Z arrangement  \
🔗 By Relation — Based on roles and relationships  \

<h4><strong>What Are the Main Principles of MVC Pattern?</strong></h4>
<p><strong>Model:</strong><br>
represents the state of the application and any business logic or operations that should be performed by it. Business logic should be encapsulated in the model, along with any implementation logic for persisting the state of the application.</p>

<p><strong>Views:</strong><br>
are responsible for presenting content through the user interface. They use a particular view engine to embed application code in HTML markup. There should be minimal logic within views, and any logic in them should relate to presenting content.</p>

<p><strong>Controllers:</strong><br>
are the components that handle user interaction, work with the model, and ultimately select a view to render. In an MVC application, the view only displays information; the controller handles and responds to user input and interaction.</p>


<h4><strong>What Common Design Patterns Are Used in UX/UI Design?</strong></h4> <p><strong>Command</strong> 
is a behavioral design pattern that turns a request into a stand-alone object that contains all information about the request. This transformation lets you pass requests as a method arguments, delay or queue a request’s execution, and support undoable operations.</p> <p><strong>Mediator</strong> is a behavioral design pattern that lets you reduce chaotic dependencies between objects. The pattern restricts direct communications between the objects and forces them to collaborate only via a mediator object.</p> <p><strong>The memento pattern</strong> is a common way to implement the undo tactic. This pattern features three major components: the originator, the caretaker, and the memento. The originator is processing some stream of events that change its state (originating from user interaction). The caretaker is sending events to the originator that cause it to change its state. When the caretaker is about to change the state of the originator, it can request a memento—a snapshot of the existing state—and can use this artifact to restore that existing state if needed, by simply passing the memento back to the originator. In this way, the caretaker knows nothing about how state is managed; the memento is simply an abstraction that the caretaker employs.</p> <p><strong>Observer</strong> is a behavioral design pattern that lets you define a subscription mechanism to notify multiple objects about any events that happen to the object they’re observing. The pattern is a way to link some functionality with one or more views. This pattern has a subject—the entity being observed—and one or more observers of that subject. Observers registers with the Subject; When the State of the Subject changes, the Observers are notified. Pattern is often used to implement MVC (and its variants).</p> <p><strong>Chain of Responsibility</strong> is a behavioral design pattern that lets you pass requests along a chain of handlers. Upon receiving a request, each handler decides either to process the request or to pass it to the next handler in the chain.</p> <p><strong>State</strong> is a behavioral design pattern that lets an object alter its behavior when its internal state changes. It appears as if the object changed its class.</p>




_________________________________________________________________________________________________________________________
**<h1>Security</h1>**

<h4><strong>Definitions of Security and Privacy. Common Security Tactics.</strong></h4>

Security Definition: </br>
A system’s ability to protect data and services from unauthorized access while ensuring access for legitimate users and systems.

- 🔒 **Confidentiality** – Protection from unauthorized access. E.g.:
  - a hacker cannot access your income tax returns on a government computer.

- 🛡️ **Integrity** – Ensuring data and services are not manipulated without authorization. E.g.:
  - your grade has not been changed since your instructor assigned it.

- 📶 **Availability** – Guaranteeing the system is accessible for legitimate use. E.g.:
  - a denial-of-service attack won’t prevent you from ordering a book from an online bookstore.

Privacy Definition: </br>

A concern closely related to security,  
governed by separate regulations.

- 📜 **Regulated by frameworks** like **GDPR** and similar data protection laws.

- 🔥 **Personally Identifiable Information (PII)** includes:
  - Data that can identify a person (e.g., name, SSN, birth date, biometric data)
  - Data linked or linkable to a person (e.g., medical, educational, financial, or employment info)

Security tactics </br>
- **Objective:**  
  Implement proactive and reactive measures to ensure system resilience against security threats.

- **Detect Attacks**  
  Identify potential threats through monitoring and alerts.

- **Resist Attacks**  
  Prevent or limit impact using controls like authentication, authorization, firewalls and encryption.

- **React to Attacks**  
  Contain and respond to active threats by revoking access or restricting login.

- **Recover from Attacks**  
  Restore systems and data and resume normal operations.

<h4><strong>What Are the Common Ways to Implement Authentication in Web Applications? What Purpose Do OAuth and OpenID Serve For?</strong></h4>

### HTTP Authentication:
- **Basic** – Username and password sent encoded but unencrypted  
- **Digest** – One-way MD5 hash of credentials and request using a server-provided nonce

### App Authentication:
- **API Key** – Simple key sent via header or query  
- **Certificate-Based** – Uses digital certificates to identify users/devices  
- **OpenID** – Standard for federated identity across providers
- **Shibboleth** – Academic-focused identity federation  
- **SAML** – Secure exchange of identity data between identity and service providers

### Resource Authorization:
- **OAuth 2.1** – Secure delegated access to third-party services 

OAuth and OpenID purpose:
**Authorization Server:**  
Issues security tokens after user authentication, enabling apps and APIs to manage access (grant, deny, revoke).

**Client:**  
The app requesting access to protected resources (e.g., web app, SPA, or API calling another API).

**Resource Owner:**  
The end-user who owns the data; grants or denies access to their resources.

**Resource Server:**  
Hosts the data; relies on the authorization server to verify tokens and control access to data based on token information.

<h4><strong>Definition of Multi-Factor Authentication.</strong></h4>

- **Definition:**  
  Grants access only after presenting two or more authentication factors:
  - **Knowledge (Something you know):**  
    Password, PIN, secret questions
  - **Possession (Something you have):**  
    Security card, smartphone, hardware token
  - **Inherence (Something you are):**  
    Fingerprint, facial recognition, iris scan

- **Third-Party Authenticator (TPA):**  
  Apps that generate rotating codes for second-factor authentication


<h4><strong>Common Authorization Methods.</strong></h4>

- **Role-Based Access Control (RBAC):**  
  Access is granted based on a user’s assigned role. Also known as non-discretionary access control.

- **Policy-Based Access Control (PBAC):**  
  Access is dynamically determined by evaluating rules and policies.

- **Attribute-Based Access Control (ABAC):**  
  Grants access based on user, resource, and environment attributes.

- **Privileged Access Management (PAM):**  
  Secures and monitors accounts with elevated access to sensitive systems.


<h4><strong>Common Security Vulnerabilities and How to Avoid Them?</strong></h4>

1. **Broken Object Level Authorization**
   - Implement authorization checks with user policies and hierarchy  
   - Don’t rely on IDs sent from client. Use IDs stored in the session object instead  
   - Check authorization each time there is a client request to access database  
   - Use random non-guessable IDs (UUIDs)  

2. **Broken Authentication**
   - Check all possible ways to authenticate to all APIs  
   - Password reset APIs and one-time links also allow users to get authenticated and should be protected just as seriously  
   - Use standard authentication, token generation, password storage, Multi-factor authentication  
   - Use short-lived access tokens  
   - Authenticate your apps (so you know who is talking to you)  
   - Use stricter rate-limiting for authentication, implement lockout policies and weak password checks  

3. **Broken Object Property Level Authorisation**
   - Don’t automatically bind incoming data and internal objects  
   - Explicitly define all the parameters and payloads you are expecting  
   - For object schemas, use the `readOnly` set to `true` for all properties that can be retrieved via APIs but should never be modified  
   - Precisely define at design time the schemas, types, patterns you will accept in requests and enforce them at runtime  

4. **Unrestricted Resources Consumption**
   - Rate limiting  
   - Payload size limits  
   - Rate limits specific to API methods, clients, addresses  
   - Checks on compression ratios  
   - Limits on container resources  

5. **Broken Function Level Authorization**
   - Don’t rely on app to enforce admin access  
   - Deny all access by default  
   - Grant access based on specific roles  
   - Properly design and test authorization  

6. **Unrestricted Access to Sensitive Business Flows**
   - The mitigation planning should be done in two layers:  
     - *Business*: identify the business flows that might harm the business if excessively used  
     - *Engineering*: choose the right protection mechanisms to mitigate the business risk  
   - Slow down automated threats:  
     - Device fingerprinting (e.g., deny service to headless browsers)  
     - Human detection (e.g., CAPTCHA, typing pattern biometrics)  
     - Non-human pattern detection (e.g., too-quick checkout behavior)  
   - Consider blocking IPs of Tor exit nodes and known proxies  

7. **Server-Side Request Forgery (SSRF)**
   - Isolate the resource fetching mechanism in your network  
   - Use allowlists for:  
     - Remote origins (e.g., Google Drive, Gravatar)  
     - URL schemes and ports  
     - Accepted media types  
   - Disable HTTP redirections  
   - Use a well-tested URL parser  
   - Validate and sanitize all client-supplied input  
   - Do not send raw responses to clients  

8. **Security Misconfiguration**
   - Repeatable hardening and patching processes  
   - Automated process to locate configuration flaws  
   - Disable unnecessary features  
   - Restrict administrative access  
   - Define and enforce all outputs including errors  

9. **Improper Inventory Management**
   - Inventory all API hosts  
   - Limit access to anything that should not be public  
   - Limit access to production data; segregate access to production and non-production data  
   - Implement additional controls such as API firewalls  
   - Properly retire old versions or backport security fixes  
   - Implement strict authentication, redirects, CORS, etc.  

10. **Unsafe Consumption of APIs**
   - Evaluate service providers for API security posture  
   - Ensure secure communication (TLS) for all API interactions  
   - Validate and sanitize data received from integrated APIs  
   - Maintain an allowlist of safe redirect destinations for integrated APIs  




_________________________________________________________________________________________________________________________
**<h1>Performance</h1>**

<h4><strong>What Is Performance? What Are the Main Principles of High-Performance Software Design? What Are the Common Performance Tactics?</strong></h4>
Performance is about time and software system’s ability to meet timing requirements.

1. **Efficient Algorithms and Data Structures**  
   Use time- and space-efficient solutions to reduce complexity and improve responsiveness.

2. **Concurrency and Parallelism**  
   Leverage multi-threading, async I/O, and parallel processing to maximize CPU utilization.

3. **Caching**  
   Store frequently accessed data in memory to reduce computation and latency.

4. **Minimize I/O Operations**  
   Reduce disk, network, and DB I/O where possible.  
   Use batch operations and lazy loading.

5. **Optimized Resource Management**  
   Efficiently manage memory, threads, and network connections. Avoid resource leaks.

6. **Horizontal and Vertical Scaling**  
   Design for scale-out (adding nodes) and scale-up (more powerful hardware).

7. **Load Balancing**  
   Distribute traffic evenly across services or nodes to prevent overload and ensure availability.

8. **Fault Tolerance and Resilience**  
   Use retries, circuit breakers, redundancy, and graceful degradation to handle failures.

9. **Performance Monitoring and Optimization**  
   Use profiling, tracing, and metrics to identify and resolve bottlenecks proactively.

10. **Lean and Modular Architecture**  
   Keep components small, cohesive, and loosely coupled for agility and better maintainability.

## Performance Tactics

The goal of performance tactics is to *generate a response to events arriving at the system under some time-based or resource-based constraint*.

### Control Resource Demand
- Manage Work Requests  
- Limit Event Response  
- Prioritize Events  
- Reduce Computational Overhead  
- Bound Execution Times  
- Increase Efficiency  

➡️ Reduce or smooth load through caching, load shedding, or limiting user input.

### Manage Resources
- Increase Resources  
- Introduce Concurrency  
- Maintain Multiple Copies of Computations  
- Maintain Multiple Copies of Data  
- Bound Queue Sizes  
- Schedule Resources  

➡️ Allocate CPU, memory, and I/O wisely using prioritization, pooling, and concurrency control.

<h4><strong>What Is Rate-Limiting? Common Types of Rate-Limiting Algorithms.</strong></h4>
Rate limiting controls the rate at which users or services can access a resource.

## Rate-Limiting Algorithms

Rate-limiting algorithms are essential tools that enable organizations to control and limit the rate of incoming requests to their applications and systems. Different algorithms can be used depending on the specific needs of the application or system.

---

### 1. **Token Bucket Rate Limiting**

**How It Works:**
- Tokens are added to a bucket at a steady rate (e.g., 1 token per second).
- The bucket has a maximum capacity.
- Each request removes one token.
- If the bucket is empty, the request is rejected.

**Benefits:**
- Allows bursts of traffic.
- Smooths out request rates over time.
- Good for APIs with variable usage patterns.

---

### 2. **Leaky Bucket Rate Limiting**

**How It Works:**
- Requests enter a queue.
- The queue is processed at a constant rate (like water leaking).
- If the queue is full, new requests are rejected.

**Benefits:**
- Smooths out bursts.
- Prevents overload.
- Simple to implement.

---

### 3. **Fixed Window Counter**

**How It Works:**
- Track the number of requests in a fixed time window (e.g., 1 minute).
- Reset the counter when the window expires.
- Allow requests if the count is below the limit.

**Benefits:**
- Simple and efficient.
- Good for DDoS protection.

**Drawback:**
- Can allow bursts at window boundaries.

---

### 4. **Sliding Log Algorithm**

**How It Works:**
- Store timestamps in a list.
- Remove timestamps older than the time window.
- Count the remaining timestamps.
- Allow request if count < limit.

**Benefits:**
- Very accurate.
- Flexible and fair.

**Drawback:**
- Memory-intensive for high traffic.

---

### 5. **Sliding Window Counter**

**How It Works:**
- Track counts for current and previous windows.
- Calculate how far into the current window we are.
- Estimate total requests using:

  `estimatedCount = previousCount × (1 − fraction) + currentCount`

- Allow request if estimated count < limit.

**Benefits:**
- Smooths out spikes.
- More accurate than fixed window.
- Less memory usage than sliding log.

<h4><strong>What Is Caching? Common Caching Strategies.</strong></h4>

## Caching

Caching is the process of persisting frequently used data for a certain period of time to ensure its faster access and off-load work from the database.

---

### Cache Types

- **Client-Side Caching**  
  Data is stored on the client side. In the case of a web browser, this could be browser-specific caches.

- **Network-Level Caching**  
  Intermediate HTTP web servers and routers are configured to cache API calls and resources.

- **Disk-Level Caching**  
  Files are stored on disk and accessed by their name.

- **In-Memory Caching**  
  Files or data are stored in memory (RAM) for very fast access.

- **Distributed Caching**  
  A cache shared by multiple app servers, typically maintained as an external service (e.g., Redis, Memcached) accessed by all servers.

---

### HTTP Caching

- **Private Cache**  
  Tied to a specific client, typically a browser cache.  
  Header example: `Cache-Control: private`

- **Shared Cache**  
  Located between the client and server; stores responses that can be shared among multiple users.  
  Header controls:  
  `Cache-Control: no-store, no-cache, max-age=0, must-revalidate, proxy-revalidate`

_________________________________________________________________________________________________________________________
**<h1>Availability</h1>**

<h4><strong>Availability Definitions: Fault, Error, Failure. Types of Faults.</strong></h4>
- **Availability** – software is there and ready to carry out its task when needed.

- **Availability = reliability + recovery** (when the system breaks, it repairs itself)
  - A *fault* is an unexpected or abnormal behavior in a system component that can lead to an error or failure.
  - An *error* is an erroneous state of the system that results from faults.
  - A *failure* defines an event where a system can’t deliver a service or accomplish its intended purpose. It’s a visible result of an error.

## Types of Faults

Faults can be categorized based on:

### 1. **Frequency of Appearance**
- **Transient** – Occurs once and disappears (e.g., temporary power loss).
- **Intermittent** – Occurs occasionally and unpredictably (e.g., loose connection).
- **Permanent** – Consistent and reproducible (e.g., hardware failure).

### 2. **Root Causes**
- **Hardware** – Faults due to physical components (e.g., disk crash).
- **Software** – Bugs or misconfigurations in code or logic.
- **Human-error** – Mistakes made by users or administrators (e.g., misconfigured firewall).
- **Non Human-error** – Automatic system actions that result in faults (e.g., auto-scaling misbehaving).
- **Environmental** – External factors like power outages, temperature spikes, or natural disasters.

<h4><strong>Definition of Highly Available Architecture. Purpose and Principles of Load-Balancing, Data Scalability, Geographical Diversity, and Business Continuity and Disaster Recovery.</strong></h4>
## Highly Available Architecture

- **Load Balancing**  
  Distribute traffic across nodes with a pre-defined failover strategy for node failures.

- **Data Scalability**  
  Scale databases via replication or partitioning or allow each instance to manage its own data.

- **Geographical Diversity**  
  Deploy clusters across regions to ensure resilience against local outages or disasters.

- **Backup & Recovery**  
  Plan for full system recovery using a clear backup strategy (e.g., 3–2–3 rule: 3 copies, 2 media, 3 locations).

## Load Balancing

- **Definition:**  
  - Distributes client requests across multiple service instances to ensure reliability and performance.

- **Static:**
  - Round Robin  
  - Sticky Round Robin  
  - Weighted Round Robin

- **Dynamic:**
  - Least Connections  
  - Least Response Time

Scalability:
## Sharding vs Replication

- **Sharding:**  
  A large dataset is split into smaller chunks (*shards*) distributed across multiple databases.  
  It’s a horizontal scaling solution that increases the number of database instances in a system.

- **Replication:**  
  Identical copies of a database are created on additional machines.

## Geographical Diversity & Availability Zones

- **Availability Zones (AZs)**  
  - Located within a region, AZs offer low-latency interconnects but are isolated enough to avoid shared failure risks.

- **Infra Independence**  
  - Each AZ has its own power, cooling, and networking, ensuring fault isolation.

- **High Availability**  
  - If one AZ fails, others can maintain regional service continuity and capacity.

## Business Continuity and Disaster Recovery

Disaster recovery measures are strategies and procedures that organizations put in place to ensure that they can recover from natural or man-made disasters that could disrupt their normal operations.

**The goal of disaster recovery** is to minimize the impact of a disaster on an organization’s ability to function and to restore normal operations as quickly as possible.

---

### Key Metrics

1. **Recovery Time Objectives (RTO):**  
   Maximum acceptable length of time that the resource can be down.

2. **Recovery Point Objectives (RPO):**  
   Maximum age of the data that can be lost.

3. **The number of plans** that cover each *critical business process*.

4. **The amount of time** since each plan was updated.

5. **The number of business processes** that are threatened by a potential disaster.

6. **The actual time** it takes to recover a business process.

7. **The difference** between *target* and *actual* recovery time.

<h4><strong>What Does the CAP Theorem Define?</strong></h4>

## CAP Theorem

A distributed system **cannot simultaneously guarantee**:

- **Consistency (C)** – Every node returns the most recent data.
- **Availability (A)** – Every request gets a non-error response.
- **Partition Tolerance (P)** – The system continues to operate despite network splits.

---

### In the event of a network partition (P), a system must choose either:

- **Consistency (C)** → Reject requests to avoid stale data.
- **Availability (A)** → Respond with possibly outdated data.

➡️ *You can only choose two of the three (C, A, P).*

_________________________________________________________________________________________________________________________
**<h1>Energy Efficiency</h1>**

<h4><strong>Common Energy Efficiency Tactics</strong></h4>
## Energy Efficiency Tactics

### Objectives:
- Conserve or manage energy while maintaining the required functionality.

---

### Monitor Resources
- Track usage to identify inefficiencies.

### Allocate Resources Wisely
- Use only what’s needed—scale up/down based on demand.

### Reduce Demand
- Optimize code, batch workloads, and offload non-critical tasks.

---

### Tactic Tree (Summary)
**Monitor Resources**
- Metering  
- Static Classification  
- Dynamic Classification

**Allocate Resources**
- Reduce Usage  
- Discovery  
- Schedule Resources

**Reduce Resource Demand**
- Manage Event Arrival  
- Limit Event Response  
- Prioritize Events  
- Reduce Computational Overhead  
- Bound Execution Times  
- Increase Resource Usage Efficiency


_________________________________________________________________________________________________________________________
**<h1>Enterprise Architecture</h1>**

<h4><strong>What Is Enterprise Architecture?</strong></h4>
## What is Enterprise Architecture?

- **The integrated blueprint of the enterprise:**  
  - A collection of special documents (artifacts) describing various aspects of an organization from an integrated business and IT perspective, intended to bridge the communication gap between business and IT stakeholders.

- **A rigorous model** consisting of:  
  - Motivations, structures, information, processes, and systems of an enterprise created for the purpose of decision support.

- **A plan for the fundamental structure** of systems:  
  - Which comprise and support the enterprise together with the context of those systems and the principles governing their development and evolution.

- **A process of analyzing, assessing and documenting:**  
  - The context & environment of the systems, researching options, and making decisions for the systems components, structures & principles.

- **Enterprise architecture drives to standardization**, which in turn **drives to commercialization**:
  - *Lower run-the-engine (RTE)* costs
  - *Faster rollout of a function*, whether this is an atomic function (e.g., configure a server, configure a storage partition) or a more complex integrated function (e.g., new software application).
 
## Why Enterprise Architecture?

1. Unreliable enterprise information  
2. Untimely enterprise information  
3. New complex projects  
4. Acquisitions of new companies  
5. Business unit selling plans  
6. Identification of outsourcing opportunities  
7. Compliance with regulatory requirements  
8. Automation of relationships with partners  
9. Automation of relationships with customers  
10. IT--Business Unit relationship issues  
11. Interoperability challenges of IT systems  
12. Unmanageable IT systems

<h4><strong>What Are the Main Principles of The Zachman Framework? What Are the Rows and Columns About?</strong></h4>
## The Zachman Framework

- The Zachman Framework is an **enterprise ontology** and is a **fundamental structure** for enterprise architecture which provides a formal and structured way of viewing and defining an enterprise.

- The ontology is a **two-dimensional classification schema**:
  - **Aspects:** What, How, When, Who, Where, and Why  
  - **Perspectives:**  
    - Executive (*Planner*)  
    - Business Manager (*Owner*)  
    - Architect (*Designer*)  
    - Engineer (*Builder*)  
    - Technician (*Implementer*)  
    - Enterprise (*Operator*)

- The Framework **IS NOT a methodology** for creating the implementation (an instantiation) of the object.  
  ➝ It is about a **structure**, not a **process**.

## The Framework as a Classification Structure

The Framework is the product of many years of research and experience (from the late 80s), finding words and graphic concepts to represent and convey the classification logic as precisely as possible.

---

### Zachman defines 7 rules for using the framework:

1. **Do Not Add Rows or Columns** to the Framework  
2. **Each Column Has a Simple Generic Model**  
3. **Each Cell Model Specializes Its Column’s Generic Model**  
4. **No Meta Concept Can Be Classified Into More than One Cell**  
5. **Do Not Create Diagonal Relationships Between Cells**  
6. **Do Not Change the Names** of the Rows or Columns  
7. **The Logic is Generic, Recursive**

---

### Perspectives (Rows):

- **Planner** – *Executive Perspective*  
- **Owner** – *Business Manager Perspective*  
- **Designer** – *Architect Perspective*  
- **Builder** – *Engineer Perspective*  
- **Implementer** – *Technician Perspective*  
- **Operator** – *The Enterprise (Functioning System)*

---

### Aspects (Columns):

- **What** – Material  
- **How** – Process  
- **Where** – Geometry  
- **Who** – Instructions  
- **When** – Timing  
- **Why** – Objectives

<h4><strong>What Is the TOGAF? What Is Considered as the Core of TOGAF? What Are the Main Differences Between TOGAF and Zachman Framework?</strong></h4>
Viewed as an architectural process, TOGAF complements Zachman, which is categorized as an architectural taxonomy. 
![image](https://github.com/user-attachments/assets/78281eec-7205-41ea-ad7d-b384950391b9)

## TOGAF & The Architecture Development Method (ADM)

The most important part of **TOGAF** is the **Architecture Development Method (ADM)**.  
ADM is a *recipe* for creating an architecture — and a recipe can be categorized as a *process*.

---

### ADM Phases

- **Preliminary Phase:**  
  Preparation, initiation, and customization

- **Phase A: Architecture Vision**  
  Initiative scope, identification of key stakeholders, creation of the architecture vision, and buy-in from stakeholders

- **Phase B: Business Architecture**  
  Business workflow and strategy changes needed to support the architecture vision. Describes the processes the business uses to meet its goals.

- **Phase C: Information Systems Architecture**  
  Logical and physical data model changes needed to support the architecture vision. Describes how specific applications are designed and how they interact.

- **Phase D: Technology Architecture**  
  Hardware, software, platforms, and infrastructure changes needed to support the architecture vision

- **Phase E: Opportunities & Solutions**  
  Create roadmap showing the iterations and projects required to satisfy the architecture vision

- **Phase F: Migration Planning**  
  Identify business value for each iteration and sort/ prioritize projects based on dependencies, cost, benefit, and risks

- **Phase G: Implementation Governance**  
  Defines acceptance criteria and outstanding issues; ensures alignment between implementation and architecture vision

- **Phase H: Architecture Change Management**  
  Governs and measures change during implementation of the architecture vision and roadmap; identifies and manages risks

---

### TOGAF vs Zachman

- TOGAF is an **architectural process**  
- Zachman is an **architectural taxonomy**

➡️ *Zachman tells you how to categorize your artifacts.  
TOGAF gives you a process for creating them.*




_________________________________________________________________________________________________________________________
**Legal, ethical, and social aspects of IS**

<h4><strong>Software Engineering Code of Conduct</strong></h4>

## SWE Code of Conduct Principles

### Be impartial
The good of the general public is equally important to the good of your organization or company. The good of your profession and your company are equally important to your personal good. It is wrong to promote your agenda at the expense of your firm, and it is wrong to promote the interests of your firm at the expense of society.

### Disclose information that others ought to know
- Do not let others come to harm by concealing information from them.  
- Do not make misleading or deceptive statements.  
- Disclose potential conflicts of interest.

### Respect the rights of others
Do not infringe on the privacy rights, property rights, or intellectual property rights of others.

### Treat others justly
Everyone deserves fair wages and appropriate credit for work performed. Do not discriminate against others for attributes unrelated to the job they do. Do not penalize others for following the Code.

### Take responsibility for your actions and inactions
As a moral agent, you are responsible for the things you do, both good and bad. You may also be responsible for bad things that you allow to happen through your inaction.

### Take responsibility for the actions of those you supervise
Managers are responsible for setting up work assignments and training opportunities to promote quality and reduce risk. They should create effective communication channels with subordinates so that they can monitor the work being done and be aware of any quality or risk issues that arise.

### Maintain your integrity
Deliver on your commitments and be loyal to your employer, while obeying the law. Do not ask someone else to do something you would not be willing to do yourself.

### Continually improve your abilities
Take advantage of opportunities to improve your software engineering skills and your ability to put the Code to use.

### Share your knowledge, expertise, and values
Volunteer your time and skills to worthy causes. Help bring others to your level of knowledge about software engineering and professional ethics.


![image](https://github.com/user-attachments/assets/2f2dcd51-1666-4253-930a-653b98ae91db)

![image](https://github.com/user-attachments/assets/917b4d22-944a-4835-9baa-9cf7d80d4c51)

![image](https://github.com/user-attachments/assets/8800421c-fe3f-4ba1-a97a-2054d64cb108)




