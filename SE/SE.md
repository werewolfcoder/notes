
# SDLC
	1. Requirment analysis
			Communication with user
			 Risk identification
			 Senior members
			 Ambiguity problem
	2. Defining requirement
			 make SRS
			 Aprroval from customer
	3. Design
			 Product Desgin
			 Design Document
	4. Devlopment
			 Code writing
			 use compiler interpreter debugger
	5. Testing
			 detect report track fix and retest
			 repeat untill matches SRS
	6. Deployment
			 Release
			 Maintain


![[Pasted image 20251118093909.png]]
# Software Process models
	1. Waterfall model
	2. Spiral Model
	3. Incremental Model
	4. Agile Model
	5. Prototyping Model
	6. Rapid App Dev(RAD) mode

# Waterfall Model

![[Pasted image 20251102162348.png]]

## Advantages of Waterfall model:

- Simple and easy to understand.
    
- Clear, structured phases.
    
- Easy to manage and track progress.
    
- Well-defined goals from the start.
    
- Effective for fixed requirements.
    
- Facilitates clear documentation and communication.
    

## Disadvantages of Waterfall model:

- Inflexible to changes.
    
- No working software until late.
    
- Late discovery of defects.
    
- Limited stakeholder involvement after early phases.
    
- Not suitable for complex or evolving projects.
    
- Overlapping phases not allowed, causing delays.

# Spiral Model


![[Pasted image 20251102162420.png]]

## Advantages of Spiral Model:

- Early software production.
    
- Excellent risk management at every phase.
    
- Flexible to requirement changes.
    
- Suitable for large, complex projects.
    
- High customer involvement.
    
- Strong documentation and approval control.
    
- Scalable and adaptable to project size.
    

## Disadvantages of Spiral Model:

- Can be costly to implement.
    
- Requires specialized risk analysis expertise.
    
- Success highly dependent on risk management.
    
- Not suitable for small, low-risk projects.
    
- Complex to manage and document.
    
- Development timeline can be unpredictable.


# RAD model

The **Rapid Application Development (RAD)** model is an **incremental** software process model that emphasizes an extremely short development cycle.

It is a "high-speed" adaptation of the linear sequential model. Ideally, the RAD approach allows a development team to create a "fully functional system" within a very short time period (e.g., **60 to 90 days**).

**Key Concept:** instead of building the whole software at once, RAD breaks the project into modules and builds them **in parallel** using reusable components and automated tools.
![[Pasted image 20251118201607.png]]

### ✅ Advantages (Merits) of RAD

- **Speed:** Drastically reduces the development time (speedy delivery).
    
- **Reusability:** Encourages the reuse of existing program components, which saves money and effort.
    
- **Customer Feedback:** Since it relies on prototyping and short cycles, the customer can see the product early and give feedback, leading to higher satisfaction.
    
- **Reduced Risk:** Because modules are developed in increments, major issues can be spotted and fixed early.
    
- **Integration:** Integration is done from the very beginning (as modules are combined), so there are fewer "surprise" integration issues at the end.
    

### ❌ Disadvantages (Demerits) of RAD

- **Requires Strong Commitment:** For large but scalable projects, RAD requires sufficient human resources (developers and customers) to create the right number of teams. If developers or customers are not committed to the rapid "fire-drill" schedule, the project will fail.
    
- **Requires Modular System:** Not all types of applications are appropriate for RAD. If a system cannot be properly modularized (broken into pieces), building the components necessary for RAD will be problematic.
    
- **High Cost:** It requires expensive automated tools (CASE tools) and highly skilled, expensive developers.
    
