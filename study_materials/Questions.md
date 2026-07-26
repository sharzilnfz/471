# 📝 UML Diagram Practice Question Bank

> **Print-Friendly Collection**: Contains only the scenario descriptions and problem statements for **Activity Diagrams**, **Sequence Diagrams**, and **Use Case Diagrams**. Solutions, explanations, and diagrams have been omitted for clean printing and self-assessment.

---

# Part 1: Activity Diagram Questions

## Q1. Coffee Shop Order Processing (Mini-Example)

A customer orders coffee. The barista checks if the order is hot or cold. For hot drinks, the barista steams milk while the machine brews espresso. For cold drinks, the barista blends ice. Both paths end with the barista serving the drink.

*Design an activity diagram for the scenario above.*

---

## Q2. Student Assistance Fund (SAF) Authorization Process

Student Assistance Fund (SAF) authorization has a number of steps in its approval process. A SAF authorization form is used in most universities to approve funding for students to aid their studies. Suppose a student fills out a blank form and sends it to his or her departmental chairperson for a signature. If the amount of funds requested by the student is small (under Tk. 10,000), then the chairperson signs the form and routes it to accounts payable to be input into the accounting system. The system cuts a check that is sent to the student for the right amount, and after the check is cashed, the form is filed away with the canceled check. If the check is not cashed within 30 days, the form expires. When the amount of the requested fund is large (over Tk. 10,000), the chairperson signs the form and sends it to the chief financial officer along with a paragraph explaining the reason for the grant, and the chief financial officer will sign the form and pass it along to accounts payable. Both the chairperson and the chief financial officer can reject the SAF authorization form if they do not feel that the reasons for seeking funding are reasonable. In this case, the student can change the form to include more explanation or decide to pay the entire fee.

*Design an activity diagram based on the above information.*

---

## Q3. Pentagon Security System Protocol

The Pentagon is working on a new security protocol to ensure that no one other than no Russian spy can infiltrate and get access to classified materials. The protocol set is as follows:
1. The user must first enter their password on the password kiosk.
2. The password kiosk will send the hash of the password to the basic credentials module (which is a part of the credentials system) and prompt the user to enter their YubiKey.
3. The basic credentials module takes the hash and performs the following simultaneously:
   1. It matches the hash against known passwords, and if there is a match, then it gets the user uuid, otherwise it generates a false uuid.
   2. Generates a set of random numbers.
4. After the uuid and the random numbers are generated, the basic credentials module concatenates them to create a string and sends it back to the password kiosk.
5. The password kiosk will then use the YubiKey and the string to generate a hash.
6. If the hash is under a specific limit, the user is allowed access, otherwise the user is declined access.

*Design the activity diagram based on the above scenario.*

---

## Q4. NFT Marketplace Minting & Order Flow

Non-Fungible Tokens (NFT) are an application of blockchains where the proof of ownership of an asset is placed on the blockchain network and the owner of the asset has the hash of the block stored in a digital wallet. First the creator of a NFT collection opens up a crypto wallet and then logs into it, if the creator already has a wallet, then s/he just logs in. After that, the creator connects his/her wallet to a marketplace, during the connection process, the marketplace will check if the wallet is already connected or not, if the wallet was not connected, then the wallet will be added to the database and a confirmation message will be sent, otherwise just the confirmation message will be sent. After connecting the wallet, the creator will request to add the NFT collection to the marketplace. The marketplace will check the collection and generate a minting cost in cryptocurrency and then will check if the wallet contains sufficient cryptocurrency to mint (add) the collection. If sufficient cryptocurrency is not present, the request will be denied. If sufficient cryptocurrency is present, then the marketplace will start the minting process. In the minting process, requests are sent to the blockchain network and the remote storage network. The blockchain network mines the block and then validates the block, the remote storage network stores the collection on a server. After both these processes are complete, the creator is sent a notification of the success.

*Construct an activity diagram from the above scenario.*

---

## Q5. TeaLeaves Order Management System

Company TeaLeaves has recently adopted a new order management system for handling production requests. The sales representative can place a new order for production. If special materials are required for producing the new order, then an order is placed for special materials with the supplier. Otherwise, if no special materials are required for producing the new order or the supplier has finished providing the special materials, the order is added to the production list. Afterward, the order is scheduled for production. Once the order is confirmed, a letter is generated to the sales representative and to the manager.

