# **Data-Science-in-Golf-Strokes-Gained-vs-Traditional-Metrics**

Unleashed the power of data science to analyze the performance of golfers from the PGA tour. Built ML models and compared Strokes Gained to traditional metrics, resulting in insightful findings and actionable recommendations for golfers at all levels. Showcased advanced data analysis, ml models, and visualizations in this comprehensive project.

### **Objectives**

The objective of this project is to analyze data from the 2010 to 2018 PGA tour season using various metrics, including Strokes Gained, to draw insight into the performance of professional golfers. The specific objectives of this project are as follows:

* Draw insight from data from the 2010 to 2018 PGA tour season.
    * Which features lead to the greatest success in golf? Specifically compare how **strokes gained stats compare to the traditional stats**. 
    * Investigate if the traditional view that **short game (putting and chipping) is more valuable than long game skills (driving and approach shots)**?
    * Investigate if the traditional view that **driving accuracy (fairways hit %) is more valuable than driving distance**?
* Determine a the **highest impact features** to measure "sucess" in golf,
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

--------------------------------
## **Model Building**
--------------------------------
### **Conclusions**
#### **Model Performance**
We built multiple decision tree based models that can predict average_score, they generally **performed well** but with varying degrees **overfitted**:

Both the random forest models rf_1 and rf_2 performed well with:
    * rf_1 being overall more accurate
    * rf_2 being slighlty less overfitted
**The best option moving forward for a generalized model is likely rf_1 giving the greater accuracy of 86%.**

#### **Feature Importance**
Feature importance showed that:
   * **Strokes Gained Approach** is the **highest impact** feature for determining a players score.
   * Strokes Gained Off The Tee and Average Scrambling show **significant impact** for a players score.
   * Strokes Gained Putts and Strokes Gained Around The Green show **minor impact** for a players score.
   * Average Putts, Greens in regulation, driving distance, and fairway percentages showed **very little impact** for a players score. 
    
    
This, along with insight drawn from EDA, answers a number of our objective questions:
   * We can see the **top impact features** for a players score, and therefore the **skills golfers should prioritize** first, are **approach shots, tee shots, and then scrambling**.
      * Although it is likely that scrambling only performed better than SG-Putts and SG-Around the green because it is a sudo combination of those to metrics that is biased towards better play. 
  * Between the strokes gained stats and traditional stats, **strokes gained is clearly more impactfull**. With **traditional metrics having little to no impact** other than average scrambling. 
  * The traditional view that short game is a higher priority than long game is also debunked, with **long game metrics holding the top 2 positions**. 
  * The hypothesis that **fairways percentage** is a missleading metric is also confirmed with it holding the **lowest ranking position**.  
  
### **Recommendations**
#### **Model Improvements**
* While our model performs with a high accuracy of 86% and will likely generalize well, there still **room for improvement in both accuracy and overfitting**. Given the training and testing gap remained even with many itterations of tuning, we speculated these issues are likely coming from having a relatively **small data set of 1,678**. To further improve our model it is recomended:

**Increase our data** set by finding additional data bases to draw from and merge with our current dataset.
  * We can do this by sampling from PGA tour data outside of the 2010 to 2018 seasons
       * However we should perhaps avoid the covid season of 2020-2021 as the data could be biased
  * A better option to increase our data would be to sample from outside of the PGA tour. Not only would this give us more data but a greater range of player skill levels and therefore more diverse data. The best option for this would likely come from the ameture and college golf leagues as the recording of data is held to a high efficacy.
  
#### **Applications**
Beyond the insights derived from our model it also has many practical applications. We can easily use this to predict a players performance given their past years stats, and therefore show players what the impact improvements in each stat would have. 

It should also be noted that while Strokes Gained stats have prooven to be of higher impact, they are not as practical to record as the more traditional stats. However, there is potential to train other models using this data to predict the strokes gained stats using the more traditional stats, specifically:
  * SG Putts could be derived from gir, Average_Putts, and Average_Scrambling.
  * SG ARG could be derived from gir, Average_Putts, and Average_Scrambling.
  * SG-APR could be derived from Avg_Distance, Fairway_Percentage.
  * SG-OTT could be derived from Avg_Distance, Fairway_Percentage.

It would likely take additional features to do this with the needed accuracy but we could then use all the models in combination to take easily measured stats, to predict strokes gained stats, and then average score. For the everyday player this would provide a valuable system that would show them how to best improve at the game. 
