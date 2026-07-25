<!-- Slide number: 1 -->
# UML DiagramsRef: Whitten et all, Systems Analysis and Design Methods 7e. McGraw-Hill Higher Education

### Notes:

<!-- Slide number: 2 -->
# Key Ideas
Introduction to UML diagrams
Use case diagram
Sequence diagram
Activity diagram

Slide ‹#›

### Notes:

<!-- Slide number: 3 -->
# UML diagram
Stands for Unified Modeling Language
A language  with notion which can be understand by all the parties involved with software
Initiated by Rational Software in 1994-95
Popular tools –
Rational Rose
Microsoft Visio
Draw.io

‹#›

### Notes:

<!-- Slide number: 4 -->
# Different Types of UML

![Hierarchy of UML 2.2 Diagrams, shown as a class diagram](GoogleShape170p4.jpg)

‹#›

### Notes:

<!-- Slide number: 5 -->
# Use case diagram

### Notes:

<!-- Slide number: 6 -->
# What is Use Case ?
Use case diagrams considers mostly as a requirement analysis tool
It identifies the uses of the system based on a case
Use indicates the actions
Case indicates the action linked with actor (who performs the action)
All the action verbs mentioned in requirement specification is an use case in this diagram
To draw the use case diagram, one need to
Identify all the entity who will performs action
And all the actions needed to support by the system

‹#›

### Notes:

<!-- Slide number: 7 -->
# Components of Use Case diagram
Use case diagram is composed of four components
Actor
Use case
System boundary
Relations

![](GoogleShape193g31283f7e1e8_0_0.jpg)
‹#›

### Notes:

<!-- Slide number: 8 -->
# Actor
The entity which performs the actions or roles in the system
Actor is responsible for giving input to the system
Responsible to use processed output for performing particular action
Actor must be connected with at least one use case

Primary actor
Secondary actor
External hardware
Other System

![Angle,Monochrome Photography,Symbol PNG Clipart - Royalty Free SVG ...](GoogleShape208p8.jpg)
Figure: Actor in Usecase
‹#›

### Notes:

<!-- Slide number: 9 -->
# Types of Actor

Primary actor
People who performs the main system functions.
For example rider of a ride sharing system. As s/he is requesting for ride, or paying the money using the system.

Secondary actor
People who performs the administrative functions.
For the aforementioned system a manager who sets the discounts is an example of Secondary actor.
‹#›

### Notes:

<!-- Slide number: 10 -->
# Types of Actor (cont.)

External hardware
Any external hardware device which is a part of the application.
If the system using amazon datastore as their database.

Other System
Any external system which has interaction with the current system.
Payment gateway is an example of such actor.
‹#›

### Notes:

<!-- Slide number: 11 -->
# Use Cases
Indicates the system functions performed by an actor
It can also describes the sequence of actions in a system
Every Use case must have a unique name
Use case must be started with principal verb
Use cases in the diagram must be enclosed by the system boundary
Every Use case should be connected with either actor or another use case
Must be represented by an ellipse
Book a ride
Figure: An Use case
‹#›

### Notes:

<!-- Slide number: 12 -->
# System Boundary
Shows how the system interacts with the user
Class in which use case are executed
Represented by the use cases within a rectangle and actors will outside of the system boundary

![](GoogleShape241p12.jpg)
Figure: The system boundary of  Use case
‹#›

### Notes:

<!-- Slide number: 13 -->
# Relation
Also Known as by communication line
It represents the connection between any two components of use case diagram
Can be of three types
Association
Generalization
Dependency
‹#›

### Notes:

<!-- Slide number: 14 -->
# Association
Connects an actor with the use case
Identifies the actor(s) are responsible/user of the use case
Represented by a straight solid line
No arrow
Not dashed or curved line
A actor must have at least one association in the diagram
An use case can be associated with zero or more actors

Book a ride

![Angle,Monochrome Photography,Symbol PNG Clipart - Royalty Free SVG ...](GoogleShape257p14.jpg)
Rider
Figure: association between an actor and an use case
‹#›

### Notes:

<!-- Slide number: 15 -->
# Generalization
Represents the parent-child relation
Represented by a straight line with hollow arrow
Can indicate the relation between
Either Actors
Or Use cases

![Angle,Monochrome Photography,Symbol PNG Clipart - Royalty Free SVG ...](GoogleShape269p15.jpg)
Rider

![Angle,Monochrome Photography,Symbol PNG Clipart - Royalty Free SVG ...](GoogleShape271p15.jpg)