*Draw the activity diagram for the above scenario.*

---

## Q6. GroceryDash Grocery Delivery System

In the digital age, GroceryDash, an online grocery delivery app, simplifies the process of getting essential items at your doorstep. Here's a scenario outlining the key steps in the GroceryDash ordering system:

Users initiate the process by logging into the GroceryDash app, where they can browse and select their desired groceries. After selecting items, the order manager receives the request and checks for the availability of the chosen products.
If the items are available, the order manager proceeds with the checkout process. However, if certain items are out of stock, the system notifies the user and provides alternative suggestions. If the alternative suggestions are not according to the preference of the user, the user can remove the out-of-stock item or cancel the order itself.
Upon successful checkout and payment, the delivery manager is activated. The system checks the proximity of available delivery personnel within a specified radius.
If a delivery person is found, both the user and the delivery man are notified of the estimated delivery time and location. If both the delivery man and the user approve of the delivery time and location, only then the system updates the user's order status to 'Out for Delivery.' If any one doesn't approve of the delivery time, the system goes back to searching for a new delivery man.
After the 'Out for Delivery' status comes up for the user, the user can track the live location of the delivery personnel. Once the groceries have arrived in the specified location, both the user and delivery man have to approve of receiving the items and delivering the items for the order status to change into 'Delivered,' which then sends the user a confirmation message.

*Design an activity diagram based on the above scenario.*

---

## Q7. Sarah the Editor: Book Proposal Process

Sarah also works as a part-time editor. She logs into an app with her email and password where she is already registered and she reviews any book proposal she gets. She can choose to accept a proposal after analyzing the proposal or reject the proposal. If the project is rejected it will notify the agent and end the scenario. The agent also uses the same app and is registered as an agent with a different interface where he/she can send book proposals to enlisted editors and contracts to enlisted writers. Due to Sarah accepting the proposal, the agent can offer a contract to the writer. The writer analyzes the offer and asks the agent's opinion on the offer. If both are positive to work on it, the writer will notify Sarah, who is the editor, about accepting it and then begin his/her writing.

*Design an activity diagram from the above scenario.*

---

# Part 2: Sequence Diagram Questions

## Q8. Website User Authentication Flow (Mini-Example)

A user logs into a website. The website sends the credentials to the AuthService. The AuthService checks the database for the user. If the user exists and password matches, the AuthService returns a token to the website, which shows a welcome page. If the password is wrong, an error message is shown. If the user doesn't exist, a registration link is shown.

*Draw a sequence diagram for the above scenario.*

---

## Q9. ABEC University Food Ordering System

ABEC University's permanent campus has multiple restaurants inside the campus premises. So the university has developed a system that helps students order food from those restaurants. To use the system, a student must first visit the site and search for a food item, which is then passed to the SearchEngine. The SearchEngine then fetches the RestaurantPages from RestaurantDatabase which sells that particular food item, serializes them, and returns them to the student. The student then selects the RestaurantPage. From the RestaurantPage, the student adds the item to their cart which sends a request to the StudentCart. After receiving the request, StudentCart adds the item. The student may again search for more than one food item, which will be passed to the SearchEngine. In this case, the previous steps will be repeated. However, multiple food items can be added to the StudentCart if all of them belong to the same restaurant. Finally, when the student decides to order all the food items, he/she selects to check out which sends a request to the CartCheckout where the student has to enter his/her student ID, gsuite email address, phone number, and select the payment method. When all the information has been given, the system confirms the order and shows the estimated delivery time.

*Draw the sequence diagram for the above scenario.*

---

## Q10. Smart Home Automation System

Design a smart-home automation system that integrates a CPU, sensors, displays, sound systems, and mobile devices to provide automation and security.
After waking, the user can ask the CPU for scheduled tasks, where tasks exceeding five are sent to the user's mobile, while tasks five or fewer are displayed on the screen. At 10:00 AM, before leaving the house, the CPU asks the user to set a fingerprint via the sensor, followed by setting a PIN to the CPU. Upon returning, the user provides a fingerprint and PIN.
If the fingerprint is matched, the sensor sends the fingerprint-matched message to the CPU, and the CPU checks the PIN. In case of the correct pin, a welcome message is shown in the display; otherwise, the user receives a resetting instruction and resets the pin. However, if an unrecognized fingerprint is detected, the CPU receives a fingerprint-mismatched signal and sends an intruder alert to the user's mobile.

