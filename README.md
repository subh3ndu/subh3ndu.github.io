# Software Engineering

# Module - 1

## 1. Explain interactive and incremental development in agile development?

Ans:-

### Incremental development

-   Incremental development is a development approach that slices the product into fully working slices that are called increments.
-   Each new increment builds on top of the existing released functionality.

#### Example: Ecommerce Website

-   Consider a team building an ecommerce website using incremental development. The final target product has search, product information, a shopping basket, checkout, favourites, and customer reviews.

-   For the first released increment, the team builds the basic functionality to buy a product. It includes search, product information, adding products to a shopping basket and checkout. This first slice would only be released once it’s complete.

-   The second released increment builds on that basic functionality, and would add another capability such as favourites. The would be released when the favourites functionality is complete.

-   The third released increment adds customer reviews once that is complete, and so on.

<p align='center'>
	<img src='https://agility.im/wp-content/uploads/2020/06/Incr-vs-iterative.png' />
</p>

### Iterative development

-   Iterative development is when teams gradually build up the features and functions but don’t wait until each of these is complete before releasing.
-   They release a basic version of each feature and the add to that feature in subsequent iterative releases, usually based on feedback from the basic version released.

#### Example: Ecommerce Website

-   Assume a team building the same ecommerce website using an iterative process.

-   The first release has a really stripped back version of all the required functionality; namely search, product information, a shopping basket, checkout, favourites, and customer reviews.

-   For the second iterative release, the team would improve some of the existing basic functionality, taking into account feedback from stakeholders or customer, or other inputs such as analytics.

-   On every subsequent iterative release, new ideas and requirements are added or low value/usage areas may be removed.

## 2. How Agile process is differed from classical waterfall process?

Ans:-

|                    | Waterfall                                                                                                                                                                                                                                                                                     | Agile                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Timeline           | Waterfall has a fixed timeline. The idea is that the start and finish of the project are already mapped out from the beginning.                                                                                                                                                               | Agile is a lot more flexible and accounts for experimenting with different directions. Rather than a fixed timeline, the schedule adapts as the project progresses. The Agile Manifesto , an online document released in 2001 by a group of software developers, says team members are expected to, “Deliver working software frequently, from a couple of weeks to a couple of months, with a preference to the shorter timescale.” |
| Client Involvement | Once the end goal is established, Waterfall does not involve the client or project owner during the process, apart from specific check-ins or for deliverables. The course of the project is outlined from the start, so incorporating client feedback is not an ongoing part of the process. | A fundamental part of Agile is including clients in the project development at every step. The Agile Manifesto states, “Our highest priority is to satisfy the customer through early and continuous delivery of valuable software.” Therefore, business owners are expected to be involved and give feedback to the software development team as they progress through the different phases of the project.                         |
| Flexibility        | Waterfall is not as flexible as Agile because each phase needs to be fully completed before moving on to the next phase. The project is also planned out ahead of time, making this management system ideal for teams with a clear vision of where they are headed from start to finish.      | Flexibility is built into the Agile method. Agile values short bursts of work, which are called sprints. The method welcomes adapting to different directions, incorporating new information even at a later stage of the project.                                                                                                                                                                                                   |
| Budget             | Fixed. The budget for projects using the Waterfall methodology is generally fixed. Because the project is determined from start to finish, there is less room to change the budget mid-project.                                                                                               | Flexible. Agile is open to adaptation, encourages experimentation and welcomes changes of direction, even in later phases of the project. Because of this, the budget tends to be more flexible.                                                                                                                                                                                                                                     |

## 3. Why Extreme program is called “Extreme”?

Ans:-

## 4. Explain why spiral model is called meta model?

Ans:-
The Spiral model is called a Meta-Model because it subsumes all the other SDLC models.

For example:

-   a single loop spiral actually represents the Iterative Waterfall Model.
-   The spiral model incorporates the stepwise approach of the Classical Waterfall Model.
-   The spiral model uses the approach of the Prototyping Model by building a prototype at the start of each phase as a risk-handling technique.
-   Also, the spiral model can be considered as supporting the evolutionary model – the iterations along the spiral can be considered as evolutionary levels through which the complete system is built.

# Module - 2

# Module - 3