![Angle,Monochrome Photography,Symbol PNG Clipart - Royalty Free SVG ...](GoogleShape273p15.jpg)
Premium Rider
Irregular Rider
Figure: Generalization relation between actors
pay online

pay with card
pay with bkash
Figure: Generalization relation between use cases
‹#›

### Notes:

<!-- Slide number: 16 -->
# Dependency
Indicates the dependency relationship between two use cases.
Two types of dependencies : Include & Extend

Include relationships
One use case (base) includes the functionality of another (inclusion case)
Supports re-use of functionality

Extend relationships
One use case (extension) extends the behavior of another (base)

Book a ride
<<include>>
Confirm the ride
Figure: Include relation
Finish the ride
<<extend>>
Give review
Figure: extend relation
‹#›

### Notes:

<!-- Slide number: 17 -->
# Dependency
Arrow Position

The arrow should be placed with the use case which will complete first.
In first example, You need to book a ride first then you can confirm. So the arrow is with book a ride.
in second example, You need to finish the ride first then you can give review or not. So arrow is with Finish the ride.
Book a ride
<<include>>
Confirm the ride
Figure: Include relation
Finish the ride
<<extend>>
Give review
Figure: extend relation
‹#›

### Notes:

<!-- Slide number: 18 -->
# Use case example 1 : Purchasing an item

![](GoogleShape326p18.jpg)
‹#›

### Notes:

<!-- Slide number: 19 -->
# How to Create a Use Case Diagram
Identifying Actors
Identifying Use Cases
Look for Common Functionality to use Include
Is it Possible to Generalize Actors and Use Cases
Optional Functions or Additional Functions
Slide ‹#›

### Notes:

<!-- Slide number: 20 -->
# How to Create a Use Case Diagram
Identifying Actors

Customer
Bank employee
NFRC Customer

![](GoogleShape341p20.jpg)

![](GoogleShape343p20.jpg)
customer

![](GoogleShape342p20.jpg)
Bank Employee
NFRC customer
Slide ‹#›

### Notes:

<!-- Slide number: 21 -->
# How to Create a Use Case Diagram
Identifying Use Cases
A good way to do this is to identify what the actors need from the system
A customer will need to
open accounts
Deposit funds
withdraw funds
request check books
Slide ‹#›

### Notes:

<!-- Slide number: 22 -->
# How to Create a Use Case Diagram
Open account

![](GoogleShape368p22.jpg)

![](GoogleShape360p22.jpg)
Convert currency
Deposit funds
NFRC customer
customer
Withdraw funds

![](GoogleShape372p22.jpg)
Open account
Bank employee
Slide ‹#›

### Notes:

<!-- Slide number: 23 -->
# How to Create a Use Case Diagram
Look for Common Functionality to use Include
find two or more use cases that share common functionality
Withdraw funds
<<include>>

![](GoogleShape383p23.jpg)
Update balance
Deposit funds
<<include>>
Slide ‹#›

### Notes:

<!-- Slide number: 24 -->
# How to Create a Use Case Diagram
Is it Possible to Generalize Actors ?

![](GoogleShape400p24.jpg)
customer

![](GoogleShape402p24.jpg)
NFRC customer
Slide ‹#›

### Notes:

<!-- Slide number: 25 -->
# How to Create a Use Case Diagram
Optional Functions or Additional Functions
There are some functions that are triggered optionally
Amount over 50000 or
Age over 55
<<extend>>
Deposit funds
Calculate bonus
Slide ‹#›

### Notes:

<!-- Slide number: 26 -->

![Screen Clipping](GoogleShape422p26.jpg)

![](GoogleShape424p26.jpg)

![](GoogleShape425p26.jpg)

### Notes:

<!-- Slide number: 27 -->
# Use case Description
Every use case diagram must have its description
Usually description is presented in tabular form
The diagram should have a unique id
Typically the description form include the fields –
Use case Name,  Id, Actor(s), Description, Precondition, Postcondition, Action Flow, Exceptions, etc.
All the fields might not be available for all the diagrams.

![](GoogleShape433p17.jpg)
Figure: An Use case description table
‹#›

### Notes:

<!-- Slide number: 28 -->

![](GoogleShape442p29.jpg)
#

‹#›

### Notes:

