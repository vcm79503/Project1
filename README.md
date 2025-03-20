# Team 4 MIST 4610 Group Project 1

## Team Name
**Group 4**

## Team Members
1. Vivek Murugulla
2. Sejal Arora 
3. Angie Lin
4. Alyssa Luangxay
5. Robert Anthony

## Problem Description
The goal of this project is to design and develop a relational database that models the operations of multiple bars in Athens, Georgia. At the center of the model is the Bar entity, representing each independent business within the city's bar industry. Each bar has an owner, employs staff, serves customers, and maintains an inventory of food and drinks sourced by various suppliers.

This database captures essential business functions, including customer orders, employee roles, inventory tracking, supplier relationships, and marketing campaigns. It also tracks food and drink demand, allowing better management of supply and operational efficiency.

We aim to define these relationships, generate sample data, and populate the entities with relevant attributes. Additionally, we will run queries on this data to uncover key business insights, such as sales trends, inventory needs, the effectiveness of marketing efforts, and other insights across the entire Athens bar industry.

## Data Model
Our data model represents a system designed for managing bar operations. At the core of the data model is the **Owner** entity, which stores information about the bar's owner(s), establishing a clear line of management. The **Owner** entity is linked to the **Bar** entity through a one-to-many relationship, allowing each owner to manage multiple bars. The **Bar** entity itself includes details such as location, operating hours, and a reference to the owner via the foreign key (FK) **ownerID**.  

Next is the **Employee** entity, which includes details such as their role, hourly salary, and personal information. This entity is associated with a specific bar via a one-to-many relationship, representing how one bar can have many employees.  

Further, customer interactions are captured through the **Customer** and **BarOrders** entities. The **Customer** entity stores basic customer information, while the **BarOrders** entity tracks individual orders, including the order date, time, total price, and the associated customer and employee. The **Customer** entity is linked to **BarOrders** in a one-to-many relationship because one customer can place many orders. **BarOrders** is linked to **Employees** in a one-to-many relationship, representing how one employee can take or make many drink orders.  

**Inventory management** is another important aspect of bar operations, which is addressed within the data model through the **InventoryItem, Food, and Drink** entities. The **InventoryItem** entity tracks all items in the bar's inventory, including their name, type, quantity, restock date, and status. This is linked to **Bar** in a one-to-many relationship, as one bar has many inventory items. These items are then linked to specific food and drink items through associative entities like **FoodIngredients** and **DrinkIngredients**, allowing for the tracking of ingredients used in each menu item.  

The **Food** and **Drink** entities themselves store information about each menu item, including its name, type, price, and supplier. The **Supplier** entity stores information about the bar's suppliers, including their name, contact information, and the types of products they supply. This allows the bar to track its relationships with different suppliers and manage its supply chain effectively. **Supplier** has a one-to-many relationship with **Bar**, since one bar can have many suppliers. **Supplier** also has a one-to-many relationship with **Food and Drink**, showing how one supplier can supply many food and drink items.  

The **MarketingCampaign** entity tracks various promotional activities, including the campaign name, budget, and start and end dates. This is linked to **Bar** in a one-to-many relationship since a bar can have multiple marketing campaigns. 


Finally, we have **FoodDemand** and **DrinkDemand**, which both have a one-to-many relationship with **BarOrders**. This relationship shows how a singular order at the bar may include demand for multiple food and drink items. The **InventoryDemand** entity is connected to both **InventoryItem** and **BarOrders** in a one-to-many relationship, representing how a single order can demand multiple inventory items, and a single inventory item can be demanded from multiple bar orders.

<img width="1504" alt="Screenshot 2025-03-18 at 1 49 31 PM" src="https://github.com/user-attachments/assets/ce0b0aec-1bc6-4e64-8332-8530b3d6bd6d" />