*Draw a sequence diagram based on the above scenario.*

---

## Q11. User Login & Mobile OTP Authentication Solution

The following scenario shows a successful authentication of a client using the mobile OTP solution.
The authentication is initiated when a user requests access to a service that requires authentication. The SP notifies the authenticator that a user needs to be authenticated. The session is redirected to the authenticator and the user is asked to enter a username. The username is sent to the AS, which gets the secret key for this client and, from this generates an OTP. The OTP is also based on a challenge. A different challenge is used every time so the generated OTP is always changing. At last a message authentication code (MAC) based on the secret key is calculated over the OTP. The AS sends the triplet (challenge, MAC, OTP) to the Authenticator which relays the challenge and the MAC to the client. Upon receiving the challenge, the client calculates the OTP. Then it calculates the MAC and compares it to the one received from the Authenticator. If the values match the client can authenticate the AS since the AS has proved that it is in possession of the shared key. The client then sends the OTP back to the Authenticator. If the MAC is wrong, the authentication is aborted. The Authenticator compares the OTP with the one received from the AS and if they match, notifies the SP that the client is authenticated. A mutual authentication of the client and server has been achieved and the session is redirected back to the SP which grants the user access to the service.

*Draw a sequence diagram based on the above information.*

---

## Q12. Online Examination System

A student logs into an online examination system to take a timed multiple-choice test. First, the student enters their username and password. The system checks if the credentials are valid; if not, it asks the student to try again (this can repeat up to 3 times). If successful, the system shows the list of available tests. The student selects a test and starts it. The system then starts a timer (which updates itself every second) and loads the first question. If all the questions are not seen, for each question, the student can either answer it, skip it, or mark it for review. If the student answers, the system saves the response immediately. If they skip, the system moves to the next question. If they mark for review, the system adds the question to a separate review list and also goes to the next question. If the student clicks "End Test" before time is up, the system shows a confirmation box with two choices: confirm or cancel. If confirmation is selected, the test ends early. If cancellation is selected, the student returns to the test. When the timer runs out or the student confirms the end, the system saves all answers, submits the test. A result generator object is then created by the system, which calculates the score using its grading method (one question at a time until all are done), then sends the result back to the system. The system then destroys the result generator. Finally, the system shows the result to the student.

*Draw a sequence diagram based on the above scenario.*

---

## Q13. E-Commerce Order & Payment Process

Ecommerce has been booming in Bangladesh, and especially with the pandemic, the demand for it has exponentially increased. A general case ecommerce runs as follows:
1. After a customer visits the site, they search for a product by typing its name, which is passed to the SearchEngine
2. The SearchEngine then fetches the products from the ProductsDatabase and serializes them in accordance with the relevance of the searched keywords and returns them to the customer
3. The customer selects an item which takes the user to the ProductPage
4. From the ProductPage, the customer adds the item to their cart which sends a request to the CustomerCart
5. After receiving the request, CustomerCart sends a request to the ProductsDatabase to check if the item is in stock, if the item is in stock, the product gets added to the CustomerCart otherwise an error is shown
6. Finally, the customer selects to check out, which sends a request to the CartCheckout where the customer has to enter their full name, email address, phone number and delivery address
7. If all the information has been entered correctly, a success message is shown, otherwise an error message is shown

*Draw the sequence diagram for the above scenario.*

---

## Q14. Hoichoi Video Streaming Search Service

Watching a movie or documentary in hoichoi is always exciting. In a simple hoichoi site, after the user logs in using the credentials, there is a simple dashboard containing the suggested movie or Tv series along with a search bar at the top to search for any item. The user can search for the contents in three ways. They can search by a content name like "Mahanagar", they can search by the name of an Artist or Director like "Mostafa Sarwar Faruki," and finally they can search by a genre like "Crime Thriller." For the first case, the hoichoi search manager fetches a single entry along with the metadata from the hoichoi server and displays it to the user as a tile along with the metadata. For the second case, a list of content involving the Artist or Director is showed (not as tiles) to the users after being fetched from the server. And finally, the relevant contents of a genre search are offered as tiles (without the metadata) for the user to select, however the search manager fetches the metadata from server for later use. All user communication with the search manager is relayed by the web interface of hoichoi.

