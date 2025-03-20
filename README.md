# Team 4 Mist 4610 Group Project 1

## Team Name:
**Group 4**

## Team Name:
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

