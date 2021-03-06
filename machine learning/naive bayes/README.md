# 朴素贝叶斯

### 一个定理

朴素贝叶斯分类时，对给定的输入$x$，通过学习到的模型计算后验概率分布$P(Y=c_k|X=x)$，将后验概率最大的类作为$x$的类输出，后延概率计算根据贝叶斯定理:$P(Y=c_k|X=x)=\frac{P(X=x|Y=c_k)P(Y=c_k)}{\sum_kP(X=x|Y=c_k)P(Y=c_k)}$，一般来说，$x$指的是文本，里面由很多词构成。

### 一个假设

朴素贝叶斯对条件概率分布做了条件独立性的假设，由于这是一个较强的假设，朴素贝叶斯也由此得名：$P(X=x|Y=c_k)=P(X^{(1)}=x^{(1)},…,X^{(n)}=x^{(n)}|Y=c_k)=\prod_{j=1}^nP(X^{(j)}=x^{(j)}|Y=c_k)$

有了这个假设， 我们就可以把上面贝叶斯定理中的分子换掉。

### 两个先验估计

朴素贝叶斯，学习意味着估计$P(Y=c_k)$和$P(X^{(j)}=x^{(j)}|Y=c_k)$，用极大似然估计法估计相应的概率。

$P(Y=c_k)=\frac{\sum_{i=1}^NI(y_i=c_k)}{N},k=1,2,…,K$

设第j个特征$x^{(j)}$可能取值的集合为${a_{j1},a_{j2},…,a_{jS_j}}$，则$P(X^{(j)}=a_{jl}|Y=c_k)=\frac{\sum_{i=1}^NI(x_i^{j}=a_{jl},y_i=c_k)}{\sum_{i=1}^NI(y_i=c_k)},j=1,2,…,3; l=1,2,…,S_j;k=1,2,…,K$

### 一个问题

用极大似然估计可能会出现所要估计的概率值为0的情况，这时会影响到后验概率的计算结果，用拉普拉斯平滑，分子+1，分母+$S_j$。
