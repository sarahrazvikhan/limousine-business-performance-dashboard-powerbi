## DAX Measures & Calculations

This project uses DAX measures in Microsoft Power BI to calculate key business metrics related to revenue, operations, and profitability in a ride-hailing / limousine business.

###  Core KPIs

Total Revenue
Total Revenue = SUM(Trips[Fare_AED])

Total Trips
Total Trips = COUNT(Trips[Trip_ID])

Average Fare
Avg Fare = AVERAGE(Trips[Fare_AED])

Total Distance
Total Distance = SUM(Trips[Distance_km])


###  Revenue Analysis

Revenue per Car Type
Revenue per Car Type = SUM(Trips[Fare_AED])

Revenue per Platform
Revenue per Platform = SUM(Trips[Fare_AED])


###  Time-Based Analysis

Hour (Calculated Column)
Hour = HOUR(TIMEVALUE(Trips[Time]))

Revenue by Hour
Revenue by Hour = SUM(Trips[Fare_AED])

Trips per Day
Trips per Day = COUNT(Trips[Trip_ID])


###  Vehicle Cost & Profitability

Monthly Cost
Monthly Cost = SUM(Vehicle_Cost[Monthly_Cost_AED])

Revenue by Car
Revenue by Car = SUM(Trips[Fare_AED])

Profit
Profit = [Total Revenue] - [Monthly Cost]

ROI %
ROI % = DIVIDE([Profit], [Monthly Cost], 0)


###  Advanced Metrics

Average Rating
Avg Rating = AVERAGE(Trips[Customer_Rating])

Revenue per Trip
Revenue per Trip = DIVIDE([Total Revenue], [Total Trips], 0)

Driver Rank
Driver Rank =  RANKX(     ALL(Trips[Driver_ID]),     [Total Revenue],     ,     DESC )


##  Notes & Assumptions

- Revenue is calculated using trip fare in AED.
- Monthly vehicle cost is treated as a fixed cost per car type.
- ROI is calculated as Profit divided by Monthly Cost.
- Time-based analysis is performed using extracted hourly data.


##  Limitations

- Dataset is simulated and may not reflect real-world variability.
- Monthly cost is not allocated per trip (simplified assumption).
- External factors like fuel, maintenance, and driver incentives are not included.