## 1. What do you mean by coupling? Describe the different types of coupling?

Ans:-

### Coupling:-

Coupling is a measure that defines the level of inter-dependability among modules of a program.

-   It tells at what level the modules interfere and interact with each other.
-   The lower the coupling, the better the program.
-   There are five levels of coupling, namely -

1. **Content coupling :-**
    - When a module can directly access or modify or refer to the content of another module, it is called content level coupling.
2. **Common coupling :-**
    - When multiple modules have read and write access to some global data, it is called common or global coupling.
3. **Control coupling :-**
    - Two modules are called control-coupled if one of them decides the function of the other module or changes its flow of execution.
4. **Stamp coupling :-**
    - When multiple modules share common data structure and work on different part of it, it is called stamp coupling.
5. **Data coupling :-**
    - Data coupling is when two modules :-interact with each other by means of passing data (as parameter). If a module passes data structure as parameter, then the receiving module should use all its components.
6. **External Coupling :-**
    - External Coupling arises when two modules share an externally imposed data format, communication protocols, or device interface. This is related to communication to external tools and devices.

Ideally, no coupling is the best.

<p align="center">
	<img src = "https://static.javatpoint.com/tutorial/software-engineering/images/software-engineering-coupling-and-cohesion2.png" />
</p>

## 2. What do you mean by cohesion? Describe the different types of cohesion.

Ans: -

### Cohesion:-

-   Cohesion is a measure that defines the degree of intra-dependability within elements of a module. The greater the cohesion, the better is the program design.
-   There are seven types of cohesion, namely –

1. **Co-incidental cohesion :-**

    - It is unplanned and random cohesion, which might be the result of breaking the program into smaller modules for the sake of modularization.
    - Because it is unplanned, it may serve confusion to the programmers and is generally not- accepted.

2. **Logical cohesion :-**

    - When logically categorized elements are put together into a module, it is called logical cohesion.

3. **Temporal Cohesion :-**

    - When elements of module are organized such that they are processed at a similar point in time, it is called temporal cohesion.

4. **Procedural cohesion :-**

    - When elements of module are grouped together, which are executed sequentially in order to perform a task, it is called procedural cohesion.

5. **Communicational cohesion :-**

    - When elements of module are grouped together, which are executed sequentially and work on same data (information), it is called communicational cohesion.

6. **Sequential cohesion :-**

    - When elements of module are grouped because the output of one element serves as input to another and so on, it is called sequential cohesion.

7. **Functional cohesion :-**

    - It is considered to be the highest degree of cohesion, and it is highly expected. - Elements of module in functional cohesion are grouped because they all contribute to a single well-defined function.
    - It can also be reused.

<p align="center">
  <img src="https://static.javatpoint.com/tutorial/software-engineering/images/software-engineering-coupling-and-cohesion7.png" />
</p>

## 3. Describe different types of software design strategy.

Ans:-

-   Software design is a process to conceptualize the software requirements into software implementation.
-   Software design takes the user requirements as challenges and tries to find optimum solution.
-   While the software is being conceptualized, a plan is chalked out to find the best possible design for implementing the intended solution.

-   There are multiple variants of software design. Let us study them briefly:

### Structured Design :-

-   Structured design is a conceptualization of problem into several well-organized elements of solution. It is basically concerned with the solution design. Benefit of structured design is, it gives better understanding of how the problem is being solved. Structured design also makes it simpler for designer to concentrate on the problem more accurately.

-   Structured design is mostly based on ‘divide and conquer’ strategy where a problem is broken into several small problems and each small problem is individually solved until the whole problem is solved.

-   The small pieces of problem are solved by means of solution modules. Structured design emphasis that these modules be well organized in order to achieve precise solution.

-   These modules are arranged in hierarchy. They communicate with each other. A good structured design always follows some rules for communication among multiple modules, namely -

1. **Cohesion** - grouping of all functionally related elements.

2. **Coupling** - communication between different modules.

A good structured design has high cohesion and low coupling arrangements.

### Function Oriented Design :-

-   In function-oriented design, the system is comprised of many smaller sub-systems known as functions. These functions are capable of performing significant task in the system. The system is considered as top view of all functions.

