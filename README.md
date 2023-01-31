# **Data-Science-in-Golf-Strokes-Gained-vs-Traditional-Metrics**

Unleashed the power of data science to analyze the performance of golfers from the PGA tour. Built ML models and compared Strokes Gained to traditional metrics, resulting in insightful findings and actionable recommendations for golfers at all levels. Showcased advanced data analysis, ml models, and visualizations in this comprehensive project.

### **Objectives**

The objective of this project is to analyze data from the 2010 to 2018 PGA tour season using various metrics, including Strokes Gained, to draw insight into the performance of professional golfers. The specific objectives of this project are as follows:

* Draw insight from data from the 2010 to 2018 PGA tour season.
    * Which features lead to the greatest success in golf? Specifically compare how **strokes gained stats compare to the traditional stats**. 
    * Investigate if the traditional view that **short game (putting and chipping) is more valuable than long game skills (driving and approach shots)**?
    * Investigate if the traditional view that **driving accuracy (fairways hit %) is more valuable than driving distance**?
* Determine a the **best predictive feature** to measure "sucess" in golf,
* Build a prediction model for "success" in golf based on based on that feature.
* Compare the effectiveness of the Strokes Gained metrics to traditional metrics in predicting success by conducting **feature analysis** on the impact of different metrics. 

--------------------------------
## **Exploratory Data Analysis (EDA)**
--------------------------------
### **Results**

* Average_Score is a good metric that focuses on playing well. **It is our best option of all predictive features**. 
* Strokes gained features beat out the other top 4 traditional features in **overall correlation** with `Average_Score`(1.96 versus 1.55)
* In correlation with Average_SG_Total : SG:APR(0.67) > SG:OTT(0.53) > SG:ARG(0.39) > Average_SG_Putts(0.36)
  * Showing that the traditional view short game is the higher value skill is likely incorect and in fact the opposite is likely to be true.
  * This is visualized and re-confirmed in our scatter plots
* Our hypothesis that fairways hit in regulation is a traditional stat that sounds good but can be misleading has prooven to be true, having the lowest correlation of 0.17 with `Average_Score`.
* The same is similarly true for greens hit in regulation, despite having a correlations of (0.49) with `Average_Score` it performs worse than its strokes gained counter-part SG_APR with a correlation of (0.67). Meaning that there are likely miss-leading shots in `gir` that are reducing its total correlation. 
* Driving distance has a greater correlation with average score than fairway percentage (0.27 vs 0.17). This means that our second traditional view that driving accuracy (fairways hit %) is more valuable than pure driving distance is also likely a myth.
  * This is confirmed visualy by our scatter plot showing driving distance has a much tigher relationship.

