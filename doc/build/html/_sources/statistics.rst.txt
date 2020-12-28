
统计学
==========

   整理一下统计学中常用的概念、方法论。作为一个统计学出身的人，遇到这些问题时希望不要被难倒。

内容
-------------------------

   - 大数定律、中心极限定理
   - 贝叶斯公式、贝叶斯定理
   - 参数估计
      - 点估计、区间估计
   - 最大似然估计与EM算法
   - 假设检验
      - A/B test
   - 方差分析
   - 回归分析
   - 主成分分析
   - 因子分析
   - 聚类分析
   - 统计显著性


1.大数定律、中心极限定理
---------------------------

   - `维基百科 <https://zh.wikipedia.org/wiki/%E5%A4%A7%E6%95%B0%E5%AE%9A%E5%BE%8B>`__

      在统计学中，大数定律又称大数法则、大数率，是描述相当多次数重复实验的结果的定律；根据这个定律，样本数量越多，则其算术平均值就有越高的概率接近期望值。

   - **定义1 大数定律**

      若 :math:`\xi_1, \xi_2,...,\xi_n,...` 是随机变量序列，令
      
      .. math:: 
      
         \eta_{n} = \frac{\xi_1+\xi_2+...+\xi_n}{n}
      
      若存在常数序列 :math:`a_1,a_2,...,a_n,...` 对任何的正数 :math:`\epsilon`, 恒有

      .. math:: 
         
         \lim\limits_{n \to \infty}P(|\eta_n-a_n|<\epsilon)=1
      
      则称序列 :math:`{\epsilon_n}` 服从 **大数定律**(或**大数法则**)。

   - **切比雪夫(Chebyishev)不等式**

   - **切比雪夫定理的特殊情况**

   - **伯努利大数定理**

   - **辛钦大数定理**

   - **定义2 中心极限定理**

      对于独立随机变量序列 :math:`\xi_1, \xi_2,...,\xi_n,...`，假定 :math:`E(\xi_n)` 和 :math:`D(\xi_n)` 都存在，令

      .. math:: 
      
         \zeta_n=\frac{\sum_{i=1}^{n}\xi_i-\sum_{i=1}^{n}E(\xi_i)}{\sqrt{\sum_{i=1}^{n}}}
      
      若
      
      .. math::
      
         \lim\limits_{n \to \infty}P(\zeta_n < x)=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{x}e^{\frac{-t^2}{2}}dt
      
      则称序列 :math:`{\xi_n}` 服从 **中心极限定理(Central Limit Theorem)**。

   - **同分布的中心极限定理**

   - **德莫佛－拉普拉斯定理**

2.统计推断理论
-------------------------

   - 参数估计

      - 点估计

      - 区间估计

   - 假设检验

      - 参数假设检验问题

      - 非参数假设检验问题

   - 抽样分布

2.1 参数估计
~~~~~~~~~~~~~~~~~~~~~~~~

2.2 假设检验
~~~~~~~~~~~~~~~~~~~~~~~~

   假设检验(hypothesis test)是由K.Pearson于20世纪初提出的，之后由费希尔进行了细化，并最终由Neyman和E.Pearson提出了较完整的假设检验理论。

2.2.1 统计显著性
^^^^^^^^^^^^^^^^^^^^^^^^

   显著性、统计显著性(Statistical significance)：是指零假设为真的情况下拒绝零假设所要承担的风险水平，又叫概率水平，或者显著水平。

      - 显著性的含义是指两个群体的态度之间的任何差异是由于系统因素而不是偶然因素的影响。假定控制了可能影响两个群体之间差异的所有其他因素，
        因此，余下的解释就是我们所推断的因素，而这个因素不能够 100% 保证，所以有一定的概率值，叫显著性水平(Significant level)。

      - 总的来说，它表示群体之间得以相互区别的能力。在统计假设检验中，公认的小概率事件的概率值被称为统计假设检验的显著性水平，
        对同一量，进行多次计量，然后算出平均值。



