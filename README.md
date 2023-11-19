# Customers-Segmentation
-----------------------------------------------------------
This aim of this project is to analyze and categorize customers according to their preferences, behaviors, and demographics. The valuable insights gained from this segmentation endeavor will enable companies to optimize their marketing strategies, services, and offerings, ensuring a more personalized approach that addresses the distinct needs of various customer groups.

# Methodology
-----------------------------------------------------------
One of the most popular, easy-to-use, and effective segmentation methods to enable marketers to analyze customer behavior is LRFMC analysis:

* **Length**: the length of days between subscriber's first register day to observation time. A larger number means they have been a member for a longer time (the bigger the better)
* **Recency**: the length of a passenger's last consumption to observation window. A smaller number means they flew more recently (the smaller the better)
* **Frequency** the passenger's consumption frequency within a certain period of time. A bigger number means they flew more frequently (the bigger the better)
* **Monetary** the average amount spent over a certain period of time. A bigger number means they spent more money (the bigger the better)
* **Discount Coefficient**: the average space discount factor for passengers traveling within a certain period of time A bigger number means they use discounts more (the smaller the better)

Therefore, we base our feature selection on this LFRMC analysis:
* **L**ength: `LOAD_TIME` - `FFP_DATE`
* **R**ecency: `LAST_TO_END`
* **F**requency: `FLIGHT_COUNT`
* **M**onetary: `SEG_KM_FM`
* **C**ustomer Cost: `avg_discount`

The K-means algorithm was used to segment the customers, with the elbow method and the silhouette score to determine the optimal number of clusters (k-value).

## Conclusion
From elbow plot, there is a possibility that the optimum clusters are 4-6. After consider the business perspective,
we decide that the suitable number of clusters are 5. The clusters are:
1. Cluster 1 - The Hibernating Customers 
2. Cluster 2 - The Promising Customers 
3. Cluster 3 - The Loyal Customers 
4. Cluster 4 - The Old-Seasonal Customers 
5. Cluster 5 - The Cheap Customer 
