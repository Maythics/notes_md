# Real Analysis

## 抽象测度与抽象积分

略

## 正Borel测度

这一章最关键是要搞清楚全篇的目的

首先，上一章全部讨论的是抽象层面的，意在给出最general的结论，但是没有一些实例。这一章讨论的就是一个实例---Borel测度。

前面几节是拓扑前置基础，乱花渐欲迷人眼。重头戏从Riesz表示定理开始

我最初了解Riesz表示定理是在Linear Algebra Done Right中，讲述一个线性泛函与内积之间的对应关系，非常强大。现在来看，那里讲的只是一个special case，用测度去联系更加general，有更深厚的含义

### Riesz表示定理

**定理 Riesz Representation** 
定理陈述：若$X$是局部紧的Hausdorff空间，$\Lambda$是一个在$C_c(X)$上的正线性泛函。那么，存在$X$上的一个$\sigma$代数$\mathfrak{M}$，包含所有的Borel sets,且存在$\mathfrak{M}$上的一个唯一的正测度$\mu$使得：
    1. $\Lambda f = \int_X f d\mu$，对于所有$f\in C_c(X)$
    2. $\mu(K)<\infty$对于所有紧集$K$成立
    3. 对于任何$E\in \mathfrak{M}$，有 $\mu(E) = \inf\set{\mu(V): E\subset V, V \text{ is open}}$
    4. 对于所有开集$E$，以及所有的$\mu(E)<\infty$的那些$\mathfrak{M}$中元素$E$，$\mu(E) = \sup\set{\mu(K): K\subset E, K \text{ is compact}}$
    5. 若$E\in \mathfrak{M}$，$\mu(E)=0$，则一旦$A\subset E$，即可得$A\in \mathfrak{M}$

解释一下：首先，第一条是最最核心的结论。第二条则说明这种“从线性泛函诱导出来的测度”有良好的性质---使紧集测度有限。第三条度这个条件称为“外正则”(outer regular)，第四条的条件则被称为“内正则”(inner regular)，这两条是说，这样诱导出来的测度，在$\sigma$代数上必定有外正则性，而在所有$\sigma$代数中测度有限的成员上以及所有开集上，有内正则性。第五条这种性质则被称为完备性---“任何零测集的子集都可测”，该条说明，这样诱导出来的测度还是完备的。

再说的白话一点，Riesz表示定理说的就是，在……上的正线性泛函，可以唯一的被一个测度“表示”，而这个测度同时会具有2～4条所述的那些性质，所以非常好。

### Borel测度

**定义 Borel measure** 就是指定义在局部紧的Hausdorff空间的Borel sets形成的$\sigma$代数上的测度

可以看到，Riesz表示定理实际上就是告诉我们，给出一个正线性泛函后，可以找到这样的一种Borel measure，且有怎么怎么样的性质……

但是呢，Riesz表示定理还不够好，因为内正则性不是所有$\mathfrak{M}$中的成员都满足。要是所有的成员既外正则又内正则就好了！（那就叫正则的），还要加一点条件，才能达成这一点，因此有了定理2.17,这个额外的条件就是$\sigma$-compact。

还可以再看的广一点，不再拘泥于“线性泛函诱导出来的测度”，其实，如果一个局部紧Hausdorff空间上的所有开集都是$\sigma$-compact的，那么在这个空间上任何一种“使得紧集测度有限”的Borel测度都是正则的！这就是定理2.18
