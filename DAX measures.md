# 📊 Power BI DAX Measures  

This file contains all DAX measures used in the Interactive Business Performance Dashboard with Power BI.

---

## **Measure Table**  

```DAX
1. Return Rate = 
DIVIDE(
    [Quantity Returned],
    [Quantity Sold],
    "No Sales"
)  

2. Revenue Target = [Previous Month Revenue] * 1.1  

3. Revenue Target Gap = [Total Revenue] - [Revenue Target]  

4. Total Cost = 
SUMX(
    'Sales Data',
    'Sales Data'[OrderQuantity] * 
    RELATED('Product Lookup'[ProductCost])
)  

5. Total Customers = DISTINCTCOUNT('Sales Data'[CustomerKey])  

6. Total Orders = DISTINCTCOUNT('Sales Data'[OrderNumber])  

7. Total Orders (Customer Detail) = 
IF(
    HASONEVALUE('Customer Lookup'[CustomerKey]),
    [Total Orders],
    "-"
)  

8. Total Profit = [Total Revenue] - [Total Cost]  

9. Total Returns = COUNT('Returns Data'[ReturnQuantity])  

10. Total Revenue = 
SUMX(
    'Sales Data',
    'Sales Data'[OrderQuantity] * 
    RELATED('Product Lookup'[ProductPrice])
)  

11. Total Revenue (Customer Detail) = 
IF(
     HASONEVALUE('Customer Lookup'[CustomerKey]),
     [Total Revenue],
     "-"
)  

12. Weekend Orders = 
CALCULATE(
    [Total Orders],
    'Calendar Lookup'[Weekend] = "Weekend"
)  

13. YoY Growth Rate = 
DIVIDE(
    [Total Revenue] - [Previous Year Revenue],
    [Previous Year Revenue]
)  

14. YTD Revenue = 
CALCULATE(
    [Total Revenue],
    DATESYTD('Calendar Lookup'[Date])
)  

15. % of All Orders = 
DIVIDE(
    [Total Orders],
    [All Orders]
)  

16. % of All Returns = 
DIVIDE(
    [Total Returns],
    [All Returns]
)  

17. 10-day Rolling Revenue = 
CALCULATE(
    [Total Revenue],
    DATESINPERIOD(
        'Calendar Lookup'[Date],
        MAX('Calendar Lookup'[Date]),
        -10,
        DAY
    )
)  

18. 90-day Rolling Profit = 
CALCULATE(
    [Total Profit],
    DATESINPERIOD(
        'Calendar Lookup'[Date],
        MAX('Calendar Lookup'[Date]),
        -90,
        DAY
    )
)  

19. Adjusted Price = [Average Retail Price] * (1 + 'Price Adjustment (%)'[Price Adjustment (%) Value])  

20. Adjusted Profit = [Adjusted Revenue] - [Total Cost]  

21. Adjusted Revenue = 
SUMX(
    'Sales Data',
    'Sales Data'[OrderQuantity] * [Adjusted Price]
)  

22. All Orders = 
CALCULATE(
    [Total Orders],
    ALL('Sales Data')
)  

23. All Returns = 
CALCULATE(
    [Total Returns],
    ALL('Returns Data')
)  

24. Average Retail Price = AVERAGE('Product Lookup'[ProductPrice])  

25. Average Revenue per Customer = 
DIVIDE(
    [Total Revenue],
    [Total Customers]
)  

26. Average YoY Growth Rate = 
AVERAGEX(
    VALUES('Calendar Lookup'[Year]),
    [YoY Growth Rate]
)  

27. Bike Return Rate = 
CALCULATE(
    [Return Rate],
    'Product Categories Lookup'[CategoryName] = "Bikes"
)  

28. Bike Returns = 
CALCULATE(
    [Total Returns],
    'Product Categories Lookup'[CategoryName] = "Bikes"
)  

29. Bike Sales = 
CALCULATE(
    [Quantity Sold],
    'Product Categories Lookup'[CategoryName] = "Bikes"
)  

30. Bulk Orders = 
CALCULATE(
    [Total Orders],
    'Sales Data'[OrderQuantity] > 1
)  

31. High Ticket Orders = 
CALCULATE(
    [Total Orders],
    FILTER(
        'Product Lookup',
        'Product Lookup'[ProductPrice] > [Overall Average Price]
    )
)  

32. Order Target = [Previous Month Orders] * 1.1  

33. Order Target Gap = [Total Orders] - [Order Target]  

34. Overall Average Price = 
CALCULATE(
    [Average Retail Price],
    ALL('Product Lookup')
)  

35. Previous Month Orders = 
CALCULATE(
    [Total Orders],
    DATEADD('Calendar Lookup'[Date], -1, MONTH)
)  

36. Previous Month Profit = 
CALCULATE(
    [Total Profit],
    DATEADD('Calendar Lookup'[Date], -1, MONTH)
)  

37. Previous Month Returns = 
CALCULATE(
    [Total Returns],
    DATEADD('Calendar Lookup'[Date], -1, MONTH)
)  

38. Previous Month Revenue = 
CALCULATE(
    [Total Revenue],
    DATEADD('Calendar Lookup'[Date], -1, MONTH)
)  

39. Previous Year Revenue = 
CALCULATE(
    [Total Revenue],
    PARALLELPERIOD('Calendar Lookup'[Date], -1, YEAR)
)  

40. Profit Target = [Previous Month Profit] * 1.1  

41. Profit Target Gap = [Total Profit] - [Profit Target]  

42. Quantity Returned = SUM('Returns Data'[ReturnQuantity])  

43. Quantity Sold = SUM('Sales Data'[OrderQuantity])

```
---

## **Price Adjustment % Table**

```DAX
1. Price Adjustment (%) = GENERATESERIES(-1, 1, 0.1)  

2. Price Adjustment (%) Value = SELECTEDVALUE('Price Adjustment (%)'[Price Adjustment (%)], 0)

```
---

## **Customer Metric Selection Table**

```DAX
1. Customer Metric Selection = {
    ("Total Customers", NAMEOF('Measure Table'[Total Customers]), 0),
    ("Revenue per Customer", NAMEOF('Measure Table'[Average Revenue per Customer]), 1)
}

```
---

