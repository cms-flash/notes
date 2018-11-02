# Introduction to Software Engineering

# Introduction

- Software engineering is the process of solving customers’ problems by the systematic development and evolution of large, high-quality software systems within time, budget and other constraints and in the context of constant change.

- Software engineering aims at addressing the problem of developing and maintaining software that is:

  - Large and complex;

  - Team-worked;

  - Multi-versioned;

  - Long-lived;

  - Routinely updated.

- Software engineering takes a systematic, well-understood, and repeatable approach to produce high-quality software systems.

- Software engineering is applicable to small, medium, and large-scale systems, and to every domain of software systems.

- Main obstacles to production of high-quality software:

  - Complexity:

  - in the system;

  - in the problem;

  - in development;

  - Change:

  - during development;

  - after delivery.

# Software Process

- Software process refers to a set of activities and the way those activities are structured to produce software. 

- Classification:

  - Predictive models:

    - Waterfall;

    - Waterfall with feedbacks;

    - Sashimi waterfall.

  - Adaptive models:

    - Unified process;

    - Rapid prototyping;

    - Scrum.

- The waterfall model:

  - Requirements engineering, which delivers a requirements specification;

  - Design, which delivers a design specification;

  - Implementation, which delivers code;

  - Testing, which delivers test reports;

  - Deployment, which delivers an installed system;

  - Operation and maintenance.

- In the waterfall model, a phase can only be started after its preceding phase terminates.

- In the rigid form of waterfall, a phase cannot be reentered once declared complete.

- In the loose form, succeeding phases can provide feedback to previous phases, and trigger rework. However, the complexity and high cost lead to the common practice of setting up a limited time window before freezing a phase.

- Major problems with waterfall:

  - It can lead to badly structured system due to workarounds caused by prematurely frozen designs.

  - It is inflexible and does not easily accommodate change.

  - It lacks customer involvement. Customer do not see the progress after requirements engineering until deployment, which leads to late discovery of mis-captured requirements and expensive fixes.

# Requirements Engineering

- Requirements engineering is the most important and most difficult part in software process. Mistakes at this stage are disastrous if not discovered early.

- Levels of requirements:

  - Business requirements:

    - These requirements capture the high-level business goals of the organization, why they need the system, and what part of the problem the system addresses.

    - These are stored in the vision and scope document.

  - User requirements:

    - These requirements capture what the user should be able to do with the system, to satisfy business requirements.

    - These are stored in the user requirements document.

  - Functional and non-functional requirements:

    - These describes what should be delivered to satisfy user requirements.

    - These are stored in the software requirements specification.

- Functional and non-functional requirements:

  - Functional requirements:

    - Functional requirements describe the interaction between the system and the environment, what services it provides, how it responds to certain inputs, and how it behaves under certain circumstances.

    - In modern developments, these are stored in use cases.

  - Non-functional requirements:

    - Non-functional requirements describe constraints on the functions, e.g. quality, technology, standards etc.

    - Accompanying use cases, these requirements are stored in the supplementary specification.

# The Use Case Model

- The use case model captures functional requirements in the form of a set of stories describing users using the system to get value.

- The use case model is a user-centric approach to capture requirements. It preserves the visibility of the overall goal of the software system.

- Components of a use case model:

  - The software system;

  - Actors:

    - Primary actors;

    - Supporting actors;

  - Use cases.

- Construction of a use case model:

  - Define the system boundary;

  - Identify primary actors;

  - Identify goals of primary actors;

  - Collect the goals and translate them into use cases;

  - Step 1 to 3 are done simultaneously and iteratively.

- Use case:

  - A use case is a story of an actor successfully using the system to achieve his/her goal.

  - Qualification of a use case:

    - The elementary business process principle:
      - An elementary business process is a task conducted by one person in one place at one time which generates certain value and produces information in a consistent fashion.

  - A use case usually consists of 5 to 10 steps.

- Formality of use case:

  - Brief;

  - Casual;

  - Fully-detailed.

- Formality of step in use case:

  - Essential;

  - Concrete.

- Components of a use case in fully-detailed form:

  - The start and the end of the use case, which may include triggers, pre- and post-conditions, actors/interest lists, etc.

  - The main success scenario;

  - Extensions, which may be divided into alternative flows and exceptions.

