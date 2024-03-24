<a name="br1"></a> 

**SUPPLY CHAIN SOLVER USING MACHINE**

**LEARNING**

· **INTRODUCTION**

This repository contains a Python implementation of a supply chain network optimization model

using the PuLP library. The model is designed to help businesses make informed decisions

regarding their manufacturing and distribution processes. It considers various factors such as

fixed and variable costs, manufacturing capacities, shipping costs, and customer demand to

optimize the supply chain network.

· **PROBLEM STATEMENT**

As the Head of Supply Chain Management for an international manufacturing company, I aim to

redefine our Supply Chain Network over the next 5 years. Our network encompasses five key

markets: Brazil, USA, India, Japan, and Germany. We operate two types of manufacturing

facilities: low-capacity and high-capacity sites. To optimize our network, we must account for

recent increases in shipping costs and forecasted customer demand. Our considerations include

the following factors:

**Shipping Costs ($/container):** We need to analyze the costs associated with shipping containers

between different locations to determine the most cost-effective transportation routes.

**Customer Demand (Units/year):** Understanding the forecasted demand in each market is

crucial for aligning our production capacities with the needs of our customers.

**Manufacturing Facility Fixed Costs:**

By optimizing our supply chain network considering these factors, we aim to enhance

operational efficiency, minimize costs, and ensure timely delivery of products to meet customer

demands effectively.

1\. MANUFACTURING FIXED COST PER PLANT

![image](https://github.com/prabhneetS/SupplyChainSolver/assets/163606021/77f9233e-7cd2-48e9-93d4-e314f707cf82)


<a name="br2"></a> 

This encompasses various expenses such as capital expenditure for equipment, utilities

(electricity, water), factory management, administrative staff, and space rental. These fixed costs

vary depending on the country and the type of manufacturing plant.

2\. MANUFACTURING VARIABLES COST

![image](https://github.com/prabhneetS/SupplyChainSolver/assets/163606021/3075ad8e-b190-4130-ae98-ba7937def9b5)


The variable cost includes the production line operators and cost of procuring raw materials for

manufacturing of the product.

3\. SEA FREIGHT SHIPPING COSTS ($/CONTAINER)

![image](https://github.com/prabhneetS/SupplyChainSolver/assets/163606021/572b6620-3225-41fa-8a7c-6c232a438bc0)


This table includes the cost of shipping the product from X to Y place in a container assuming 1

container contain 1000 containers.

4\. MANUFACTURING SITE CAPACITY

![image](https://github.com/prabhneetS/SupplyChainSolver/assets/163606021/d6a33895-c85d-44bf-8d51-551ee16e2dae)


This table contains the capacity of each site to produce the units per month

5\. CUSTOMER’S DEMAND PER MARKET

![image](https://github.com/prabhneetS/SupplyChainSolver/assets/163606021/3c4f4939-9b0a-4797-87b6-80f856cf4e73)


<a name="br3"></a> 

This table contains the expected demand of the goods from each market around the globe per

month.

· **OBJECTIVE FUNCTION AND CONSTRAINTS:**

The objective function is defined to minimize total costs, considering fixed costs and variable

costs.

Constraints are added to ensure that production quantities meet demand and do not exceed

manufacturing capacities.

· **SOLVING THE MODEL AND ANALYSIS:**

The model is solved using the PuLP solver and we have taken 3 different scenarios which are

**1. INITIAL SCENARIO**

![image](https://github.com/prabhneetS/SupplyChainSolver/assets/163606021/ffa23d82-25f6-4417-92be-0a155b3f544c)

Brazil plant is producing for the local market and the USA to meet its demand

![image](https://github.com/prabhneetS/SupplyChainSolver/assets/163606021/8a46a887-90b7-494b-9df5-4da6aa30a74d)

India plant produce for all countries except Brazil



<a name="br4"></a> 

![image](https://github.com/prabhneetS/SupplyChainSolver/assets/163606021/bf3a0f96-7d65-49e5-a126-cf2bdd16b57c)

Japan needs to produce locally because of the limited capacity of India

![image](https://github.com/prabhneetS/SupplyChainSolver/assets/163606021/e127d38c-e468-4676-9ced-3c01fa820f79)

Total cost to produce the goods

**2. SCENARIO 2: OUTSOURCING TO LOW COSTS REGIONS**

What if we double the size of high-capacity plants in India?

Let us try to double the size of the India High Capacity plant, assuming that it will double the fixed

costs.

![image](https://github.com/prabhneetS/SupplyChainSolver/assets/163606021/51c4bc83-7297-48c5-bc6f-b129984915a7)

Brazil plant is still producing for the local market and the USA

![image](https://github.com/prabhneetS/SupplyChainSolver/assets/163606021/2506a6cc-b3a5-4fe8-84c9-85a425045565)

India plants produce for all countries except Brazil

Japan does not produce locally anymore.

![image](https://github.com/prabhneetS/SupplyChainSolver/assets/163606021/d5d36e9b-6a03-46cb-ac78-0f335dde3b5d)

Final Costs



<a name="br5"></a> 

**3. SCENARIO 3: SURGING SHIPPING COSTS DUE TO CONTAINER SHORTAGE**

What if we have container costs multiplied by 5?

![image](https://github.com/prabhneetS/SupplyChainSolver/assets/163606021/b5834f62-488d-4732-bf2c-9cbde9cae914)

Brazil is producing for the local market only

![image](https://github.com/prabhneetS/SupplyChainSolver/assets/163606021/d81fa9a8-28ec-46c1-9f31-f8557012ee31)

The USA started to produce for the local market, and Japan

![image](https://github.com/prabhneetS/SupplyChainSolver/assets/163606021/a6dfe5ad-557f-41c8-9a8f-d5c435418ba1)

India closed its low-capacity factory

![image](https://github.com/prabhneetS/SupplyChainSolver/assets/163606021/e30c8fb6-d38d-4927-ad9c-9dfeeebba3df)

Japan starts to produce for its local market

Because of their limited production capacity, Japan and the USA still rely on the Indian plant.

![image](https://github.com/prabhneetS/SupplyChainSolver/assets/163606021/209732d9-0a80-4533-8ce7-b59aff5dccee)

Final Costs

· **HOW CAN THIS MODEL HELP BUSINESSES?**



<a name="br6"></a> 

1\. **Cost Reduction**: By optimizing the supply chain network, businesses can minimize

manufacturing and shipping costs, leading to overall cost reduction.

2\. **Capacity Planning**: The model assists in determining the optimal manufacturing capacity for

each location based on demand forecasts, thereby improving resource utilization and efficiency.

3\. **Demand Fulfillment**: By aligning production quantities with customer demand, businesses can

ensure timely delivery and enhance customer satisfaction.

4\. **Scenario Analysis:** The model allows businesses to simulate different scenarios (e.g., changes in

production capacity, fluctuations in shipping costs) to evaluate their impact on costs and make

informed decisions accordingly.

5\. **Risk Mitigation:** Businesses can use the model to identify potential risks such as supply chain

disruptions or capacity constraints and develop contingency plans to mitigate these risks.

6\. **Competitive Advantage:** Optimizing the supply chain network enables businesses to operate

more efficiently, leading to improved competitiveness and profitability in the market.

· **HOW TO USE:**

Ensure you have Python installed on your system along with the necessary libraries (PuLP,

pandas).

Download the provided Python script and Excel files containing relevant data.

Run the script in a Python environment.

Analyze the results to make informed decisions about your supply chain network optimization.

· **NOTE:**

This model provides a foundational framework that can be customized and extended to suit

specific business requirements.

Continuous improvement and refinement of the model parameters based on real-world data and

feedback are recommended for ongoing optimization.

· **CONTRIBUTOR:**

Prabhneet Singh

For any inquiries or feedback, please contact prabhneets50@gmail.com