2.2.2 假设检验的基本思想
^^^^^^^^^^^^^^^^^^^^^^^^

   假如实验结果与原假设H发生矛盾就拒绝原假设 H，否则就接受原假设 H

   假如对某个指标 :math:`\theta` 进行检测，检测的临界值为 :math:`\theta_0`，即如果 :math:`\theta \geq \theta_0` 则认为指标
   :math:`\theta` 合格，如果 :math:`\theta < \theta_0`，则认为指标 :math:`\theta` 不合格；

   因此命题 “:math:`\theta \geq \theta_0`” 将涉及如下两个参数集合：

      .. math::
         
         \Theta_0 = \{\theta:\theta \geq \theta_0\}

      .. math::
         
         \Theta_1 = \{\theta:\theta < \theta_0\}

   - 在统计学中，这两个非空不相交的参数集合都称作 ``统计假设``，简称 ``假设``

   - 通过样本对一个假设作出“对”或“不对”的具体判断规则就称为该假设的一个 ``检验`` 或 ``检验法则``

   - 检验的结果若是否定该命题，则称 ``拒绝这个假设`` ，否则就称为 ``接受该假设``

   - 若假设可用一个参数的集合表示，该假设检验问题称为 ``参数假设检验`` ，否则称为 ``非参数假设检验问题``，
     上面的问题就是一个参数假设检验问题，而对假设“总体为正太分布”作出检验的问题就是一个非参数假设检验问题

