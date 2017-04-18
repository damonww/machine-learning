## Naive Bayesian Classification
1. 主要思想
假设样本X = (x1,x2,...,xn), 类别C = (c1,c2,...,cm)
样本X被分为ci类的概率是：
p(ci|X) = p(X|ci)*p(ci)/p(X)=p(x1|ci)*p(x2|ci)*...*p(xn|ci)*p(ci)/p(X)
由于p(X)对所有的类别都是一样的，所以使p(x1|ci)*p(x2|ci)*...*p(xn|ci)*p(ci)最大的类别ci即为X从属的类

这样分类问题就被转化为了条件概率的求解问题。

2. 概率求解
p(ci) = count(ci)/size(C)
p(xj|ci)：
1. 如果xj是离散的，假设所有离散值为[aj1,aj2,...,ajk]:
p(xj|ci) = p(xj=ajl,Cx=ci)/p(Cx=ci)=count(xj=ajl,Cx=ci)/count(Cx=ci)
2. 如果xj的分布是连续的，则需要对其概率分布作出假设，通常假设其分布满足高斯分布
3. 如果p(xj|ci) = 0,则需要做Laplace校准
因为如果p(xj|ci)=0，则整个条件概率就为0，会严重影响分类器的效果，而Laplace校准是当某一类中没有出现过某一属性时，就对该类别下的所有划分+1，这样既可避免概率为零的情况