-   Function oriented design inherits some properties of structured design where divide and conquer methodology is used.

-   This design mechanism divides the whole system into smaller functions, which provides means of abstraction by concealing the information and their operation.. These functional modules can share information among themselves by means of information passing and using information available globally.

-   Another characteristic of functions is that when a program calls a function, the function changes the state of the program, which sometimes is not acceptable by other modules. Function oriented design works well where the system state does not matter and program/functions work on input rather than on a state.

-   **Design Process :**

    1.  The whole system is seen as how data flows in the system by means of data flow diagram.

    2.  DFD depicts how functions changes data and state of entire system.

    3.  The entire system is logically broken down into smaller units known as functions the basis of their operation in the system.

    4.  Each function is then described at large.

### Object Oriented Design :-

-   Object oriented design works around the entities and their characteristics instead of functions involved in the software system. This design strategies focuses on entities and its characteristics. The whole concept of software solution revolves around the engaged entities.

-   Let us see the important concepts of Object Oriented Design:

1.  **Objects**

    -   All entities involved in the solution design are known as objects. For example, person, banks, company and customers are treated as objects. Every entity has some attributes associated to it and has some methods to perform on the attributes.

2.  **Classes**

    -   A class is a generalized description of an object. An object is an instance of a class. Class defines all the attributes, which an object can have and methods, which defines the functionality of the object.

    -   In the solution design, attributes are stored as variables and functionalities are defined by means of methods or procedures.

3.  **Encapsulation**

    -   In OOD, the attributes (data variables) and methods (operation on the data) are bundled together is called encapsulation. Encapsulation not only bundles important information of an object together, but also restricts access of the data and methods from the outside world. This is called information hiding.

4.  **Inheritance**

    -   OOD allows similar classes to stack up in hierarchical manner where the lower or sub-classes can import, implement and re-use allowed variables and methods from their immediate super classes. This property of OOD is known as inheritance. This makes it easier to define specific class and to create generalized classes from specific ones.

5.  **Polymorphism**

    -   OOD languages provide a mechanism where methods performing similar tasks but vary in arguments, can be assigned same name. This is called polymorphism, which allows a single interface performing tasks for different types. Depending upon how the function is invoked, respective portion of the code gets executed.

