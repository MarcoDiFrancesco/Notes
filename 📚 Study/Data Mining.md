# Data Mining

Credits: 5
Notes: Yes
Status: Studying
Year: 4

[MyCourses](https://mycourses.aalto.fi/course/view.php?id=37034)

[Zulip](https://mdm-fall-2022.zulip.aalto.fi/login/)

- Archive unitn course
    
    [DOL](https://didatticaonline.unitn.it/dol/course/view.php?id=32420)
    
    [YouTube](https://www.youtube.com/playlist?list=PLSwol1tRBDbhZDB53uf1gcPokUxpaJLXN)
    
    ## Lectures
    
    - [L-01](https://didatticaonline.unitn.it/dol/pluginfile.php/1520654/mod_resource/content/1/01.%20Data%20Mining.pdf) What is DM, meaningfulness, tf-idf
    - [L-02](https://didatticaonline.unitn.it/dol/pluginfile.php/1526231/mod_resource/content/1/02%20Data%20Integration.pdf) Data integrations systems, Information integration
    - [L-03](https://didatticaonline.unitn.it/dol/pluginfile.php/1526232/mod_resource/content/1/03.%20EntityResolution.pdf) Data cleaning for data integration, entity resolution, entity linkage
    - [L-04](https://didatticaonline.unitn.it/dol/pluginfile.php/1529977/mod_resource/content/1/03.%20Matching.pdf) Finding similar sets, min-hashing
    - [L-05](https://didatticaonline.unitn.it/dol/pluginfile.php/1533571/mod_resource/content/2/04.%20Frequent%20Itemsets%20B.pdf) Frequent itemset finding
    - [L-05](https://didatticaonline.unitn.it/dol/pluginfile.php/1537144/mod_resource/content/1/Clustering.pdf) Clustering
        - [ ]  Missing lecture [video](https://didatticaonline.unitn.it/dol/mod/kalvidres/view.php?id=1007643) - clusters FROM 36:19
    - [L-06](https://didatticaonline.unitn.it/dol/pluginfile.php/1539883/mod_resource/content/1/06.%20Recommendation%20Systems%20I.pdf) Recommendation systems
    - [L-07](https://didatticaonline.unitn.it/dol/pluginfile.php/1542408/mod_resource/content/1/13.%20Map%20Reduce%20Ullman.pdf) Map Reduce and Parallel Algorithms
    - [L-08](https://didatticaonline.unitn.it/dol/pluginfile.php/1547235/mod_resource/content/1/Latent%20Factor%20Recommender%20Systema.pdf) Recommendation systems
    - [ ]  [L-09](https://didatticaonline.unitn.it/dol/pluginfile.php/1547234/mod_resource/content/1/07.%20Dimensionality%20Reduction.pdf) Dimensionality reduction

Assignments [link](https://mycourses.aalto.fi/course/view.php?id=37034&section=2): done as group 3-5 students. 

Grading:

- 15% (5 points): presentations during lecture
- 30% (10 points): graded homeworks (last task) made in groups
- 55% (20 points): final exam

## Future check-out

- Statistical significance testing: guarantees that a similar pattern holds in future in other similar data/samples from the same source
- Scaling, discretization, dimension reduction

## Schedule

- Lecture 1 ~3h: data types
    - Prerequisite test ~2h
- Lecture 2 ~2h: PCA, similarity, distances
    - Exercises 1 ~3h
    - [ ]  Homework 1 ~5h (2 on wed)
    
    [[exercise1.pdf]]
    
- Lecture 3 ~1h: Clustering
- [ ]  Lecture 4 ~2h
    - Exercises 2
    - Homework 2
- [ ]  Lecture 5 ~3h

## Notes

**Data mining** has the aim of discovering patterns and models that are valid (hold on new data), useful, unexpected (non-obvious), understandable (interpretable).

Machine Learning (find the best model) vs Data Mining (find the best patterns)

- **Model** (ML) fits entire data, e.g. passing the course (course success) is predicted from exercise points, time spent on course and participation in exercise groups
- **Patterns** (DM) fit some part of data, e.g. if students achieve high points in assignment 2 they tend to achieve high points also in the project work

## Data types

Data types:

- **Structured**: datapoints with features, e.g. multidimentional, graph-formed, time series
- **Semistructured**: contains tags that identify and separate data e.g. xml, docs, emails
- **Unstructured**: no pre-defined format e.g. text, audio, video

**Dependency-orientated** data allows to have relations explit relations e.g. in graphs, or implicit e.g. consecutive temperature readings likely similar

Data types:

- **Nominal** (aka categorical, qulitative) is data that cannot be ordered like colors
- **Ordinal** is data that can be ordered but the gap between the steps might not be equal, e.g. satisfaction might have a different gap between satisfied/unsatisied and unsatified/really unsatisfied
- **Interval-ratio** (aka quantitative, parametric) is data that can be mesured in an equal scale like weight, age
    - **Discrete** when there can be only hole numbers like age
    - **Continuous** when there are continuous numbers
- **Circular variables** data where we cannot calculate mean, e.g. angles, days of the week

**Spatiotemporal data** has contextual attributes (e.g. spatial and temporal) that define the conext where behavioural attributes (e.g. termperatue) are measured

## Data cleaning

Strategies:

- check inconsistencies between data sources, e.g. name spelling
- using domain knowledge checking ranges of values (e.g. cannote be 800 yrs old) and known relationship (e.g. country=’USA’, city,’Sanghai’)
- checking outliers
- data trasformation: see section

Missing values in a dataset can be solved by

- pruning the feature
- pruning the record
- **imputing**
    - mean or meadian of the feature
    - predict missing value using other features, e.g. random forest imputation

## Data transformation

Scaling is used because features with large magnitures often dominate

**Min-max scaling** to get range [0, 1]

![Untitled](Data%20Mining/Untitled.png)

**Mean normalization** to get range [-1, 1] and mean=0

![Untitled](Data%20Mining/Untitled%201.png)

**Standardization** (aka z-score normalization) to get mean=0, stdev=1

![Untitled](Data%20Mining/Untitled%202.png)

![Untitled](Data%20Mining/Untitled%203.png)

**Log transoformation** can help make distribution less skewed or even normal

![Untitled](Data%20Mining/Untitled%204.png)

![Untitled](Data%20Mining/Untitled%205.png)

**Discretization**: makes data numerical to categorical, e.g. numerical to bins

- Equi-width: discretization makes equally wide bins
- Equi-depth: each bin has an equal number of records

![Untitled](Data%20Mining/Untitled%206.png)

**One-hot encoding** uses the binariztion to specify the categories with 1s and 0s

![Untitled](Data%20Mining/Untitled%207.png)

**Discretization** methods can be used to handle mixed data, or removing noise for indivisual variation

- **equi-width**: equally wide bins
- **equi-depth**: each bin has an equal number of records

![Untitled](Data%20Mining/Untitled%208.png)

**Similarity graph** can be created from any type of data where we can define the distance/similarity in directed graphs.

**Data reduction** approaches

- **Sampling**: select a subset of records, for static data or data streams
- **Feature selection**: subset of features
    - Filtering: manual filter
    - **Wrapper methods**: using models (like clustering) to evaluate goodness of feature set by getting the best set over the 2^k − 1 combinations
    - Hybrid: choose candidate sets by filtering and evaluate them with models
    - Embedded: analyze classifier to exclude unimportant features
- **Dimensionality reduction**
    - Axis rotation: rotate axes such that correlations disappear, e.g. PCA, *SVD (for numerical), LSA (for text)*
    - *Type tranformation: transform complex data type to less complex ones, e.g.  time series → multidimensional (discrete Fourier and wavelet transformations), weighted graph → multidimensional (multidimensional scaling and spectral methods)*

## SVD - PCA

Fitting data starts from looking at the median of the data and shifting it to the origin, we then project a line through the origin

![Untitled](Data%20Mining/Untitled%209.png)

We then fit the data changing the slope of the line, we are looking at maximizing the distance of each projected point from the origin.

**Principal Component** (aka, eigenvector, singular vector) is the redline, there is one PC for each feature. For each PC the objective is to maximize the variance between the data points, we are fitting all PCs except for the last, because it’s just the intersection of the first ones, e.g. in 3 dimensions we are fitting only 2 PCs.

**Eigenvalue** the sum of the square distances of the green crosses from the center

**Singular value** (SS) the square root of the eigenvalue

**Variation** is singular value over the sum of all PC singular values, e.g.
PC1 (red) = SS 25
PC2 (blue) = SS 5
PC1 = Variation 80%

![Untitled](Data%20Mining/Untitled%2010.png)

We then take the line from the center and normalize it to 1, in this case dividing all the weights by 4.12

![Untitled](Data%20Mining/Untitled%2011.png)

**Singular value decomposition** (SVD) is obtained by rotating the PC1 and PC2 into x and y axis.

**Principal component analysis** (PCA) is simply SVD where we make dimensionality reduction by dropping the dimension with the least variance.

**Kernel PCA** (KPCA) is PCA with the kernel trick so obtaining a non linear transformation in the original space.

![Untitled](Data%20Mining/Untitled%2012.png)

## Similarity and Distance measures

**Distance** is a [0, +∞] value

**Similarity** (s) if distance is [0, 1] then: Similarity = 1 - Distance, otherwise it’s normalized to the maximal distance (D)

![Untitled](Data%20Mining/Untitled%2013.png)

**Metric space** is a space where we define the notion of distance, so that we can map values like strings

![Untitled](Data%20Mining/Untitled%2014.png)

Triangle inequality speed-up:

- Naive solution: compute for each point the distance (d) with all the centroid
- **Pruning trick**: for each centroid (c1) we compute the distance with every other centroid (c2), if the distance between a datapoint (x) and centroid (c1) is smaller than 2 times, then it means this is the closest centroid thanks to the triangle inequality

![Untitled](Data%20Mining/Untitled%2015.png)

**Lp-norm** (aka Minkowski distance) is the most common measure of distance, e.g. p=2 is the euclidean distance, p=1 Manhattan distance, p=**∞** Chebyshev distance.

![Untitled](Data%20Mining/Untitled%2016.png)

Problem with Lp-norm is that it does not work well in high dimensions because may consider a lot of irrelevant features, e.g. it may consider male 0 and female 1 but sex may be an irrelevant feature

**Match-based similarity**, *given a min and max of the bin width we try to undestand what are the bins that are the most important when comparing them. For instance finding a patient that has one illness and at the same time has another problem. ([link](https://mycourses.aalto.fi/pluginfile.php/1772624/course/section/211531/lecture02.pdf?time=1662478295895) slide 43)*

**Cosine similarity** is used rappresenting the points in an n-dimentional space using vecors from the orgin, then we look at the angle of it and we calculate the cosine. This value can go from 1 with same direction, to -1 in opposite directions.

![Untitled](Data%20Mining/Untitled%2017.png)

![Untitled](Data%20Mining/Untitled%2018.png)

**Mahalanobis distance** is used when we have a cluster and we want to weight the distance from the origin of 2 points not only using euclidean distance, but also looking at the distribution of data

![Untitled](Data%20Mining/Untitled%2019.png)

**Overlap similarity** tipically uses w=1/k, k is the number of features

![Untitled](Data%20Mining/Untitled%2020.png)

![Untitled](Data%20Mining/Untitled%2021.png)

**Goodall similarity** is used in categorical data and ****can include the values giving more importance to the most rare features (goodall measure).

![Untitled](Data%20Mining/Untitled%2022.png)

Mixed data can be merged giving a trade-off value λ, standard deviation σ

![Untitled](Data%20Mining/Untitled%2023.png)

**Hamming distance** is overlap similarity for binary data, the problem is that does not consider the size of the records

![Untitled](Data%20Mining/Untitled%2024.png)

**Jaccard coefficient** is hamming distance considering the number of 1s in both rows

![Untitled](Data%20Mining/Untitled%2025.png)

**Lebernshtein distance** allows insert, delete and subsitute one character in a string and measures is the smallest number of operations to get the strings matching
e.g. kitten → sitten → sittin → sitting

**Term frequency-inverse document frequency** (tf-idf) describes the frequency of a word in a text proportianally to how many documents contain it, the more documents it's contained in, the least counts.

## Clustering

**Hard clustering**: each point belongs to one cluster

**Soft clustering**: a point belongs to multiple clusters with different probabilites or weights

Clustering features:

- shape: is the shape of clusters fixed? e.g. hyperspherical
- size: balanced clusters or clusters of differnet size?
- density: do we allow variable density points?
- overlapping or well-separated?
- outliers: allowed?

TOREMOVE Data (D), Clusters (C), Cluster number (K)

**Within-cluster variation** (wc) should be minimized

**Between-cluster variation** (bc) shoud be maximized

![Untitled](Data%20Mining/Untitled%2026.png)

**Sum of Squares estimates of Error** (SSE) minimizes within-cluster variance and maximizes between-cluster variance

![Untitled](Data%20Mining/Untitled%2027.png)

**Pairwise distance** is the bistance beween a point and every other point. Randomly chosen points will have a normal distribution.

![Untitled](Data%20Mining/Untitled%2028.png)

![Untitled](Data%20Mining/Untitled%2029.png)

![Untitled](Data%20Mining/Untitled%2030.png)

**Entropy** measures how random is data, if entropy is high means it’s random while if low it’s clustered, *high dimensionality makes it difficult to calculate entropy*. It is computed taking a number of bins.

Features selection using entrpy can be done from:

- Forward selection: by adding the best feature each round
- Backward selection: drop the worst feature TO UNDESTAND

**Holpkins statistic** is used to undestand if data is generally clustered. It works by comparing nearest neighbour distance between original data (blue points) and random data points (red points). We do it by calculating both of them, summing them up. H≅1 then it’s highly clustered, H ≅ 0,5 data is random, H≅0 data is uniformly distributed.

![Untitled](Data%20Mining/Untitled%2031.png)

![Untitled](Data%20Mining/Untitled%2032.png)

## K-means

**K-means** selects k random points, we assign a cluster of a certain size, we look at the centroid (center of all the points) of the points that are inside the cluster and we recenter the cluster.

When K-means converges we look at the avarage distance between the points to judge how good it did. Understanding the number of cluster is trial and error.

K-means may not converge

Cons is that it may converge to local optimum and not necessarily global

If we have a lot of points we can just take 1.000 random points and then we cluster them and when comparing the other 1.000.000 points we look at the distance from the centroids.

Bradley-Fayyad-Reina (BFR) algorithm is an improvment of K-means making the assumpion data have a certain distribution. This is used to summarize the data........

**Elbow mothod** chooses number of clusters by eye, can implement different methods but they are always by eye

![Untitled](Data%20Mining/Untitled%2033.png)

**Sihlouette** tells how well an individual data point is clustered, we make an average and we look at the peak

a=mean distance of x to points in the same cluster
b=mean distance of x to points in the closest neighbouring cluster

Value [-1, 1] higher is better

![Untitled](Data%20Mining/Untitled%2034.png)

![Untitled](Data%20Mining/Untitled%2035.png)

***Calinski-Harabasz** uses inter-cluster and intra-cluster variance*

![Untitled](Data%20Mining/Untitled%2036.png)

![Untitled](Data%20Mining/Untitled%2037.png)

***Gap statistic** is used* 

![Untitled](Data%20Mining/Untitled%2038.png)

**K-medians** uses instead of the $L_1$ instead of $L_2$ measures

K-me…

**K-modes** …

## Clustering - UniTrento - TOMERGE

Clutering considers only points that are close to each other and does not consider outliers. Sometimes outliers are more important than clusters, for instance a cluster of people that died and an outlier that didn't is going to be interesting.

**Hierarchical clustering** is used to merge data. When we cluster data together we look at the centroid, take the points and centroids and points and watch how is closer, then we recalcuate the centroid looking at all the points.

![Untitled](Data%20Mining/Untitled%2039.png)

Cluteroid is an alternative to the centroid where we don't look at the average of all the points but we get the point closest to all the other points.

![Untitled](Data%20Mining/Untitled%2040.png)

When we are trying to merge 2 cluster we can do it in differnt ways

- **diameter** setting the maximum distance between points in the cluster
- **average distance** beween points in the cluster

When reaching one of these 2 I stop.

All of this with some optimization has cost n^2*log(n)

## New lecture

**Internal validity** indicies assume clustering reward methods with the same objective

- Silhlouette index
- Calinski-Harabasz
- Davies-Bouldin

$$
S_{D B}={\frac{1}{K}}\sum_{i=1}^{K}\operatorname*{max}_{j\neq i}{\frac{S_{i}+S_{j}}{D_{i j}}}
$$

$$
{\bf S}_{i}=\left({\frac{1}{\vert C_{i}\vert}}\,\sum_{{\bf X}\in C_{i}}\,L_{p}^{q}({\bf X},{\bf c}_{i})\right)^{\frac{1}{q}}
$$

**External validation**

**Clustering vs classification confusion matrix** can be computed

![Untitled](Data%20Mining/Untitled%2041.png)

Purity measures how 2 clusters have the same values in common

$$
P u r(C)={\frac{1}{n}}\sum_{i=1}^{K}\operatorname*{max}_{j}\left|C_{i}\cap D_{j}\right|
$$

**Statistical hypothesis testing** decide null hypothesis H_0 to test, decide a test statistic T, what is the probability to obtain at least as good as H_0

![Untitled](Data%20Mining/Untitled%2042.png)

### New lecture p2 (Mining association patterns)

**Mining association patterns** are used to detect common patterns in data

**Statistical independence** can be computed by 

$$
P\left(\bigwedge_{A_{i}\in\mathbf{X}}A_{i}{=}a_{i}\right)=\prod_{A_{i}\in\mathbf{X}}P(A_{i}{=}a_{i})
$$

## Notes - UniTrento

Tasks of data mining use:

- **descriptive** methods: find human interpretable patterns like clustering
- **predictive** methods: use variable to predict future values

**Meaningfulness** of analytic answers is that we may discover patterns that are meaningless. In statistics it's called **Bofferroni's principle** when we try to find a pattern in data when we have little occurrencies and instead of finding a good correlation we just statistical artifacts got by randomness or just a huge number of cases that are not useful if we are looking at few.

**Feature extraction** finds the strongest statistical dependencies among the objects.

**Matthew Effect**

![Untitled](Data%20Mining/Untitled%2043.png)

## Data architecture

**Warehouse** is a central collection of multiple **data sources** imported using **data cleaning**, for example importing data may require to transform dollars in euros and this is done through a **wrapper**.

**Warehouse architecture** updates data on a time fixed schedule like every night or every weeked and has the problem that data are not always updated. Another example is Microsoft buys Skype and want to merge the service with another platform.

**Virtual integration architecture** answers a query leaving data of the different data sources, braking down the query into sub-queries for the sources using a **mediator** that find the best way to gather information.

In VIA we have a **local schema** for each data source and we use **schema mappings** to create a **global schema** and query this one.

**Peer-Based integration** does not used a central warehouse and queries are made peer-to-peer. 

![Untitled](Data%20Mining/Untitled%2044.png)

Problem of data integration is that udpates are difficult to make.

The communication between the mediator and the source has a **language for schema mapping**. This can be done in 2 ways:

![Untitled](Data%20Mining/Untitled%2045.png)

- **Global-as-View** (GAV): make views from the global schema and in case a table does not have a specific field set to null

![Untitled](Data%20Mining/Untitled%2046.png)

- **Local-as-View** (LAV): we define views that are a query understandable by the local schema

![Untitled](Data%20Mining/Untitled%2047.png)

GAV has the disadvantage of loosing information in case you are joining table and one of the 2 tables contains more data than the other, for example one table contains data from 1970 and one from 1960, but has the advantage of very easy conceptually.

LAV has the advantage that if source disappear we can just remove the view, with GAV we need to change all the views (remove null values).

## Schema mapping system

**Mapping** is an expression that describes how data gets translated from global to local schema.

Schema mapping can be done either manually looking at the similarities between the schema or through a schema mapping tool. **Schema matching** is when we locate similar characteristics, but they do not describe all the details of the transofrmation because they may not translate 1 to 1.

![Untitled](Data%20Mining/Untitled%2048.png)

**Entity** is a propery like id, name, age.

**Entity resolution** (aka entity linkage and data cleaning) is made when analyzing 2 dataset and link together the same element. This can be due to mispellings, way people write (street Roma vs str. Roma), abbreviation etc. . Another problem is that data evolve during time, like a person that changes name.

ER is going to merge data when the 2 entities are similar enough.

We can define similarity in different ways:

**Levenshtein distance** looks at how many characters are in common, for example "DESI" and "DEIS" has a similarity of 0.5.

**Jaro similarity** looks at misplaced characters, C the common character and T the number of character to switch:

![Untitled](Data%20Mining/Untitled%2049.png)

**Jaro-Winkler similarity** gives more importance to first characters compared to the last ones.

**Probabilistic databases** return the probability of 2 datapoints being the same value depeding on how much we trust the point. 

![Untitled](Data%20Mining/Untitled%2050.png)

## Finding similar sets

Strings can be compared with **Jaccard similarity** where we look at the lenght of the intersection over the union of the set. It has a value from 0 to 1 with 1 being the exact match. Comparing AC and ABCC we have 2/3, we don't consider duplicates.

![Untitled](Data%20Mining/Untitled%2051.png)

**Real applications** can be plagarism or clustering documents with Jaccard similarity above a threshold and for Netflix recommendation system.

This can be used not only to compare the letters but also words in a phrase where the set contains all the possible words. These are called **tokens**.

We can rappresent the data we have in a document with the list all the possible words in the dictiorary and assign 0 if the word is not present 1 if it is. The problem with this is that we are assigning to each document a huge vector containing all the possible words.

**Nextflix similarity** can be computed looking at the matrix that has in the x axis all the movies, y axis the users. We compare 2 vectors in the x axis (still using the Jaccard similarity) to get the similarity of what users like, or we can compare in the y axis to look at the movies and cluster them by genere.

**Shingling** convert documents to sets. **Shingles** are a contiguous subsequence of tokens. Instead of having words or sentences as tokens we can take triplets to keep the relation between the words like "united states" or "corona virus". The problem with this is that we are increasing the set.

- Possible solution to compress signatures
    
    **Min-hashing** converts large sets to short signatures preserving similartiy. It solves the problem of assigning to each document a huge number of bits assigned to each token. This can be implemented using an hash function that assignes the same hashed value to multiple shingles, setting 1 and 0s when a shingles appear or not. For instance this allows to rappresent 1 000 000 shingles in 1000 bits.
    

**MinHashing** randomize the order in which they are picked, then we look at the first non-0 bit and we rappresent the string with this value called **signature**. We take multiple random permutations that generate multiple signatures for each document. Min-hashing has the property of having the same probability of the Jaccard similarity value.

![Untitled](Data%20Mining/Untitled%2052.png)

Problem of this implementation of MinHash is that it stores all the permutation vector in memory, so 1000 permutations over 1 000 000 items are generating 1 bilion values.

We can solve this problem using instead the number of the row and apply it to a **function** that will generate the signature. In this example we use 2 functions, we compute the value of the function using the row number and we replace the values in the table only if there is 1 in the shingle, if there are other numbers we replace it only if smaller.

![Untitled](Data%20Mining/Untitled%2053.png)

![Untitled](Data%20Mining/Untitled%2054.png)

**Locality-Sensitive Hasing** (LSH) is used when comparing really similar documents that for instance differ of one word, then we compare the documents that ended up in the same bucket. Because it's difficult to get similar documents hashing we just use different hash functions to get different hash tables. This allows us to have way less **candidate pairs** to compute the difference.

This hash functions could be for instance the division of the signature in 5 different blocks, and then comparing each block and looking at possible candidate pairs.

![Untitled](Data%20Mining/Untitled%2055.png)

- [ ]  Index prefixes???

## Frequest itemset mining

A good example is the beer and diaper purchase, where customers in a supermarket buy both of them because people can't go to the bad due to children and they buy beers for home. Another example is Amazon that offers another purchase together with the one you are making.

**Market-Basket Model** has backet with 1 or more items (but always a really small number of items) and raccomendation of 1 item. This can be realated with min-hashing on the dodument (basket) and the words (items). This is a 2-layer graph with baskets being nodes and items neighborns.

![Untitled](Data%20Mining/Untitled%2056.png)

**Support** for an itemset (subset) is the number of basket where there is this itemset.

**Support threshold** is a fixed value (valid for all the supports) where we consider an item to appear frequently.

**Confidence** is the value where we try to group together the items appear more frquently. This value is smaller than 1, if we have a high value it's likely they should be in the same backet, if is a low value than the items are not related.

![Untitled](Data%20Mining/Untitled%2057.png)

The problem of confidence is that an item may appear as realated just because it's always present. Like everyone buys milk, then it's not interesting. **Interest** is the value where we remove the probaility (frequency) of that item to appear.

![Untitled](Data%20Mining/Untitled%2058.png)

For example we see there is an high confidence but because that items appear 5 out of 8 times.

![Untitled](Data%20Mining/Untitled%2059.png)

We can generate rules where we look at all the possibilities (???)

![Untitled](Data%20Mining/Untitled%2060.png)

**Maximal frequent itemset** we give more importance to the sets have a low intereset when we add a new item to the set. If ABC has high value and ABC + each other item has low intereset, then ABC is a good itemset.

**Closed itemset** we don't consider the subsets, because if ABC appear 100 times and AB 100 times, we don't get any information from the last association.

![Untitled](Data%20Mining/Untitled%2061.png)

There are 2 ways of keeping all the possibiilities, or we can keep only the one that really occur. An int is 4 bytes, so if we keep the matrix we just keep 4 bytes of the number of occurences, if we keep only the occurences we need to keep the positions i, j and the value, so 12 bytes.

![Untitled](Data%20Mining/Untitled%2062.png)

## A-Priori Algorightm

If ham is not frequent than for every combination with ham inside will not be frequent.

If we have have all the tuples over a b c d, like ab, ac, ad, bc, bd etc. and we see that b is not frequent with a first scan then we can remove ab, bc and bd.

If we are using a triangular matrix then we can remove the line and row that contain it keeping the number of the old item.

![Untitled](Data%20Mining/Untitled%2063.png)

We can do this iteratively always increasing the size of the sets always considering only the occurencies that appear more often.

![Untitled](Data%20Mining/Untitled%2064.png)

If we go too further we get less and less correlation, if we make too little than we may miss correlations.

**PCY algorithm** is an improvement that uses the space left in memory. We can use an hash function to filter even more, so instead of having each combination we can have buckets that may have the value of multiple combinations and we can not take them if they don't go over a threshold like we do in the other filter of the algorithm. In the picture the hash table contains all the combinations, the bitmap just which one we are thinking are useful.

![Untitled](Data%20Mining/Untitled%2065.png)

**Approximation algorithm** can be used when we don't have enough memory to keep all data in memory, so for instance we take 1/10 of the dataset in memory and we set the threshold to 1/10 (to accept a value) and what we get is most of the times about the same values.

For instance the dataset of 1 000 000 receipt is split in 100 000, if ham if frequent in all this 10 divisions then it's really frequent.

What we can do it doing this division randomly multiple times to confirm that the results are correct.

*SON Algorithm COMING SOON*

## Recommendation systems

A buyer has a **profile** that means.

Recommendation systems differentiate from query answering because allows not only to answer the query but also to return items we think are more important.

**Long tail** is when we have sell not only the most famous product like a physical shop would do, but we just sell them because costs us almost nothing.

A way to recommend is by **simple aggregates** by advising the most popular product, the problem is that it's not personalized to the specific user.

Formal **model** is composed by a set of customers (X) and set of Items (S), set of rating (R) that is an ordered set and the **utility function** is X x S -> R.

**Utility matrix** is putting together movies and users and it's rating. The problem is that it's sparse.

Rating can be gathered asking explicitly the user or guessing it from watchtime or how many times you bought a product. This process is called **exptrapolation**.

![Untitled](Data%20Mining/Untitled%2066.png)

A problem with extrapolation is the **cold start** when we don't have information about the user, a product or a movie.

**Serendipity** is when we suggest something the user is not directly interested but we guess may be interested to something new.

## Content-based recommendation system

A profile a a user is a set of features, for example a movie may the list of all the actors and we can get a matrix containing T and F if the actor partecipated or not. This means that we can have 2/5 for Actor1 and 3/5 for Actor2 or even weight them by the ranking we gave to the movie. The problem is that the average of the user may be always high or low so we need to subtract the aveage of the ranking the user gives, this is called **normalization**.

MOVED Cosine similarity

## Map reduce and Parallel algorithms

MapReduce is a lightweight framework, providing:

- Automatic parallelization and distribution
- Fault-tolerance
- I/O scheduling
- Status and monitoring

**Scalability** means to have an algorithm scale up the quantity of calculated data, computing the complexity with big O.

Parallelism can be used in data analysis to speed up execution, but it's implementable only if the data are separables.

**Map-reduce style** is a way to program just the map and reduce functions used for generating big data sets with a parallel, distributed algorithm on a cluster.

The process is:

- we split data: destribute documents over k computers
- **map** function: return set of (word, freq)
- red part: big distributed list of all the type of sets
- split by type of sets: like red, blue, green
- **redece** function: we count them

For instance we want to count words in a file, we use a map function to get the key value pairs, then we count them with a reduce function and then make an histogram

![Untitled](Data%20Mining/Untitled%2067.png)

RDBMS:

- Declarative query languages
- Schemas
- Logical Data Independence
- Indexing
- Algebraic Optimization
- Caching/Materialized Views
- ACID/Transactions

MapReduce:

- High Scalability
- Fault-tolerance
- “One-person deployment”

## Data processing

In 2000 batch data

In 2004 MapReduce

In 2010 streaming data (social media)

In 2014 **Apache Spark** used for batch data

In 2011 **Apache Flink** used for streaming data

In 2006 **Apache Hadoop** uses HBase is a database using HDFS filesystem suitable for very large file and streaming file.

Hadoop allows **block abstraction**, so to put a single file in different machines. This is managed by the datanote machines, so we send data just to one machine and it will be responsible to send to other machines in case there is no space in that one.

The **limitation** of Hadoop is that it is not good at rewritng after processing a batch of data like we do in ML because does not keep data in memory, this was fixed by Spark.

Spark uses **Resilient Distributed Dataset** (RDD)

Spark allows to process way more data sources, like sql and ml libraries. It is fault tollerant so if one machine goes down it does not stop all.

Spark has lazy evaluation, that means a certain action get trigger just when we are using it.

Spark uses DataFrames and Datasets in a distributed way.

DataFrame is not typed, Datasets are. When we interface from Python to Spark we have a catalyst that changes the DataFrame or SQL to Spark.

## Collaborative filtering

Collaborative filtering is about advicing a certain item because there are other people that liked it and a user is similar to him.

Given a matrix of users and movies where each point is the rating, we can look at how similar are 2 people but using Jaccard similairy implies ignoring ratings. 

*MATRIX slide Option 1: Jaccard Similarity*

We can compute instead the aveage of the movie

*MATRIX centered cosine similarity*

So we can multiply the rating with the similarity over the sum of the similarities. This is called **user to user collaborative filtering**.

*FORMULA with the similarity. Slide Rating predictions* 

**Item to item collaborative filter** uses the similarity to the movie instead of the user. It works better because... .

A possible implementation of it is to use clustering, we collect a set of factors (features) that define the movies (fantasy, it's long, director) and we connect user → facor → move. This is different from user profiling because we don't consider predefined features.

**Rank aggregation** is the problem of combining ranked list to produce a single ranking.

## Vector similarity

SUBGEADING TOMERGE/MOVE

Relational database used keyword-based search assigning to tags to a specific content (e.g. movie, music, actor)

![[/Matching_Engine_blog_visuals_1.max-2000x2000.png]]

Vector search uses instead an array with the length of the features with values from 0 to 1 and compute the cosine similarity in milliseconds.

![[/Matching_Engine_blog_visuals_3.max-2000x2000.png]]

## Advertising on the Web

Online algorithms is about data stream model.

**Bipartite matching** matches one left node with one right node, and the perfect match is when one left node if matched with one right node. A maximum matching is the perfect matching where we match the biggest number of nodes. 

![Untitled](Data%20Mining/Untitled%2068.png)

In an online matching algorithm we don't have the whole data but we are given a node at a time.

Matching can be done with a **greedy** algorithm just taking the first match, 

*Competitive* ratio is the minimum of: (all the possible nodes)/(greedy matching/best batching)

So compared with the perfect matching at worse we can match 1/2 of the nodes.

Web advertisement differntiate from paper one from how many person people saw it, and the demography the sees it.

It 2002 there was the invention of bidding, where we pay only we the customer clicked. The bidding comes in when Google needs to show the ads, this is called the adwords problem.

Adwords problem is the one that given: click-though rate in percentage, budget and number of ads displayed to each search query (simplifing we will take 1). Here we need to find the best matching *with a connection being an ad shown to a person*, we need to compute it as bid*CTR.

**Deterministic** random selection makes random choices but considering a seed.

**Balance algorithm** chooses the bidder with the biggest unspent budget and the worse case is 3/4.