- Preconditions and postconditions:

  - Preconditions:

    - A precondition of a use case is an assumption and requirement of the world state when the use case is triggered.

    - Checking of preconditions should be done by the system outside of, not within, the use case.

    - A precondition associated with a use case should be specific to that use case.

  - Postconditions:

    - A postcondition of a use case is a promise of the world state after successful completion of it.

    - It describes a delivered value or achieved goal of users or other stakeholders.

- In contemporary development, use cases drive development.

# Supplementary Specifications

- Supplementary specifications are specifications for non-functional requirements, system-wide functional requirements, and any other requirements that need to be grouped together to be seen.

- They are of no lower priority than use cases, and often higher, since non-functional requirements often have a strong influence on architectural choices.

- Quality attributes constitute a large part of non-functional requirements. FURPS+ is a classic model of quality attributes, categorizing them into functionality, usability, reliability, performance, supportability and others.

- Quality attributes expressed in vague words are not verifiable, and hence are of little value as requirements. They must be quantified, or treated as guidelines instead of requirements.

- Different requirements might be in conflict, which requires us to guide stakeholders to prioritize different requirements.

# Vision and Scope

- The vision statement describes, in most compact form, what the product is, what business objectives it serves, and how it differentiates from competition.

- The scope defines what the product is and what it is not, what is inside it and what is outside of it.

- A common template for the vision statement: For <> who <>, the <> is <> that <>. Unlike <>, it <>.

- Vision and scope is short but extremely important. Despite an iterative approach, it is still of great interest to make it right at the beginning and minimize change thereafter.

- By building the document, appropriate knowledge of the domain for the developer is developed.

# Risk-Driven Development

- A risk is a probabilistic event that have negative impact on the project.

- Characteristics of a risk:

  - Uncertainty;

  - Impact;

  - Exposure, which is the product of the two above.

- Risk mitigation strategies:

  - Avoidance;

  - Reduction;

  - Transfer;

  - Acceptance.

- We maintain a risk list recording all identified risks faced by the project, and sort them by their exposure.

- In development, we concentrate on technical risks that can drive development. Business risks are handled by managers. Requirements-related risks are captured by use cases.

- Risk-driven development leads us to an iterative and incremental approach.

- Each iteration is risk-driven and use case-driven. It addresses the greatest remaining risk, which is identified with one or more use cases.

# Unified Process

- The unified process is an iterative and incremental approach of software development. It is central and fundamental to various other iterative software processes.

- The unified process consists of four stages, each with a distinct goal to fulfill, risks to address, products to deliver, and a test to pass. Each test is a go/no-go gate, the next stage cannot be started without passing the corresponding test.

- Stages in the unified process:

  - Inception:

    - In the inception stage, feasibility iterations are conducted to learn what to build.

    - In this stage, the vision, high-level requirements and business cases are established.

    - Inception addresses business risks.

    - Inception delivers software prototypes.

    - The results of inception are tested against the life cycle objectives gate.

  - Elaboration:

    - In the elaboration stage, architecture iterations are conducted to learn how to build the system.

    - In this stage, the baseline architecture is verified and most requirements get detailed.

    - Elaboration addresses architectural and technical risks.

    - Elaboration delivers software architectures.

    - The results of the elaboration stage are tested against the life cycle architecture gate.

  - Construction:

    - In the construction phase, usable iterations are conducted to build the system.

    - In this stage, a working product is produced, the system test is completed.

    - Construction addresses logistical risks.

    - Construction delivers test releases.

    - The results of the construction phase are tested against the initial operational capacity gate.

  - Transition:

    - In the transition phase, product release iterations are conducted to tweak the system per user feedbacks.

    - In this stage, stakeholder acceptance is conducted.

    - The transition phase addresses delivery and roll-out risks.

    - The transition phase delivers the final release.

    - The results of the transition phase are tested against stakeholder acceptance.

- Project planning:

  - Project plan;

  - Phase plan;

  - Iteration plan.

