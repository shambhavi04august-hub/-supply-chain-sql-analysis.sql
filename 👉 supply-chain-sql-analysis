--- capstone_p ---

create database capstone;

use capstone;

RENAME TABLE `operations_supply_chain_logistics_2.0`
TO operations_supply_chain_logistics_2_0;


-- Question NO. 1 ---

SELECT 
    YEAR(order_date) AS Year,
    MONTH(order_date) AS Month,
    COUNT(order_id) AS Total_Orders,
    SUM(quantity) AS Total_Quantity
FROM operations_supply_chain_logistics_2_0
GROUP BY YEAR(order_date), MONTH(order_date)
ORDER BY Year, Month;

-- Question 2 --

SELECT 
    warehouse,
    AVG(DATEDIFF(delivery_date, order_date)) AS avg_delivery_time_days
FROM operations_supply_chain_logistics_2_0
GROUP BY warehouse
ORDER BY avg_delivery_time_days DESC;

-- Question 3 --

SELECT 
    shipping_mode,
    ROUND(SUM(shipping_cost) / SUM(quantity), 2) AS cost_per_unit
FROM operations_supply_chain_logistics_2_0
GROUP BY shipping_mode
ORDER BY cost_per_unit DESC;

-- Question 4 --

SELECT 
    supplier,
    AVG(DATEDIFF(delivery_date, order_date)) AS Avg_Delivery_Days
FROM operations_supply_chain_logistics_2_0
GROUP BY supplier
ORDER BY Avg_Delivery_Days DESC;

-- Question 5 --

SELECT 
    order_id,
    stock_level,
    reorder_point
FROM operations_supply_chain_logistics_2_0
WHERE stock_level < reorder_point
ORDER BY stock_level DESC;


-- Question 5 --

SELECT 
    warehouse,
    COUNT(order_id) AS Total_Orders,
    AVG(DATEDIFF(delivery_date, order_date)) AS Avg_Delivery_Days,
    SUM(ABS(total_cos)) AS Total_Cost
FROM operations_supply_chain_logistics_2_0
GROUP BY warehouse
ORDER BY Total_Orders DESC;