*Draw a sequence diagram based on search system of hoichoi as described above.*

---

# Part 3: Use Case Diagram Questions

## Q15. Library Book Borrowing System (Mini-Example)

A library system allows members to search for books and borrow them. When borrowing, the system must check membership validity. Members can optionally reserve books that are currently checked out. Librarians can add new books and manage member accounts. Both members and librarians must log in first. There are two types of members: Regular and Premium. Premium members can access e-books.

*Design a Use Case diagram for the scenario above.*

---

## Q16. Google Classroom System

Google Classroom is a teacher/student platform, which Google designed for the way teachers and students think and work. It converts traditional paper-based teaching mechanisms to an online paperless one. It all starts with the creation of a classroom by a teacher. Students can easily connect to a classroom using a unique code created for each classroom. It also allows the teachers to create and add materials to assignments, such as YouTube videos, a Google Forms survey, and other items from Google Drive. In this pandemic situation, it has done more for the teacher-student community. Teachers can set graded assignments. Due date setting facility is also offered for the assignments. Once the assignment is posted, students can solve those and submit them online. On completion of submission, teachers can grade and return the result to the students. The updates of the events are also emailed to corresponding email addresses which are used while connecting to the classroom.

*Design a Use-case diagram based on the above information.*

---

## Q17. BDEX Courier Management System

Analyzing the system for BDEX (a Bangladeshi courier service), following requirements were identified:
* There will be three types of users: Customer, First Officer and Manager
* Customers can initiate emergency delivery by providing item details
* Customer can choose between regular and express delivery
* Reward points are added into Customer account for express delivery
* First Officer can fill out courier form with necessary information
* For confidential and/or fragile item(s), First Officer must fill out insurance and policy documents during packaging, but it is not needed for general items.
* Manager can approve and sign off parcel item(s) for delivery
* Manager can contact Customer for delay in parcel arrival
* Manager can mark packages delivered after getting Customer confirmation

*Design a use case diagram based on the above information.*

---

## Q18. Bus Ticket Booking System (PAYBD)

Analyzing the system for online ticket booking, the following requirements were identified:
* There can be three types of passengers: General, Premium and New
* Passenger can register into the system with his – NID, Name, Email, Mobile Number, and Password
* Passenger can login into the system with his email and password
* Passenger can buy tickets
* Tickets should be confirmed by the System Admin
* Passenger can pay the ticket price online after being confirmed
* Online payment should be using the "PAYBD" payment gateway
* Passenger can cancel a booking
* Passenger can request for return money for the canceled booking

*Design a Use Case diagram based on the above information.*

---

## Q19. Student Assignment Management System

Analyzing the system for student assignment management, the following requirements were identified:
* There can be three types of users: Teacher, Teaching Assistant (TA) and Student
* Teacher can add new assignments
* Teacher can edit/remove an existing assignment
* TA can edit/remove an existing assignment
* Student can submit an assignment
* Student can edit his submission (before due date)
* TA can assign grade to submission (after due date)
* Teacher can modify grade after graded by the TA
* Student can view grade
* Student can generate reports of his submissions after graded by the TA

*Design a Use Case diagram based on the above information.*

---

## Q20. Community Robbery Prevention & Response Platform

A community robbery prevention and response platform is being developed to tackle the growing issue of robbery incidents in Bangladesh.
Registered users can log in to the platform to report robbery incidents by providing details or evidence such as photos or videos. They can also request immediate help through a panic button. The panic button works as an emergency alert and notifies a law enforcement officer. Some users who act as volunteers might respond to emergency alerts to help the users if they are available. Users will get notified if volunteers have responded to the alert. After providing assistance volunteers can update the status of incidents and can communicate with law enforcement officers. Any user can apply to be a volunteer, and administrator will verify and approve the request. Law enforcement officers can review reported incidents and update the progress of investigations. They can also communicate with both users and volunteers for coordinated actions. Moreover, users can view robbery-prone areas on an interactive map and receive safety tips. Administrators of the platform oversee the entire system by managing user and volunteer registrations. Additionally, the system includes AI-powered analytics reports which include prediction of high-risk robbery zones based on incident data and preventive suggestions.

