- **Steps**
    1. Start with k centroids by putting them at random points here k =2
    2. Compute distance of every point from centroid and cluster them accordingly to the nearest centroid
    3. Adjust centroid so they become center of gravity of given cluster [Mean on each cluster is the new centroid]
    4. Again recluster every point based on distance with adjusted centroid
    5. Reiterate until data points stop changing cluster
    6. Again adjust centroids
   
- **Best way to select K**
    - perform the above steps of different values of K
    - Calculate Sum of Squared Errors[SSE] for each k[SUM( Dist( each point - centroid)^2]
    - Plot the the SSE vs K on a plot and the elbow of the plot is the perfect value for K [Elbow Plot]