<!-- Slide number: 29 -->
# Use case Description (cont.)
Each use case has a name and number
The priority may be assigned to indicate the relative significance of the use case in the overall system.
The actor refers a person, another software system, or a hardware device that interacts with the system to achieve a useful goal.
Trigger - the event that causes the use case to begin. A trigger can be an external trigger, such as a customer placing an order, and temporal trigger, such as a DVD becoming overdue at the video store or time to pay the rent.
Preconditions define the state the system must be in before the use case commences
‹#›

### Notes:

<!-- Slide number: 30 -->
# Use case Description (cont.)
Normal Course
description of the major steps that are performed to execute the response to the event
the inputs used for the steps
the outputs produced by the steps.
The normal course lists the steps that are performed when everything flows smoothly in the system.
This is sometimes called the “happy path” because there are no problems or issues that arise when the steps are able to be followed normally.
Alternative Courses
The steps followed for alternative paths through the use case are outlined.
Alternative courses are included to depict branches in logic that also will lead to a successful conclusion of the use case.
Notice that the location where the branch in logic from the normal course occurred is clearly stated.
‹#›

### Notes:

<!-- Slide number: 31 -->
# Use case Description (cont.)
Postconditions
final products of this use case.
also serve to define the preconditions for the next use case in the series.
Exceptions
a use case should describe any error conditions or exceptions that may occur as the use case steps are performed.
These are not normal branches in decision logic, but are unusual occurrences or errors that could potentially be encountered and will lead to an unsuccessful result.
Summary Inputs and Outputs
The final section of the use case summarizes the set of major inputs and outputs to the steps of the use case.
Each of the major inputs and outputs to the use case are listed, along with its source or destination
‹#›

### Notes:

<!-- Slide number: 32 -->

![Screen Clipping](GoogleShape468p74.jpg)

### Notes:

<!-- Slide number: 33 -->
# Practice
Hospital Management System is a large system including several subsystems or modules providing variety of functions. UML use case diagram example below shows actor and use cases for a hospital's reception.
Purpose: Describe major services (functionality) provided by a hospital's reception.
Hospital Reception subsystem or module supports some of the many job duties of hospital receptionist. Receptionist schedules patient's appointments and admission to the hospital, collects information from patient upon patient's arrival and/or by phone. For the patient that will stay in the hospital ("inpatient") she or he should have a bed allotted in a ward. Receptionists might also receive patient's payments, record them in a database and provide receipts, file insurance claims and medical reports.
Slide ‹#›

### Notes:

<!-- Slide number: 34 -->

![Screen Clipping](GoogleShape481p28.jpg)
Slide ‹#›

### Notes:

<!-- Slide number: 35 -->
# Exercise 1
Bank customer has to provide pin for login, verified by bank, there could be mistake while entering the pin. An error message will be shown if there is a mistake. Customer can do transactions like (fund transfer, withdraw, change pin, balance check, deposit) etc., ATM Machine will provide a print out if customer wants to get a receipt of their transaction considering some charges. Charges will also apply for each transaction. There is system administrator who monitors users’ transaction and report if any suspicious activities is noticed.
Slide ‹#›

### Notes:

<!-- Slide number: 36 -->
# Exercise 2
Suppose, you have been hired to design a course management system. The requirements for the system are as follows:
Two types of students will use this system, BSc, and MSc. Students will be able to log in to the system using a username and password. The system will check whether the credentials are valid and will give an error message if they are incorrect. Students will be able to add courses they want to complete next semester. The system will check whether the course has remaining seats and if the student has completed all pre-requisite courses to take the course. The system might suggest additional courses to the student when taking a course. After a student has completed adding courses then he/she might request for advising, and an adviser will approve the advising request. Students can view their routine and grade sheet. BSc students can add project proposals whereas MSc students can add thesis proposals and those will be approved by the advisor. Students can also make payments. Payments can be made via card or bank transfer, payment must be verified by the system.

‹#›

### Notes:

<!-- Slide number: 37 -->
# Exercise 3
In a Bangladeshi courier service system, the process begins when a customer registers or logs into the platform to access its services. To place a courier order, the customer must first be authenticated, after which they can enter shipment details, choose delivery preferences, and proceed to payment. The order is only confirmed once the payment is successfully completed through an integrated online gateway. Upon confirmation, the system automatically generates a courier slip containing parcel and tracking information. The courier staff receive the new orders in their dashboard and proceed to schedule pickups based on location and time preferences. Meanwhile, the admin monitors overall operations, manages users and branch logistics, and addresses any complex issues or customer complaints. Customers can track their shipments in real-time through the system interface. If the parcel has not yet been dispatched, they may also be able to cancel the order. Delivery agents are assigned scheduled pickups and are responsible for updating the parcel’s status at each stage of its journey. Before finalizing the delivery, they must log status updates and confirm receipt using verification methods like OTP or customer signature. This coordinated workflow ensures efficient parcel handling and transparency for both customers and service providers.
‹#›

