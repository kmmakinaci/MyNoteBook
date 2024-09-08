#  A Short Review for CPSA-F  Examination

Disclaimer: These notes are directly sourced from the *Software Architecture Foundation - 2nd Edition: CPSA Foundation® Exam Preparation Book*. Some sentences are copied verbatim as they are part of a review, while others have been modified for quicker note-taking. The notes from the [publicly available sections of the book](https://books.google.de/books?id=iMLDEAAAQBAJ&printsec=frontcover&hl=tr&source=gbs_atb#v=onepage&q&f=false) to ensure compliance with copyright regulations. The rest reflect my personal understanding.

## Chapter 1 : Basic concepts of software architecture

### LG 1-1 : Definitions of software architecture

**Discuss definitions of software architecture (R1)**

Software architects know several definitions of software architecture (incl. ISO 42010/IEEE 1471, SEI, Booch, etc.) and can name their similarities:

* Components/buildings blocks with interfaces and relationships
* Building blocks as a general term, components as a special form thereof
* Structures, cross-cutting concepts, principles
* Architecture decisions and their consequences on the entire system and its life-cycle

***Software architecture*** definition according to the IEEE 1471 : Software architecture is the fundamental organization of a system embodied in its components, their relationships to each other and to the environment, and the principles guiding its design and evolution.

#### Fundamental organization

The way things are ordered and each element is given its designated place. Fundamental because it must stand out clearly, be obvious to everyone who works on this system and act as the most profound guideline to be followed.

##### Components (Structural part or building block of systems)

The structural elements of software: Subsystems, modules, classes, functions -building blocks-. Components are usually implemented in source code in a programming language, but can also be other artifacts that make up the system.

##### Relationships (To coupling of elements, enabling them to cooperate or exchange data)

Interfaces, dependencies, associations. Components need to interact with other components, otherwise no separation of concerns (division of responsibility) would be possible.

On the downside: Designing good interfaces is really difficult, and misunderstanding of interfaces is the source of many problems in software systems.

##### Environment

Every system has some relationships (aka interfaces, dependencies) to its environment:

data, control flow of events are transferred to and from possibly different kinds of neighbors.

##### Principles (Rules or points throughout the system or its development)

A rule that holds for the whole system or several parts of it. Usually valid for several elements of the system. (Concept)

##### Design and evolution 

Cross-cutting and system-wide decisions might become necessary during both initial design and ongoing evolution and maintenance of systems.

*SEI / Bass+2021* : The software architecture of a system is the set of structures needed to reason about the system, which comprise software elements, relations among them, and properties of both.

*Galan & Perry* : The structure of the components of a program/system, their interrelationships, and principles and guidelines governing their design and evolution over time.

**Commonalities of definitions**

The following terms appear repeatedly in several definition of software architecture:

* Component: Structural part or building block of systems.
* Structure: An arrangement of interrelated elements (aka. components or building blocks) that together perform a common task.
* Relationships/dependencies: The coupling of elements, enabling them to cooperate or exchange data.
* Design or architecture decisions: A system or its architecture evolves from an arbitrary number of (design or architecture) decisions of all kinds.
* Cross-cutting concepts / principles : Rules or heuristic valid at several locations or points through-out the system or its development.
* Decomposition of larger things into smaller things. One of the golden rules of life (and computer science): If a problem is too large to handle all at once, break it down into more manageable units.-

'''

Make sure you know about the most important elements of any software architecture, namely components (building block of systems), relationships (dependencies, associations), the environment(all the things outside of your system) and principles (cross cutting topics or decisions).

You should know that your design and architecture decisions might influence or relate to all of these elements.

'''

### LG 1-2: Goals and benefits of software architecture

Software architects can justify the following essential goals and benefits of software architecture

* Support design, implementation, maintenance and operation of systems
* Achieve quality requirements such as reliability, maintainability, changeability, security, etc.
* Achieve functional requirements or ensure that they can be met
* Ensure that the system's structures and concepts are understood by all relevant stakeholders
* Systematically reduce complexity
* Specify architecturally relevant guidelines for implementation and operation.



### LG 1-3: Software Architecture in Software Lifecycle

Software architects understand their tasks and can integrate their results into the overall lifecycle of IT systems.

* Identify the consequences of changes in functional requirements, quality requirements, technologies or the system environment in relation to software architecture
* Elaborate on relationships between IT system and the supported business and operational process.

Software Lifecycle (SLC), SDLC (Software Development Lifecycle)

ssSLC: describes all phases of a software product planing-development-deployment, retirement.

Initial development (at this stage architects and developers acquire knowledge of the application domain and technologies used to implement system) will be crucial for future development. More importantly, the architecture established at this stage will have a significant impact on the ease of future evolution. Architect s have to aware of timely revenue generation and time to market investment strategies in the long run.

Often first release is not delivered after the initial development, but rather after several iterations during evolution, to ensure better alignment with customer needs and a more stable system. Release dates are usually determined both by business considerations and by the degree to which quality requirements are met. This puts architects in a position where they have to broker a suitable trade off between these, often conflict of interests.

Over time, changes accumulate a point where software architecture of a system either loses its integrity and coherence or becomes obstacle that limits future changes.

-Key words- servicing stage, phase out, close down

###### Exercises

* When has architecture the greatest or the least influence?
* Reflect on the consequences of changes in functional requirements to architecture decisions.
* Reflect on the consequences of changes in quality requirements on architecture decisions.
* Imagine a that a single quality requirement (e.g. performance, robustness, understandability, etc.) is drastically changed. How might other quality attributes affected by this?

### LG 1-4 Software Architects' task and responsibilities

Software architects are responsible for achieving the required or necesary quality and creating the architecture design for a solution. Depending on the actual approach or processes model used the may align overall responsibilities of project management and/or other roles.



Task and responsibilitees:

* Clarify scrutiniye requirements and constraints and refine them if necessary. Together with functional requirements(required features),this includes the required quality characteristics (required constraints).
* Decide how to decompose the system into building blocks, while determining dependencies and interfaces between building blocks.
* Determine and decide on cross-cutting concepts (for instance persistence, communication, GUI. etc.)
* Communicate and document the software architecture based on views, architectural patterns, cross-cutting and technical concepts.
* Accompany realization and implementation of the architecture; integrate feedback fromrelevant stakeholders into architecture if necessary; review and ensure the consistency of source code and software architecture.
* Analyze and evaluate software architecture, especially with the respect to risk involving the quality requirements,
* Identify, highlight, and justify the consequences of architectural decisions to other stakeholders
* They should independently recognize the necessity of iterations in all tasks and pint out possibilities for appropriate and relevant feedback.

No algorithmic approach. iteration to the rescue: As software architecture design is a highly creative task, there is no algorithmic way for achieving results. "appropriateness"

Multiple factors influence architecture;

Design, implementation decision; business and quality requirements, organizational and technical constraints, legal constraints, budget and time constraints, available technology, existing infrastructure, and so on...

Iterative approaches and integrated feedback. (Does not mean Scrum or similar,)

* early feedback
* early risk (and problem) identification
* more time to fiy problems and mitigate risks
* better chances to adapt to changes in requirements, constraints, technology, team etc.
* Opportunities to practice every activity in the development process, especially deploy and release-related activities.

Software architecture is a team effort. But there should be one person on charge who can decide in case of doubt or if the team cannot easily come to a consensual decision.

SWArch (with the development team) design and construct all elements that necessary for the development/operation/maintenance of sw.

* building blocks as the structural elements of systems
* interfaces bw building blocks or bw external systems(neighbor systems)
* Cooperation of building blocks through interfaces
* cross-cutting concept or rules
* selection of appropriate technologies
* adoption of suitable development and operation processes
* evertything else might be require to develop/implementan d operate the system.

Software architects need to fullfill six important tasks in oreder to design and develop successful systems based upon given functional and quality requirements:

* Clarify requirements	(Requirements analysis, Domain experts, Product management)
  * Design structures
    * Communicate architecture	(Development team, management)
    * Shepherd implementation
  * Design cross-cutting Concepts
    * Evaluate architecture
    * Shepperd implementation

! It always depends how much architecture, how much documentation, how much communication ...

Appropriateness looks for additional considerations.

#### Clarify requirements

In case of missing, unclear, inconsistent or contradictory requirements, software architects need to actively clarify requirements in conjunction with the corresponding stakeholders. 

So clarify;

* Who are the **stakeholders** of the system
* **Context** and **external interfaces**, expressing your system's relation to its communication partners (neighboring system and users). Show and specify the external interfaces, usually both system and user roles.
* **Quality requirements**. These often fundamentally influence architectural decisions.
* **Functional requirements** (clarify relevant functional requirements. You may not know everything in detail but you should have a good knowledge of the *architecturally* relevant ones- will be executed frequently, most important to stakeholders, critical timing or performance constraints, reads/updates/creates/moves large amount data, requires critical parts of your infrastructure) 
* **Constraints** are facts/requirements/needs/limitations that constrain software architects in their freedom when making design and implementation decisions or decisions about the development process.
* **Stability, validity, and importance** of all the points above.



#### Design structures and concepts

*Designing* belongs to the primary task of software architects. It means decisions and resolving potential conflicts between goals, requirements or constraints.

Distinguish two separate aspects of designing:

* Design structures: Source code elements of arbitrary sizes, subsystems, components, packages, namespaces, sometime more smaller elements like classes. Black box and white box manifestations.
* Designing (cross-cutting) concepts: Concepts form the basis for conceptional integrity (consistency, homogeneity) of the architecture. They are important to achieve intrinsic qualities of your system. We call them cross-cutting as sometimes concepts cannot be handled by individual building blocks, but have to be applied to, or at. several architectural elements.

#### Communicate architecture

Software architects needc to cmmmunicate with various stakeholders about certain aspects of part of the system. Argumentation. discussion and convincing people, other parts involve (written) documentation.

#### Shepherd implementation

At the end, output of developers ultimately shapes how a system built. Documenting architectural decisions (structures, concepts or other stuff) does not necessarily mean the system will be built according to that documentation. Software architects need to make sure the system is built in the appropriate way, decisions are properly implemented and architectural principles are adhered to. Shepherding the implementation is the key activity for achieving this:

* Identify those parts of the system and its implementation that violate or endanger consistency or somehow deviate from chosen architecture. Together with the development team, find appropriate ways to correct or mitigate these issues.
* Identify potential design or implementation decisions which could improve the overall architecture. (developer can came up with cleaner, simpler, smarter, cheaper, quicker, less risky , more maintainable, resource effective improvement.)

#### Evaluate Architecture

Find out if (or if not) system, its architecture, and implementation can fullfill  or satisfy its quality requirements or if any of these requirements are at risk.

In the context of software engineering, software quality refers to two related but distinct notions that exist wherever quality is defined in a business context:

* Software functional quailty  reflects how ell it complies woth or conforms to a given design, based on functinal requiremetns or specifications.

* Software structural quality refers to how it meets non-functional requirements that support delivery of the functional requirements, such as robustness or maintainability, the degre to whoch the software was produced correctly.

  Mainly the second notion that we care for in order to guarantee the first notion over an extended period of time.



### LG 1-5 Software architects and other stakeholders

**Relate the role of software architects to other stakeholders (R1)**

Software architects are able to explain their role. They should adapt their contribution to software development in a specific context and in relation other stakeholders in particular to

* product management and product owners
* project managers
* requirement engineers
* developers
* QA and testers
* Enterprise architect and architecture board members

Regardless of the specific model or process of development, software architects need to be aware of the potential multitude of different stakeholders who are relevant for a specific development.

In many cases software architects will have at least following **four different** categories(**types**) of **stakeholders**:

1) Req. eng/Domain experts/Product Management : requirement communication feasibility, using specific terminology etc.
2) Project management/Enterprise Arch. (organizational constraints, resources, schedules)
3) Sw Dev/HW Dev /IT(CI/CD) (detailed technical level)
4) QA-Security Team (quality attributes)

