# Property-Analytics-Dashboard

<img width="605" alt="Property_Dashboard" src="https://github.com/user-attachments/assets/138d9823-056a-46e8-acdc-5aa92b8ca82f" />

## Table of Contents
- [Approach and Analysis](#approach-and-analysis)
- [Tools used](#tools-used)
- [DAX](backend)
- [Insights](Insights)

## Approach and Analysis
- To understand the data in depth used MS Excel Pivot table.
- Post understanding the requirements, the suitable KPIs were listed down.
- Utilized Figma to incorporate the colour theme and build a canvas befitting the topic, and thereafter also to design icons.
- Built the DAX models and calculated column “Efficiency category”
- Now, to make the navigation smooth, the bookmarks were utilized in addition to blank buttons to build the slicer panel and page navigation.


## Tools used
- MS Excel: for data cleaning
- Power BI: for data visualization
- Figma: Designing and Protoyping the wireframe

## DAX

### Efficiency Category
    ````DAX
    Efficiency Category = 
        IF([Energy Consumption per Sqft] < 30,
        "High Efficiency",
            IF([Energy Consumption per Sqft] <= 40,
            "Medium Efficiency",
                "Low Efficiency"
             )
            )

### Energy Conusmption per Sqft
    Energy Consumption per Sqft = 
        DIVIDE(
            SUM(
                'Data Table'[Annual Energy Consumption (kWh)]),
                 [Total Sqft]
                )

### Average Building Age
    Avg_Building_Age = 
            AVERAGE('Data Table'[Building Age])

### Average Occupancy Rate
    Average Occupancy Rate = 
            AVERAGE('Data Table'[Occupancy Rate])

            
## Insights
- Retail properties have the lowest average building age (11 years) despite having the smallest average square footage, while mixed-use properties show a relatively older average age (16.5 years).
-     This inverse relationship between property size and age suggests newer developments may prioritize smaller retail spaces, while mixed-use properties, often older, reflect historical urban planning trends favoring multi-functional buildings
  
- The analysis reveals a clear correlation: as the building age range widens (e.g., 5–10 years vs. 5–20 years), energy consumption per square foot increases progressively (31.10 kWh/sqft to 32.72 kWh/sqft) while occupancy rates decline (93.17% to 90.64%), indicating a relationship between property age, energy efficiency, and utilization.
- Mixed-use properties exhibit the highest annual energy consumption per square foot (33.91 kWh/sqft), followed by retail (32.71 kWh/sqft) and office spaces (32.22 kWh/sqft), despite office properties having the largest total square footage.
  -     This suggests that mixed-use buildings, which combine multiple functions like residential and commercial spaces, may have higher energy demands due to their complex operational requirements, while office properties offset their larger total size with comparatively lower per-unit energy usage.




