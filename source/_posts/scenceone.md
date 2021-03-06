---
title: scenceone
date: 2019-10-09 18:02:21
tags:
mathjax: true
abbrlink: 56f6db1d
---

[TOC]



# 1、假设检验

**假设检验**是[推论统计](https://baike.baidu.com/item/推论统计)中用于检验统计假设的一种方法。而“统计假设”是可通过观察一组[随机变量](https://baike.baidu.com/item/随机变量)的模型进行检验的科学[假说](https://baike.baidu.com/item/假说)。<sup>[1]</sup>一旦能估计未知[参数](https://baike.baidu.com/item/参数)，就会希望根据结果对未知的真正参数值做出适当的推论。

统计上对参数的假设，就是对一个或多个参数的论述。而其中欲检验其正确性的为[零假设](https://baike.baidu.com/item/零假设)（null hypothesis），零假设通常由研究者决定，反映研究者对未知参数的看法。相对于[零假设](https://baike.baidu.com/item/零假设)的其他有关参数之论述是[备择假设](https://baike.baidu.com/item/备择假设)（alternative hypothesis），它通常反映了执行检定的研究者对参数可能数值的另一种（对立的）看法（换句话说，备择假设通常才是研究者最想知道的）。

假设检验的种类包括：[t检验](https://baike.baidu.com/item/t检验)，[Z检验](https://baike.baidu.com/item/Z检验)，[卡方检验](https://baike.baidu.com/item/卡方检验)，[F检验](https://baike.baidu.com/item/F检验)等等。

## 1.1 基本思想

​		假设检验的基本思想是小概率[反证法](https://baike.baidu.com/item/反证法)思想。小概率思想是指小概率事件（P<0.01或P<0.05）在一次试验中基本上不会发生。[反证法](https://baike.baidu.com/item/反证法) 思想是先提出假设(检验假设H<sub>0</sub>)，再用适当的统计方法确定假设成立的可能性大小，如可能性小，则认为假设不成立，若可能性大，则还不能认为假设不成立。

​		假设是否正确，要用从总体中抽出的样本进行检验，与此有关的理论和方法，构成假设检验的内容。设**A**是关于总体分布的一项命题，所有使命题**A**成立的总体分布构成一个集合*h*<sub>0</sub>，称为原假设(常简称假设)。使命题**A**不成立的所有[总体分布](https://baike.baidu.com/item/总体分布)构成另一个集合*h*1，称为备择假设。如果*h*<sub>0</sub>可以通过有限个实参数来描述，则称为参数假设，否则称为非参数假设(见[非参数统计](https://baike.baidu.com/item/非参数统计))。如果*h*<sub>0</sub>(或*h*1)只包含一个分布，则称原假设(或备择假设)为[简单假设](https://baike.baidu.com/item/简单假设)，否则为[复合假设](https://baike.baidu.com/item/复合假设)。对一个假设*h*<sub>0</sub>进行检验，就是要制定一个规则，使得有了样本以后，根据这规则可以决定是接受它（承认命题**A**正确），还是拒绝它（否认命题**A**正确）。这样，所有可能的样本所组成的空间（称[样本空间](https://baike.baidu.com/item/样本空间)）被划分为两部分HA和HR(HA的补集)，当样本*x*∈HA时，接受假设*h*<sub>0</sub>；当*x*∈HR时，拒绝*h*<sub>0</sub>。集合HR常称为检验的[拒绝域](https://baike.baidu.com/item/拒绝域)，HA称为接受域。因此选定一个检验法，也就是选定一个拒绝域，故常把检验法本身与拒绝域HR等同起来。

## 1.2 基本方法

​		[**显著性检验**](https://baike.baidu.com/item/显著性检验) 有时，根据一定的理论或经验，认为某一假设*h*<sub>0</sub>成立，例如，通常有理由认为特定的一群人的身高服从正态分布。当收集了一定数据后，可以评价实际数据与理论假设*h*<sub>0</sub>之间的偏离，如果偏离达到了“显著”的程度就拒绝*h*<sub>0</sub>，这样的检验方法称为显著性检验。偏离达到显著的程度通常是指定一个很小的正数*α*（如0.05，0.01），使当*h*<sub>0</sub>正确时，它被拒绝的概率不超过*α*，称*α*为[显著性水平](https://baike.baidu.com/item/显著性水平)。这种假设检验问题的特点是不考虑备择假设，考虑实验数据与理论之间[拟合](https://baike.baidu.com/item/拟合)的程度如何，故此时又称为[拟合优度检验](https://baike.baidu.com/item/拟合优度检验)。拟合优度检验是一类重要的显著性检验。<sup> [1]</sup> 

​		K.皮尔森在1900年提出的Ⅹ检验是一个重要的拟合优度检验。设原假设*h*<sub>0</sub>是：“总体分布等于某个已知的[分布函数](https://baike.baidu.com/item/分布函数)*F*(*x*)”。把(－∞，∞)分为若干个两两无公共点的[区间](https://baike.baidu.com/item/区间)*I*1，*I*2，…，*I*k，对任一个区间，以*v*j记大小为*n*的样本*X*1，*X*2，…，*X*n中落在*I*j内的个数，称为区间*I*j的观测[频数](https://baike.baidu.com/item/频数)，另外，求出*I*j的理论频数(对*j*=1，2，…，*k*都这样做)，再算出由下式定义的Ⅹ统计量，皮尔森证明了：若对*j*=1，2，…，*k*，则当*n*→∞时，Ⅹ的极限分布是[自由度](https://baike.baidu.com/item/自由度)为*k*-1的Ⅹ分布。于是在样本大小*n*相当大时，从Ⅹ分布表可查得Ⅹ分布的上*α*[分位数](https://baike.baidu.com/item/分位数)（见[概率分布](https://baike.baidu.com/item/概率分布)）Ⅹ(*k*-1)。由此即得检验水平为*α*的拒绝域：{Ⅹ≥Ⅹα(*k*-1)}。如果原假设*h*<sub>0</sub>为:总体服从分布族{*F*θ，*θ*∈嘷}，式中*θ*为未知参数，嘷为*θ*的所有可能取值的集合（称[参数空间](https://baike.baidu.com/item/参数空间)），也可得到类似的拒绝域，只要在计算理论[频数](https://baike.baidu.com/item/频数)*v*j时，将所包含的未知参数*θ*用适当的[点估计](https://baike.baidu.com/item/点估计)代替，即可计算 Ⅹ统计量。但此时极限分布的自由度为 *k*-Л-1，式中Л为*θ*中的独立参数的个数。[柯尔莫哥洛夫](https://baike.baidu.com/item/柯尔莫哥洛夫)检验（见[非参数统计](https://baike.baidu.com/item/非参数统计)）也是一个重要的拟合优度检验方法。

​		**奈曼-皮尔森理论** 　J.奈曼与 E.S.皮尔森合作，从1928年开始，对假设检验提出了一项系统的理论。他们认为，在检验一个假设*h*<sub>0</sub>时可能犯两类错误：

​		第一类错误是真实情况为*h*<sub>0</sub>成立(即θ∈嘷0)，但判断*h*<sub>0</sub>不成立，犯了“以真为假”的错误。第二类错误是*h*<sub>0</sub>实际不成立(即θ∈嘷1)，但判断它成立，犯了“以假为真”的错误（见表）。这里嘷0，嘷1分别是使假设*h*<sub>0</sub>成立或不成立的θ的集合，显然嘷=嘷0+嘷1。当θ∈嘷0，样本X(即X1，X2，…，Xn组成的向量)∈HR，其概率*P*θ(X∈HR)就是犯第一类错误的概率α；当θ∈嘷1，样本X∈HA，其概率就是犯第二类错误的概率β。通常人们不希望轻易拒绝*h*<sub>0</sub>，例如工厂的产品一般是合格的，出厂进行抽样检查时不希望轻易地被认为不合格，于是在限定犯第一类错误的概率不超过某个指定值α（称为检验水平）的条件下，寻求犯第二类错误的概率尽可能小的检验方法。为了描述检验的好坏，称θ的函数*P*θ(X∈HR)为检验的功效函数。例如上述产品检验的例子中，所采用的检验可以是：当样品中的废品个数超过一定限度时，认为该批产品不合格，否则就认为合格。这个检验的功效函数有图示的形状，图中的 p0、p1、α、β根据需要选定。这种图形清楚地描述了犯两类错误的概率。

​		**优良性准则** 　基于奈曼－皮尔森理论及[统计决策理论](https://baike.baidu.com/item/统计决策理论)，可以提出一些准则，来比较为检验同一假设而提出的各种检验。较重要的准则有：

​		**一致最大功效(UMP)准则** 　欲检验*h*<sub>0</sub>:θ∈嘷0，h1:θ∈嘷1；当给定检验水平α后，在所有满足的可供选择的检验HR中，是否有一个最好的，亦即：是否存在拒绝域H，使得对于所有θ∈嘷1及一切检验水平为α的H皆有。若这样的检验存在，则称HR为检验水平α的一致最大功效检验，简称UMP检验。奈曼与皮尔森在1933年提出了著名的奈曼-皮尔森引理。这是对[简单假设](https://baike.baidu.com/item/%E7%AE%80%E5%8D%95%E5%81%87%E8%AE%BE)寻求UMP检验的一个构造性的结果，即此时[似然比](https://baike.baidu.com/item/%E4%BC%BC%E7%84%B6%E6%AF%94)检验就是UMP检验。对某些[复合假设](https://baike.baidu.com/item/%E5%A4%8D%E5%90%88%E5%81%87%E8%AE%BE)也找到了 UMP检验，但并不是所有情况都存在 UMP检验。因此有必要在对检验作某些限制下寻找最大功效检验或建立另外一些优良性准则。

​		**无偏性准则** 　要求检验在备择假设*h*1成立时作出正确判断的概率不小于检验水平*α*，这就是说在*h*<sub>0</sub>不成立时拒绝*h*<sub>0</sub>的概率要不小于在*h*<sub>0</sub>成立时拒绝*h*<sub>0</sub>的概率，这种性质称为无偏性，具有这种性质的检验称为无偏检验。显然，如果在无偏检验中存在一致最大功效检验就称为一致最大功效无偏检验（简称UMPU检验）。UMP检验不存在时，仍可能有UMPU检验存在。例如正态总体中[方差](https://baike.baidu.com/item/方差)未知时，为检验均值*μ*=*μ*0的*t*检验就是UMPU检验，但不是UMP检验。

​		因为假设检验在统计决策理论中是一种特殊的统计决策问题，两类错误影响可用特殊损失来表示。例如选取特殊的[损失函数](https://baike.baidu.com/item/损失函数)，使正确判断时损失为零，错判时损失为1。它就可归结为犯第一类错误的概率*α*和犯第二类错误的概率*β*。这同用功效函数**P**θ(*X*∈HR)来叙述是一致的。因此把统计决策理论中容许性、同变性、[贝叶斯](https://baike.baidu.com/item/%E8%B4%9D%E5%8F%B6%E6%96%AF)决策、最小化最大等概念引进来，而得到容许检验、同变检验、贝叶斯检验和最小化最大检验。在同变检验限制下，又可以建立一致最大功效同变检验的概念。这些准则又可作为假设检验的优良性准则，从而扩大了假设检验的内容。

​		寻求在一定准则下的最优检验是很困难的，何况这种最优检验有时并不存在。于是提出了若干依据直观的[推理法](https://baike.baidu.com/item/推理法)，其中最重要的是似然比法。

​		**似然比检验**　运用与最大似然估计（见[点估计](https://baike.baidu.com/item/点估计)）类似的原理，可得到似然比检验法。设样本*X*的分布密度即[似然函数](https://baike.baidu.com/item/似然函数)为*l*(尣，*θ*)，*θ*∈嘷，欲检验的假设为*h*<sub>0</sub>:*θ*∈嘷0，称为似然比。显然0≤(尣)≤1，当(尣)太小时就拒绝*h*<sub>0</sub>，否则接受*h*<sub>0</sub>，其临界值*λ*0由检验水平*α* 和(尣)在*h*<sub>0</sub>成立时的分布确定，即。然而，在一般情况下，寻求(尣的精确分布并不容易。1938年S.S.威尔克斯证明了：在相当广泛的条件下，-2l*n*(尣)是渐近Ⅹ分布的， 这就为大样本的似然比检验提供了实行的可能。

用似然比法导出的重要检验有：

​		**U检验** 　若总体遵从正态分布*N*(*μ*，*σ*)，其中*σ*已知，*X*=(*X*1，*X*2，…，*X*n)是从总体中抽取的简单随机样本，记，则遵从标准正态分布*N*(0，1)，于是可考虑对μ的以下几种假设的检验，其中*μ*0是给定的常数，*α*为检验的水平，*u*α为标准正态分布的上*α*分位数。上述检验称为*U* 检验。

​		**t检验** 　若总体服从正态分布*N*(*μ*，*σ*)，但*σ*未知，记，，则*t*=遵从自由度为*n*-1的*t*分布，可对μ有以下的水平为*α*的检验，其中*t*α为自由度为*n*-1的*t*分布的上*α*分位数。这些检验称为*t*检验。

​		**F检验** 若*X*=（*X*1，*X*2，…，）及*Y*=（*Y*1，*Y*2，…，）分别为来自正态总体*N*（*μ*1，*σ*娝）及*N*（*μ*2，*σ*娤）的简单随机样本，记 ，，，，则遵从自由度为*n*1-1，*n*2-1的*F*分布，对比较*σ*娝与*σ*娤的假设有以下的水平为*α*的检验，其中*F*α为自由度为(*n*1-1，*n*2-1)的*F*分布的上*α*分位数。这些检验称为*F*检验，在方差分析中有广泛的应用。

## 1.3 基本步骤

1、提出检验假设又称无效假设，符号是*h*<sub>0</sub>；备择假设的符号是H<sub>1</sub>。

*h*<sub>0</sub>：样本与总体或样本与样本间的差异是由抽样误差引起的；

H<sub>1</sub>：样本与总体或样本与样本间存在本质差异；

预先设定的检验水准为0.05；当检验假设为真，但被错误地拒绝的概率，记作α，通常取α=0.05或α=0.01。

2、选定统计方法，由样本观察值按相应的公式计算出统计量的大小，如X2值、t值等。根据资料的类型和特点，可分别选用Z检验，T检验，[秩和检验](https://baike.baidu.com/item/秩和检验)和[卡方检验](https://baike.baidu.com/item/卡方检验)等。

3、根据统计量的大小及其分布确定检验假设成立的可能性P的大小并判断结果。若P>α，结论为按α所取水准不显著，不拒绝*h*<sub>0</sub>，即认为差别很可能是由于抽样误差造成的，在统计上不成立；如果P≤α，结论为按所取α水准显著，拒绝*h*<sub>0</sub>，接受H<sub>1</sub>，则认为此差别不大可能仅由抽样误差所致，很可能是实验因素不同造成的，故在统计上成立。P值的大小一般可通过查阅相应的界值表得到。

​		<u>教学中的做法:</u>

```
1.根据实际情况提出原假设和备择假设；
2.根据假设的特征，选择合适的检验统计量；
3.根据样本观察值，计算检验统计量的观察值(obs)；
4.选择许容显著性水平，并根据相应的统计量的统计分布表查出相应的临界值(ctrit)；
5.根据检验统计量观察值的位置决定原假设取舍。
```

## 1.4  意义

假设检验是[抽样推断](https://baike.baidu.com/item/抽样推断)中的一项重要内容。它是根据原资料作出一个总体指标是否等于某一个数值，某一[随机变量](https://baike.baidu.com/item/随机变量)是否服从某种[概率分布](https://baike.baidu.com/item/概率分布)的假设，然后利用样本资料采用一定的统计方法计算出有关检验的统计量，依据一定的概率原则，以较小的风险来判断估计数值与总体数值(或者估计分布与实际分布)是否存在显著差异，是否应当接受原假设选择的一种检验方法。

用样本指标估计总体指标，其结论有的完全可靠，有的只有不同程度的可靠性，需要进一步加以检验和证实。通过检验，对样本指标与假设的总体指标之间是否存在差别作出判断，是否接受原假设。这里必须明确，进行检验的目的不是怀疑样本指标本身是否计算正确，而是为了分析样本指标和总体指标之间是否存在显著差异。从这个意义上，假设检验又称为显著性检验。

进行假设检验，先要对假设进行陈述。通过下例加以说明。

例如，设某工厂制造某种产品的某种精度服从[平均数](https://baike.baidu.com/item/平均数)为方差的[正态分布](https://baike.baidu.com/item/正态分布)，据过去的数据，已知平均数为75，方差为100。若经过技术革新，改进了制造方法，出现了平均数大于75，方差没有变更，但仍存在平均数不超过75的可能性。试陈述为统计假设。

根据上述情况，可有两种假设，(1) 平均数不超过75，(2)平均数大于75，即如果我们把(1)作为原假设，即被检验的假设，称作零假设，记作H<sub>0</sub>，如果其他假设相对于零假设来说，是约定的、补充的假设，则就是备择的，故称为备择假设或对立假设，记作H<sub>1</sub>。

还须指出，哪个是零假设，哪个是备择假设，是无关紧要的。我们关心的问题，是要探索哪一个假设被接受的问题。被接受的假设是要作为推理的基础。在实际问题中，一般要考虑事情发生的逻辑顺序和关心的事件，来设立零假设和备择假设。

在作出了统计假设之后，就要采用适当的方法来决定是否应该接受零假设。由于运用统计方法所遇到的问题不同，因而解决问题的方法也不尽相同。但其解决方法的基本思想却是一致的，即都是“概率反证法”思想，即：

(1)为了检验一个零假设(即虚拟假设)是否成立， 先假定它是成立的，然后看接受这个假设之后，是否会导致不合理结果。如果结果是合理的，就接受它；如不合理，则否定原假设。

(2)所谓导致不合理结果，就是看是否在一次观察中， 出现小概率事件。通常把出现小概率事件的概率记为0，即显著性水平。 它在次数[函数](https://baike.baidu.com/item/函数)图形中是[曲线](https://baike.baidu.com/item/曲线)两端或一端的面积。因此，从统计检验来说，就涉及到[双侧检验](https://baike.baidu.com/item/双侧检验)和单侧检验问题。在实践中采用何类检验是由实际问题的性质来决定的。一般可以这样考虑：

①[双侧检验](https://baike.baidu.com/item/双侧检验)。如果检验的目的是检验抽样的样本统计量与假设参数的差数是否过大(无论是正方向还是负方向)，就把风险平分在右侧和左侧。比如显著性水平为0.05，即概率曲线左右两侧各占，即0.025。

②单侧检验。这种检验只注意估计值是否偏高或偏低。如只注意偏低，则临界值在左侧，称左侧检验；如只注意偏高，则临界值在右侧，称右侧检验。

对总体的参数的检量，是通过由样本计算的统计量来实现的。所以检验统计量起着决策者的作用。

**参数估计与假设检验**

统计推断是由样本的信息来推测母体性能的一种方法，它又可以分为两类问题，即**参数估计**和**假设检验**。实际生产和科学实验中，大量的问题是在获得一批数据后，要对[母体](https://baike.baidu.com/item/母体)的某一参数进行估计和检验。

例如，我们对45钢的[断裂韧性](https://baike.baidu.com/item/断裂韧性)作了测定，取得了一批数据，然后要求45钢断裂韧性的平均值，或要求45钢断裂韧性的单侧下限值，或要求45钢断裂韧性的分散度(即[离散系数](https://baike.baidu.com/item/离散系数))，这就是**参数估计**的问题。

又如，经过长期的积累，知道了某材料的[断裂韧性](https://baike.baidu.com/item/断裂韧性)的平均值和标准差，经改进热处理后，又测得一批数据，试问新工艺与老工艺相比是否有显著差异，这就是**假设检验**的问题。

这样可以看出，参数估计是假设检验的第一步，没有参数估计，也就无法完成假设检验。

## 1.5 应用

在雷达检测中，目标是产生假设的源，它可使用两个假设：H<sub>1</sub>和H<sub>0</sub>，分别表示目标存在(H<sub>1</sub>)和不存在(H<sub>0</sub>)。这是二元简单假设检验。二元数字通信问题也是简单假设检验。如果假设中含有目标未知参量，则是复合假设检验。m元通信问题也是复合假设检验。如果未知参量是随机变化的，则是随机参量信号的假设检验。

通信系统和雷达系统常用的最佳准则，是最小错误概率准则，即最大后验概率准则。以雷达检测为例：目标是源，它可使用的两个假设是H<sub>1</sub>和H<sub>0</sub>。接收端收到样本X(雷达回波)后，判定H<sub>1</sub>为真（目标存在），或判定H<sub>0</sub>为真（目标不存在概率可分别表示为p(H<sub>1</sub>|X)和p(H<sub>0</sub>|X)，称为后验概率。最大后验概率准则的判决规则是，若
$$
\frac{P(H_{1}|X)}{P(H_{2}|X)}>1
$$
则判定H<sub>1</sub>为真(选择H<sub>1</sub>)；否则判定H<sub>0</sub>为真。

# 2、显著性检验

显著性检验（significance test）就是事先对[总体](https://baike.baidu.com/item/总体/919248)（[随机变量](https://baike.baidu.com/item/随机变量/828980)）的参数或总体分布形式做出一个[假设](https://baike.baidu.com/item/假设/1524526)，然后利用样本信息来判断这个假设（备择假设）是否合理，即判断总体的真实情况与原假设是否有显著性差异。或者说，显著性检验要判断样本与我们对总体所做的假设之间的差异是纯属机会变异，还是由我们所做的假设与总体真实情况之间不一致所引起的。 显著性检验是针对我们对总体所做的假设做检验，其原理就是“小概率事件实际不可能性原理”来接受或否定假设。

抽样实验会产生[抽样误差](https://baike.baidu.com/item/抽样误差/9921064)，对实验资料进行比较分析时，不能仅凭两个结果（平均数或率）的不同就作出结论，而是要进行统计学分析，鉴别出两者差异是抽样误差引起的，还是由特定的实验处理引起的。

## 2.1 含义

显著性检验即用于实验处理组与对照组或两种不同处理的效应之间是否有差异，以及这种差异是否显著的方法。

常把一个要检验的假设记作*H*<sub>0</sub>,称为原假设（或[零假设](https://baike.baidu.com/item/零假设)） (null hypothesis) ，与*H*<sub>0</sub>对立的假设记作*H*<sub>1</sub>，称为备择假设(alternative hypothesis) 。

⑴ 在原假设为真时，决定放弃原假设，称为第一类错误，其出现的[概率](https://baike.baidu.com/item/概率)通常记作α；

⑵ 在原假设不真时，决定不放弃原假设，称为第二类错误，其出现的概率通常记作β

(3)α+β 不一定等于1<sup> [2]</sup>  。

通常只限定犯第一类错误的最大概率α， 不考虑犯第二类错误的概率β。这样的假设 检验又称为显著性检验，概率α称为[显著性水平](https://baike.baidu.com/item/显著性水平)。

最常用的α值为0.01、0.05、0.10等。一般情况下，根据研究的问题，如果放弃真假设损失大，为减少这类错误，α取值小些 ，反之，α取值大些。

## 2.2 目的

为什么要进行显著性检验进行显著性检验是为了消除第一类错误和第二类错误。通常情况下，α水平就是第一类错误。第一类错误是零假设为真却被错误拒绝的概率。第二类错误(β)是零假设为误却被错误接受的概率或是研究假设为真却被拒绝的概率。如果P值小于某个事先确定的水平，理论上则拒绝零假设，反之，如果P值大于某个事先确定的水平，理论上则不拒绝零假设。常用的显著性水平是0.05，0.01和0.001<sup>[2]</sup> 。不同的水平各有优缺点。水平越小，判定显著性的证据就越充分，但是不拒绝错误零假设的风险，犯第二类错误的可能性就越大，统计效力(就越低。选择水平不可避免地要在第一类错误和第二类错误之间做出权衡。如果犯第一类错误造成的后果不严重，比如在试探性研究中，我们可以将α水平定得高一些，如0.05或0.1。如果研究样本很小，为了提高统计效力，我们在某些研究中也不妨提高口水平。但是，如果犯第一类错误造成的后果很严重，比如我们要基于某项研究发现决定是否在全国推行某项教学改革，我们则需要将α水平定得低一些，如0.01或0.001。

## 2.3 常用的检验

### 2.3.1 t检验

T检验，亦称student t检验（Student's t test），主要用于样本含量较小（例如n < 30），[总体标准差](https://baike.baidu.com/item/总体标准差/3861969)σ未知的[正态分布](https://baike.baidu.com/item/正态分布/829892)。 [2.1]

[^2.1]: Fisher Box, Joan. Guinness, Gosset, Fisher, and Small Samples. Statistical Science. 1987, 2 (1): 45–52.

 T检验是用t分布理论来推论差异发生的概率，从而比较两个平均数的差异是否显著。它与f检验、[卡方检验](https://baike.baidu.com/item/卡方检验/2591853)并列。t检验是**戈斯特**为了观测酿酒质量而发明的,并于1908年在Biometrika上公布 [2.2]  。

[^2.2]: 尹希果主编．计量经济学原理与操作：重庆大学出版社，2009.09：37

**适用条件**

(1) 已知一个总体均数；

(2) 可得到一个[样本均数](https://baike.baidu.com/item/样本均数)及该样本[标准差](https://baike.baidu.com/item/标准差)；

(3) 样本来自正态或近似正态总体 [2.3]。

**主要分类**

t检验可分为单总体检验和双总体检验，以及配对样本检验 <sup>[2.1]</sup>。

**1）单总体检验**

单总体t检验是检验一个[样本平均数](https://baike.baidu.com/item/样本平均数)与一个已知的[总体平均数](https://baike.baidu.com/item/总体平均数)的差异是否显著。当[总体分布](https://baike.baidu.com/item/总体分布)是正态分布，如总体标准差未知且[样本容量](https://baike.baidu.com/item/样本容量)小于30，那么样本平均数与总体平均数的[离差](https://baike.baidu.com/item/离差)[统计量](https://baike.baidu.com/item/统计量)呈t分布。

单总体t检验统计量为：
$$
t = \frac{\bar{X}-\mu}{\frac{\delta_{x}}{\sqrt{n-1}}}
$$
其中，$i = 1, ..., n$, $\bar{x} = \frac{\sum_{i=1}^{n}x_{i}}{n}$ 为样本平均数，$\delta$ 、$s = \sqrt{\frac{\sum_{i=1}^{n}(x_{i}-\bar{x})^{2}}{n-1}}$ 为样本标准差，$n$为样本数。该统计量$t$在零假说：$\mu = \mu_{0}$ 为真的条件下服从自由度为 n-1 的 t分布。

**2）双总体检验**

**双总体t检验**是检验两个[样本平均数](https://baike.baidu.com/item/样本平均数)与其各自所代表的总体的差异是否显著。双总体t检验又分为两种情况，一是独立样本t检验（各实验处理组之间毫无相关存在，即为独立样本），该检验用于检验两组非相关样本被试所获得的数据的[差异性](https://baike.baidu.com/item/差异性)；一是配对样本t检验，用于检验匹配而成的两组被试获得的数据或同组被试在不同条件下所获得的数据的差异性，这两种情况组成的样本即为相关样本。

（1）独立样本t检验[统计量](https://baike.baidu.com/item/统计量)为：
$$
t = \frac{\bar{X_{1}}-\bar{X_{2}}}{\sqrt{\frac{(n_{1}-1)S_{1}^{2}+(n_{2}-1)S_{2}^{2}}{n_{1}+n_{2}-2}}(\frac{1}{n_{1}}+\frac{1}{n_{2}})}
$$
$S_{1}^{2}$ 和$S_{2}^{2}$为两[样本方差](https://baike.baidu.com/item/样本方差)；$n_{1}$ 和 $n_{2}$为两[样本容量](https://baike.baidu.com/item/样本容量)。 

（2）配对样本检验

**配对样本t检验**可视为单样本*t*检验的扩展，不过检验的对象由一群来自常态分配独立样本更改为二群配对样本之观测值之差。若二配对样本*x*1*i*与*x*2*i*之差为*d**i*=*x*1*i*−*x*2*i*独立，且来自常态分配，则*d**i*之母体期望值*μ*是否为*μ*0可利用以下统计量：
$$
t = \frac{\bar{d}-\mu_{0}}{\frac{s_{d}}{\sqrt{n}}}
$$
其中，$i = 1, ..., n, \bar{d} = \frac{\sum_{i=1}^{n}d_{i}}{n}$ 为配对样本差值之平均数，$s_{d} = \sqrt{\frac{\sum_{i=1}^{n}(d_{i}-\bar{d})^{2}}{n-1}}$ 为配对样本差值之标准偏差，$n$ 为配对样本数。该统计量 $t$ 在零假说：$\mu = \mu_{0}$ 为真的条件下服从自由度为 $n−1$ 的[t分布](https://baike.baidu.com/item/t分布)。

**检验步骤**

下面以一个实例的单总体t检验对t检验做一说明： [2.4] 

问题：难产儿出生数n = 35，体重均值 $\bar{x}=3.42, S = 0.40$, 一般婴儿出生体重 μ0= 3.30（大规模调查获得），问相同否？

解：

​		**1.建立假设、确定检验水准α**

​		H0：μ = μ0 （零假设null hypothesis）

​		H1：μ ≠ μ0（备择假设alternative hypothesis）

​		双侧检验，检验水准：α=0.05

​		**2.计算检验统计量**
$$
t = \frac{\bar{x}-\mu_{0}}{\frac{S}{\sqrt{n}}}\\
=1.77\\
$$

$$
<Empty \space Math \space Block>
$$









### 2.3.2 t<sup>‘</sup> 检验

### 2.3.3 U检验

### 2.3.4 方差分析 





























# 参考文献

[1] 邓奋发. MATLAB R2015b概率与数理统计[M]. 北京：清华大学出版社, 2017.01.第139页.

[2] 张厚粲, 徐建平. 现代心理与教育统计学[M]. 北京师范大学出版社, 2004.

[3] 张凤菊, 刘晓娟, 赵丽平,等. 数据差异显著性检验[J]. 农机使用与维修, 2012(4):51-52.