#### Collaboration with business and domain experts

* clarify requirements
* help identify conflicting requirements
* support finding trade-offs between conflicting goals and requirements
* explain the impact of certain requirements and constraints on other requirements, the architecture, implementation and operation of the system
* support in prioritizing requirements and their development

#### Collaboration with management stakeholders

* technical consultancy: architects are consulted  by management concerning technical issues
* risk management: architects point out explain technical risks to management
* support in staffing
* support in defining and sizing work packages or work-breakdown-structure

#### Collaboration with technical stakeholders

Within development teams, software architects shall:

* communicate and explain architecture and architectural decisions
* enable and prepare technical decisions
* coach or help ti coach team members
* moderate in the discussion and design of internal and external interfaces



### LG 1-6: Development approach and software architecture



Software architects are able to explain the influence of iterative approaches on architectural decisions.

Due to inherent uncertainty, software architects often have to work and make decisions iteratively. To do so, they have to systematically obtain feedback from other stakeholders. 

Architecture work needs feedback, which is inherent feature of iterative development approaches.

**Benefits of iterative-incremental feedback**

* early feedback

* early rosk(and problem) identification

* more time to fix problems and mitigate risks

* better chances to adapt to changes in requirements, constraints, technology, team etc.

* opportunities to practice every activity in the development process, especially deploy and release-related activities.

  **Deming-cycle**:  Plan-Do-Check-Adjust . These four steps basically from the basis of every software development process as a software architect, you should actively care for getting and giving sufficient and timely feedback (push and pull) from relevant stakeholders.

  Plan : Make architectural decisions to meet the known/given requirements

  Do : Execute the plan, implement these decisions

  Check : Get feedback and evaluate the results from Do phase

  Adjust (Act) : Improve or remove decision																	