## DataDictonary 
<img width="754" alt="1" src="https://github.com/user-attachments/assets/727c9c57-cd85-42ef-bb79-1b000477d097" />
<img width="362" alt="2" src="https://github.com/user-attachments/assets/7d79b737-b177-46c2-b546-38c67b313a8f" />
<img width="703" alt="3" src="https://github.com/user-attachments/assets/1d511cfa-accb-4d06-912d-dbce86f56aae" />
<img width="369" alt="4" src="https://github.com/user-attachments/assets/b2baf23b-f940-44dd-8529-2acb7d59e646" />
<img width="696" alt="5" src="https://github.com/user-attachments/assets/ed14de90-ad4c-48ef-8590-040fe97dbe79" />
<img width="548" alt="6" src="https://github.com/user-attachments/assets/bbcf2cfd-5cc9-40c7-8867-b54a982313d4" />
<img width="547" alt="7" src="https://github.com/user-attachments/assets/924e05b0-e813-49b3-a601-8be4323bef97" />
<img width="570" alt="8" src="https://github.com/user-attachments/assets/e6635168-7b5d-4cbf-948b-718907e518ac" />
<img width="514" alt="9" src="https://github.com/user-attachments/assets/17600bc9-0001-474a-ae54-bc56415c985e" />
<img width="559" alt="10" src="https://github.com/user-attachments/assets/aef0294b-5f28-4bb9-b146-fa4968a786de" />
<img width="509" alt="11" src="https://github.com/user-attachments/assets/0d71ab51-d2fd-4e2f-975a-70f94e39b101" />
<img width="527" alt="12" src="https://github.com/user-attachments/assets/157bffd5-a30d-412c-88bc-70cca06aaaac" />
<img width="554" alt="13" src="https://github.com/user-attachments/assets/2d4da60a-9efb-461e-af61-58d394e4a973" />
<img width="516" alt="14" src="https://github.com/user-attachments/assets/c9896f32-f4bc-4c07-828b-63f470826015" />
<img width="531" alt="15" src="https://github.com/user-attachments/assets/570a6b4c-8565-4c7b-b826-c08852cbd5b7" />

## Queries and Matrix
<img width="754" alt="Screenshot 2025-03-20 at 11 41 49 AM" src="https://github.com/user-attachments/assets/502dda37-9d16-4ac6-a957-13b02d3b8bb8" />

QUERY 1 (simple): What are the Food/Drink menu options across all bars?
<img width="1115" alt="Screenshot 2025-03-20 at 11 43 19 AM" src="https://github.com/user-attachments/assets/4846f56c-d5f9-4761-8308-82c940510eb4" />

Query 1 lists the different food and drink options, as well as the item types and prices. This allows bar managers to view a consolidated menu that includes both food and drink options. By organizing the results by type and price, it becomes easier to analyze offerings, identify pricing trends, and ensure that the menu is well-balanced across categories. Managers can use this information to make decisions about menu options they may include for their particular bar.

QUERY 2 (simple): What are the most popular drinks based on order quantity?
<img width="622" alt="Screenshot 2025-03-20 at 11 45 17 AM" src="https://github.com/user-attachments/assets/05648229-5305-46a2-ba8b-9fc05dbb4eba" />

Query 2 lists the names of drinks and the total amount of times that drink has been ordered. The data is listed in descending order, having the most commonly ordered drinks at the top and the least ordered drinks at the bottom. This allows bar managers to quickly see which drinks are the most popular, and adjust their menu offerings accordingly. This also helps in predicting which drinks need to be stocked in larger quantities to meet higher demand. Lastly, this query can show changing drink preferences over time. 

QUERY 3 (simple): Which bars have the highest number of customers?
<img width="625" alt="Screenshot 2025-03-20 at 11 46 15 AM" src="https://github.com/user-attachments/assets/acd218af-d920-4f1b-a783-9b0a412fd8b9" />

Query 3 is designed to provide managers with a quick view of bars that have the largest customer base. Although relatively simple, viewing a metric like this can lead to follow-up queries detailing differences between bars with large customer bases and those with smaller ones. This query counts the number of distinct customers, groups them by their respective bar, and then orders the results by total customer count per bar in descending order.

QUERY 4 (simple): How many bars does each drink supplier supply?
<img width="622" alt="Screenshot 2025-03-20 at 11 46 52 AM" src="https://github.com/user-attachments/assets/45852e20-dafe-4d41-ae77-7a109235b0d2" />

