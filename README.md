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

<h4><strong>What Is Information Architecture? What Value It Provides?</strong></h4>

<h4><strong>What Are the Main Principles of MVC Pattern?</strong></h4>

<h4><strong>What Common Design Patterns Are Used in UX/UI Design?</strong></h4>


_________________________________________________________________________________________________________________________
**<h1>Security</h1>**

<h4><strong>Definitions of Security and Privacy. Common Security Tactics.</strong></h4>

<h4><strong>What Are the Common Ways to Implement Authentication in Web Applications? What Purpose Do OAuth and OpenID Serve For?</strong></h4>

<h4><strong>Definition of Multi-Factor Authentication.</strong></h4>

<h4><strong>Common Authorization Methods.</strong></h4>

<h4><strong>Common Security Vulnerabilities and How to Avoid Them?</strong></h4>


_________________________________________________________________________________________________________________________
**<h1>Performance</h1>**

<h4><strong>What Is Performance? What Are the Main Principles of High-Performance Software Design? What Are the Common Performance Tactics?</strong></h4>

<h4><strong>What Is Rate-Limiting? Common Types of Rate-Limiting Algorithms.</strong></h4>

<h4><strong>What Is Caching? Common Caching Strategies.</strong></h4>


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