### LG 1-7 Short- and long-term goals

Software architects can:

* explain long-term quality requirements and their differentiation from (short-term) project goals
* explain potential conflicts between short-term and long-term goals, in order to find suitable solution for all stakeholders
* Identify and specify quality requirements.



Lifespan of many software systems are much longer than the duration of typical development projects.

Let's clarify the term project and distinguish from it system.

**Project** A projects in software development or software engineering is usually a collaborative effort to achieve clearly defined goals, in most cases within limited time frame:

* several people
* the outcome (goal) of their collaboration is clearly defined
* the amount of time these people can invest is limited, as the amount of money that can be spent during the project. You can even replace project with *sprint* when your organization uses Scrum.

**System**

The application , program, software or thing a development team is working on, which is usually the outcome of one or more projects. A system may be defined as a set of components which accomplish a set of predetermined goals or fulfill predetermined requirements.

Usually lifespan of a system is longer than it took to build that system - therefore goals related to that system are often long-term goals.

'''

* Project goals are often short-term
* Architecture or system goals are often long-term
* Architectural goals usually contribute to achievement of project goals, but they can also be in conflict with each other.

'''

### LG 1-8 : Explicit statements versus implicit assumptions

Software architects:

* Should explicitly present assumptions or prerequisites, therefore avoiding implicit assumptions
* Know that implicit assumptions can lead to potential misunderstandings between stakeholders
* Formulate implicitly, if t is appropriate in the given context.