6.  **Design Process :-**
    Software design process can be perceived as series of well-defined steps. Though it varies according to design approach (function oriented or object oriented, yet It may have the following steps involved:

    -   A solution design is created from requirement or previous used system and/or system sequence diagram.

    -   Objects are identified and grouped into classes on behalf of similarity in attribute characteristics.

    -   Class hierarchy and relation among them is defined.

    -   Application framework is defined.

## 4. What do you mean by Function Oriented design? Describe different types of design notation used in Function Oriented design.

Ans:-

-   Function Oriented design is a method to software design where the model is decomposed into a set of interacting units or modules where each unit or module has a clearly defined function. Thus, the system is designed from a functional viewpoint.

-   **Design Notations** are primarily meant to be used during the process of design and are used to represent design or design decisions. For a function-oriented design, the design can be represented graphically or mathematically by the following:

<p align="center">
	<img src = "https://static.javatpoint.com/tutorial/software-engineering/images/software-engineering-function-oriented-design.png" />
</p>

### 1. Data Flow Diagram :-

1. Data-flow design is concerned with designing a series of functional transformations that convert system inputs into the required outputs. The design is described as data-flow diagrams. These diagrams show how data flows through a system and how the output is derived from the input through a series of functional transformations.

2. Data-flow diagrams are a useful and intuitive way of describing a system. They are generally understandable without specialized training, notably if control information is excluded. They show end-to-end processing. That is the flow of processing from when data enters the system to where it leaves the system can be traced.

3. Data-flow design is an integral part of several design methods, and most CASE tools support data-flow diagram creation. Different ways may use different icons to represent data-flow diagram entities, but their meanings are similar.

4. The notation which is used is based on the following symbols:

![image](https://static.javatpoint.com/tutorial/software-engineering/images/software-engineering-function-oriented-design2.png)

### 2. Data Dictionaries :-

1. A data dictionary lists all data elements appearing in the DFD model of a system. The data items listed contain all data flows and the contents of all data stores looking on the DFDs in the DFD model of a system.

2. A data dictionary lists the objective of all data items and the definition of all composite data elements in terms of their component data items. For example, a data dictionary entry may contain that the data grossPay consists of the parts regularPay and overtimePay.

$$
grossPay = regularPay + overtimePay
$$

For the smallest units of data elements, the data dictionary lists their name and their type.

3. A data dictionary plays a significant role in any software development process because of the following reasons:

    - A Data dictionary provides a standard language for all relevant information for use by engineers working in a project. A consistent vocabulary for data items is essential since, in large projects, different engineers of the project tend to use different terms to refer to the same data, which unnecessarily causes confusion.

    - The data dictionary provides the analyst with a means to determine the definition of various data structures in terms of their component elements.

### 3. Structured Charts :-

1. It partitions a system into block boxes. A Black box system that functionality is known to the user without the knowledge of internal design.

<p align="center">
	<img src="https://static.javatpoint.com/tutorial/software-engineering/images/software-engineering-function-oriented-design4.png" />
</p>

2. Structured Chart is a graphical representation which shows:

    - System partitions into modules
    - Hierarchy of component modules
    - The relation between processing modules
    - Interaction between modules
    - Information passed between modules

    ![image](https://static.javatpoint.com/tutorial/software-engineering/images/software-engineering-function-oriented-design5.png)

### 4. Pseudo Code :-

1.  Pseudo-code notations can be used in both the preliminary and detailed design phases.

2.  Using pseudo-code, the designer describes system characteristics using short, concise, English Language phases that are structured by keywords such as If-Then-Else, While-Do, and End.

## 5. What do you mean by inheritance? What are the different types of Inheritance?

Ans:-

1. Inheritance is the procedure in which one class inherits the attributes and methods of another class.

2. The class whose properties and methods are inherited is known as the Parent class. And the class that inherits the properties from the parent class is the Child class.

3. **Types of Inheritance:** 
There are different types of inheritance viz., Single inheritance, Multiple inheritance, Multilevel inheritance, hybrid inheritance, and hierarchical inheritance. 

    1. **Single Inheritance:** When a derived class inherits only from one base class, it is known as single inheritance. 
    2. **Multiple Inheritance:** When a derived class inherits from multiple base classes it is known as multiple inheritances. 
    3. **Hierarchical inheritance:** 
        - When more than one derived class is created from a single base class, it is known as
        - Hierarchical inheritance. 
    4. **Multilevel Inheritance:** 
        - The transitive nature of inheritance is itself reflected by this form of inheritance. 
        - When a class is derived from a class that is a derived class then it is referred to as multilevel inheritance. 
    5. **Hybrid inheritance:** 
        - When there is a combination of more than one type of inheritance, it is known as hybrid inheritance.

        - Hence, it may be a combination of Multilevel and Multiple inheritances or Hierarchical and Multilevel inheritance or

Hierarchical, Multilevel and Multiple inheritances.

## 6. What are the Differences between physical DFD and logical DFD.

1. **Logical DFD :-**

    - A Logical DFD focuses on the business and business activities, while a physical DFD looks at how a system is implemented.

    - So while any data flow diagram maps out the flow of information for a process or system, the logical diagram provides the “what” and the physical provides the “how.” They are two different perspectives on the same data flow, each designed to visualize and improve the system.

    - The logical DFD describes the business events that take place and the data required for each event.

<p>
	<img src="https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/seo/data-flow-diagram/discovery/data-flow-diagram-1.svg" />
</p>

2. **Physical DFD:-**

    - Physical DFD, which depicts how the data system will work, such as the hardware, software, paper files and people involved. In tandem, the logical and physical can fully visualize the current state and model the new state to be considered and then implemented.

<p>
	<img src="https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/seo/data-flow-diagram/discovery/data-flow-diagram-2.svg" />
</p>

# Module - 4

## 1. Describe the maturity levels of SEI CMMI.

## 2. Describe different types of maintenance based on their characteristics.

## 3. Describe different types of maintenance activities.

## 4. What do you mean by reverse engineering? What is the importance of reverse engineering? What are the uses of reverse engineering?

## 5. Describe software reliability model techniques.

## 6. Describe in details the software reusability process.