2.2.3 假设检验的基本步骤
^^^^^^^^^^^^^^^^^^^^^^^^

   - 建立假设

      - 原假设(零假设, null hypothesis)： :math:`H_0:\theta\in \Theta_0`

      - 对立假设(备择假设, alternative hypothesis)：:math:`H_1:\theta\in \Theta_1`

      - 简单原假设：:math:`H_0:\theta = \theta_0`

         - 双侧(双边)假设：
         
            - :math:`H_0:\theta = \theta_0` vs :math:`H_0:\theta \neq \theta_0`

         - 单侧(单边)假设：
            
            - :math:`H_0:\theta = \theta_0` vs :math:`H_0:\theta < \theta_0` 或者 :math:`H_0:\theta = \theta_0` vs :math:`H_0:\theta > \theta_0`

      - 复杂(复合)原假设：
         
         - :math:`H_0:\theta \geq \theta_0` 或者 :math:`H_0:\theta < \theta_0`

      - 在假设检验中，通常将不宜轻易加以否定的假设作为原假设；

   - 选择检验统计量，给出拒绝域形式

      - 拒绝域：对于一个假设的检验就是指这样一个法则：当有了具体的样本后，按照该法则就可以决定是接受  :math:`H_0`\还是拒绝  :math:`H_0`，即检验就等价于把样本空间划分为两个互不相交的部分  :math:`W`\和  :math:`\bar{W}`，当样本属于  :math:`W`\时，拒绝  :math:`H_0`\；否则接受  :math:`H_0`，于是，称  :math:`W`\为该检验的拒绝域，而称  :math:`\bar{W}`\为接受域；

      - 检验统计量：由样本对原假设进行检验总是通过一个统计量完成的，该统计量称为检验统计量；

   - 选择显著性水平

      - 由于样本是随机的，当应用某种检验做判断时，可能做出正确的判断，也可能做出错误的判断；

      - 两种错误：

         - 当  :math:`\theta \in \Theta_0`\时，样本由于随机性却落入了拒绝域  :math:`W`，
           于是采取了拒绝原假设 :math:`H_0` 的错误决策，称这样的错误为第一类错误(type I error)；

         - 当  :math:`\theta \in \Theta_1`\时，样本由于随机性却落入了接受域  :math:`\bar{W}`，
           于是采取了接受原假设 :math:`H_0` 的错误决策，称这样的错误为第一类错误(type II error)；

      - 犯两种错误的概率：由于检验结果受样本的影响，具有随机性，于是，可用总体分布定义犯第一类，第二类错误的概率如下

         - 犯第一类错误概率：:math:`\alpha=P_{\theta}(X \in W), \theta \in \Theta_0`

         - 犯第二类错误概率：:math:`\beta=1-\alpha=P_{\theta}(X \in \bar{W}), \theta \in \Theta_1`

      - 势函数，功效函数(power function)：每一个检验都无法避免犯错误的可能，但无法找到一个检验，使其犯两种错误的概率都尽可能地小
         :math:`g(\theta) = P_{\theta}(X \in W), \theta \in \Theta_0 \cup \Theta_1`
         显然，势函数 :math:`g(\theta)` 是定义在参数空间  :math:`\Theta` 上的一个函数，当 :math:`\theta\in\Theta_0`\时，
         :math:`g(\theta)=\alpha=\alpha(\theta)`，当  :math:`\theta\in\Theta_1`\时，
         :math:`g(\theta)=1-\beta=1-\beta(\theta)`，犯两类错误的概率都是参数  :math:`\theta`\的函数：

         .. math::

            g(\theta)=\left\{
            \begin{array}{l}
            \alpha(\theta)    & & {\theta\in\Theta_0}\\
            1-\beta(\theta)   & & {\theta\in\Theta_1}\\
            \end{array} \right.

         即

         .. math::

            \left\{
            \begin{array}{l}
            \alpha(\theta)=g(\theta)    & & {\theta\in\Theta_0}\\
            \beta(\theta)= 1-g(\theta)  & & {\theta\in\Theta_1}\\
            \end{array} \right.

         上面的函数说明，在样本量给定的条件下，:math:`\alpha`\与 :math:`\beta`\中一个减小必导致另一个增大，
         既然不能同时控制一个检验的犯第一类、第二类错误的概率，只能采取折中方案，通常的做法是仅限制犯第一类错误的概率，
         也就是费希尔的显著性检验。

      - 显著性水平

         - 对检验问题 :math:`H_0:\theta\in\Theta_0` vs :math:`H_1:\theta\in\Theta_1`，如果一个检验满足对任意的 :math:`\theta\in\Theta_0`
           都有：:math:`g(\theta)\leq\alpha`，则称该检验是显著性水平为 :math:`\alpha` 的显著性检验，简称水平为  :math:`\alpha` 的检验。

         - 提出显著性检验的概念就是要控制犯第一类错误的概率 :math:`\alpha`，但也不能使得 :math:`\alpha` 
           过小(:math:`\alpha` 过小会导致 :math:`\beta` 过大)，在适当控制 :math:`\alpha` 中制约 :math:`\alpha`，
           最常用的选择是 :math:`\alpha=0.05`，:math:`\alpha=0.10`，:math:`\alpha=0.01`

   - 给出拒绝域

      - :math:`g(\theta_0)=\alpha`

      - 显著性水平越小，拒绝域越小；

   - 做出判断

      - 在有了明确的拒绝域  :math:`W` 后，根据样本观测值就可以做出判断；

      - 由样本观测值计算检验统计量，由样本统计量是否属于拒绝域做出判断；

      - 可能会出现这样的情况：在一个较大的显著性水平下得到了拒绝原假设的结论，而在一个较小的显著性水平下却得到了接受原假设的结论；

      - 检验的  :math:`p` 值(  :math:`p-value`)

         - 在一个假设检验问题中，利用样本观测值能够做出拒绝原假设的最小显著性水平称为检验的p值，
           这样由检验的p值与人们心中的显著性水平  :math:`\alpha` 进行比较就可以很容易做出检验的结论：

            - 如果 :math:`\alpha\geq p`，则在显著性水平  :math:`\alpha` 下拒绝原假设；

            - 如果 :math:`\alpha< p`，则在显著性水平  :math:`\alpha` 下接受原假设；

         - 假设检验可以从两个方面进行：其一是建立拒绝域，考察样本观测值是否落在拒绝域中，
           其二是根据样本观测值计算检验的p值，通过将p值与事先设定的显著性水平进行比较

2.3 抽样分布
~~~~~~~~~~~~~~~~~~~~~~~~~

3.不确定性
-------------------------

3.1 非传递性骰子
~~~~~~~~~~~~~~~~~~~~~~~~

3.2 医疗概率
~~~~~~~~~~~~~~~~~~~~~~~~

3.3 混沌
~~~~~~~~~~~~~~~~~~~~~~~~

3.4 社会选择与阿罗定理
~~~~~~~~~~~~~~~~~~~~~~~~

3.5 纽科姆悖论
~~~~~~~~~~~~~~~~~~~~~~~~

4.偏度、峰度
-------------------------

4.1 偏度
~~~~~~~~~~~~~~~~~~~~~~~~~

   - 偏度（skewness）又称偏态、偏态系数，是描述数据分布偏斜方向和程度的度量，其是衡量数据分布非对称程度的数字特征。
     对于随机变量 :math:`X`，其偏度是样本的三阶标准化矩:

      .. math:: 
         
         Skew(x) = E[(\frac{(X-\mu)^{3}}{\sigma})] = \frac{E(X^{3})-3\mu \sigma^{2} - \mu^{3}}{\sigma^{3}}

   - 偏度的衡量是相对于正态分布来说，正态分布的偏度为0。因此我们说:

      - 若数据分布是对称的，偏度为0

      - 若偏度 > 0，则可认为分布为右偏，也叫正偏，即分布有一条长尾在右

      - 若偏度 < 0，则可认为分布为左偏，也叫负偏，即分布有一条长尾在左

4.2 峰度
~~~~~~~~~~~~~~~~~~~~~~~~~

   - 峰度(Kurtosis)是描述数据分布陡峭或平滑的统计量，通过对峰度的计算，
     我们能够判定数据分布相对于正态分布而言是更陡峭还是平缓。对于随机变量 :math:`X`，
     其峰度为样本的四阶标准中心矩

      .. math:: 
      
         Kurt(x) = E[(\frac{(X-\mu)^{4}}{\sigma})] = \frac{E[(X-\mu)^4]}{(E[[(X-\mu)^2]])^2}

   - 当峰度系数 > 0，从形态上看，它相比于正态分布要更陡峭或尾部更厚

   - 峰度系数 < 0，从形态上看，则它相比于正态分布更平缓或尾部更薄

   - 在实际环境当中，如果一个分部是厚尾的，这个分布往往比正态分布的尾部具有更大的“质量”，即含又更多的极端值

   - 我们常用的几个分布中，正态分布的峰度为 0，均匀分布的峰度为 -1.2，指数分布的峰度为 6

4.3 Python 实现
~~~~~~~~~~~~~~~~~~~~~~~~~

   .. code-block:: python

      import pandas as pd
      import matplotlib.pyplot as plt
      import statsmodels.stats.api as sms
      import statsmodels.formula.api as smf
      from statsmodels.compat import lzip
      from statsmodels.graphics.tsaplots import plot_acf

      # data
      df = pd.read_excel(file)

      # data scatter plot 
      fig, ax = plt.subplots(figsize = (8, 6))
      plt.ylabel("Loss")
      plt.xlabel("Distance")
      plt.plot(df["distance"], df["loss"], "bo-", label = "loss")
      plt.legend()
      plt.show()

      # Linear Regression
      expr = "loss ~ distance"
      results = smf.ols(expr, df).fit()
      print(results.summary())

      # omnibus 检验
      omnibus_label = ["Omnibus K-squared test", "Chi-squared(2) p-value"]
      omnibus_test = sms.omni_normtest(results.resid)
      omnibus_results = lzip(omnibus_label, omnibus_test)
      print(jb_results)

      # jarque_bera 检验
      jb_label = ["Jarque-Bear test", "Chi-squared(2) p-value", "Skewness", "Kurtosis"]
      jb_test = sms.jarque_bera(results.resid)
      jb_results = lzip(jb_label, jb_test)
      print(jb_results)

5.回归分析
-------------------------

5.1 回归分析简介
~~~~~~~~~~~~~~~~~~~~~~~~~


5.2 回归分析理论
~~~~~~~~~~~~~~~~~~~~~~~~~


5.3 回归分析实现
~~~~~~~~~~~~~~~~~~~~~~~~~


6.方差分析
-------------------------

6.1 方差分析简介
~~~~~~~~~~~~~~~~~~~~~~~~~


6.2 方差分析理论
~~~~~~~~~~~~~~~~~~~~~~~~~


6.3 方差分析实现
~~~~~~~~~~~~~~~~~~~~~~~~~

