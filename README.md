
# MIST 4610 SQL PROJECT 1 
# Team Name: cs_g2p1
# Team Members:
1. Thommy Chhim [@SpaMnky](https://github.com/SpaMnky)

2. Vasil Gerchev [@vgg01171](https://github.com/vgg01171)

3. Robert You [@PointBrok3n](https://github.com/PointBrok3n)

4. Brian Ferro  [@dinough](https://github.com/dinough)

5. Nathan Rockwell [@nathanrockwell](https://github.com/nathanrockwell)

# Problem Description: 
For our first MIST 4610 group project, we are tasked with constructing a data model and building a corresponding database, populating it with data, and formulating 10 SQL queries that are relevant from a managerial perspective. We have chosen to work with ChatGPT, a simulated client, to develop our project scenario. ChatGPT has been asked to act as the owner/operator of a tennis club in need of a relational database. Through interactions with ChatGPT, we aim to extract information about the tennis club's operations and business processes, enabling us to create a robust data model. The model should consist of at least 12-15 entities, with appropriate attributes and relationships between them. To ensure comprehensive documentation and collaboration, every team member is required to construct and maintain a GitHub repository containing details of the group project's progress. The resulting database and SQL queries should serve the managerial needs of the tennis club, enhancing its operations and decision-making processes. This initiative aims to tackle the complex administrative challenges faced by the club and enable more efficient organization, planning, and communication across all facets of its operation.

# ChatGPT Log: *
Team: Pretend you are the owner/operator of a tennis (or football, soccer - your choice) club needing to build a relational database. You hired some students from the MIST 4610 class at the University of Georgia to create the database for you. They need to know more about your organization to identify which entities, attributes, and relationships are important for you. Start by describing your business as a real client Be as clear and exact as possible. Make sure that each entity is unique.

ChatGPT:

As the owner/operator of a tennis club, I want to create a relational database to efficiently manage and organize the various aspects of our club's operations. Our tennis club, named "AceHaven Tennis Club," is a prominent and well-established organization located in Athens, Georgia. We provide tennis enthusiasts of all ages and skill levels with high-quality facilities and programs. Our primary goal is to promote the sport of tennis and foster a strong sense of community among our members.
Here's an overview of our club:
Members: Our club has a diverse membership base, including junior players, adults, and seniors. Each member has a unique membership ID, and we need to store their personal information, such as name, contact details, date of birth, and emergency contact information.
Coaches: We employ experienced tennis coaches who provide coaching services to our members. Each coach has a unique coach ID, and we need to maintain their contact information, qualifications, and availability.
Courts: We have several tennis courts of different types, such as clay, grass, and hard courts. Each court has a unique identifier, and we need to track its availability, maintenance schedule, and any special booking requirements.
Booking and Reservations: Members can book tennis courts for specific time slots. We need to record the reservations, including the date, time, court number, and the member making the reservation.
Tournaments and Events: We host tennis tournaments and events throughout the year. These events have details such as event name, date, location, and participating players or teams.
Payments and Invoices: We need to keep track of member payments, including membership fees, coaching fees, and tournament entry fees. Each payment should be associated with a member and a specific transaction date.
Equipment and Pro Shop: Our club also operates a pro shop where members can purchase tennis equipment and apparel. We need to maintain an inventory of items, including their names, prices, and quantities in stock.
Maintenance and Repairs: Regular maintenance is essential for our tennis courts. We need to track maintenance schedules, service providers, and any repairs carried out.
Interactions: We want to keep a log of interactions between members and coaches, such as coaching sessions, feedback, and performance improvements. This will help us evaluate and enhance our coaching services.
Employee Information: For administrative purposes, we employ staff members for various roles, including front desk staff, maintenance personnel, and management. We need to keep records of their employment details.
Feedback and Surveys: Gathering feedback from members about their experiences and preferences is crucial. We want to maintain records of feedback and conduct periodic surveys.
Member Attendance: We need to track the attendance of members in coaching sessions, events, and tournaments.
The relationships between these entities will be crucial to the efficient functioning of the club. The MIST 4610 class students should focus on designing a robust database schema that allows for easy data retrieval, updates, and reporting. They should also consider implementing data integrity constraints to maintain data accuracy and consistency. Finally, security measures should be put in place to protect sensitive member information.



Team: Be more specific about 4, 6, 7, 8, and 11

ChatGPT: 

Certainly, let's provide more specific details for entities 4, 6, 7, 8, and 11:
Booking and Reservations:
Reservation ID: A unique identifier for each reservation.
Member ID: A reference to the member making the reservation.
Court ID: A reference to the tennis court being reserved.
Date and Time: The date and time of the reservation.
Duration: The duration of the reservation.
Status: Whether the reservation is pending, confirmed, or canceled.
Payments and Invoices:
Payment ID: A unique identifier for each payment transaction.
Member ID: A reference to the member making the payment.
Payment Date: The date of the payment.
Payment Type: The type of payment (membership fee, coaching fee, tournament fee, etc.).
Amount: The amount paid.
Invoice ID: A reference to the corresponding invoice, if applicable.
Equipment and Pro Shop:
Item ID: A unique identifier for each item in the pro shop.
Item Name: The name of the item (e.g., tennis racket, tennis balls, apparel).
Price: The price of the item.
Quantity in Stock: The number of items currently in stock.
Description: A brief description of the item.
Maintenance and Repairs:
Maintenance ID: A unique identifier for each maintenance or repair task.
Court ID: A reference to the tennis court that required maintenance.
Maintenance Date: The date when maintenance or repair was performed.
Service Provider: The company or individual responsible for the maintenance.
Description: Details about the maintenance or repair work done.
Feedback and Surveys:
Feedback ID: A unique identifier for each feedback entry.
Member ID: A reference to the member providing feedback.
Date: The date the feedback was given.
Type: The type of feedback (coaching feedback, general feedback, survey response, etc.).
Content: The content of the feedback or survey response.
Rating: If applicable, a rating provided by the member.
These additional details help to clarify the structure of these specific entities and provide a clearer picture of what data should be stored and how it should be organized. It is crucial for the MIST 4610 class students to define the relationships and constraints between these attributes to ensure the integrity and functionality of the database.


TEAM: what is the relationship between coaches and members

ChatGPT: 

The relationship between coaches and members in the database for AceHaven Tennis Club involves a many-to-many association, as multiple members can be coached by multiple coaches, and coaches can have multiple members as their clients. To represent this relationship, you can use an intermediary table or entity, often referred to as a junction or association table. Let's call this table "CoachMemberAssociation."
Here's how you can set up the relationship:
Coaches Entity:
Coach ID (Primary Key)
Name
Contact Information
Qualifications
Availability
Members Entity:
Member ID (Primary Key)
Name
Contact Information
Date of Birth
Emergency Contact Information
CoachMemberAssociation Entity:
Association ID (Primary Key)
Coach ID (Foreign Key referring to Coach Entity)
Member ID (Foreign Key referring to Members Entity)
Coaching Start Date: The date when the coaching relationship started.
In this structure:
Each record in the "CoachMemberAssociation" table represents a specific coaching relationship between a coach and a member.
A coach can be associated with multiple members by having multiple records in the "CoachMemberAssociation" table with the same "Coach ID."
Similarly, a member can be associated with multiple coaches by having multiple records in the "CoachMemberAssociation" table with the same "Member ID."
This design allows you to track the coaching relationships between coaches and members, including when they started coaching and which members are being coached by which coaches. It's a flexible way to manage coaching relationships while maintaining data integrity.

Team: what attributes do Feedback and Surveys have?

ChatGPT: 

Feedback and Surveys are essential for gathering information about member experiences and preferences. Here are the attributes you can include for both Feedback and Surveys:
Feedback Entity:
Feedback ID: A unique identifier for each feedback entry (Primary Key).
Member ID: A reference to the member providing feedback (Foreign Key to the Members Entity).
Date: The date when the feedback was provided.
Type: The type of feedback, which can be categorized as coaching feedback, general feedback, event feedback, etc.
Content: The actual content of the feedback, where the member can provide detailed comments and suggestions.
Rating: If applicable, a numerical rating (e.g., on a scale of 1 to 5) given by the member.
Response: An optional field to record any response or action taken by the club in response to the feedback.
Status: Indicates whether the feedback is pending, resolved, or in progress.
Surveys Entity:
Survey ID: A unique identifier for each survey (Primary Key).
Survey Name: A name or title for the survey.
Description: A brief description of the survey's purpose or topic.
Date Started: The date when the survey was initiated.
Date Ended: The date when the survey is closed or the last day for responses.
Survey Questions: A list of questions associated with the survey, each with attributes like:
Question ID: A unique identifier for each question within the survey.
Question Text: The actual question presented to the members.
Question Type: The type of question (multiple choice, open-ended, rating scale, etc.).
Options: If the question is multiple choice, a list of answer options.
Required: A flag to indicate whether answering the question is mandatory.
Responses: A table or entity to store member responses to the survey, including:
Response ID: A unique identifier for each response.
Member ID: A reference to the member who provided the response.
Survey ID: A reference to the survey the response corresponds to.
Question ID: A reference to the specific survey question being answered.
Response Data: The actual response provided by the member (text, selected option, rating, etc.).
By including these attributes for Feedback and Surveys, the database can effectively capture and manage member feedback, responses to surveys, and any related actions or follow-ups. This information can be invaluable for improving club services and understanding member preferences.

*Disclaimer: We discussed the ChatGPT logs with our Professor, and our Professor ultimately overruled some of the things ChatGPT told us to do because some of it didn't make sense. 

# Data Model
![image](https://github.com/SpaMnky/2378/assets/131407808/11d65999-9ce2-4ca1-9c8a-aa958a88275a)

Explanation of the data model: 

Our model is structured around a hypothetical tennis club named "Ace Haven." This club is represented in our database through the "Club" table, which serves as a central reference point for various other tables in our model. The "Club" table is primarily identified by its name and includes additional information such as its founding date and address.

The key relationships in our model revolve around the "Club" table. Firstly, there is a one-to-many (1:m) relationship between the "Club" and "Member" tables, reflecting the fact that our club comprises numerous members. Similarly, there is a 1:m relationship between the "Club" and "Courts" tables, as our club features multiple tennis courts. Additionally, our club operates a "ProShop," and this is represented by a one-to-one (1:1) relationship.

Feedback is another important aspect of our club's operation. Members can provide feedback, and this relationship is represented by a 1:m connection between the "Member" and "Feedback" tables. 

Members are not only linked to feedback but also associated with teams. This is achieved through a many-to-many relationship, involving the "Team" and "TeamAssignment" tables. In the "Team" table, we track attributes like team ID and name. Teams can also register for tournaments through a many-to-many connection with the "Tournaments" table, identified as "TouRegistration." This relationship tracks the tournament ID, team ID, registration status, and date of registration.

The "Tournaments" table itself is characterized by attributes such as tournament ID, name, date, and location.

Members make payments during their membership, and this relationship is captured through a 1:m connection between the "Member" and "Payment" tables. The "Payment" table is identified by a payment ID and includes details like payment amount, date, and payment type.

Members can also make reservations for courts, and this is represented as a many-to-many relationship between the "Member" and "Courts," specifically the "Reservations" table. This relationship tracks court ID, member ID, reservation ID, and reservation date.

Members can purchase equipment from the Pro Shop, which is identified by the name "Fairway Fields" and includes an additional attribute, the phone number. The "Equipment" table is associated with the Pro Shop through a 1:m relationship and includes attributes like equipment name, price, description, and quantity in stock, as well as an ID.

Transactions made by members are recorded in the "Transaction" table, which is identified by a transaction ID and includes the transaction date. Furthermore, there is a "transactionDetails" table, which captures details like quantity bought and is identified by its ID, item, and transaction ID.

Our club employs various staff members, and this is depicted through a 1:m relationship between the "Club" and "Staff" tables. Staff members are identified by their staff ID, and we track their name, salary, and whether they hold a managerial position. This managerial status is represented through a one-to-one recursive relationship.

Finally, maintenance of the courts is handled by our maintenance staff. This relationship is established as a many-to-many connection between the "Courts" table, identified by its ID and Club, and the "Maintenance" table. The "Maintenance" table includes attributes such as maintenance ID, staff ID, court ID, and details, along with the maintenance date.


# Data Dictionary: 

![image](https://github.com/SpaMnky/2378/assets/131407808/174dc558-335b-4fb2-9215-d9364b8bd028)
![image](https://github.com/SpaMnky/2378/assets/131407808/00cb7bde-1bcb-440e-bb54-1803e1236920)
![image](https://github.com/SpaMnky/2378/assets/131407808/8725c26c-f2a1-4b02-bfcd-15ece280b17f)
![image](https://github.com/SpaMnky/2378/assets/131407808/f11ed9d7-f78b-4648-af59-c9168b3727fa)
![image](https://github.com/SpaMnky/2378/assets/131407808/71559807-74e2-4e2a-a081-2afa3fbdbce5)
![image](https://github.com/SpaMnky/2378/assets/131407808/ecb0a53d-8f9e-40b9-8f22-a88fe32f7c9a)
![image](https://github.com/SpaMnky/2378/assets/131407808/6ff564e7-13f1-4cc5-b5d0-6e0539870309)
![image](https://github.com/SpaMnky/2378/assets/131407808/eaf0f2de-8f68-4d81-b340-3175c475c642)
![image](https://github.com/SpaMnky/2378/assets/131407808/4de6d646-c4c5-42d2-ad2a-081518280374)
![image](https://github.com/SpaMnky/2378/assets/131407808/6af27ae1-1644-4bce-809b-c4e8f84dc541)
![image](https://github.com/SpaMnky/2378/assets/131407808/39787508-4305-40e4-8c1a-c02346eb1a1e)
![image](https://github.com/SpaMnky/2378/assets/131407808/d30d307e-7385-486d-a820-d29c99749761)
![image](https://github.com/SpaMnky/2378/assets/131407808/d7af0c2f-4bd1-4840-acc7-2934c2d3888f)
![image](https://github.com/SpaMnky/2378/assets/131407808/9f084612-f223-4a13-8774-4e8cfba5156d)
![image](https://github.com/SpaMnky/2378/assets/131407808/986e0ad1-b061-4162-a5de-02c66f2a9507)
![image](https://github.com/SpaMnky/2378/assets/131407808/6c1d2fe3-8c73-4752-b8c3-5e23be92c94b)



# Queries:

![image](https://github.com/SpaMnky/2378/assets/131407808/53126b5a-e574-4b46-ae31-d536dcdc83e0)

1. Query 1 Lists the full names and salaries of all staff at AceHaven Tennis Club who make more than the average salary of all staff. It accomplishes this by comparing each staff member's salary to the subquery's result, which calculates the average salary.

![image](https://github.com/SpaMnky/2378/assets/131407808/9ab625ff-51e0-4948-8ad8-6c7f7c6b3955)

The query empowers the manager to pinpoint staff members with above-average salaries, facilitating crucial decisions regarding performance recognition, budget allocation, salary fairness, and strategic staff management at AceHaven Tennis Club. These insights translate to more efficient operations and a satisfied, motivated workforce.

2. Query 2 lists the club members by their first and last names and number of reservations in the last three months. It then orders the result by number of reservations in descending order.

![image](https://github.com/SpaMnky/2378/assets/131407808/fabd2fb2-1829-4642-97bb-886d9665cbe5)

This query helps the manager pinpoint loyal, engaged members for recognition and rewards, aiding resource allocation and data-driven decision-making. It keeps the club competitive by optimizing services and enhancing member satisfaction and retention.

3. Query 3 Shows a list of all members who made a payment, including their ID, names, contact information, payment type, and amount. Show only payments in the latest month.
   
![image](https://github.com/SpaMnky/2378/assets/131407808/0b81e929-170d-4f4c-b36c-47e5bd0da0d1)

By showing the information of members who have made the latest payment, we can check them off. Furthermore, we can collect data on what type of payment members usually use.  Also, we can see which members still need to pay their monthly fees and then contact those accordingly.

4. Query 4 Shows a list of all tennis tournaments, including the tournament name, date, location, and the name of members who have registered. Additionally for each member, it displays their information. Only include tournaments with more than 2 registered members.

![image](https://github.com/SpaMnky/2378/assets/131407808/7981a32f-5b95-4502-8dc7-db8a889689f9)

By showing the list of tournaments with teams of 2 competing, we can see which tournaments are teams and not singles. Furthermore, we can see the location and which open these types of tournaments are. Also, we can see the information of the players registered to compete in the tournaments together.

5. Query 5 Retrieves and lists the item names and their total quantity sold, excluding items with a total quantity sold less than or equal to one, and presents them in descending order of total quantity sold.

![image](https://github.com/SpaMnky/2378/assets/131407808/d1b3891a-467b-4e5f-8006-99a1b9426853)

Query 5 is important because it provides us insight into which of our items is most popular or which sells the most out of our inventory. This will help the tennis club identify which products are in exceptionally high demand, which can help us make informed inventory management decisions, such as adjusting pricing, marketing, or stocking strategies. Additionally, by excluding those with low sales, we can focus on the more popular products.

6. Query 6  Retrieves the first name, last name, and member ID of customers, along with the total transaction amount and transaction date, for transactions with a total amount greater than 100 and a transaction date after '2023-01-01,' ordered by the total amount in descending order.

![image](https://github.com/SpaMnky/2378/assets/131407808/f4aa3d29-8958-4e95-9c61-82a89183b7fe)

Query 6 is important to a manager as it provides a comprehensive view of high-value transactions within a specific time frame. By listing the member names, transaction totals, and dates, the manager can quickly identify and analyze substantial transactions and the members making them. This information is essential for tracking revenue, identifying valuable customers, and making data-driven decisions to optimize business strategies and customer relationships.

7. Query 7 shows which members gave an average feedback rating that was higher than the average rating of all feedback. Lists the ID, first name, last name, and average feedback rating for each member whos feedback average was higher than the overall average.

![image](https://github.com/SpaMnky/2378/assets/131407808/2e2ef802-b5ee-4e88-aa51-e294f70f00dc)

Feedback is an important metric to measure within our tennis club. By finding out which members consistently provided good feedback, we may be able to find similarities between these members and see why they were above average with the feedback they provided. This will allow us to make connections as to why they were more satisfied with our club, which will give us a chance to improve the experience for all of our members.

8. Query 8 shows which member of the club has been most active in competitions. This query will show the members first name, last name, ID, and the amount of tournaments that they have competed in.

![image](https://github.com/SpaMnky/2378/assets/131407808/a777ad31-d797-4e2b-9e91-03f214d30cee)

By showing which member in the club has competed in the most tournaments, we are able to see which of our players is the most competitive in our league. This is important because tournaments allow for us to draw more recognition to our club. By gaining more recognition, we are able to acquire more members and ultimately gain more revenue for the club.

9. Query 9 List the names of the members who have more than one court reservation and the type of court that the reservation is for.

![image](https://github.com/SpaMnky/2378/assets/131407808/4de1216a-80b4-4bbe-b706-b062b3098657)

This query allows for the tennis club to know who their most active members are and which court they prefer to play on. The query is telling us that these three members have more than one reservation on that specific type of court. The club may use this information to give out discounts to these three members at the shop for contributing the most to the club. They could also use this information to figure out which type of court is popular, so if the club is to invest in more courts they would know what to build more of since it is more popular.

10. Query 10 List the name and date of when each member made their payment towards the club.

![image](https://github.com/SpaMnky/2378/assets/131407808/1a1384f4-7a07-4798-9933-372fbab483a1)

This query will tell the tennis club when each member makes their payments. This would allow them to know who is behind on payments, who has missed a payment, and who has paid their dues. This way they know who is technically still a member and who isn’t if they were to stop making the payments towards the club. Since the total amount is all the same for all members and they must pay the same each time, then there isn’t a need for the total amount as it is $800 for each member each time they make a payment.

# Database information:
Name of the database: cs_g2p1

Additional information: Each query listed above is stored in the database using procedures which can be called using this format: CALL Q1() (Replace 1 with any number between 1-10 to represent each query)
