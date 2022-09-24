# 🔍 Supervised methods

[MyCourses](https://mycourses.aalto.fi/course/view.php?id=37029&section=2)

#### Assignment 1 answers
1a - False → …from the same *unknown* distribution…????

**1b - True**

1c - False → ..all the *Consistent* hypotheses…

2a - False → It’s not a diagonal line, it’s straight to top and then streight left

**2b - True** → *Maybe -1 is 0 ??*

2c - False → AUC ≤ 1

3a - False

**3b - True** → Precision

3c - False

**4a - True** → Recall

4b - False

4c - False

**5b - True** → 166.13637311857883
    

Grading:

- 30% exercises
- 70% exam


## Schedule
- Lecture 1: ~2h
    - Quiz 1: ~3h
- [ ]  Lecture 2: ~2h
- [ ]  Lecture 3: ~2h
    - [ ]  Quiz 2
    - [ ]  Quiz 3
- Lecture 4: 27 Sep

## Notes

## Machine learning

**Machine Learning** is the study of algorithms that: at some task T, improve their performance P, with experience E. A well-defined learning task is given by a triplet $<T, P, E>$. Learning is about generalizing from the training data to un unseen target domain.

X is the input and Y is the output

$$
f: X\to Y
$$

F task is the space where all the possible functions lie, f is one of these functions

$$
{F}_{task}\subset{Y}^{X}
$$

$f$ is the function in $F_{task}$ that allows to get che best value $f^*$

**Objective function** computes how well the optimization worked. It's defined either by the probabilty distribution of data or by the hypotesis space H.

![[Untitled 2.png]]

$$
\math{argmin} \!w\!\ln_{w,b}\sum_{i=1}^{n}\!J o S\!(y y^{\dagger})\!+\!\lambda\,\,r e g u l a r i z e r(w,b)
$$

![[Untitled 3.png|300]]

**Indicator function** returns 0 if correct, 1 if not correct

**Overfitting** is the problem that comes when the model is able to perform really well in training data, but badly in validation data. **Underfitting** is when we find a local minima.

![[Untitled 4.png]]

**Feature** are the parameters of the input, in ML the features are handcrafted and we try to find the best values (not maximum) values for each feature.

**Model-based machine learning** works in 3 steps: pick a model (like hyperplane or decision tree), pick a criterion to optimize with an objective function (like training error), develop a learning algorithm that minimizes/maximizes the objective function.

![[screenshot_2021-04-21_09-42-02.png|300]]

![[Untitled 5.png|300]]

**Cost function** is a type of objective function, it measures the error between what value your model predicts and what the value actually is. An example can be the sum of loss functions over your training set, plus regularization.

**Surrogate Loss function** is a function with a contionuous output and only one local minima. It is used to fix the problem of the 0/1 loss, because it this loss a little change in the weights can lead to a big change in output and we could get stuck in a local minima.

**Loss function** measures the penalty on a data point compared to it's target, given a model the objective function is usually to minimize the loss. There are some well know loss function:

**Activation function** decide whether the neuron should be activated or not. Usually there is 1 activation function for all the hidden layers and a different one for the output layer.

**Optimizer** in a neural network the algorithm that calculate the values to optimize the ouput. The objective of an optimizer is to minimize the loss function.

**Leaning rate** in the optimizer is a value usually between 0.01 and 0.0001 that is used to update the value in the node. Raising the LR means that we could **overshoot** and miss the minimum of the loss function. Lower the leaning rate means learning slower. This number is just guessed.

**Bias** is how strong the model assumptions are. High-bias is for exmple linear separability, because sometimes it's not possible separate all points with it. ([link](https://stackoverflow.com/a/2499936/7924557))

**L1** loss funciton, aka Mean Absolute Error (MAE), is the absolute difference between real value and the predicted one. **L2** loss, aka Mean Squared Error (MSE), is this value squared. Practically L2 is almost always the prefered option for regression problems, but with outliers L1 performs better.

## Loss function

**Loss function** (L) measures the discrepancy between outputs y and y’

**Generalization error** (aka out-of-sample error) is the real error of the probabilty distribution

**Empirical risk** (R) approximates the generalization error of the model by computing the average of the losses of the individual instances

$$
\hat{R}(h)=\frac{1}{m}\sum_{i=1}^{m}L(h(x_{i}),y_{i})
$$

Loss function depend on the task:
- **Squared loss** for regression
- **0-1 loss** for classification, hinge loss as alternative for mathematical properies
- **Hamming loss** used in multilabel, it’s a 0-1 loss but uses XOR instead of AND, so that true negative contribute

$$
R(h)=\mathbb{E}_{(\mathbf{x},y)\sim D}\left[\,L(h(\mathbf{x}),y\,\right)\,]
$$

## Binary classification

Binary classification includes:
- **General hypothesis** (G) that cannot be expanded
- **Specific hypothesis** (S) that cannot be made smaller
- **Version space**: if classifies correctly all samples
- **Margin** (h) is the minimum distance between S and G

![[Untitled 8.png|400]]

![[Untitled 9.png|400]]

## Confusion matrix
**Confusion matrix** is a kind of contingency table used to visualize performance of a supervised learning algorithm

Metrics:
- **Precision** (aka Positive Predictive Value): flagging legit emails (FP) as spam is a problem, better to have some spam (FN) in the inbox

$$
\mathrm{PPV}={\frac{\mathrm{TP}}{\mathrm{TP}+\mathrm{FP}}}
$$
- **Recall** (aka Sensitivity): factory that needs to find all faults, so FP are not a problem; rare diseese we must find everyone, so FP are not a problem

$$
\mathrm {TPR} ={\frac {\mathrm {TP} }{\mathrm {TP} +\mathrm {FN} }}
$$

- **F1 score**
$$
\mathrm {F} _{1}={\frac {2\mathrm {TP} }{2\mathrm {TP} +\mathrm {FP} +\mathrm {FN} }}
$$

![Untitled](Untitled%2013.png)

Multiclass classification confusion matrix is a way to show how many times each action is correct, but also showing which actions were the most confused.

![[Untitled 14.png]]

## ROC Curve

ROC Curve summarizes the trade-off beween TPR and FPR. Same TPR means leftmost point is better, depending on how many FP we want we can choose the leftmost of the 3 points or of the 2 points.

![[Untitled 15.png|400]]

TPR can be replaced by Precision, so that in the rare diseese examle works better.

**Area under curve** (AUC) *is equivalent to the probability that a randomly chosen positive instance is ranked higher than a randomly chosen negative instance. A classifier with high AUC can occassionally score worse in a specific region than another classifier with lower AUC. But in practice, the AUC performs well as a general measure of predictive accuracy.*

## Learning/Genearlization

**Generalization error** (R) of an hypothesis class (h)

$$
R(h)=\mathbb{E}_{(\mathbf{x},y)\sim D}\left[\,L(h(\mathbf{x}),y\,)\,\right]
$$

**Independent and identically distributed** (i.i.d) is an assumption where we generate data with the random variables having the same probability distribution

Given:
- Concept class (C) that needs to be learned $C: X \rightarrow Y$
- Unknown probability distribution (D)

$$
R(h)=\mathbb{E}_{x\sim D}\left[L_{0/1}(h(x),C(x))\right]=\operatorname*{Pr}_{x\sim D}(h(x)\neq C(x))
$$

**Probably Approximate Correct (PAC)** is a learning framework with the goal of learning an hypothesis with a low generalization error

A class (C) is **PAC-learnable** if there exists an agorithm (A) that given a training sample has a generalization error that satisfies

generalization error (R)
hypothesis ($h_S$)
training samples (S) where $S = ((x_1, C(x_1)), ..., (x_m , C(x_m ))$ i.i.d from D
ε level of error, e.g. ε=0.1 to get 10% error
1-δ level of confidence, e.g. δ=0.05 for the algorithm to fail 5% of the times

$$
Pr(R(h_S ) ≤ \epsilon) ≥ 1 − δ
$$

**Efficient** PAC learnable is an algorithm that runs in polynomial time

epsilon and *delta meaning*:

![[Untitled 18.png]]

$A_c$ is the event where $R’$ misses at least one rectangle, Each $r_i$ has probability mass $\epsilon / 4$ and probability of missing one rectangle $1 − \epsilon/4$, so with m samples the probability of missing at least one rectangle is:

$$
P r(A_{C})\leq4(1-\epsilon/4)^{m}
$$

![Untitled](Untitled%2020.png)

The hypothesis class also in the case of an square are infinite because we could fit inside a square of any dimension.

If we are proving that VCdim is ≥ then 3, then just find one example where it’s possible to separate them, if we are proving that VCdim is = 3 then find any example is possible to separate them. What happens if it’s in one line?