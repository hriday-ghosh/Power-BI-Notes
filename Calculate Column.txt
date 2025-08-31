Delivery Comission =   -- This creates a new column/measure called "Delivery Commission"

CALCULATE(             -- CALCULATE changes the filter context (it tells DAX: 
                       -- "Do this calculation, but first apply some filters")

    MAX(table_deliverypartner[Commission]),  
                       -- MAX() is an aggregation function. 
                       -- It finds the highest number in the column [Commission] 
                       -- from the table 'table_deliverypartner'.

    RELATEDTABLE(table_deliverypartner)  
                       -- RELATEDTABLE() returns all rows from the related table 
                       -- 'table_deliverypartner' that are connected to the 
                       -- current row (through relationships in your data model). 
                       -- Basically: "Filter the delivery partner table 
                       -- so I only see rows related to the current row I’m on."
)