### Notes:
%% Use Case Diagram graph TD A[Customer] -- Registers/Logs In --> UC1(Authenticate User) A -- Places Order --> UC2(Place Courier Order) UC2 -- Includes --> UC3(Enter Shipment Details) UC2 -- Includes --> UC4(Choose Delivery Preferences) UC2 -- Includes --> UC5(Make Payment) UC5 -- Extends --> UC6(Process Online Payment) UC2 -- Includes --> UC7(Confirm Order) UC7 -- Extends --> UC8(Generate Courier Slip) A -- Tracks Shipment --> UC9(Track Shipment) A -- Cancels Order --> UC10(Cancel Order) B[Courier Staff] -- Receives New Order --> UC11(Receive New Order) B -- Schedules Pickup --> UC12(Schedule Pickup) C[Delivery Agent] -- Assigns Pickup --> UC13(Assign Pickup) C -- Updates Parcel Status --> UC14(Update Parcel Status) C -- Confirms Delivery --> UC15(Confirm Delivery) D[Admin] -- Monitors Operations --> UC16(Monitor Overall Operations) D -- Manages Users --> UC17(Manage Users) D -- Manages Branch Logistics --> UC18(Manage Branch Logistics) D -- Addresses Issues/Complaints --> UC19(Address Issues/Complaints)

<!-- Slide number: 38 -->
UML Activity Diagrams

### Notes:

<!-- Slide number: 39 -->
# OUTLINE
Introduction
Activity Diagrams - notation
How to apply activity diagrams
Guidelines
Examples

### Notes:

<!-- Slide number: 40 -->
# What is an Activity Diagram?
An Activity Diagram is one of the Behavior diagrams.
Activity modelling is the sequence and conditions for coordinating lower-level behaviors, rather than which  classifiers own those behaviors.
These are commonly called control flow and object flow models.
The behaviors coordinated by these models can be initiated because other behaviors finish executing, because objects and data become available, or because events occur external to the flow.
A UML Activity Diagram shows sequential and parallel activities in a process.
Useful for modelling:
Business processes
Workflows
Data flows
Complex algorithms

### Notes:

<!-- Slide number: 41 -->
# Initial and Final Nodes
Initial Node:
An initial node is a control node at which flow starts when the activity is invoked.
An activity may have more than one initial node.

Final Node:
An activity may have more than one activity final node;
       the first one reached stops all flows in the activity.

![](GoogleShape528p35.jpg)

![](GoogleShape529p35.jpg)

### Notes:

<!-- Slide number: 42 -->
# Action
Action:
An action represents a single step within an activity that is not further decomposed within the activity.
An activity represents a behavior that is composed of individual elements that are actions.
An action is simple from the point of view of the activity containing it, but may be complex in its effect and not be atomic.
An activity can be reused in many places, whereas an instance of an action is only used once at a particular
An action will not begin execution until all of its input conditions are satisfied.

![](GoogleShape536p36.jpg)

### Notes:

<!-- Slide number: 43 -->
# Merge and Decision Nodes
Merge Node:
A merge node is a control node that brings together multiple alternate flows.
It is not used to synchronize concurrent flows but to accept one among several alternate flows.
A merge node has multiple incoming edges and a single outgoing edge.

Decision Node:
A decision node accepts tokens on an incoming edge and presents them to multiple outgoing edges.
Which of the edges is actually traversed depends on the evaluation of the guards on the outgoing edges.

![](GoogleShape544p37.jpg)

![](GoogleShape543p37.jpg)

### Notes:

<!-- Slide number: 44 -->
# Join and Fork Nodes

![](GoogleShape555p38.jpg)
Join Node:
A join node is a control node that synchronizes multiple flows.
A join node has multiple incoming edges and one outgoing edge.

Fork Node:
A fork node is a control node that splits a flow into multiple concurrent flows.
A fork node has one incoming edge and multiple outgoing edges.

![](GoogleShape556p38.jpg)

![](GoogleShape551p38.jpg)

![](GoogleShape552p38.jpg)
Fork Node
Join Node

