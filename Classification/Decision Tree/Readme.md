### 🌳 Decision Tree

![Untitled](Algorithms%200b0fbf0dc49d47469ecd398540facaf3/Untitled.png)

- Goal is to achive purest form of distribution of lable for each each node
- this algorithm is also known as the **greedy algorithm**, as we have an excessive desire of lowering the cost
- **Imp Resources**
    
    [Decision Tree Algorithm - A Complete Guide - Analytics Vidhya](https://www.analyticsvidhya.com/blog/2021/08/decision-tree-algorithm/)
    
    [Understanding the Gini Index and Information Gain in Decision Trees](https://medium.com/analytics-steps/understanding-the-gini-index-and-information-gain-in-decision-trees-ab4720518ba8)
    
    [Decision-Trees/Decision_trees_implementation.ipynb at main · AnshulSaini17/Decision-Trees](https://github.com/AnshulSaini17/Decision-Trees/blob/main/Decision_trees_implementation.ipynb)
    
- **Root Nodes**
    
    It is the node present at the beginning of a decision tree from this node the population starts dividing according to various features.
    
- **Decision Nodes**
    
    The nodes we get after splitting the root nodes are called Decision Node
    
- **Leaf Nodes**
    
    The nodes where further splitting is not possible are called leaf nodes or terminal nodes
    
- **Sub-tree**
    
    Just like a small portion of a graph is called sub-graph similarly a sub-section of this decision tree is called sub-tree.
    
- **Pruning**
    
    It is nothing but cutting down some nodes to stop overfitting.
    
- **`Entropy**`
    - Entropy is nothing but the **`uncertainty in our dataset or measure of disorder`**. Let me try to explain this with the help of an example.
    - `**Entropy basically measures the impurity of a node.`** Impurity is the degree of randomness; it tells how random our data is
        
        ![Here p+ is the probability of positive class;                           S is the subset of the training example;                                 p– is the probability of negative class](Algorithms%200b0fbf0dc49d47469ecd398540facaf3/Untitled%201.png)
        
        Here p+ is the probability of positive class;                           S is the subset of the training example;                                 p– is the probability of negative class
        
    - **`In order to make a decision tree, we need to calculate the impurity of each split, and when the purity is 100%, we make it as a leaf node.`**
    - `**Always remember that the higher the Entropy, the lower will be the purity and the higher will be the impurity.**`
        
        ![x-axis presents data points and the y-axis shows the value of entropy     **Entropy is the lowest (no disorder) at extremes (both end) and maximum (high disorder) in the middle of the graph.**](Algorithms%200b0fbf0dc49d47469ecd398540facaf3/Untitled%202.png)
        
        x-axis presents data points and the y-axis shows the value of entropy     **Entropy is the lowest (no disorder) at extremes (both end) and maximum (high disorder) in the middle of the graph.**
        
- **`Information Gain`**
    - “Information gain”  tells us `**how much the parent entropy has decreased after splitting it with some feature.**`
    - Information gain **`measures the reduction of uncertainty`** given some feature and it is also a deciding factor for which `**attribute should be selected as a decision node or root node.**`
        
        ![ It is just entropy of the full dataset – entropy of the dataset given some feature.](Algorithms%200b0fbf0dc49d47469ecd398540facaf3/Untitled%203.png)
        
         It is just entropy of the full dataset – entropy of the dataset given some feature.
        
    - Hence we will `**select the feature which has the highest information gain**` and then **`split the node based on that feature`**.
- **`Gini Index`**
    - **`measure how often a randomly chosen element from the set would be incorrectly labeled`**
    - A Gini score gives an idea of how good a split is by how mixed the response classes are in the groups created by the split
        
        ![Untitled](Algorithms%200b0fbf0dc49d47469ecd398540facaf3/Untitled%204.png)
        
    - *Gini index varies between values 0 and 1*
        - *where 0 expresses the purity of classification, i.e. All the elements belong to a specified class or only one class exists there.*
        - *And 1 indicates the random distribution of elements across various classes.*
        - *The value of 0.5 of the Gini Index shows an equal distribution of elements over some classes.*
- **Gini Index vs Information Gain**
    
    Take a look below for the getting discrepancy between Gini Index and Information Gain,
    
    1. The Gini Index **facilitates the bigger distributions** so easy to implement whereas the Information Gain **favors lesser distributions** having small count with multiple specific values.
    2. The method of the Gini Index is **used by CART algorithms**, in contrast to it, Information Gain is **used in [ID3, C4.5 algorithms](https://medium.com/datadriveninvestor/tree-algorithms-id3-c4-5-c5-0-and-cart-413387342164)**.
    3. Gini index **operates on the categorical target variables** in terms of “success” or “failure” and **performs only binary split**, in opposite to that Information Gain **computes the difference between entropy** **before and after the split** and indicates the impurity in classes of elements.
- ****When to stop splitting?****
    - We can set the maximum depth of our decision tree using the ***max_depth*** parameter.  The training error will off-course decrease if we increase the ***max_depth*** value but when our test data comes into the picture, we will get a very bad accuracy. Hence you need a value that will not overfit as well as underfit our data and for this, you can use GridSearchCV.
    - It is denoted by ***min_samples_split.*** Here we `specify the minimum number of samples required to do a spilt`. For example, we can use a minimum of 10 samples to reach a decision. That means if a node has less than 10 samples then using this parameter, we can stop the further splitting of this node and make it a leaf node.
    - ***min_samples_leaf*** – represents the minimum number of samples required to be in the leaf node. The more you increase the number, the more is the possibility of overfitting.
    - ***max_features*** – it helps us decide what number of features to consider when looking for the best split.
- ****Pruning****
    
    It is another method that can help us avoid overfitting. It helps in improving the performance of the tree by cutting the nodes or sub-nodes which are not significant. It removes the branches which have very low importance.
    
    There are mainly 2 ways for pruning:
    
    (i) **Pre-pruning** – we can stop growing the tree earlier, which means we can prune/remove/cut a node if it has low importance **while growing** the tree.
    
    (ii) **Post-pruning** – once our **tree is built to its depth**, we can start pruning the nodes based on their significance.
    
- 🔴 `**Interview Question**`
    - Can you mention some advantages and disadvantages of decision trees?
        
        The advantages of decision trees are that they are easier to interpret, are nonparametric and hence robust to outliers, and have relatively few parameters to tune. On the other hand, the disadvantage is that they are prone to overfitting.
        