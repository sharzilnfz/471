<!-- Slide number: 1 -->
# <<Include>> in Use case
The include relationship could be used:
To simplify large use case by splitting it into several use cases
To extract common parts of the behaviors of two or more use cases.
The base use case is incomplete without the included use case.
The included use case is mandatory and not optional.
Slide ‹#›

### Notes:

<!-- Slide number: 2 -->
# <<Include>> in Use case

![Screen Clipping](GoogleShape254p2.jpg)
Slide ‹#›

### Notes:

<!-- Slide number: 3 -->
# <<Include>> in Use case

![Screen Clipping](GoogleShape262p3.jpg)
Slide ‹#›

### Notes:

<!-- Slide number: 4 -->
# <<Include>> in Use case

![Screen Clipping](GoogleShape269p4.jpg)

![Screen Clipping](GoogleShape270p4.jpg)
Slide ‹#›

### Notes:

<!-- Slide number: 5 -->
# <<extend>> in Use case
Extends relationship is "optional"!
It adds further functionality to the base use case which may be restricted by constraints
The extending use case is dependent on the extended (base) use case.
The extended (base) use case must be meaningful on its own.
Slide ‹#›

### Notes:

<!-- Slide number: 6 -->
# <<extend>> in Use case

![](GoogleShape285p6.jpg)
Slide ‹#›

### Notes:

<!-- Slide number: 7 -->
# <<extend>> in Use case

![Screen Clipping](GoogleShape292p7.jpg)
Slide ‹#›

### Notes:

<!-- Slide number: 8 -->
# <<extend>> in Use case

![Screen Clipping](GoogleShape299p8.jpg)
Slide ‹#›

### Notes:

<!-- Slide number: 9 -->
# How to Create a Use Case Diagram
Identifying Actors
Identifying Use Cases
Look for Common Functionality to use Include
Is it Possible to Generalize Actors and Use Cases
Optional Functions or Additional Functions
Slide ‹#›

### Notes:

<!-- Slide number: 10 -->
# How to Create a Use Case Diagram
Identifying Actors

Customer
Bank employee
NFRC Customer

![](GoogleShape314p10.jpg)

![](GoogleShape316p10.jpg)
customer

![](GoogleShape315p10.jpg)
Bank Employee
NFRC customer
Slide ‹#›

### Notes:

<!-- Slide number: 11 -->
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

<!-- Slide number: 12 -->
# How to Create a Use Case Diagram
Open account

![](GoogleShape341p12.jpg)

![](GoogleShape333p12.jpg)
Convert currency
Deposit funds
NFRC customer
customer
Withdraw funds

![](GoogleShape345p12.jpg)
Open account
Bank employee
Slide ‹#›

### Notes:

<!-- Slide number: 13 -->
# How to Create a Use Case Diagram
Look for Common Functionality to use Include
find two or more use cases that share common functionality
Withdraw funds
<<include>>

![](GoogleShape356p13.jpg)
Update balance
Deposit funds
<<include>>
Slide ‹#›

### Notes:

<!-- Slide number: 14 -->
# How to Create a Use Case Diagram
Is it Possible to Generalize Actors ?

![](GoogleShape373p14.jpg)
customer

![](GoogleShape375p14.jpg)
NFRC customer
Slide ‹#›

### Notes:

<!-- Slide number: 15 -->
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

<!-- Slide number: 16 -->

![Screen Clipping](GoogleShape395p16.jpg)

### Notes:

<!-- Slide number: 17 -->
# Practice
Hospital Management System is a large system including several subsystems or modules providing variety of functions. UML use case diagram example below shows actor and use cases for a hospital's reception.
Purpose: Describe major services (functionality) provided by a hospital's reception.
Hospital Reception subsystem or module supports some of the many job duties of hospital receptionist. Receptionist schedules patient's appointments and admission to the hospital, collects information from patient upon patient's arrival and/or by phone. For the patient that will stay in the hospital ("inpatient") she or he should have a bed allotted in a ward. Receptionists might also receive patient's payments, record them in a database and provide receipts, file insurance claims and medical reports.
Slide ‹#›

### Notes:

<!-- Slide number: 18 -->

![Screen Clipping](GoogleShape408p18.jpg)
Slide ‹#›

### Notes:

<!-- Slide number: 19 -->
UML Use Case diagram for Travel Agency is shown below. The various participants of the same are detailed below:
Actors: - Customer, Agent

The corresponding use cases for these actors are:-
Customer: Make Enquiry, Plan Trip, Select a Trip and Finalize It, Make Payment, Cancel Trip, Receive Ticket, Get Refund
Agent: Provide Enquiry Details, Give Different Trip Details, Receive Payment, Cancel Tickets, Book Ticket, Give Discount If Any, Refund Money
Other relationships:
While a customer makes a payment will receive the ticket and get a refund for the cancelation of the ticket.
The agent will book a ticket while receiving payment and give a discount if applied. It also refunds money while canceling tickets.
Customer and Agent can be divided into two types, new and existing.
**You have to show include, extern, and generalization relationship.

### Notes:

<!-- Slide number: 20 -->

![](GoogleShape419p20.jpg)
#
Slide ‹#›

### Notes:

<!-- Slide number: 21 -->
#
Bank customer has to provide pin for login, verified by bank, there could be mistake while entering the pin, customer can do transactions like (fund transfer, withdraw, change pin, balance check, deposit) etc., ATM Machine will provide a print out if customer wants to get a receipt of their transaction considering some charges, charges will also apply for each transaction. There is system administrator who monitors users’ transaction and report if any suspicious activities is noticed. Also maintains ATM machine money loading and maintenance.
Slide ‹#›

### Notes: