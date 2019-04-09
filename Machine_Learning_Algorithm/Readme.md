# Gradient Descent
通过数据一步步寻找最佳拟合函数，即寻找RSS（Residual Sum of Squares，残差平方和）的minima，此处RSS是成本/损失函数的值，要优化的参数是成本/损失函数的自变量。
# Linear Regression
## 正则化
* 思想：让模型忽略干扰，别拟合的那么精细，关注有效数据。
* 手段：限制模型参数大小
## Ridge Regression (Linear Regression with L2 Regularizer)
* 误差平方和损失函数（经验风险）越小，模型复杂度越高，越容易过拟合。
* 正则化项是模型复杂度的单调递增函数，最小化损失函数的同时也最小化正则化项，从而降低模型复杂度，减少过拟合。
## LASSO Regression (Linear Regression with L1 Regularizer)
* LASSO和Ridge都可以限制参数大小，但是LASSO由于是L1正则，正则项并非处处可导，会使得一些参数变成0，所以可以用作特征选择。
# Logistic Regression
# Naive Bayes  
原理基于贝叶斯公式  
$P(H|X)=\frac{P(X|H)P(H)}{P(X)}$
* where $P(H|X)$ is the posteriori probability
* where $P(H)$ is the prior probability
* where $P(X|H)$ is the likelihood
* where $P(X)$ is the evidence
# Decision Tree  
## Characteristic
* 决策方式类似于：if-this-then-that
* 建模非线性关系
* 可以对分类和连续结果变量建模
* 理解和可视化容易
* 容易过拟合
## ID3树和Information Gain
1. 划分数据集D需要的信息（D的信息熵）为Expected Information  
   $Info(D)=-\sum_{i=1}^mp_i\log_2(p_i)$  
   $p_i$ is the relative frequency of class i in D
2. 计算出用属性A划分D的Information Needed  
   $Info_A(D)=\sum_{j=1}^v\frac{|D_j|}{|D|}\times Info_A(D_j)$
3. Information Gain = Expected Information - Information Needed  
   $Gain(A)=Info(D)-Info_A(D)$
* 树需要作出获得最高信息增益（即熵最低，亦即纯度最高）的决定
## CART树和Gini Index
1. 如果数据集D被分成N类，则D的总gini index为：  
   $gini(D)=1-\sum_{i=1}^{N}p_i^2$  
   $p_i$ is the relative frequency of class i in D
2. 如果D被属性A划分为$D_1$和$D_2$，则A的gini index为：  
   $gini_A(D)=\frac{|D_1|}{|D|}gini(D_1)+\frac{|D_2|}{|D|}gini(D_2)$  
3. A带来的gini变化，即Reduction in Impurity  
   $\Delta gini(A)=gini(D)-gini_A(D)$ 
* 树需要作出最小化基尼系数、或最大化$\Delta gini$的决定。
# Random Forest
## Characteristic
* 多个决策树
* 减少过拟合和方差（都是为了在新数据上更好的泛化）
# Adaptive Boost
# Support Vector Machine
# K Nearest Neighbor