*Design a Use Case diagram based on the above scenario.*

---

## Q21. Course Management System

Suppose you have been hired to design a course management system. The requirements for the system are as follows:
Two types of students will use this system, BSc, and MSc. Students will be able to log in to the system using a username and password. The system will check whether the credentials are valid and will give an error message if they are incorrect. Students will be able to select courses they want to complete next semester. The system will check whether the course has remaining seats and if the student has completed all pre-requisite courses to take the course. The system might suggest additional courses to the students when taking a course. After a student has completed selecting courses then he/she might request for advising, and an adviser will approve the advising request. Students can view their routine and grade sheet. BSc students can add project proposals whereas MSc students can add thesis proposals and those will be approved by the advisor. Students can also make payments. Payments can be made via card or bank transfer; payment must be verified by the system.

*Design a Use Case Diagram based on the above information.*

---

## Q22. Bookflix Online Book Borrowing System

Bookflix is an online book borrowing system. In this system, a user can view a list of books that are available for borrowing. They have to search for the books by author or book name first. They can also read snippets before borrowing a book. The users can rate the books and also write reviews about the books they borrow. This system has two types of subscription service: monthly and yearly. There are two types of payment methods in this system: mobile banking and card. A user will be upgraded to a premium user, if he/she avails of the yearly package. Premium users can view available slots to book for online sessions with the book authors. The authors will set the date and time of the online sessions. The user will receive notification about best-selling books that are available. Users can turn on notifications for their desired books to know their availability. They will also get a notification about the due payments. Customer service will be available for the users to get help and file complaints. Customer service will provide feedback and take necessary actions upon the complaints.

*(Note: You don't have to draw any authentication related use cases).*

*Design a Use Case Diagram based on the above scenario.*

---

## Q23. E-Learning Platform Coursework & Enrollment

This scenario focuses on a student enrolling in a course and completing coursework on an e-learning platform.
The student accesses the E-Learning Platform and logs in with their account credentials. Then he/she can browse the course catalog and search for a course of interest. Students views the course details, including description, learning objectives, instructor information, and prerequisites (if any). When a student decides to enroll in the course, they may need to pay a fee or use a subscription depending on the platform's model. The E-Learning Platform processes the enrollment and grants the student access to the course content. The student accesses the course materials, which may include videos, lectures, readings, quizzes, and assignments. The student progresses through the course content at their own pace, completing learning activities. Students take quizzes and complete assignments as required by the course. The E-Learning Platform grades these assessments and provides feedback. The student interacts with the discussion forum or other communication tools within the course to ask questions and collaborate with other learners. Upon completing all course requirements, the student may receive a certificate of completion or a grade, depending on the platform and course structure.

*Design a Use Case Diagram based on the above scenario.*

---

## Q24. Quick Fix Mechanix Car Servicing System

Quick Fix Mechanix is a system developed with the aim of easing the hassles of modern-day car servicing problems by providing proper car care solutions that can be monitored remotely from anywhere. The users of the system include Regular Customers, Premium Customers and Service Providers. All the users of the system will first register and then login to the system. Registration will be verified through OTP. Customers will be able to choose a specific service (cleaning, repairing, health checkup) from the garage of his/her choice. The customer can choose a service type like home or in-garage service. If the service provider (garage) accepts a service request, the customer will be able to monitor the progress of the service. After the completion of the service, the consumer will be able to complete the payment transaction (using card or bkash) through the system and optionally can also provide rating on the services. The customer will be able to search for nearby available parking slots. He/she can also request for tow-truck service using an emergency button. Nearby garages can accept the request and send a tow-truck. Regular customers can upgrade to premium subscription for a monthly charge. Premium customers will get discounts on various services and will get notifications for offers on the services. When the next service is due, he/she will receive notification from the system. Consumers will be able to fill up relative insurance papers through the system. The system admin manages insurance forms. Customers can also register complaints upon receiving a service. The admin manages complaints upon receiving any complaints.

*Design a Use Case Diagram based on the above scenario.*

---