Software architects should (and can) be explicit in their decisions: Never call a decision obvious, as whilst it might be obvious to you, it might not be so obvious to others. It is better to explain(important) decisions explicitly, as this makes them easier to understand and avoids any misunderstandings,

* Explicitly documenting quality requirements , e.g. form of quality scenarios
* Explicitly documenting architecture decisions
* Using clear and unambiguous terminology, especially domain/business terminology, e.g. by using an explicit domain model or a glossary for your system
* Explicitly defining a cross-cutting concepts
* Explicitly considering different perspectives before making difficult decisions, for example quality requirements, domain structure, external interfaces, building-block structure, technical infrastructure, etc.
* Explicitly developing cross-cutting concepts to improve the -> consistency -> (conceptional integrity) of your system
* Explicitly analyzing and evaluating your system, its architecture and code in order to get feedback on your architectural work 



## Chapter 2: Design and development of software architectures

### LG 2-1 : Approaches and heuristic for architecture development

Select and use approaches and heuristic for architecture development;

Software architects are able to name, explain. and use the fundamental approaches of architecture, for example:

* Top-down and bottom-up approaches to design (*)
* View-based architecture development (*)
* Iterative and incremental design (*)
  * necessity of iterations, especially when decision-making is affected by uncertainties (*)
  * necessity of feedback on design decisions(*)
* Domain-driven design (-)
* Evolutionary design (-)
* Global analysis (-)
* Model-driven architecture (-)

There is no deterministic or algorithmic approach to software design, you should consider an iterative approach to designing your software and its architecture. These iterations exist in addition to the flow of the overall development process.

### Building blocks

Representation of a building block (black box and white box) can be immensely useful for software architecture. A single building block can be a black box in one communication, diagram or model, and a white box in others.

**Properties of black box representations**

As a black box hides internal structure, it adheres to the -> information hiding principle. Hiding internal things is an abstraction or simplification. When using the black box representation or simply the name of a building block, one does not need to consider all the internal details. This abstraction can simplify communication or documentation.

In addition, you might use a black box to delegate responsibility for the design implementation of this  building block to somebody else.

A black box hides:

* Internal structure, that means internal building blocks and internal dependencies
* Internal processing, algorithms or functions
* Internal data and data structures

A black box should have an appropriate name, and needs to expose the following in its description (black box template):

* Its responsibility: what does this black box do , what is its function or service?
* The provided interface(s): what functions, services or data does this black box provide?
* The required interface(s): what other functions, services or data does this black box require to fulfill its responsibility?

Use a bottom-up approach to:

* Reduce risks
* Build proof -of-concept implementations
* Validate decisions or proposals, providing that they can work in practice
* Build-up knowledge and experience in important areas, like new technologies, products or business domains 
* Work from detailed, specific or concrete elements up to larger, more abstract ones.

In some cases it can be useful if a black box provides some additional information about itself:

* Additional attributes, like qualities: Is this black box capable of multi-user access, what is the maximum throughput, what are guaranteed, minimal or average response times and so on.
* Known restrictions, risks or problems.

**Properties of white box representations**