Query 4 lists the total amount of distinct bars that the drink supplier supplies. We chose drink suppliers in particular because of the intense competition and standard drink offerings at bars. This query provides valuable information to both bar managers and suppliers who are mutually interested in sustaining successful relationships for their businesses. Both parties may also use this information to strategically position their business for competitive purposes. This query counts the number of distinct bars, filters those suppliers who supply “Drinks”, and then groups the supplier and supplier name correspondingly. Finally, the results are displayed by the number of distinct bars supplied in descending order. 

QUERY 5 (complex): Which customer's order price is higher than their bar's average order price?
<img width="623" alt="Screenshot 2025-03-20 at 11 47 31 AM" src="https://github.com/user-attachments/assets/cb203cee-9da9-4581-b3dd-680a52da53df" />

Query 5 identifies which customer order prices are higher than the bar’s average order price. This is beneficial for bar managers because it gives insight as to which customers frequently spend a lot of money at the bar, allowing the bar to develop promotions or loyalty programs for customers who consistently spend the average amount, or create performance benchmarks based on average order values across different bars.

QUERY 6 (complex): Which employee's revenue per order exceeds the industry average?
<img width="1138" alt="Screenshot 2025-03-20 at 11 48 56 AM" src="https://github.com/user-attachments/assets/00756c71-c0df-4358-96d2-2a4ececae2de" />

Query 6 works to compute the revenue per order for each employee by dividing their total generated revenue by the number of orders. This identifies the employees whose average revenue per order exceeds the industry average (calculated across all orders). This is useful for bar managers to identify employees who consistently generate higher-than-average revenue per order, which indicates strong upselling skills or customer engagement. This would further help bar managers when it comes to staffing decisions, such as shifts, roles, scheduling, etc.

QUERY 7 (complex): How much revenue does each drink type produce, and what % of total drink revenue does it account for?
<img width="1139" alt="Screenshot 2025-03-20 at 11 49 36 AM" src="https://github.com/user-attachments/assets/eac48422-2006-41fe-9099-d73ac203542e" />

Query 7 calculates the total revenue and percentage contribution of each drink’s revenue to overall drink sales, ranked by highest-earning items. This shows which drinks drive profitability and which underperform relative to others. This helps bar managers to understand the high-revenue drinks, which signals the need to prioritize those drinks’ inventory and marketing efforts. This data is also helpful for understanding customer preferences and behaviors to better tailor menu offerings.

QUERY 8 (complex): How much revenue does each bar's marketing campaign produce?
<img width="623" alt="Screenshot 2025-03-20 at 11 50 22 AM" src="https://github.com/user-attachments/assets/1c5c5710-cc26-4527-ae61-775f15371260" />

Query 8 provides insight into the success of various marketing campaigns employed by different bars. This information can be used by managers who are considering launching a campaign or would like to review the success/failure of a past marketing campaign. This query lists each marketing campaign as a promo name and the corresponding bar it belongs to. The query also filters orders made during the campaign and the total revenue it led to. 

QUERY 9 (complex): What is the most common Food/Drink pairing in orders?
<img width="625" alt="Screenshot 2025-03-20 at 11 50 58 AM" src="https://github.com/user-attachments/assets/c5dcc46c-226c-4810-91b4-1f9736abcd51" />

Query 9 allows managers to see what are the most frequently paired items from both food and drink menu options. Combination orders typically lead to a higher total order price, so it’s worthwhile for managers to research this information. This query lists the foodItem/drinkItem pair and the number of times that pair was ordered across all bars in our database. Finally, the results are displayed by order frequency in descending order

QUERY 10 (complex): List suppliers, their contact info, and the number of instances where food item ingredients are low/out of stock
<img width="626" alt="Screenshot 2025-03-20 at 11 51 41 AM" src="https://github.com/user-attachments/assets/eeccd696-347b-4ff5-9fe6-a2c1a5c8564f" />

Query 10 provides vital information for managers looking to monitor food ingredient inventory status and reassess supplier relationships. Since low/out-of-stock typically negatively impacts a bar’s sales, managers will be eager to evaluate which suppliers are responsible for the supply and either contact them or look for alternative suppliers. This query counts the number of distinct food items whose stock is either low or out in the database. Results are grouped by supplier ID, supplier name, and contact information for managers looking to reach out. 

## Database Information

Name of the database: al_ra14858





