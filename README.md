
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

![image](https://github.com/SpaMnky/2378/assets/131407808/ab6fbc74-f299-42d8-b148-1c6e09daa593)

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