- Project plan:

  - For a typical, medium-scale, first-version, low-risk project without a pre-existing architecture, an estimate of the time and effort distribution is as follows:
    - Inception: 10% time, 5% effort;

    - Elaboration: 30% time, 20% effort;

    - Construction: 50% time, 65% effort;

    - Transition: 10% time, 10% effort.

- Typical durations of the unified process:

  - Duration of an iteration:

    - An iteration lasts 1-6 weeks, usually 2-4, depending on the size of the team.

  - Duration of phases:

    - Inception:

      - Inception can last 0 iteration for maintenance projects.

      - It takes 1-2 iterations for full new projects, delivering exploratory prototypes which implement core functionalities and user interfaces.

    - Elaboration:

      - Elaboration lasts 1 iteration at least, when there is an established framework in place. An architectural baseline where key components are attached is delivered.

      - It takes 2 iterations in the absence of an established framework. The first iteration delivers an architectural prototype and the second delivers an architectural baseline.

      - It may take 3 iterations for highly risky or novel projects, with the first two iterations delivering architectural prototypes, allowing some trials-and-errors.

    - Construction:

      - Construction generally takes 2 iterations, delivering an alpha release and a beta release respectively.

      - It can take 3 iterations for projects with a large amount of routine work, delivering 2 alpha releases and a beta one.

    - Transition:

      - Transition generally takes 1 iteration, delivering a modified version of the beta release as the final product.

      - It may take 2 iterations when it is necessary to take in more user feedbacks, resulting in the delivery of an additional beta release followed by the final one.

- Methods of requirement elicitation:

  - Interview;

  - Workshop;

  - Observation;

  - Questionnaires;

  - Prototyping.

- Prototyping:

  - Horizontal prototyping:

    - Horizontal throwaway prototyping;

    - Horizontal evolutionary prototyping;

  - Vertical prototyping:

    - Vertical throwaway prototyping;

    - Vertical evolutionary prototyping.

  - Key points:

    - Quick and fast.

    - The type of prototyping must be decided before starting.

# Unified Modelling Language

- Object-oriented analysis and design are conducted in the Unified Modelling Language.

- UML diagrams and system models:

  - Class diagrams capture the static structure of the system.

  - Sequence diagrams capture the dynamic interaction within and at the boundary of the system.

  - State machine diagram is optionally included to describe life cycles of objects.

- Sequence diagram:

  - A sequence diagram visualizes interactions between objects modelled by messaging.

  - Constituents of a sequence diagram:

    - Object:

      - Classes and instances:

        - Class: `A`;

        - Anonymous instance: `:A`;

        - Named instance: `a:A`.

      - Life line;

      - Execution specification bar;

    - Messages:

      - Formal grammar of a message:

        - $m(a:A,b:B,...):M$.

      - Synchronous message;

      - Returning;

      - Asynchronous message;

      - Constructor.

- Class diagram:

  - Class:

    - Name:

      - Name for a concrete class;

      - Name for an abstract class;

    - Attributes:

      - Primary attributes;

      - Derived attributes.

    - Operations;

    - Accessibilities:

      - Private;

      - Protected;

      - Public.

  - Relations:

    - Association:

      - End classes;

      - End names;

      - Association name;

      - Association direction indicator;

        Multiplicities;

    - Composition:

      - Component class;

      - Compositor class;

      - Component name;

      - Multiplicity for component;

    - Interfacing:

      - Interface provider;

      - Interface user.

# Analysis

- Analysis is the process of modelling the problem to solve.

- Analysis is the basis for design.

- System sequence diagram:

  - System sequence diagram is sequence diagram used in object-oriented analysis.

  - A system sequence diagram represents cross-boundary interactions of a use case.

  - System sequence diagrams are usually used to visualize system-actor interaction for main success scenarios of crucial and complicated use cases and their frequent extensions.

- Domain model:

  - The domain model models conceptual classes and their associations and attributes, using a class diagram.

  - The domain model models only concepts relevant to the problem the system solves.

  - In iterative development, a domain model modelling only concepts relevant to the use cases addressed in the current and previous iterations and a few other concepts that are crucial to an understanding of the problem domain is used.

  - The domain model, as the object-oriented tool for analysis of the static structure of the problem domain, greatly improve the continuity of structure from the problem space to the software.

  - It is critical to strike a balance between the use of attributes and one-to-one associated classes.