### Notes:

<!-- Slide number: 45 -->
# Object Node
Object Node:
An object node is an activity node that indicates an instance of a particular classifier, possibly in a particular state, may be available at a particular point in the activity.
Object nodes can be used in a variety of ways, depending on where objects are flowing from and to.

![](GoogleShape564p39.jpg)

### Notes:

<!-- Slide number: 46 -->
# NOTE
Note:
A note (comment) gives the ability to attach various remarks to elements.
A comment carries no semantic force, but may contain information that is useful to a modeler.

![](GoogleShape571p40.jpg)

### Notes:

<!-- Slide number: 47 -->
# Business Process Modelling
Example: Parcel shipping

The process of shipping a parcel is non-trivial; there are many parties involved (customer, driver,. . . ) and many steps.

The process can be captured by a Use Case diagram, but activity diagrams are great example of “a picture being worth a thousand words”.

Object nodes are useful for illustrating what is moving around.

### Notes:

<!-- Slide number: 48 -->

![](GoogleShape582p42.jpg)

### Notes:

<!-- Slide number: 49 -->
# Activity Diagram of order management system

![](GoogleShape587p43.jpg)

### Notes:

<!-- Slide number: 50 -->
# Guideline for Activity Modelling
The technique proves most valuable for very complex processes, usually involving many parties.
On a first overview “level 0” diagram, keep all the actions at a very high level of abstraction, so that the diagram is short. Then expand details in sub-diagrams at the “level 1” level,. . . etc.
Try to make the level of abstraction of action nodes roughly equal within a diagram (Very different levels of abstraction might be a node labelled “Deliver Order” and a node labelled “Calculate Tax”).

### Notes:

<!-- Slide number: 51 -->

![](GoogleShape600p45.jpg)
# More Examples: Recycling Activity Diagrams

### Notes:

<!-- Slide number: 52 -->
# Swimlanes
Swimlanes (or activity partitions) indicate where activities take place.
Swimlanes can also be used to identify areas at the technology level where activities are carried out
Swimlanes allow the partition an activity diagram so that parts of it appear in the swimlane relevant to that element in the partition

### Notes:

<!-- Slide number: 53 -->
# Swimlanes
Partitions may be constructed on the basis of:

the class and actor doing the activity
Partitioning by class and actor can help to identify new associations that have not been documented in the class model
the use case the activity belongs to
Partitioning by use cases can help document how use cases interact

### Notes:

<!-- Slide number: 54 -->
# Example Activity
Process Order - Problem Description
Once the order is received, the activities split into two parallel sets of activities. One side fills and sends the order while the other handles the billing.

On the Fill Order side, the method of delivery is decided conditionally. Depending on the condition either the Overnight Delivery activity or the Regular Delivery activity is performed.

Finally the parallel activities combine to close the order.

![](GoogleShape619gb815c2ce27_0_9.jpg)

### Notes:

<!-- Slide number: 55 -->
# Example Swimlanes

![](GoogleShape627p49.jpg)

### Notes:

<!-- Slide number: 56 -->

![](GoogleShape632p50.jpg)

### Notes:

<!-- Slide number: 57 -->

![](GoogleShape637p51.jpg)

### Notes:

<!-- Slide number: 58 -->

![](GoogleShape642p52.jpg)

### Notes:

<!-- Slide number: 59 -->

![](GoogleShape647p54.jpg)

### Notes:

<!-- Slide number: 60 -->
Student Assistance Fund (SAF) authorization has a number of steps in its approval process. A  SAF authorization form is used in most universities to approve funding for students to aid their  studies. Suppose a student fills out a blank form and sends it to his or her departmental  chairperson for a signature. If the amount of funds requested by the student is small (under Tk.  10,000), then the chairperson signs the form and routes it to accounts payable to be input into  the accounting system. The system cuts a check that is sent to the student for the right amount,  and after the check is cashed, the form is filed away with the canceled check. If the check is  not cashed within 30 days, the form expires. When the amount of the requested fund is large  (over Tk. 10,000), the chairperson signs the form and sends it to the chief financial officer  along with a paragraph explaining the reason for the grant, and the chief financial officer will  sign the form and pass it along to accounts payable. Both the chairperson and the chief financial  officer can reject the SAF authorization form if they do not feel that the reasons for seeking  funding are reasonable. In this case, the student can change the form to include more  explanation or decide to pay the entire fee.
Design an activity diagram based on the above information.

### Notes: