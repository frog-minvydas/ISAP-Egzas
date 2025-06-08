**<h1>Domain Driven Design</h1>**

**<h4>What is DDD? What issues it attempts to solve, what values does it provide, and what are the main principles of DDD?</h4>**

Domain Driven Design – an approach to software development enabling teams to more effectively manage the construction and maintenance of software for complex problem domains!

Solves issues:
cost centric vs profit centric view on development process
solving problems using technology rather than careful thought and design
database is given too much priority
improper naming of objects and operations
too fast delivery -> lower quality -> big ball of mud
business logic in user interface components and persistence components
broken, slow, and locking database queries 
wrong abstractions
strongly coupled services

Values:

domain model
precise definition and understanding of the business is developed
domain experts contribute to software design 
better user experience is gained 
clean boundaries are placed around pure models 
Enterprise Architecture is better organized
Agile, Iterative, Continuous modelling
new tools, both Strategic and Tactical, are employed

Principles:

Exploration and experimentation
Challenging assumptions
Continuously modelling
No wrong models – practice
Flexible code aids discovery
Problem solver first, technologist second
Don’t solve all the problems
Good is good enough



**<h4>What are the main concerns of strategic modelling in DDD?</h4>**
Bounded context, Ubiquitous language, context map, concrete view

**<h4>What is the Concept map? What is the value of good domain boundaries?</h4>**

Good domain boundaries contribute to many organizational and technical improvements.
As shown in figure, looser coupling results in fewer dependencies and
faster flow—and, from personal experience, much happier teams. Cohesive boundaries
that group related concepts lead to a clearer sense of purpose, aligning and motivating
teams and incentivizing sustainable practices. Cohesion also makes it easier to
learn the domain, in turn helping teams go beyond coding to contributing product
and domain innovations.

Context map - global view of bounded contexts
overlap between project management and software design
does not have to be documented in any form; yet it needs to be understood and agreed.

Domain Types:
Core Domain
Supporting Domain
Generic Domain
Bounded Contexts:
Internal
External

**<h4>What are the context mapping patterns?</h4>**

Shared kernel
Partnership
Customer/Supplier
Anticorruption Layer
Open Host Service
Even Publisher
Published Language
Separate ways
Conformist



**<h4>Tactical modelling concepts and patterns.</h4>**

Aggregate
A cluster of associated objects that are treated as a unit for the purpose of data changes.
External references are restricted to one member of the aggregate, designated as the root.
A set of consistency rules applies within the aggregate boundaries.
Entity
An object fundamentally defined not by its attributes, but by a thread of continuity and identity.
Value Object
An object that describes some characteristic or attribute but carries no concept of identity.
Whole Value
An object that models a single, complete concept.
Repository
A mechanism for encapsulating storage, retrieval, and search behavior which emulates a collection of objects.
Service
An operation offered as an interface that stands alone in the model, with no encapsulated state.
Factory
A mechanism for encapsulating complex creation logic and abstracting the type of a created object for the sake of a client.


**<h4>Domain Model Implementation patterns: domain model, transaction script, table module, active record, anemic domain model.</h4>**

Domain model
The domain model pattern is based on the premise that there is no database
Model‐driven as opposed to data‐driven design

Transaction script
Follows a procedural style of development rather than an object‐oriented approach
Single procedure is created for a business transaction; grouped in a static manager or service class
Each procedure contains all the business logic that is required to complete the business transaction
from the workflow, business rules, and validation checks 
to persistence in the database

Table Module
A single object represents a table or view in the database. 
The object is responsible for all persistence needs along with business logic behavior. 
Good fit for simpler parts of the domain that are isolated by a bounded context and that are simply forms over data. 
If the object model and database model start to diverge, then refactor toward the domain model pattern.

Active record
An object that wraps a row in a database table or view, encapsulates the database access, and adds domain logic on that data.

Anemic domain model
Anemic domain model – anti-pattern: domain objects lack significant business logic.
Business logic resides outside the model, leaving domain objects as mere data transfer classes.
Violation of the "Tell, Don’t Ask" principle; objects should communicate capabilities instead of exposing properties for client determination.
Suitable for parts of domain models with minimal logic or teams less experienced in object-oriented programming.
Can integrate with the Ubiquitous Language (UL) and serve as a preliminary step toward a richer domain model.

_________________________________________________________________________________________________________________________
**<h1>Introduction to Software Architecture</h1>**


**<h4>What is Software Architecture and why it is important?</h4>**

**<h4>Common Software Architectural patterns and styles.</h4>**

**<h4>Common types of Client/Server applications. Difference between Multi-Page and Single-Page Web Applications.</h4>**

**<h4>Common structural patterns of Software Architecture.</h4>**

**<h4>Data management design patterns: CRUD and CQRS. Principles, purposes, differences.</h4>**

**<h4>Software Architecture definition principles and techniques.</h4>**


_________________________________________________________________________________________________________________________
**<h1>Software Architecture Styles</h1>**


<h4><strong>Laws and Characteristics of Software Architecture</strong></h4>

<h4><strong>Common Fallacies about Distributed Software Architecture</strong></h4>

<h4><strong>Principles of Monolith Software Architecture Style</strong></h4>

<h4><strong>Principles of Pipeline Architecture Style</strong></h4>

<h4><strong>Principles of Microkernel Architecture Style</strong></h4>

<h4><strong>Principles of Service-Based Architecture Style</strong></h4>

<h4><strong>Principles of Event-Driven Architecture Style</strong></h4>

<h4><strong>Differences between Broker and Mediator Topologies in Event-Driven Architecture</strong></h4>

<h4><strong>When is Hybrid Event-Driven Architecture Typically Considered?</strong></h4>

<h4><strong>Main Principles of Space-Based Architecture Style</strong></h4>

<h4><strong>Main Principles of Microservices Architecture Style</strong></h4>

<h4><strong>What Should Be Considered When Selecting an Architectural Style?</strong></h4>

_________________________________________________________________________________________________________________________
**<h1>Software Modifiability</h1>**


<h4><strong>How Modifiability Can Be Measured?</strong></h4>

<h4><strong>What Is Coupling, Cohesion, and Connascence?</strong></h4>

<h4><strong>General Software Design Principles</strong></h4>

<h4><strong>What Concerns Are Typically Considered in Software Design? What Is Separation of Concerns?</strong></h4>

<h4><strong>What Are the Main Principles of YAGNI?</strong></h4>

<h4><strong>What Are the Main Cohesion Principles?</strong></h4>

<h4><strong>What Are the Main Coupling Principles?</strong></h4>

<h4><strong>What Are the SOLID Principles?</strong></h4>


_________________________________________________________________________________________________________________________
**<h1>Deployability</h1>**


<h4><strong>What Is the Cloud Computing Model? What Perspectives Does It Cover?</strong></h4>
<h4><strong>What Are the Possible Cloud Deployment Technology Options?</strong></h4>
<h4><strong>What Is the Difference Between Virtualization vs Containerization?</strong></h4>
<h4><strong>What Are the Common Types of &lt;Resource&gt;-as-a-Service? What Are the Differences Between Them?</strong></h4>
<h4><strong>What Are the Common Cloud Deployment Models?</strong></h4>
<h4><strong>What Are the Common Deployability Tactics?</strong></h4>

_________________________________________________________________________________________________________________________
**<h1>Integrability</h1>**


<h4><strong>What Are the Common Module/Service Integration Styles?</strong></h4>

<h4><strong>What Is API? What Different Styles of API Do You Know?</strong></h4>

<h4><strong>What Is REST API? What Properties Does It Possess? What Are the REST API Maturity Levels?</strong></h4>

<h4><strong>How to Ensure Asynchronicity in REST API Design?</strong></h4>

<h4><strong>What Is Message-Based Communication?</strong></h4>

<h4><strong>What Is the Purpose of Different Messaging Patterns? Provide Some Examples of Messaging Patterns?</strong></h4>

<h4><strong>How Sync/Async APIs Can Be Documented?</strong></h4>


_________________________________________________________________________________________________________________________
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

<h4><strong>Definition of Highly Available Architecture. Purpose and Principles of Load-Balancing, Data Scalability, Geographical Diversity, and Business Continuity and Disaster Recovery.</strong></h4>

<h4><strong>What Does the CAP Theorem Define?</strong></h4>


_________________________________________________________________________________________________________________________
**<h1>Energy Efficiency</h1>**

<h4><strong>Common Energy Efficiency Tactics</strong></h4>


_________________________________________________________________________________________________________________________
**<h1>Enterprise Architecture</h1>**

<h4><strong>What Is Enterprise Architecture?</strong></h4>

<h4><strong>What Are the Main Principles of The Zachman Framework? What Are the Rows and Columns About?</strong></h4>

<h4><strong>What Is the TOGAF? What Is Considered as the Core of TOGAF? What Are the Main Differences Between TOGAF and Zachman Framework?</strong></h4>


_________________________________________________________________________________________________________________________
**Legal, ethical, and social aspects of IS**

<h4><strong>Software Engineering Code of Conduct</strong></h4>



![image](https://github.com/user-attachments/assets/2f2dcd51-1666-4253-930a-653b98ae91db)

![image](https://github.com/user-attachments/assets/917b4d22-944a-4835-9baa-9cf7d80d4c51)

![image](https://github.com/user-attachments/assets/8800421c-fe3f-4ba1-a97a-2054d64cb108)