As a white box is the "same thing" as its black box, it inherits all attributes of the black box, and adds the internal structure. In addition, we propose that a white box representation explains the reason why it is structured exactly in this specific way, sometimes called the **"design rationale"**

A white-box representation of a building block should contain the following information (wb template):

* Name of this white box
* Reference or link to its black box
* An overview (at best a diagram) of its internal structure, hsowing the contained black boxes plus their dependencies
* Design rationale, the reason for this structure
* A list or table of contained black boxes, each with name, responsibility and dependencies.

A fundamental concept of building-block view in software architecture is the systematic on-demand refinement of black boxes to white boxes in order to increase levels of detail. This is a simple method to explain the static structure of any software system by starting at the context level, and applying stepwise refinement. Such stepwise refinement serves two different purposes: firstly it is a communication mechanism, facilitating, understanding of low-level structures by showing these structures on context. And secondly, you may start designing and implementing your system on any abstraction level and use a combination of bottom-up and top-down approaches during development.

**Top-down approach**

Start from general, abstract or bird's eye perspective and step into details. You may use a top-down approach within a single subsystem or component - this approach is not limited to the whole system. Top down approach could be used to split the whole system into several subsystems, each of which will be developed by its own team.

Use a top-down approach to:

* Keep an overview of multiple components or subsystems
* Abstract away details that are not currently needed
* Keep things consistent over various components
* Work from abstract or large elements to specific or smaller ones.

**Bottom-up approach**

Think and work on a detailed level: Solve detailed problems, take detailed or low-level decisions. Later encapsulate (abstract away) these details, hiding them in higher-level abstractions, building blocks or components.

Use a bottom-up approach to:

* Reduce risks
* Build proof-of-concept implementations
* Validate decisions or proposals, proving that they can work in practice
* Build-up knowledge and experience in important areas, like new technologies, products or business domains
* Work from detailed, specific or concrete elements up to larger, more abstract ones.

Top-down and bottom-up approaches complement each other nicely.

**View-based architecture**

View focus on specific concerns, parts or aspects of a system. They can be used to consider certain things in isolation, thereby applying the "separation of concerns" principle to architecture work.

* Building block view (static structure) - component diagrams
* Runtime view (interactions)   - state diagrams
* Deployment view ()
* context view (external interfaces) - use case diagrams (user diagrams)

Use architecture views to:

* Facilitate structural, runtime or hardware decisions, as these concerns can be discussed separately
* Facilitate communication and documentation
* Gain flexibility in the degree of detail shown in various views
* Address specific stakeholder concerns (e.g. operational aspects are covered in the deployment view)

**Recognize interdependencies and trade-offs between design decisions**

Many decisions will have consequences that are hidden or indirect, but they might be grave.

In software architecture and system development you should be aware of it and consider its consequences.

* Great runtime performance (good) often created by caching, parallel execution, sophisticated pre-loading strategies and such, quite often increases code side and complexity(bad).

  

### LG 2-4: Cross-cutting concepts

Software architects are able to:

* Explain significance of such cross-cutting concepts
* Decide on and design cross-cutting concepts, for example persistance, communication, GUI, error handliing, concurrency, energy efficiency
* Identify and asses potential interdependencies between decisions
* Know that how such cross-cutting concepts may be re-used throughout the system

Some architectural decisions will concern or affect topics relevant for multiple or all elements within the architecture. A typical (low-level) example is logging, another example are security related topics.

Such concepts include overreaching or cross-cutting issues, which often affect several building blocks of the system. These concepts can have a significant impact on building block structures or their omplmenetation. They often represent central technical decisions.

Cross- cutting concepts can be used to solve recurring problems (aka cross-cutting concerns) that have to be addressed within ,multiple elements of the architecture.

Some examples of such cross-cutting concerns are:

* Fundamental technology decisions relevant throughout the system or within several building blocks
* Selection of frameworks or third party tools/libraries
* Usage of such technologies within the system, or specific purposes
* Conventions for interfaces between building blocks

**Significance of cross-cutting concepts**

Cross-cutting decisions can help to ensure *consistency*: Topics governed by cross-cutting concerns will (most likely) be implemented in the same manner, based upon the same technology, using the same patterns or conventions.

Such consistency facilitates understanding and makes the corresponding parts or elements of the system similar in these specific aspects.

Often such concepts are used for knowledge-transfer between people and/or systems. A concept that has helped solve a specific problem in one system might be re-used in another system.

**Risks involved in cross-cutting concepts**

Similar to every standardization effort: If the standard is bad, systems using the standard will (likely) also be bad. If your cross-cutting concepts do not solve the underlying problems, then all components using or implementing those concepts will have issues.