# Design

- Requirements engineering and analysis defines and investigates the problem to solve, design is where we start to build the solution to it.

- In the design phase, the main goal is to create a system design with high maintainability, including:

  - Modularity;

  - Reusability;

  - Analyzability;

  - Modifiability;

  - Testability.

- Responsibility-driven design:

  - Responsibility-driven design views design as a process of allocating different responsibilities to different classes and their instances.

  - Types of responsibilities:

    - Knowledge;

    - Behavior.

  - Design by contract is a design philosophy to base the design on a fully-detailed set of pre- and post-conditions. Although usually not explicitly documented in practice, the philosophy born in mind helps produce high quality code.

- Generic design principles:

  - Abstraction;

  - Encapsulation;

  - Cohesion;

  - Decoupling.

- General responsibility assignment software patterns (GRASP):

  - Information expert; 

  - Creator;

  - Controller:

    - Facade controller;

    - Use case controller.

- The SOLID design principles:

  - Single responsibility principle;

  - Open and closed principle;

  - Liskov substitution principle;

  - Interface segregation principle;

  - Dependency inversion principle.

# Software Architecture

- Software architecture is the topmost level of software design.

- We have logical architectures and physical architectures.

- Common architectural styles:

  - Monolithic;

  - Multi-layer;

  - Component-based;

  - Rule-based;

  - Data-centric;

  - Distributed.

- Layered architecture:

  - Layered architecture separates concerns of various levels.

  - Higher layers depend on lower layers, not conversely.

  - Strict and loose layering:

    - Strict layering;

    - Relaxed layering.

  - Four canonical layers:

    - Presentation;

    - Application;

    - Business;

    - Infrastructure.

  - Layered architecture improves cohesion, decoupling, modifiability, portability and testability.

  - Layered architecture can be improved by dependency inversion.

# Design Patterns

- A design pattern is the core of a canonical solution to a commonly recurring problem in software design.

- Constituents of a design pattern:

  - Name;

  - Problem;

  - Solution;

  - Consequences.

- Classical design patterns:

  - Observer (listener);

  - Strategy, etc.

- Model-view-controller and its variants:

  - Model-view-controller;

  - Model-view-presenter;

  - Model-view-controller-service;

  - Model-template-view.

# Beyond Iterative Development

- Iterative and incremental development reduces risk and improves agility from waterfall by performing multiple integrations each at the end of an iteration, instead of a single integration at the end of development.

- By further extending the occasion of integration to the end of development of any small cohesive changes, we have a more agile development process called continuous integration.

- By further extending the occasion of quality assurance testing to follow each commitment of change, we have an even more agile process named continuous delivery.

- Ultimately, by extending deployment to the end of the quality assurance testing for each commitment, we have continuous deployment.

- This leads to a merger of the development, quality assurance and operation team, as in modern development processes like DevOps.

- In continuous deployment, the bottleneck is the deployment of a huge monolithic software.

- To tackle that, the microservices architecture divides the software and hence the team by not horizontal layers but vertical functionalities, making each component a cohesive end-to-end service that serves users and/or other microservices.

- Each team is cross-functional and is responsible for one or more microservices, usually consisting of no more than 9 members as in Scrum.

- All the layers, including the domain model, is distributed across microservices.

- Microservices are completely independent of each other except for their public interfaces, usually in the form of REST HTTP requests.

- A tradeoff between layering and microservice architecture, in each specific context, leads to one of or a combination of the two architectures.

- In the hexagonal architecture, the core logic is protected by a shell exposing limited ports where adapters can be plugged into to communicate with different actors.

# Testing

- Black box testing is the fundamental approach of modern software testing.

- Phases of testing:

  - Unit test;

  - Integration test;

  - System test;

  - Acceptance test.

- Inputs believed to be tracing through the same execution path are collected as an equivalence class.

- For multidimensional input space, each valid equivalence class need to be covered by at least 1 test case, while each invalid equivalence class need to be covered individually.

- Since boundary points are vulnerable to defects, boundary point analysis uses boundary points as representative for equivalent classes.
