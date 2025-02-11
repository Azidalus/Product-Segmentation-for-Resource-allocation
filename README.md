# Product-Segmentation-for-Resource-allocation
## Table of contents
* [Project background](https://github.com/Azidalus/Product-Segmentation-for-Resource-allocation#Project-background)
* [Data structure](https://github.com/Azidalus/Product-Segmentation-for-Resource-allocation#Data-structure)
* [Executive summary](https://github.com/Azidalus/Product-Segmentation-for-Resource-allocation#Executive-summary)
* [Recommendations](https://github.com/Azidalus/Product-Segmentation-for-Resource-allocation#Recommendations)

## Project background
Amazon is a global e-commerce company selling products of various categories via its website and mobile app. 

The company has big amounts of data on its sales. This project analyzes this data in order to optimize Amazon's inventory so that the company knows on what SKUs to focus. Based on the analysis insights, recommendations are provided for two departments: supply chain and marketing.

## Data structure
Sales data consists of one table with 487,827 rows. To perform the inventory analysis, data from one month, November 2010, is used, as for a fast-paced industry like retail monthly trends are important. The total number of rows used in analysis is 77,733 and the total number of SKUs is 2,927.

![Untitled (5)](https://github.com/user-attachments/assets/fd53b4e3-3454-4737-9a07-e4925063e56d)

## Executive summary

### ABC Analysis
The resultant ABC analysis chart: 

![image](https://github.com/user-attachments/assets/129a0efc-22af-4950-93c0-c7fed8ad4bae)

Out of total of 2,927 SKUs to be managed:
- The top 10% products contribute to 60% of revenue (class A). These are high-value items, often characterized by high demand, significant sales volume, and potential stockout risks.
- 28% products contribute to 25% of revenue (class B). These items hold moderate importance.
- 62% products contribute to 10% of revenue (class C). These are low-value items, often characterized by low demand and minimal impact on overall inventory costs.

### ABC-XYZ Analysis
ABC classification can be oversimplistic, so to form more analytically advanced groups of inventory, another dimension is included for product classification: XYZ classification, which classifies SKUs based on their demand/consumption variability. 

The resultant ABC-XYZ analysis chart:

![image](https://github.com/user-attachments/assets/1d3ea98d-cddc-49c5-88e6-debe501d1439)

Challenges come from the items with CoV > 1.2, as coefficient of variation greater than 1.2 indicates unstable demand that needs more attention.

## Recommendations
**For marketing department**
- We should invest resources in marketing and promoting class B SKUs in order to increase their sales potential, as this group consists of only 28% of items but contributes to a good percentage of revenue (25%).

### For supply chain department
**High priority:**
- Pay close attention to the 297 references from class A. We should always have these items in stock, as they comprise as little as 10% of SKUs, while bringing 60% of revenue.
- Focus on accurate demand forecasting and inventory planning for AX and AY items, and only then for AZ items. Use advanced forecasting methods, collaborate with suppliers for better demand visibility.

**Medium priority:**
- Implement inventory management strategies for the 755 items from class B.
- For SKUs in BY and BZ classes, use safety stock to minimize stock-out risks while keeping inventory costs under control.
    
**Last priority:**
- For all class C items, use inventory optimization techniques such as periodic review to minimize holding costs, as these items have the highest demand volatility.

- **A-class (Blue)**: the highest-priority SKUs in terms of sales volume and revenue contribution.
  - Pay close attention to these 297 references to ensure optimal inventory levels.
  - Focus on accurate demand forecasting and inventory planning.
- **B-class (Yellow)**: moderate impact on revenue.
  - Implement inventory management strategies for these 755 items.
  - For SKUs with CoV > 1.2, use safety stock to minimize stock-out risks while keeping inventory costs under control.
- **C-class items (Red)**: the lowest impact on revenue.
  - Coincidentally, these items have the highest demand volatility, so they should have the last focus.
  - Use inventory optimization techniques such as periodic review to minimize holding costs.

## Background
A common approach to this inventory management problem is **ABC analysis**. ABC analysis is a method of dividing inventory into three classes - A, B, and C - based on the total annual/monthly consumption value of items. 
- **Class A items**: constitute 20% of the total number of SKUs in the inventory and account for about 80% of the total consumption value. These are high-value items, often characterized by high demand, significant sales volume, and potential stockout risks. These items must always be in-stock.
- **Class B items**: represent around 30% of inventory SKUs and contribute approximately 15% of the total consumption value. These items hold moderate importance, requiring a balance between maintaining sufficient stock levels and controlling carrying costs.
- **Class C items**: typically comprise the remaining 50% of the inventory SKUs but contribute only around 5% of the total consumption value. These are low-value items, often characterized by low demand and minimal impact on overall inventory costs. They should be given low priority in marketing and sales.

However, ABC classification is, for many situations, over simplistic. Prioritising items only based on their value misses many other important factors that should influence what inventory to hold. We therefore can combine it with another common analysis - **XYZ analysis** - to form more analytically advanced groups of inventory. \
XYZ analysis classifies SKUs based on their demand/consumption variability. X class items are with the lesser uncertainty, while Z class items with the highest uncertainty, meaning the most difficult to manage.
- **X-items**: regular demand
- **Y-items**: strong variability in demand
- **Z-items**: very irregular and difficult to predict demand