- **Technical Risk:** It is not suitable for projects with high technical risks (e.g., using a completely new technology that the team doesn't know).




# Incremental Model

![[Pasted image 20251102163627.png]]

A=Communication
D=Planning
C= Modeling
T= Devlopment/Construction
M = Deployment

## Advantages of Incremental Model:

- Delivers working software early and quickly.
    
- Flexible and easier to change requirements.
    
- Easier to test and debug smaller increments.
    
- Customer can give feedback on each increment.
    
- Low initial delivery cost.
    
- Better risk management through iterative releases.
    
- Manages workload by dividing the project into smaller parts.
    

## Disadvantages of Incremental Model:

- Requires good planning and clear system definition.
    
- Total cost can be higher than Waterfall.
    
- Problems in one module may affect others, causing delays.
    
- Each phase is rigid, with no overlap.
    
- System architecture may suffer if requirements are incomplete upfront.



# Agile Model

Agile model is an iterative and incremental software development approach focused on flexibility, customer collaboration, and rapid delivery of working software in small, manageable increments called iterations or sprints.

It emphasizes adapting to change, continuous feedback, and delivering functional software frequently to meet evolving user needs

Agile promotes teamwork, communication, and responsiveness to change over rigid processes and documentation, making it suitable for complex projects with uncertain or changing requirements.

## Xtreme Programming

Extreme Programming (XP) is an Agile software development methodology focused on improving software quality and responsiveness to changing customer requirements.

It emphasizes short, iterative development cycles, frequent releases, and close collaboration between developers and customers.

Key practices include pair programming (two developers working together), test-driven development (writing tests before code), continuous integration, and regular customer feedback. 

XP promotes simplicity, communication, and rapid adaptation to change, making it well-suited for small to medium-sized teams dealing with dynamic requirements

## XP values

1. Communication: Continuous, clear communication among team members and customers is crucial for shared understanding and project success.
    
2. Simplicity: Focus on doing the simplest thing that works to reduce complexity and avoid unnecessary work.
    
3. Feedback: Frequent feedback from testing and customers helps identify problems early and improve the product continuously.
    
4. Courage: Team members are encouraged to speak up, take risks, accept change, and improve without fear.
    
5. Respect: Every team member's contributions and opinions are valued, fostering a supportive and collaborative environment.


## XP Process

	1. Planning
			Customer ke sath baith ke suna jata hai 
			 SRS banaya jata hai 
			 cutomer stories likhta hai based on requirements
			 stories ko priority assign karta hai 
			 fir senior devs stories ko cost assign karte hain
			 cost in terms of dev weeks
			 project velocity calculate ki jati hai 
			 project velocity is number of stories implemented in a week
			 project velocity project estimation me help karti hai 

     2.Design
		     KIS(keep it simple) approach is followed for design
			 when a complex problem or design situation is faced thne instead of                 imeplementing that complex problem we design a 'SPIKE SOLUTIO'n 
			 Spike solution is a basic simple working prototype
			 Thhe Product is refactored frequently 
			 refactoring is a process of optimizing the product without changing it              core functions

	 3.Coding  4. Testing
			 first unit tests are developed based on cutomer stories
			 then  coding starts in such a way thet it passes the unit tests
			 pair programming is done , where 2 coders do the code 
			 one writes it and one verifies it at the same time
			 then rapid integration is done to avoid inteface errors and conflicts
			 then code is tested by unit tests
			 then it is tested against XP acceptance test specified by cutomer and               derived from user stories



# Scrum model

![[Pasted image 20251102182342.png]]


Product owner gives the product backlog 
Product backlog is a list features or requirements needed in the product 
Then a sprint planning is done by all the stakeholders like owner scrum master scrum team members
Sprint is time duration of 1-4 weeks to implement specific features
Scrum master is a team leader of scrum team
In Sprint planning a sprint backlog is decided 
Sprint backlog is list of selective features to be implemented during the sprint
Then  Sprint starts
In each day of a Sprint a daily scrum meeting of around 15 minutes is done to discuss what we done yesterday and we are gonna do today
After Sprint Completion a Sprint review is done by all the stakeholders to check if we met the sprint backlog or not
After that a Sprint retrospective is done to discuss where we fell behind what could be improved , all the postives , negatives , what we done well , weakness, streangth , things to be improved in next sprint
And all this is repeated untill the final project is ready

### Merits (Advantages) of Scrum

1. **High Adaptability:** Scrum is designed to handle change. If the customer changes their mind or market trends shift, the team can pivot quickly at the start of the next Sprint (usually every 2-4 weeks) rather than waiting for the end of a long project.
    
2. **Transparency and Visibility:** With daily stand-up meetings and the use of artifacts like the **Sprint Backlog** and **Burndown Charts**, everyone (including management and the client) knows exactly what is going on, what is stuck, and how fast the team is moving.
    
3. **Early and Frequent Delivery:** Scrum delivers a "potentially shippable product increment" at the end of every Sprint. This means the customer gets working software early and can start getting value from it immediately.
    
4. **Improved Quality:** Testing happens continuously throughout the Sprint, not just at the end. Because features are built in small chunks, bugs are found and fixed immediately.
    
5. **Higher Customer Satisfaction:** The customer is highly involved (through the **Product Owner**) and gives feedback after every Sprint Review. This ensures the team builds exactly what the customer needs, not just what was written in a document months ago.
    

### ❌ Demerits (Disadvantages) of Scrum

1. **Scope Creep:** Because there is no fixed finish date and requirements can change, there is a danger that the project continues indefinitely with new features constantly being added ("scope creep") if not strictly managed by the Product Owner.
    
2. **Requires Experienced Team:** Scrum relies on a **self-organizing team**. It works poorly with inexperienced or junior developers who need constant direction and supervision. If the team isn't disciplined, the process falls apart.
    
3. **Difficult to Scale:** Scrum works best for small teams (typically 3 to 9 people). Implementing it for large projects with hundreds of developers (requiring "Scrum of Scrums") is complex and difficult to coordinate.
    
4. **Documentation Can Be Neglected:** Since the Agile manifesto values "working software over comprehensive documentation," Scrum teams sometimes fail to create necessary documentation (like user manuals or architectural docs), which hurts maintainability later.
    
5. **Meeting Overhead:** While communication is good, the rigorous schedule of Daily Standups, Sprint Planning, Sprint Reviews, and Sprint Retrospectives can sometimes feel like too many meetings, eating into actual coding time.
# SE a layered approach

![[Pasted image 20251103221044.png]]


QUALITY FOCUS:
	correctness
	 Maintainability
	 Usability
	 Base of any product

Process:
		what  to do ?
		 Deals with task action activity
		 raises how to questions

Method:
		answer how to ?
		 communication
		 using programming tools
		 testing suport

Tools:
		Environment
		 helping hand of process



# Risk
 **Different Types of Risks in Software Projects:**

- **Technical Risks:** Issues with technology, tools, integration, or unproven platforms (e.g., development complexity, software defects).
    
- **Project Management Risks:** Poor planning, estimation errors, scope creep, or inadequate resources (e.g., missed deadlines, budget overruns).
    
- **Organizational Risks:** Changes in organizational structure, lack of stakeholder support, or unclear requirements.
    
- **External Risks:** Market changes, regulatory updates, supplier delays, or changes in customer requirements.
    
- **Human Resource Risks:** Team skill gaps, key personnel turnover, or inadequate training.


# COCOMO Model

	Constructive cost model 
		it is a software project estimation model . measures cost and efforts                needed for a project.

Primary factors that decide the size of the project are line of code and function points

Types of projects
	Organic: small simple less innovative
	 semi detatched: medium sized , medium complexity , medium innovation
	 Embedded: large scale very complex and innovative projects

Types of COCOMO:

	BASIC
	 Intermediate
	 Advanced

	project estimation is done on the units of Person per month and line of code

effort = a1(KLOC)^a2
Time = b1(efforts)^b2



# Measure:
quantitative indication of the amount dimension or size of the atribute of a product

# Metrics:
values that shows how much of a perticular quality a system has

# Indicators:
Combination of metrics that help understand how well a project is doing overall

# Direct Metrics:
Quality that can be measured directly like line of code speed

# Indirect Metrics:
Qualtiy that cannot be measured directly like how reliable something is 

# Faults:
are mistakes or problems in a software

# Errors:
faults found by devs while building

# Defects:
faults found by users after release


# Software Metrics:

1. Process Metrics

- **Definition:** Quantitative measures used to assess and improve the _software development process itself_.
- **Purpose:** Identify bottlenecks, improve efficiency, and ensure continuous improvement.
- **Examples:**

- Defect removal efficiency (percentage of defects found before release)
- Effort spent in each phase (requirements, design, coding, testing)
- Cycle time (time taken to move from one stage to another)
- Productivity rates (e.g., function points per person-month)

👉 Think of process metrics as the "health check" of the _workflow_.

🔹 2. Project Metrics

- **Definition:** Measures that help in _managing and controlling a specific software project_.
- **Purpose:** Track progress, estimate resources, and manage risks.
- **Examples:**

- Cost and schedule variance (planned vs. actual)
- Number of open vs. closed issues
- Team workload distribution
- Milestone completion rate
- Risk assessment indicators

👉 Project metrics are like the _dashboard gauges_ for a project manager—showing whether the project is on track.

🔹 3. Product Metrics

- **Definition:** Measures that evaluate the _software product itself_—its quality, performance, and maintainability.
- **Purpose:** Ensure the delivered software meets user expectations and quality standards.
- **Examples:**

- Lines of Code (LOC)
- Cyclomatic complexity (measures code complexity)
- Reliability (mean time between failures)
- Maintainability index
- Usability scores or response time










# Software Measurement

![[Pasted image 20251112194446.png]]
![[Pasted image 20251112194504.png]]



# Verfication and Validation 

## 📝 Definitions

- **Verification:** The process of evaluating products of a development phase to determine whether they meet the specified requirements for that phase.
    
    - **Mantra:** "Are we **building the product right**?"
        
    - **Focus:** Checking that the software aligns with its design specifications, requirements, and standards.
        
- **Validation:** The process of evaluating the software at the end of the development process to determine whether the software meets the customer's expectations and requirements.
    
    - **Mantra:** "Are we **building the right product**?"
        
    - **Focus:** Checking that the final product satisfies the actual user needs in its intended operational environment.


|**Aspect**|**Verification**|**Validation**|
|---|---|---|
|**Primary Question**|Are we building the product right?|Are we building the right product?|
|**Focus**|Design, specifications, and internal consistency.|User needs, expectations, and intended use.|
|**Activity Type**|Static Testing (does not require code execution)|Dynamic Testing (requires code execution)|
|**Timing in SDLC**|Throughout the development lifecycle (early and continuous).|Typically after a module or the entire system is built (end of development).|
|**Methods**|Reviews, inspections, walkthroughs, static analysis, desk-checking, unit tests.|Functional testing, system testing, usability testing, User Acceptance Testing (**UAT**).|
|**Goal**|Detect defects and discrepancies early.|Ensure the final product is fit for purpose.|


# function and non functional requirements

| **Aspect**           | **Functional Requirements (FRs)**                                          | **Non-Functional Requirements (NFRs)**                                                         |
| -------------------- | -------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| **Primary Question** | **What** must the system **do**?                                           | **How** must the system **be** (its quality)?                                                  |
| **Focus**            | Specific system features, behaviors, and functions (e.g., business rules). | Quality attributes, constraints, and operational characteristics (e.g., speed, security).      |
| **Mandatory**        | Generally **compulsory** for the system to fulfill its purpose.            | Often **critical** for user satisfaction and system viability, influencing architecture.       |
| **Capture Method**   | Use Cases, User Stories, Data Flow Diagrams.                               | Quality attribute specifications, design constraints.                                          |
| **Testing Type**     | Functional Testing (Unit, Integration, System, UAT).                       | Non-Functional Testing (Performance, Security, Usability, Load).                               |
| **Failure Impact**   | System does not meet core **business needs** or perform the required task. | System performs the task, but is **unusable** (too slow, crashes, insecure).                   |
| **Examples**         | Login with username/password, generate a monthly report, add item to cart. | Response time $< 3$ seconds, must support 1,000 concurrent users, must use AES-256 encryption. |

# Requirement Engineering

### 📋 What is Requirements Engineering?

**Requirements Engineering (RE)** is the systematic process of defining, documenting, and maintaining the requirements for a software system. It acts as the critical bridge between the customer's needs and the design and construction activities carried out by the development team.

The process is generally broken down into seven major tasks:

---

### 1. Inception

This is the starting point of the project. The primary goal is to establish a basic understanding of the problem and the scope of the solution.

- **What it is:** The initial "ask" or "idea" phase.
    
- **Key Activities:**
    
    - **Identify Stakeholders:** Who is this for? (e.g., users, customers, business managers).
        
    - **Understand the Problem:** What problem needs to be solved? Why is this system needed?.
        
    - **Assess Feasibility:** Is the project technically possible, economically beneficial, and operationally viable?.
        
    - **Define Scope:** Establishing a rough boundary for the project to prevent "scope creep" later.
        

---

### 2. Elicitation

This is the task of gathering or "drawing out" the requirements from all stakeholders. This is often the most difficult task because stakeholders may not know exactly what they want, may have conflicting needs, or may have trouble communicating their needs.

- **What it is:** The "information gathering" phase.
    
- **Common Techniques:**
    
    - **Interviews:** One-on-one discussions with stakeholders.
        
    - **Workshops/Brainstorming:** Group sessions to generate ideas and requirements collaboratively.
        
    - **Surveys/Questionnaires:** Used to gather information from a large group of users.
        
    - **Use Cases & Scenarios:** Describing how a user will interact with the system to achieve a specific goal.
        
    - **Document Analysis:** Studying existing business documents or older systems.
        

---

### 3. Elaboration

Once requirements are gathered, they are often unclear, incomplete, or jumbled. The elaboration task involves analyzing, expanding, and refining these requirements to build a more detailed technical model.

- **What it is:** The "analysis and modeling" phase.
    
- **Key Activities:**
    
    - Analyzing the information to understand the system's functions, features, and constraints.
        
    - Creating models (like data models, class-oriented models, or scenario-based models) to represent the requirements visually and technically.
        
    - Categorizing requirements into **functional** (what the system _does_) and **non-functional** (how the system _is_).
        

---

### 4. Negotiation

It's rare for a project to have unlimited time and money. Furthermore, different stakeholders often have conflicting desires (e.g., Marketing wants many features, while Management wants a low budget).

- **What it is:** The "trade-off and prioritization" phase.
    
- **Key Activities:**
    
    - **Identifying Conflicts:** Finding requirements that clash with each other.
        
    - **Prioritizing Requirements:** Asking stakeholders to rank what is a "must-have" vs. a "nice-to-have".
        
    - **Assessing Risk & Cost:** Discussing the risks, cost, and time associated with specific requirements.
        
    - **Finding a 'Win-Win':** Negotiating a realistic set of requirements that all parties can agree upon.
        

---

### 5. Specification

This is the task of formally documenting the agreed-upon requirements. This is one of the most common exam questions you identified (e.g., "Write SRS for...").

- **What it is:** The "documentation" phase.
    
- **Key Output:** The **Software Requirements Specification (SRS)** document.
    
- **Format:** The SRS can be a written document, a set of graphical models, a collection of use cases, or even a prototype.
    
- **Goal:** To create a clear, unambiguous, complete, and consistent record that developers can use to build the system and testers can use to create test cases.
    

---

### 6. Validation

Before committing to design and code, the SRS document must be checked for quality. Validation answers the question: "Are we building the _right_ product?".

- **What it is:** The "quality check" phase.
    
- **Key Activities:**
    
    - **Formal Technical Reviews (FTRs):** This is the primary validation technique, also a common exam topic. A team of stakeholders (engineers, customers, users) reviews the SRS to find errors, ambiguities, omissions, or conflicts.
        
    - **Prototyping:** Showing a mock-up or early version to users to get feedback.
        

---

### 7. Requirements Management

Requirements are not static; they change throughout the project. Requirements Management is the ongoing process of managing these changes.

- **What it is:** The "change control" phase.
    
- **Key Activities:**
    
    - **Change Control:** Implementing a formal process for anyone to request a change, which is then assessed, approved, or rejected.
        
    - **Version Control:** Keeping track of different versions of the requirements document.
        
    - **Traceability:** Maintaining links from each requirement to the design components, code modules, and test cases related to it. This helps in assessing the impact of a change.





# 🏆 What is a Software Quality Standard?

A software quality standard is a set of defined rules, requirements, and guidelines that an organization follows to ensure its software products are consistently high-quality. These standards do not usually dictate _how_ to write code (like indentation), but rather **how to manage the process** of developing software to minimize errors and ensure customer satisfaction.

They provide a benchmark so that an organization can say, "We follow international best practices."

### 📝 Examples of Quality Standards

According to your syllabus, the key standards are:

1. **ISO 9000 Series (specifically ISO 9001)**
    
2. **Six Sigma**
    
3. **CMM (Capability Maturity Model)**
    

---

### 🌍 Detailed Example: ISO 9001

**ISO 9001** is the most widely recognized quality management standard in the world. It applies to any industry, but in software, it focuses on the **Quality Management System (QMS)**.

**Key Concept:** ISO 9001 does not check the _software itself_ (it doesn't look for bugs). Instead, it checks the **process** used to build the software. The logic is: **"If you have a high-quality, disciplined process, you will produce a high-quality product."**

**Core Principles of ISO 9001:**

1. **Customer Focus:** The organization must understand and meet customer needs.
    
2. **Leadership:** Leaders must establish a unity of purpose and direction.
    
3. **Evidence-based Decision Making:** Decisions should be based on data analysis, not guesses.
    
4. **Process Approach:** Activities should be managed as interrelated processes.
    
5. **Continual Improvement:** The organization must constantly try to improve its processes.

# Six Sigma 

**Six Sigma** is a highly disciplined, data-driven quality management methodology. Its primary goal is to improve processes to the point where they are **99.99966% defect-free**.

In simple terms, this means producing no more than **3.4 defects per million opportunities (DPMO)**.

- **In a software context:**
    
    - A **"defect"** could be a bug, a failed test case, a security vulnerability, or any failure to meet a user's requirement.
        
    - An **"opportunity"** could be a line of code, a function point, a use case, or a requirement.
        

The core idea is to **reduce process variation** so that the final product (the software) is consistently high-quality and predictable. It focuses on finding and eliminating the _root causes_ of defects rather than just finding and fixing the defects themselves.
### The DMAIC Methodology

Six Sigma achieves its goal by following a formal five-phase project methodology called **DMAIC**:

1. **D - Define**
    
    - **Goal:** Define the problem, the project goals, and the customer (user) requirements.
        
    - **Software Example:** A project team might _define_ the goal as "Reduce critical bugs reported by users in the first month after release." They would identify key quality requirements, like system response time or data accuracy.
        
2. **M - Measure**
    
    - **Goal:** Measure the current process performance to get a baseline. This is data-intensive.
        
    - **Software Example:** The team would _measure_ the current process by collecting data on:
        
        - How many bugs are found per 1,000 lines of code (KLOC)?
            
        - How many bugs are reported by users?
            
        - How much time is spent fixing bugs?
            
3. **A - Analyze**
    
    - **Goal:** Analyze the collected data to find the root cause(s) of the defects.
        
    - **Software Example:** The team _analyzes_ the data and discovers that 70% of the critical bugs originate from unclear or "ambiguous" requirements. The root cause isn't "bad coding," but a "flawed requirements engineering process."
        
4. **I - Improve**
    
    - **Goal:** Implement solutions to eliminate the root causes of the defects.
        
    - **Software Example:** To _improve_ the process, the team implements a mandatory **Formal Technical Review (FTR)** for all requirement documents _before_ coding begins. This ensures ambiguities are caught and fixed early.
        
5. **C - Control**
    
    - **Goal:** Implement controls to sustain the improvements and prevent the process from reverting to the old way.
        
    - **Software Example:** The team _controls_ the new process by using SQA (Software Quality Assurance) audits to ensure FTRs are being conducted properly. They continue to measure defect rates to prove the new process is working



# black box vs White box testing

![[Pasted image 20251115205221.png]]


# DevOps

DevOps is a combination of cultural philosophies, practices, and tools that merges software **Dev**elopment (Dev) and IT **Op**eration**s** (Ops). The main goal is to shorten the software development lifecycle, deliver applications and services at high velocity, and increase efficiency and reliability.

![[Pasted image 20251116004100.png]]

![[Pasted image 20251116004115.png]]


# 7Cs of devops

## Continuous Integration:
		Planning and Coding of the software are involved in this initial phase.
		During the planning phase, the vision of the project and scope is decided.           After the planning, developers used to begin coding the application.
## Continuous Development:
		The new functionality is continuously integrated with the existing code. So, there is continuous development of software. The newly written code needs to be integrated continuously and smoothly with the systems to reflect changes to the end-users. 
Jenkins is a famous tool used for continuous integration. Once the change in the Git repository is ready, then Jenkins fetches the committed code and prepares a build of that code. Then this build is given to the test server or the production server.

## Continuous Deployment: 
			The new code is deployed continuously, and configuration management tools play an essential role in executing tasks frequently and quickly. Here are some popular tools which are used in this phase, such as Chef, Puppet,
Ansible, and SaltStack.

## Continuous Operations:
			All the operations in DevOps are based on the continuity with complete automation of the release process. It allow the organization to accelerate the overall time to market.
			
## Continuous Testing:
			In this phase, software continuously testing for bugs. The tools like TestNG, JUnit, Selenium etc are used for the constant testing.
			
## Continuous Monitoring:
			Monitoring is the phase where important information about the use of software is recorded and processed to identify the problem areas. Monitoring is integrated with the operational capabilities of the software application. The system errors such as server not reachable, low memory, etc are resolved in this phase. It maintains the security and availability of the service.
			
## Continuous Feedback :
			By analyzing the results from the operations of the software, one can improve the application development. 
This can be achieved by constant feedback among the development and the operations of the next version of the current software applications.
![[Pasted image 20251118202025.png]]

# Choosing right devops tool

supports collaboration
supports learning
provides api


# Challanges of Devops

Shortage of Tool
Knowledge

Choice of Tools

Lack of Tool Integration

Cultural Challenges

Isolated Teams

Risk Analysis

# Cyclomatic complexity 

		is a white box testing metric that measures the complexity of program code by counting the number of linearly independent paths through code


![[WhatsApp Image 2025-11-16 at 01.08.32_ed0c1e0e.jpg]]


# INtegration testing

**Integration Testing** is the phase where individual software modules, which have already been unit-tested, are combined and tested as a group. The goal is to find errors in the **interfaces** and interactions between these combined modules.

- **Top-Down Integration:**
    
    - **Process:** Testing starts from the **top-level (main) module** and moves downwards.
        
    - **Stubs:** Lower-level modules that are not yet developed are simulated by "stubs." A stub is a dummy program that mimics the module's interface and returns a simple value.
        
    - **Advantage:** It allows for early testing of the system's main control flow and architecture.
        
    - **Disadvantage:** Can be difficult to test lower-level, complex functionalities in detail early on.
        
- **Bottom-Up Integration:**
    
    - **Process:** Testing starts from the **lowest-level modules** (e.g., utility functions) and moves upwards.
        
    - **Drivers:** Higher-level modules that are not yet developed are simulated by "drivers." A driver is a test program that calls the module being tested and passes it test data.
        
    - **Advantage:** Excellent for testing and finding errors in low-level, critical modules early and thoroughly.
        
    - **Disadvantage:** The overall system-level architecture and flow are not tested until the very end.

---
---

# 🎯 Functional vs. Non-Functional Requirements

This is the most common practical question on this topic.

- **Functional Requirements (FRs):**
    
    - **What they are:** These describe the **specific services or functions** the system must perform. They define _what the system does_.
        
    - **How to think of them:** If a user performs an action, what is the system's expected behavior? Think of them as verbs or features.
        
    - **Example:** "The user **shall be able to** search for a book by its title."
        
- **Non-Functional Requirements (NFRs):**
    
    - **What they are:** These define the **quality attributes, constraints, and characteristics** of the system. They define _how well the system performs_ its functions.
        
    - **How to think of them:** These are adjectives. How _fast_, _secure_, _easy-to-use_, or _reliable_ must the system be?
        
    - **Example:** "The book search **must return results** in under 3 seconds."
        

Here are practical examples for the systems mentioned in the exam papers.

#### Example 1: Blood Bank Management System

- **Functional Requirements:**
    
    - The system shall allow staff to register a new blood donor.
        
    - The system shall track the blood type, donation date, and expiry date for each blood bag.
        
    - The system shall allow staff to search for blood bags by blood type (e.g., "A+", "O-").
        
    - The system shall generate a report of low-stock blood types.
        
    - The system shall record when a blood bag is issued to a hospital.
        
- **Non-Functional Requirements:**
    
    - **(Security):** The system must be accessible only to authorized hospital staff using a password.
        
    - **(Performance):** A search for blood by type must return results within 2 seconds.
        
    - **(Reliability):** The system must be operational 24/7 with 99.9% uptime.
        
    - **(Usability):** The interface for registering a new donor should be simple enough for a new staff member to use with minimal training.



# 🏛️  Software Quality Assurance (SQA)

SQA is an umbrella activity that is applied throughout the entire software process. Its primary goal is not to _find_ bugs (that's testing), but to _prevent_ bugs by ensuring the team is following the correct processes and standards to build a high-quality product

#### Importance of SQA

- **Defect Prevention:** It institutes processes (like reviews and audits) that prevent defects from being introduced in the first place.
    
- **Improves Processes:** SQA monitors and audits the software process itself, helping to identify and fix inefficiencies.
    
- **Increases Confidence:** It gives management and customers confidence that the final product will be reliable and meet the defined standards.
    
- **Saves Cost:** Preventing bugs is significantly cheaper than finding and fixing them after the software has been built or, worse, after it has been released to the customer

#### SQA Tasks (or Activities)

- **Formal Technical Reviews (FTRs):** These are structured meetings where technical personnel review a document or code to find errors. This is a core SQA activity for defect removal.
    
- **Process Audits:** The SQA team regularly checks (audits) that the project team is correctly following the defined software development process.
    
- **Standards and Procedures:** SQA is responsible for defining or selecting the standards (e.g., coding standards, documentation standards) that the team must follow.
    
- **Measurement and Reporting:** SQA collects data (metrics) on the process and product, such as the number of defects found, and reports this to management.
    
- **Configuration Management:** Ensuring that all changes to the software are controlled and tracked, which is essential for maintaining integrity.




# 📊 CMM (Capability Maturity Model)

The **Capability Maturity Model (CMM)** is a model used to judge the maturity of an organization's software development processes. Its main **use** is to provide a framework for process improvement, allowing an organization to move from an ad-hoc, chaotic process to a mature, disciplined, and optimized process.

It consists of 5 levels:

- **Level 1: Initial (Chaotic)**
    
    - The process is unpredictable, ad-hoc, and poorly controlled.
        
    - There are no stable processes; success depends entirely on individual effort and heroes.
        
    - This is the default starting point for many organizations.
        
- **Level 2: Repeatable (or Managed)**
    
    - Basic project management processes are established to track cost, schedule, and functionality.
        
    - Successful practices from previous projects can be repeated.
        
    - The process is not yet standardized across the _entire_ organization, but it works on a per-project basis.
        
- **Level 3: Defined**
    
    - The software process for _both management and engineering activities_ is documented, standardized, and integrated into a **standard software process** for the entire organization.
        
    - All projects use an approved, tailored version of this standard process.
        
- **Level 4: Quantitatively Managed**
    
    - The organization sets quantitative goals for both the software process and product quality.
        
    - Detailed metrics are collected and analyzed to understand and control the process.
        
    - You can make accurate statistical predictions about project outcomes.
        
- **Level 5: Optimizing**
    
    - This is the highest level. The entire organization is focused on **continuous process improvement**.
        
    - The organization uses quantitative feedback from the process and from piloting new ideas to proactively improve its processes over time.



# Cohesion and Coupling

### 🟢 1. Cohesion (The "Internal" Quality)

Cohesion measures how **focused and related** the responsibilities within a _single_ module (like a class or a function) are.

- **Goal: High Cohesion (Good)**
    
    - **High Cohesion** means all the elements (code, functions, variables) inside a module belong together and work on a single, well-defined task. Think of it as a well-organized kitchen drawer that _only_ contains an organized set of cutlery (forks, knives, spoons).
        
    - **Low Cohesion** (Bad) means a module is a jumble of unrelated tasks. This is like a junk drawer that contains batteries, old keys, a hammer, and a few spoons. It's confusing and hard to maintain.
        
- **Types of Cohesion (Briefly, as asked by the exam):** The papers ask for the types of cohesion. They are typically ranked from best (highest) to worst (lowest):
    
    1. **Functional (Best):** The module performs one single, well-defined task (e.g., `calculate_square_root`).
        
    2. **Sequential:** Tasks in the module must be done in a specific order, and the output of one is the input to the next (e.g., `read_data_and_process_it`).
        
    3. **Communicational:** All elements operate on the same data set (e.g., a module that `print_student_details` and `calculate_student_gpa` using the same student object).
        
    4. **Procedural:** Elements are grouped because they must be executed in a specific order (like a flowchart).
        
    5. **Temporal:** Elements are grouped because they are processed at the same time (e.g., an `initialize()` function that starts up many different, unrelated things).
        
    6. **Logical:** Elements are grouped because they are _logically_ related, but they don't do the same thing (e.g., a single function that handles all mouse and keyboard inputs).
        
    7. **Coincidental (Worst):** Elements are in the same module purely by chance, with no real relationship.
        

---

### 🔴 2. Coupling (The "External" Quality)

Coupling measures how **interdependent** two or more _separate_ modules are on each other.

- **Goal: Low Coupling (Good)**
    
    - **Low Coupling** (or "loose coupling") means modules are independent. They don't know or care about the internal details of other modules. This is good because you can change one module without breaking all the others. Think of a USB plug—your computer doesn't need to know if it's a keyboard or a mouse; it just uses a standard interface.
        
    - **High Coupling** (or "tight coupling") (Bad) means modules are heavily linked and depend on each other's internal workings. If you change one module, you are forced to change many others. This is like trying to change your car's tire, but finding it's been welded directly to the axle instead of bolted on.
        
- **Types of Coupling (Briefly, as asked by the exam):** The papers also ask for the types of coupling. They are ranked from best (lowest coupling) to worst (highest coupling):
    
    1. **Data (Best):** Modules communicate only by passing data (e.g., parameters to a function).
        
    2. **Stamp:** Modules share a common data structure (like an object or record) but may not use all of it.
        
    3. **Control:** One module passes a "control flag" to another, telling it _what_ to do (e.g., a `do_task(flag)` where `flag` means "save" or "delete").
        
    4. **Common:** Modules share the same global data (very bad, as anyone can change it).
        
    5. **Content (Worst):** One module directly modifies or relies on the internal code or data of another module.




# Risk

### ⚠️ 1. What is a Software Risk?

A risk is an uncertain event that, if it occurs, will have a negative impact on the software project. The goal of risk management is not to avoid all risks (which is impossible) but to identify them early and have a plan to deal with them, minimizing their impact.

### 🗂️ 2. Categories of Software Risks

- **Project Risks:** These are risks that threaten the project's schedule and cost.
    
    - **Example:** Budget cuts, schedule slippage, loss of key team members, or using the wrong tools.
        
- **Product Risks (or Technical Risks):** These are risks that threaten the quality, performance, or functionality of the software being built.
    
    - **Example:** The technology being used is new and unproven, the design is too complex ("gold plating"), or the performance requirements are impossible to meet.
        
- **Business Risks:** These are risks that threaten the viability of the software product in the market.
    
    - **Example:** Building a product that the market doesn't actually want, a competitor releasing a better product first, or changes in company strategy that make the project irrelevant.
        

---

### 🧭 3. The Risk Management Process

1. **Risk Identification:** The first step is to identify all potential risks. This is a team effort, brainstorming "What could go wrong?" in all categories (Project, Product, Business).
    
2. **Risk Analysis & Assessment:** Once risks are identified, you analyze them. This involves:
    
    - **Assessment:** Estimating the **probability** (likelihood) of the risk occurring.
        
    - **Analysis:** Estimating the **impact** (damage) the risk would cause if it did occur.
        
    - You can then prioritize them. A high-probability, high-impact risk must be managed immediately.
        
3. **Risk Planning (or Control):** This is where you decide what to do about each major risk. This is where the **RMMM plan** comes in.
    
4. **Risk Monitoring:** You must continuously monitor the project to see if any new risks have appeared, if the probability/impact of an old risk has changed, or if your mitigation plan is working.
    

---

### 📜 4. The RMMM Plan

**R**isk **M**itigation, **M**onitoring, and **M**anagement Plan.

It is the formal document you create during the "Risk Planning" stage. For each major risk you've identified, the RMMM plan details your strategy. It has three parts:

- **Risk Mitigation (Proactive):**
    
    - This is your _proactive_ plan to avoid the risk or reduce its probability.
        
    - **Example Risk:** "Key developer (Sarah) might quit."
        
    - **Mitigation Plan:** "Document all of Sarah's work. Train another developer (John) to be her backup and encourage knowledge sharing."
        
- **Risk Monitoring (Awareness):**
    
    - This part describes the "trigger" or warning sign you will look for to know if the risk is about _to_ happen.
        
    - **Example Risk:** "Key developer (Sarah) might quit."
        
    - **Monitoring Plan:** "Monitor team morale in weekly check-ins. Watch for any signs of Sarah being unhappy or disengaged."
        
- **Risk Management (Reactive):**
    
    - This is your _contingency_ plan, or "Plan B," that you will execute if the risk actually happens.
        
    - **Example Risk:** "Key developer (Sarah) might quit."
        
    - **Management Plan:** "If Sarah quits, John will immediately take over her modules. The project schedule will be re-assessed, and we will pause work on non-essential Feature X to absorb the delay."
        

In short, **Mitigation** is what you do _before_ it happens, **Monitoring** is how you watch for it, and **Management** is what you do _after_ it happens.



# Reverse & Re-engineering

These topics are about dealing with old, legacy software.

- **Reverse-Engineering:** This is the process of analyzing an existing software system to understand its design, components, and how they interact. The goal is **not** to change the system, but simply to **understand it** or create documentation for it.
    
- **Re-engineering:** This is the process of taking an existing (legacy) system and rebuilding or modifying it to improve its quality, maintainability, or performance. It's a "rebuild" process that often starts with reverse-engineering to understand the old system first. The **Software Reengineering Process Model** typically involves:
    
    1. **Reverse Engineering:** Understand the old system.
        
    2. **Code Restructuring:** Clean up the "bad" code.
        
    3. **Data Restructuring:** Clean up or migrate the database.
        
    4. **Forward Engineering:** Use the new understanding to rebuild the system with modern technology
![[Pasted image 20251116015248.png]]


# System testing


System testing is a level of software testing where a complete and fully integrated software product is tested as a whole.

It is performed _after_ **Integration Testing** (where individual modules are combined and tested) and _before_ **Acceptance Testing** (where the end-user validates the product).

The main purpose of system testing is to evaluate the system's compliance with all the specified requirements, both functional and non-functional.

---

### 🎯 Key Goals and Details

- **End-to-End Verification:** System testing validates the complete, end-to-end flow of the application. For example, in an e-commerce website, a system test would check the entire process from a user logging in, adding items to the cart, entering payment details, and successfully checking out.
    
- **Black-Box Testing:** It is primarily a **black-box testing** technique. This means the tester does not need to know the internal code or logic. They focus only on the inputs and the expected outputs, just as a real user would.
    
- **Covers All Requirements:** It's the first level of testing that checks the system against the complete **System Requirements Specification (SRS)**. This includes:
    
    - **Functional Requirements:** Does the system do what it's supposed to do?
        
    - **Non-Functional Requirements:** _How well_ does the system do it? This includes testing performance, security, reliability, and usability.
        
- **Real-World Environment:** System testing should be done in an environment that is as close to the actual production or live environment as possible. This helps discover issues related to the system's configuration or deployment.
    
- **Finds System-Level Defects:** Its goal is to find bugs that only appear when the entire system is integrated, such as issues with data flow, incorrect interactions between components, or problems with system-wide performance.




# Testing

		levels
			Unit testing
			 Integration testing
			 System testing
			 Acceptance testing

		 Approaches
			 Black Box Testing
			 White Box Testing 
			 Grey Box Testing

		 Main categories
			 Functional Testing
			 Non Functional Testing



# Software Myths

![[WhatsApp Image 2025-11-16 at 01.46.26_5f6bfe19.jpg]]



![[Pasted image 20251116014850.png]]


![[Pasted image 20251116015116.png]]



# Project Scheduling
![[Pasted image 20251116102659.png]]
![[Pasted image 20251116102637.png]]


Methods:
		PERT- Program evaluation and review technique
			 CPM-Critical path method



# Project Tracking

![[Pasted image 20251116102809.png]]


# QFD

![[Pasted image 20251116103409.png]]



# SRS
characteristics
![[Pasted image 20251116103521.png]]



# Function Point
![[Pasted image 20251118102917.png]]

![[Pasted image 20251118102927.png]]

![[Pasted image 20251118102947.png]]




![[Pasted image 20251118103614.png]]




![[Pasted image 20251118113715.png]]



![[Pasted image 20251118115321.png]]

![[Pasted image 20251118115416.png]]


![[Pasted image 20251118120001.png]]



# Modular Decomposition
**Modular Decomposition** is the process of breaking a large, complex software system down into smaller, manageable, and independent parts called "modules." It is the application of the "Divide and Conquer" strategy to software engineering.

Here is why it is used and why it is crucial for architectural design:

### 1. To Manage Complexity (Divide and Conquer)

The primary reason is that large systems are simply too complex for a single human mind to understand all at once. By breaking the problem into smaller sub-problems (modules), developers can focus on one piece of the puzzle at a time without being overwhelmed by the whole system.

### 2. Parallel Development

If a software is one giant block of code, only a few people can work on it effectively. Modular decomposition allows different teams or developers to work on different modules **simultaneously**.

- _Example:_ Team A works on the "User Interface" module while Team B works on the "Database" module.
    

### 3. Reusability

Well-designed modules can be reused in other parts of the application or even in completely different projects.

- _Example:_ If you create a "Login/Authentication" module, you can plug that same module into your next project, saving huge amounts of time.
    

### 4. Easier Maintenance and Debugging

When a bug occurs, it is much easier to find it in a small, specific module than in a massive, monolithic codebase. Furthermore, if you need to update a feature, you likely only need to modify one specific module rather than the entire system.

### 5. Encapsulation (Information Hiding)

Modules allow you to hide the complex internal details (code and data) behind a simple interface. Other parts of the system don't need to know _how_ a module works; they just need to know _what_ it does. This protects the integrity of the data.



# Structural vs behavioural diagrams

|**Feature**|**Structural Models**|**Behavioral Models**|
|---|---|---|
|**Nature**|**Static:** Describes the structure that doesn't change during execution.|**Dynamic:** Describes what happens while the system is running.|
|**Focus**|Focuses on the **organization** of the system (classes, objects, interfaces).|Focuses on the **execution** and flow of control/data.|
|**Key Question**|**"What is the system made of?"**|**"How does the system function/react?"**|
|**Time Factor**|**Time-independent.** The structure exists before the program runs.|**Time-dependent.** It shows sequences of events and states over time.|
|**Analogy**|A **blueprint** of a house (shows walls, rooms, doors).|A **video** of people living in the house (shows movement, opening doors, cooking).|


# Top down vs bottom up

|**Feature**|**Top-Down Integration**|**Bottom-Up Integration**|
|---|---|---|
|**Direction**|Testing starts from the **main (top)** control module and moves down to lower-level modules.|Testing starts from the **lowest level** modules (atomic units) and moves up to the main control module.|
|**Helper Used**|Uses **Stubs**.<br><br>  <br><br>_(A stub is a dummy program that simulates a sub-module not yet developed)._|Uses **Drivers**.<br><br>  <br><br>_(A driver is a dummy "main" program that calls the module being tested)._|
|**Main Advantage**|The main control logic and interface are tested **early**. You get a working prototype quickly.|Critical low-level utility functions (like database access or calculations) are verified thoroughly **early**.|
|**Main Disadvantage**|Low-level data processing is tested late. Writing many "Stubs" can be time-consuming.|The overall system design and UI are not tested until the very end (the "Big Bang" moment).|
|**Complexity**|Complexity increases as you move down.|Complexity increases as you move up.|

# 📝 Formal Technical Review (FTR)

**1. Definition** A Formal Technical Review (FTR) is a software quality control activity performed by software engineers (and others). It is a meeting conducted to uncover errors in a software artifact (like code, design documents, or requirements) before they move to the next phase of development. It is a primary filter for software quality assurance.

**2. Objectives** (This addresses the specific question in Winter 2020, Q.7(a))

- **Uncover Errors:** To discover functional and logical errors in the product early.
    
- **Verify Compliance:** To verify that the software under review meets established requirements and standards.
    
- **Uniformity:** To ensure the software is represented in a uniform manner (adhering to coding/documentation standards).
    
- **Training:** To make projects more manageable and help junior engineers learn from senior engineers' critiques.
    

**3. The Review Meeting Constraints (The Guidelines)** (This addresses the question in Winter 2023, Q.4(b)) For an FTR to be effective, it must follow strict guidelines:

- **Small Team:** Between **3 to 5 people** should be involved.
    
- **Preparation:** Participants must prepare in advance (usually no more than 2 hours of prep work).
    
- **Duration:** The meeting should be short, typically **less than 2 hours**.
    
- **Focus on Product:** Review the **product**, not the **producer**. Criticism should never be personal.
    

**4. Key Roles**

- **Producer:** The person who created the work product (code/document).
    
- **Review Leader:** Plans the meeting and sets the agenda.
    
- **Recorder:** Notes down all the issues and decisions made.
    
- **Reviewers:** The team members who analyze the product and find errors.
    

**5. The Outcome** At the end of the review, one of three decisions is made:

1. **Accept:** The product is accepted without modification.
    
2. **Reject:** The product has severe errors and must be reviewed again after fixing.
    
3. **Accept with Modification:** The product has minor errors; it is accepted pending the corrections (no second review needed).






# **Software Configuration Management (SCM)** 
is the task of tracking and controlling changes in the software. Since change is inevitable in software development (due to bugs, new features, or requirement shifts), SCM ensures that these changes do not lead to chaos.

It is the "art of identifying, organizing, and controlling modifications to the software being built".

### ⚙️ The SCM Process (Activities)

The SCM process consists of several key activities that manage the software's "configuration" (all the files, code, and documents that make up the project).

1. **Configuration Identification:**
    
    - This involves identifying all the items that need to be tracked. These items are called **Software Configuration Items (SCIs)**.
        
    - Examples of SCIs: Source code files, Requirement documents (SRS), Design diagrams, Test plans, User manuals.
        
2. **Version Control:**
    
    - This combines procedures and tools to manage different versions of configuration items created during the software process.
        
    - It allows developers to go back to a previous version if a new change breaks the code. It handles "check-in" and "check-out" of files so multiple people can work without overwriting each other's work.
        
3. **Change Control:**
    
    - This is the _human_ process of managing change. It ensures that changes are not made haphazardly.
        
    - **Process:**
        
        1. A **Change Request** is submitted.
            
        2. The **Change Control Board (CCB)** evaluates the technical and cost impact.
            
        3. The change is either **Approved** or **Rejected**.
            
        4. If approved, the engineering team implements the change.
            
4. **Configuration Auditing:**
    
    - This acts as a quality assurance check. It answers the question: "Did the change actually fix the problem without breaking anything else?"
        
    - It verifies that the software matches the requirements and that all approved changes have been correctly implemented.
        
5. **Status Reporting:**
    
    - This is the "communication" activity. It answers: "What happened? Who did it? When did it happen?"
        
    - It provides reports to management about the status of changes, versions, and releases.


# version control and change control

- **Version Control** is largely **automated** (using tools like Git). It manages the _files_ and their history.
    
- **Change Control** is largely **manual** (using forms and meetings). It manages the _approval_ and _decision-making_ regarding whether a change should happen at all.



# Mobile Testing

Mobile apps are unique because they run on devices with limited resources (battery, memory), varied screen sizes, and unstable network connections. Therefore, the testing strategy is broader than just checking if features work.

### 📱 Key Mobile Testing Approaches

**1. Usability Testing (User Experience)** Since mobile screens are small and inputs rely on touch (gestures like swipe, pinch), usability is critical.

- **Goal:** Ensure the app is intuitive and easy to use.
    
- **Check:** Are buttons large enough to tap? Is the text readable without zooming? Do navigation menus work smoothly?
    

**2. Compatibility Testing (Configuration Testing)** Mobile devices are highly fragmented (thousands of different Android phones and iPhones).

- **Goal:** Ensure the app works across different hardware and software configurations.
    
- **Check:**
    
    - **Different OS Versions:** Does it work on Android 10, 11, 12, 13, and iOS 15, 16, 17?
        
    - **Screen Sizes:** Does the layout adjust correctly for a small phone vs. a large tablet?
        
    - **Device Hardware:** Does it work on devices with low RAM vs. high RAM?
        

**3. Connectivity (Network) Testing** Mobile phones move around, so network connection is never guaranteed.

- **Goal:** Ensure the app handles network changes gracefully.
    
- **Check:**
    
    - **Switching Networks:** What happens when switching from Wi-Fi to 4G/5G?
        
    - **Low Bandwidth:** Does the app crash on slow 2G/3G networks?
        
    - **Offline Mode:** If the internet is lost, does the app show a helpful "No Connection" message or just crash?
        

**4. Performance & Resource Testing** Mobile devices run on batteries and have limited processing power compared to desktops.

- **Goal:** Ensure the app is efficient.
    
- **Check:**
    
    - **Battery Drain:** Does using the app for 10 minutes drain 20% of the battery? (This is bad).
        
    - **Memory Leaks:** Does the app slow down the phone or crash after long usage?
        
    - **Startup Time:** Does the app launch quickly?
        

**5. Interrupt Testing** Mobile apps are constantly interrupted by other phone functions.

- **Goal:** Ensure the app can pause and resume without losing data.
    
- **Check:** What happens to the app when:
    
    - An incoming call is received?
        
    - A text message pops up?
        
    - The battery dies?
        
    - A push notification is received?
        

**6. Security Testing** Mobile phones are easily lost or stolen, and apps often use unsecured public Wi-Fi.

- **Goal:** Protect user data.
    
- **Check:** Is sensitive data (like passwords or credit cards) encrypted? Does the app ask for unnecessary permissions (like accessing the camera when it doesn't need to)?





# 💨 What is Smoke Testing?

Smoke testing is an integration testing approach that is commonly used when software is being developed. It is a "sanity check" performed on a new software build to verify that the **critical functionalities** work correctly before the build is accepted for thorough testing.

If the smoke test fails (meaning the program "catches smoke" or crashes immediately), the build is rejected, and the testing team does not waste time testing a broken application. It is often described as a "rolling integration" approach.

### 🏗️ Activities Encompassed by Smoke Testing

According to standard software engineering practices (like those in the reference books listed in your syllabus), smoke testing encompasses the following specific activities:

1. **Integration of Code (The Build):** Software components that have been translated into code are integrated into a "build." A build includes all data files, libraries, reusable modules, and engineered components that are required to implement one or more product functions.
    
2. **Designing Critical Tests:** A series of tests is designed to expose errors that would keep the build from performing its function. These are not exhaustive deep-dive tests; they are broad tests meant to uncover "showstopper" errors (e.g., Does the program launch? Does the login work? Does the main menu open?).
    
3. **Daily/Frequent Execution:** The build is integrated with other builds, and the entire product (in its current form) is smoke tested. Ideally, this happens daily.
    
4. **Assessment (Go/No-Go Decision):**
    
    - **If the tests pass:** The build is declared stable enough for the QA team to begin rigorous functional and regression testing.
        
    - **If the tests fail:** The build is rejected immediately. It is sent back to the developers to fix the critical block, preventing the QA team from wasting time on a broken system.




### 🏗️ What is Software Architecture?

**Software Architecture** is the high-level structure or organization of a software system. It serves as the **blueprint** for the system.

It is defined as the set of structures needed to reason about the system, which comprises:

1. **Software Elements:** The components or modules (e.g., a database, a user interface, a payment processing service).
    
2. **Relations:** How these elements connect and interact with each other (e.g., function calls, data transfer).
    
3. **Properties:** The characteristics of both the elements and the relations (e.g., security, speed, reliability).
    

> **Simple Analogy:** If software engineering is construction, **Software Architecture** is the architectural blueprint of the building. It decides where the pillars, walls, and rooms go _before_ anyone starts laying bricks.


## Importance
- **Stakeholder Communication:** Acts as a bridge between non-technical clients and technical developers.
    
- **Risk Management:** Helps identify high-risk areas early in the lifecycle.
    
- **Cost Estimation:** Allows for better estimation of cost and schedule before detailed coding begins.
    
- **Scalability:** Defines how the system will grow (e.g., can it handle 1 million users?).






# Types of SW models
### 1. Prescriptive Models (Traditional/Linear)

These are the "strict" models. They prescribe a set of rigid activities that must happen in a specific order. They focus on stability, documentation, and clear milestones. They are best when requirements are fixed and unlikely to change.

- **Waterfall Model:** The classic linear approach (Analysis → Design → Code → Test).
    
- **V-Model:** A variation of Waterfall where every development phase has a corresponding testing phase running in parallel.
    

### 2. Incremental Process Models

These models are a middle ground. They don't build the whole system at once (like Waterfall), but they also don't just "evolve" endlessly. They break the project into small "chunks" (increments) and deliver them one by one.

- **Incremental Model:** You deliver the "core" product first, then add more features in subsequent releases (Increment 1, Increment 2, etc.).
    
- **RAD (Rapid Application Development) Model:** A high-speed adaptation of the linear model. It uses component-based construction to build a fully functional system in a very short time (60-90 days).
    

### 3. Evolutionary Process Models

These models are designed specifically to handle **change**. They acknowledge that requirements are often unclear at the start and will evolve over time. They are iterative, meaning they cycle through phases repeatedly to refine the software.

- **Prototyping Model:** You build a quick "throwaway" version of the software just to understand the requirements, then discard or refactor it to build the real system.
    
- **Spiral Model:** Combines the iterative nature of prototyping with the systematic aspects of the Waterfall model. It is heavily focused on **Risk Analysis** at every loop.
    
- **Concurrent Development Model:** Allows different teams to be in different stages of development simultaneously (e.g., one team is designing while another is already coding).
    

### 4. Agile Process Models

These are modern, lightweight models focused on speed, flexibility, and customer satisfaction over rigid documentation. They are built to handle unpredictability.

- **Scrum:** Uses short cycles called "Sprints" (usually 2-4 weeks) to deliver working software frequently.
    
- **Extreme Programming (XP):** Focuses on technical excellence and good programming practices (like Pair Programming, TDD) to handle changing requirements.
    
- **Kanban:** Focuses on visualizing work and limiting "work in progress" to improve flow.

| **Category**     | **Key Characteristic**                            | **Examples**        |
| ---------------- | ------------------------------------------------- | ------------------- |
| **Prescriptive** | Linear, rigid, heavy documentation.               | Waterfall, V-Model  |
| **Incremental**  | Deliver in chunks/pieces.                         | Incremental, RAD    |
| **Evolutionary** | Iterative, built to handle changing requirements. | Spiral, Prototyping |
| **Agile**        | Flexible, customer-focused, rapid delivery.       | Scrum, XP, Kanban   |




### 🛣️ Basic Path Testing

**Basic Path Testing** is a **white-box testing** technique first proposed by Tom McCabe. It is a structural testing method that allows the tester to derive a logical complexity measure of a procedural design and use this measure as a guide for defining a basis set of execution paths111.

**Key Characteristics:**

- **Goal:** The primary objective is to ensure that every independent path through the code is executed at least once during testing2.
    
- **Independent Path:** An independent path is any path through the program that introduces at least one new set of processing statements or a new condition.
    
- **Cyclomatic Complexity:** This technique uses the **Cyclomatic Complexity** metric to calculate the exact number of independent paths in the source code. This number tells the tester exactly how many test cases are needed to ensure full path coverage3.
    

**How it works (The Process):**

1. Draw a **Control Flow Graph** from the code.
    
2. Calculate the **Cyclomatic Complexity** (V(G)) of the graph (e.g., using the formula $V(G) = Edges - Nodes + 2$).
    
3. Determine the set of **independent paths**.
    
4. Design test cases to force execution of each path4.



# object oriented design vs Procedural design

| **Feature**       | **Procedural Design**                                                                                     | **Object-Oriented Design (OOD)**                                                                  |
| ----------------- | --------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| **Primary Focus** | Focuses on **functions** (algorithms/logic). Data is secondary.                                           | Focuses on **data** (objects). Logic is secondary.                                                |
| **Decomposition** | **Top-Down approach:** Break the big problem into smaller sub-functions.                                  | **Bottom-Up approach:** Build small objects first and combine them to form the system.            |
| **Data Security** | **Low:** Data moves openly between functions (often using global data), making it vulnerable.             | **High:** Data is hidden inside objects (**Encapsulation**) and can only be accessed via methods. |
| **Reusability**   | **Low:** Difficult to reuse code because functions are often dependent on the specific program structure. | **High:** Classes can be easily reused in other projects, especially via **Inheritance**.         |
| **Complexity**    | Suitable for smaller, simpler programs or scripts.                                                        | Suitable for large, complex, and scalable systems.                                                |
| **Communication** | Functions communicate by passing data values.                                                             | Objects communicate by passing messages.                                                          |



# Agile Vs Devops

| **Feature**        | **Agile Development**                                                                      | **DevOps**                                                                                |
| ------------------ | ------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| **Primary Focus**  | Focuses on **Software Development** processes. It improves how the team _builds_ the code. | Focuses on **End-to-End Delivery**. It improves how the team _deploys and runs_ the code. |
| **Scope**          | Stops when the software is "potentially shippable" (Dev complete).                         | Extends to "deployed in production" and maintained (Dev + Ops).                           |
| **Team Structure** | Involves Developers, Testers, and Product Owners.                                          | Involves Developers, Testers, and **IT Operations (SysAdmins)** working together.         |
| **Goal**           | To handle **changing requirements** and deliver updates frequently.                        | To handle **continuous delivery** and ensure reliability/stability.                       |
| **Feedback**       | Feedback comes primarily from the **Customer** (via Sprint Reviews).                       | Feedback comes from the **Customer** AND **Live Monitoring** (System health, logs).       |
| **Automation**     | Emphasizes automated **testing**.                                                          | Emphasizes automated **testing, deployment, and infrastructure** (CI/CD).                 |


### 📅 1. Project Scheduling Process

Project scheduling is the activity that distributes the estimated effort across the planned project duration by allocating specific tasks to specific dates. It answers the question: **"What needs to be done, by whom, and strictly by when?"**

The process typically follows these steps:

1. Compartmentalization (Identify Tasks):
    
    The project is broken down into a number of manageable activities and tasks. This is often done using a Work Breakdown Structure (WBS).
    
2. Interdependency Identification (Sequence):
    
    Determine the relationship between tasks. Some tasks must be completed before others can begin (e.g., "Design" must finish before "Coding" begins). These are called sequential tasks. Others can run in parallel.
    
3. Effort Validation (Estimation):
    
    Estimate the time and effort required to complete each task. (e.g., "Task A will take 2 developers 5 days").
    
4. Resource Allocation:
    
    Assign specific people or teams to each task based on their skills and availability.
    
5. Network Creation:
    
    Create a "Task Network" (like a PERT or CPM chart) to visualize the critical path—the sequence of tasks that determines the shortest time to complete the project.
    
6. Schedule Generation:
    
    Map these tasks onto a calendar timeline. This is where the Gantt Chart is created.
    

---

### 📊 2. The Gantt Chart

The **Gantt Chart** (named after Henry Gantt) is the most widely used tool for project scheduling. It is a type of **bar chart** that illustrates a project schedule.

**Key Components:**

- **Vertical Axis (Y-axis):** Lists the tasks to be performed (e.g., Requirements, Design, Coding).
    
- **Horizontal Axis (X-axis):** Represents the time scale (e.g., days, weeks, months).
    
- **Horizontal Bars:** Each task is represented by a horizontal bar.
    
    - The **left end** of the bar marks the planned **start date**.
        
    - The **right end** marks the planned **end date**.
        
    - The **length** of the bar represents the **duration**.
        
- **Milestones:** Significant events (like "Design Approved" or "Alpha Release") are usually marked with a **diamond shape** ($\diamond$) and have zero duration.
    
- **Dependencies:** Arrows often connect the bars to show that one task depends on another (Task B cannot start until the bar for Task A ends).
    

![Image of Gantt chart example](https://encrypted-tbn0.gstatic.com/licensed-image?q=tbn:ANd9GcSwvKc6DjJuaWWObMCLSwOnD2_FNZukUDchJ7NENbfd_aMM5QSe-LEON8ADWpbG8BOa0h02ILMl5ibI1idnpHAOm9I6UAgvMn4OAXpkWYw27vNkqcA)


**How it is used for Tracking:**

- **Planning:** Initially, it shows the _planned_ schedule.
    
- **Tracking:** As work progresses, the bars are often shaded or a second bar is drawn below the first to show the _actual_ progress.
    
- **Comparison:** If the "Actual" bar is shorter than the "Planned" bar for today's date, the project manager knows immediately that the task is behind schedule.
    

**Advantages:**

- Simple to understand and easy to read.
    
- Clearly shows overlapping tasks (parallel work).
    
- Excellent for tracking daily/weekly progress against the plan.



### 🏗️ What is Architectural Design?

**Architectural Design** represents the structure of data and program components that are required to build a computer-based system. It considers the architectural style that the system will take, the structure and properties of the components (modules), and the interrelationships between them.

It serves as the **blueprint** for the system. Just as an architect creates a blueprint for a building to ensure it is safe and functional, a software architect designs the system structure to ensure it meets requirements like performance, security, and maintainability.

**Key Goals:**

- To define the components (modules) of the system.
    
- To define how these components communicate (interfaces).
    
- To address non-functional requirements (scalability, reliability).
    

---

### 🏛️ Architectural Styles and Patterns

An **Architectural Style** is a descriptive pattern that defines a family of systems in terms of structural organization. The most common styles used in software engineering are:

#### 1. Data-Centered Architecture (Repository Style)

In this style, a data store (like a file or database) resides at the center of the architecture and is accessed frequently by other components that update, add, delete, or modify data.

- **Example:** A standard database-backed web application or an IDE (where the "code" is the central data accessed by the compiler, editor, and debugger).
    
- **Pros:** Easy to share data; components are independent of each other.
    

#### 2. Data-Flow Architecture (Pipe and Filter)

This architecture is applied when input data is to be transformed through a series of computational or manipulative components into output data.

- **Structure:** A set of components (filters) connected by pipes that transmit data from one component to the next.
    
- **Example:** A compiler (Source Code → Lexical Analyzer → Parser → Semantic Analyzer → Code Generator).
    
- **Pros:** Easy to maintain and reuse; supports parallel execution.
    

#### 3. Call and Return Architecture

This style enables a software designer to achieve a program structure that is relatively easy to modify and scale. It typically includes:

- **Main Program/Subroutine:** A classic top-down approach where a main program invokes sub-programs.
    
- **Remote Procedure Call (RPC):** Components on different computers across a network communicate effectively.
    

#### 4. Layered Architecture

A specific type of "Call and Return" where components are organized into horizontal layers. Each layer provides services to the layer above it and consumes services from the layer below it.

- **Example:** The OSI Model or a 3-Tier Web App (Presentation Layer, Business Logic Layer, Database Layer).
    
- **Pros:** Increases maintainability; you can change the "User Interface" layer without breaking the "Database" layer.
    



#### 5. Object-Oriented Architecture

The components of a system encapsulate data and the operations that must be applied to manipulate the data. Communication and coordination between components are accomplished via message passing.

- **Example:** Any system built using Java or C++ where classes interact (e.g., a `Customer` object sending a message to an `Order` object).
    

#### 6. Client-Server Architecture

(Mentioned in syllabus "Advanced Topics" ) The system is distributed across a network.

- **Client:** Requests services (e.g., a web browser).
    
- **Server:** Provides services (e.g., a web server).
    
- **Pros:** Scalability; centralized data management.




### 🚧 What is Boundary Value Analysis (BVA)?

**Boundary Value Analysis (BVA)** is a **Black Box Testing** technique. It is based on the principle that errors are most likely to occur at the **boundaries** of the input domain rather than in the "center" of the input data.

Instead of testing random values, BVA focuses on testing the values at the extreme ends of the valid ranges (Minimum, Maximum, Just Below Min, Just Above Max).

**Example:** If a text field accepts Age between 18 and 60:

- **Valid Boundaries:** 18, 60
    
- **Invalid Boundaries:** 17, 61
    
- **BVA Test Cases:** 17, 18, 19, 59, 60, 61.
    

---

### ✅ Merits (Advantages) of BVA

1. **Finds Errors Efficiently:** It is excellent at catching "off-by-one" errors (e.g., using `>` instead of `>=` in the code), which are very common programming mistakes.
    
2. **Small Test Set:** It reduces the total number of test cases required compared to testing every possible value, while still maintaining high effectiveness.
    
3. **Clear Guidelines:** It provides clear, deterministic rules for designing test cases (Min, Max, Min-1, Max+1), so it's easy for testers to apply without needing to know the internal code logic.
    

### ❌ Demerits (Disadvantages) of BVA

1. **Ignores Internal Logic:** Since it is a black-box technique, it does not test the internal path or logic of the code. It might miss errors that occur "inside" the valid range but are not related to boundaries.
    
2. **Not for Complex Dependencies:** It assumes that input variables are independent. It doesn't work well when the valid range of one input depends on the value of another input.
    
3. **False Sense of Security:** Passing boundary tests doesn't guarantee the program works for _all_ values in the middle. It only guarantees the edges are correct.



### 📅 Project Planning Activities

Project planning is the "management" phase where you decide how the work will get done before you actually start coding. The goal is to establish a pragmatic strategy for controlling, tracking, and monitoring a complex technical project.

The major activities include:

1. **Estimation:**
    
    - Estimating the **size** of the project (using LOC or FP).
        
    - Estimating the **effort** required (in person-months) and the **cost** (budget).
        
2. **Scheduling:**
    
    - Defining the project tasks and milestones.
        
    - Assigning start and end dates to each task (creating Gantt charts).
        
    - Identifying dependencies (Task B cannot start until Task A finishes).
        
3. **Risk Management:**
    
    - Identifying potential risks (technical, business, or personnel).
        
    - Creating a plan to mitigate (reduce) or manage those risks (RMMM Plan).
        
4. **Resource Allocation:**
    
    - Assigning the right people (developers, testers) to the right tasks.
        
    - Identifying hardware/software resources needed.
        
5. **Quality Management Planning:**
    
    - Defining the quality standards and procedures (like SQA plans) to be followed.



# Error tracking

Error tracking is a project management activity used to monitor the quality of the software and the progress of the team. It is part of the "Project Tracking" phase.

- **Definition:** It is the process of recording, managing, and resolving every defect or bug found in the software.
    
- **What is tracked?**
    
    - **Errors found per module:** (Which part of the code is buggy?)
        
    - **Severity of errors:** (Is it a minor typo or a system crash?)
        
    - **Effort to fix:** (How long did it take to fix the bug?)
        
- **Why is it important?**
    
    - It helps the project manager estimate the current quality of the system.
        
    - It helps predict if the project is on schedule (if the error rate is high, the release will likely be delayed).
        
    - It provides data for future project estimation (learning from past mistakes).




# DEsign Principles

When designing software, you must follow certain core principles to ensure the system is maintainable, scalable, and robust. These principles guide the architect in making the right decisions.

### 📐 Core Design Principles

**1. Abstraction** Abstraction is the process of hiding complex implementation details and showing only the essential features of the object.

- **Goal:** To manage complexity.
    
- **Example:** When you use a `Sort()` function, you don't need to know if it uses Bubble Sort or Quick Sort internally. You just need to know it sorts the data.
    

**2. Encapsulation (Information Hiding)** Encapsulation bundles the data (variables) and the methods (functions) that operate on the data into a single unit (class) and restricts direct access to some of an object's components.

- **Goal:** To protect the data from outside interference and misuse.
    
- **Example:** A `BankAccount` object keeps its `balance` variable private. You can only change it via `deposit()` or `withdraw()` methods, which ensures you can't set a negative balance directly.
    

**3. Modularity (Divide and Conquer)** Software should be divided into separately named and addressable components, called modules, that are integrated to satisfy problem requirements.

- **Goal:** To make the software easier to build, test, and maintain. If a bug is in the "Login" feature, you only check the Login module.
    

**4. Coupling (Low Coupling)** Coupling is the degree of interdependence between software modules.

- **Principle:** Aim for **Low Coupling**. Modules should be independent. A change in Module A should not break Module B.
    

**5. Cohesion (High Cohesion)** Cohesion is the degree to which the elements inside a module belong together.

- **Principle:** Aim for **High Cohesion**. A module should do _one thing_ and do it well. All functions in a `Customer` module should relate to customers.
    

**6. Refinement** This is a top-down design strategy. You start with a high-level statement of function (e.g., "Process Order") and successively refine or decompose it into more detailed steps (e.g., "Check Inventory," "Calculate Tax," "Charge Credit Card").