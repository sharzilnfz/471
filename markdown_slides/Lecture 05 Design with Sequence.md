<!-- Slide number: 1 -->
UML Sequence diagram

### Notes:

<!-- Slide number: 2 -->
# Sequence Diagram(make a phone call)
Caller
Phone
Recipient

Picks up

Dial tone

Dial

Ring
Ring notification

Picks up

Hello

### Notes:

<!-- Slide number: 3 -->

![](GoogleShape1311p3.jpg)
Person kicks the cat
Cat reports to inspector
Inspector reports to Policeman
Policeman arrests person
Slide ‹#›

### Notes:

<!-- Slide number: 4 -->

![](GoogleShape1318p4.jpg)
Slide ‹#›

### Notes:

<!-- Slide number: 5 -->

![](GoogleShape1324p5.jpg)
Slide ‹#›

### Notes:

<!-- Slide number: 6 -->
# Sequence Diagrams
Dynamic model
Illustrate the objects that participate in a use-case
Show the sequence of messages that pass between objects for a particular use-case over time
Example: order food, change tv channel
It models a single scenario executing in the system
Slide ‹#›

### Notes:

<!-- Slide number: 7 -->

![Screen Clipping](GoogleShape1338p7.jpg)
#

### Notes:

<!-- Slide number: 8 -->
# Sequence Diagrams – Object Life Spans
Creation
Create message
Object life starts at that point
Activation
Symbolized by rectangular stripes
Place on the lifeline where object is activated.
Rectangle also denotes when object is deactivated.
Deletion
Placing an ‘X’ on lifeline
Object’s life ends at that point

A

Create

B

X
Return
Deletion
Lifeline

   Activation bar

### Notes:

<!-- Slide number: 9 -->
# Sequence Diagram
Sequence diagrams demonstrate the behavior of objects in a use case by describing the objects and the messages they pass.

The horizontal dimension shows the objects participating in the interaction.

The vertical arrangement of messages indicates their order.

The labels may contain the seq. #  to indicate concurrency.

![](GoogleShape1372p9.jpg)
Message

### Notes:

<!-- Slide number: 10 -->
# Sequence Diagram for Patient appointment Use Case

![](GoogleShape1383p10.jpg)
Slide ‹#›

### Notes:

<!-- Slide number: 11 -->
# Sequence Diagram for Print Invoice use case

![](GoogleShape1389p11.jpg)

### Notes:

<!-- Slide number: 12 -->
# Example: Use Case Diagram of the Vending Machine

### Notes:

<!-- Slide number: 13 -->
# Sequence Diagramfor Deposit Money Use Case

### Notes:

<!-- Slide number: 14 -->
# System Sequence Diagramfor Make Selection Use Case

### Notes:

<!-- Slide number: 15 -->
# System Sequence Diagramfor Cancellation Use Case

### Notes:

<!-- Slide number: 16 -->
# System Sequence Diagramfor Update Database Use Case

### Notes:

<!-- Slide number: 17 -->
# Building a Sequence Diagram
Determine the context of the sequence diagram
Identify the participating objects
Set the lifeline for each object
Add messages
Add execution occurrence on each object’s lifeline
Validate the sequence diagram
Slide ‹#›

### Notes:

<!-- Slide number: 18 -->
# Alternate / if-else scenario in sequence diagram

![](GoogleShape1476p18.jpg)
Upper or lower part will work at a time.
Based on the condition.

### Notes:

<!-- Slide number: 19 -->
# Sequence Diagram for search book Use Case

![](GoogleShape1485p19.jpg)

### Notes:

<!-- Slide number: 20 -->

![](GoogleShape1491p20.jpg)
#

### Notes:

<!-- Slide number: 21 -->
# Multiple If-else condition

![](GoogleShape1498p21.jpg)
Slide ‹#›

### Notes:

<!-- Slide number: 22 -->
# Example
ABEC University’s permanent campus has multiple restaurants inside the campus premises. So the university has developed a system that helps the students of the university order food from those restaurants. To use the system, at first, a student must visit the site and he/she will search for a food item which is passed to the SearchEngine. The SearchEngine then fetches the RestaurantPages from RestaurantDatabase which sells that particular food item, serials them, and returns them to the student. The student then selects the RestaurantPage. From the RestaurantPage, the student adds the item to their cart which sends a request to the StudentCart. After receiving the request, StudentCart adds the item. The student may again search for more than one food item which will be passed to the SearchEngine. In this case, the previous steps will be repeated. However, multiple food items can be added to the StudentCart if all of them belong to the same restaurant. Finally, when the student decides to order all the food items, he/she selects checkout which sends a request to the CartCheckout where the student has to enter his/her student ID, gsuite email address, phone number, and select the payment method. When all the information has been given, the system confirms the order and shows the estimated delivery time.
Now, draw the sequence diagram for the above scenario.

### Notes:

<!-- Slide number: 23 -->
# Thanks

*
‹#›

### Notes: