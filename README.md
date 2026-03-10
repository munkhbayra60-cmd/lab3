-- UNION жишээ
SELECT city FROM customers UNION SELECT city FROM customers;

-- UNION ALL жишээ
SELECT city FROM customers UNION ALL SELECT city FROM customers;
-- Ажилтан ба түүний менежер
SELECT e.name AS employee, m.name AS manager
FROM employees e
LEFT JOIN employees m ON e.manager_id = m.employee_id;
SELECT c.name, o.order_date, p.product_name, oi.quantity
FROM customers c
JOIN orders o ON c.customer_id = o.customer_id
JOIN order_items oi ON o.order_id = oi.order_id
JOIN products p ON oi.product_id = p.product_id;
erDiagram
    ORDERS ||--o{ ORDER_ITEMS : contains
    PRODUCTS ||--o{ ORDER_ITEMS : "is in"
    CUSTOMERS ||--o{ ORDERS : places
