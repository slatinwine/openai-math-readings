---
layout: default
title: "Arithmetic classification and non-Pisot singularity for Bernoulli convolutions"
family: "153"
discipline: "Dynamical systems and ergodic theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Arithmetic classification and non-Pisot singularity for Bernoulli convolutions

> 结果族 153：Arithmetic classification and non-Pisot singularity for Bernoulli convolutions　·　学科：Dynamical systems and ergodic theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文为无偏 Bernoulli 卷积（Bernoulli convolution）\(\nu_\lambda\) 建立了覆盖全部 \(\lambda\in(0,1)\) 的奇异性算术判据——一个用显式有限代数单位集表达的单侧逼近条件，并证明了 Pisot 之外的奇异参数：一切四次 Salem 数的倒数、以及一个 31 次多项式的非 Pisot 根的倒数处均奇异，回答了近期文献记录的公开问题。

## 问题背景

对 \(0<\lambda<1\)，\(\nu_\lambda\) 是随机级数 \(Y_\lambda=\sum_{n\ge0}\varepsilon_n\lambda^n\)（符号独立、取 \(\pm1\) 各半）的分布。Jessen 与 Wintner（1935）证明它具有纯类型（pure type）：要么奇异（singular）要么绝对连续（absolutely continuous），故每个参数都有明确的分类问题。\(\lambda<1/2\) 时覆盖论证直接给出奇异性，\(\lambda=1/2\) 是均匀分布，真正的困难集中在 \((1/2,1)\)。Erdős（1939）证明当 \(\lambda^{-1}\) 是 Pisot 数（Pisot number，其余共轭模长均小于 1 的实代数整数）时奇异，依据是 Fourier 变换不趋于零；Garsia（1962）对另一算术类证明绝对连续。此后 Solomyak、Hochman、Shmerkin、Varjú 的几乎处处理论（如可能奇异的参数集 Hausdorff 维数为零）把例外压缩到极小集合，却无法判定具体参数的类型。更棘手的是 Salem（1943）证明只要 \(\lambda^{-1}\) 不是 Pisot 数，Fourier 变换必趋于零，Erdős 的方法对 Salem 数（Salem number，共轭含 \(\beta^{-1}\) 与单位圆上的复对）天然失效；是否存在倒数非 Pisot 的奇异例子，被近期文献明确列为公开问题。

## 主要结果

论文有三项定理。**算术判据（定理 2.1）**：对整数 \(n\ge1\)、\(d\ge2\)，令 \(R(n,d)\) 为度数 \(dn\)、极小多项式系数全在 \(\{-1,0,1\}\)、模 2 不可约、常数项为 \(-1\) 的实代数单位（algebraic unit）\(r\in(1/2,1)\) 构成的有限集；把与 \(r\) 距离不超过 \(4^{-n}\) 的同类单位的系数前缀向量收集为 \(W_n(r;d)\)。若至少 \(2^n/d\) 个坐标卦限（orthant）内各含不少于 \(j(2r)^n\) 个不同向量，则称 \(r\) 被保留。定理断言：\(\nu_\lambda\) 奇异当且仅当对某个固定的 \(d\)、一切 \(j\) 和无穷多个 \(n\)，存在保留单位 \(r\) 使 \(r-4^{-n}\le\lambda<r\)。这是无穷的单侧逼近条件，而非有限的成员判定算法；把 \(\limsup\) 换成 \(\liminf\) 结论不变。**四次 Salem 定理（定理 5.1）**：任何四次 Salem 数 \(\beta\in(1,2)\) 都使 \(\nu_{1/\beta}\) 奇异；显式特例为 \(x^4-x^3-x^2-x+1\) 与 \(x^4-2x^3+x^2-2x+1\) 的大于 1 的实根。**31 次多项式定理（定理 6.1）**：多项式 \(p(t)=t^{31}-2t^{30}+\sum_{j=0}^{9}(t^{3j+1}-t^{3j})\)（满足 \((t^2+t+1)p(t)=t^{33}-t^{32}-t^{31}-t^{30}-1\)）在 \((1.8392,1.8393)\) 内有唯一实根 \(\beta\)；它有一对模长平方约 \(1.000209\) 的共轭复根落在单位圆外，故不是 Pisot 数，而 \(\nu_{1/\beta}\) 奇异。文中还从判据重新推出 Erdős 的 Pisot 奇异性与 Garsia 参数的绝对连续性两类经典结果。

## 证明思路

判据的一个方向是纯测度论计数：若保留单位满足 \(r-4^{-n}\le\lambda<r\)，则其近邻单位的系数前缀 \(w\) 都满足 \(|\sum_{i<n}w_i\lambda^i|\le B\lambda^n\)（因 \(4^{-n}=o(\lambda^n)\)），于是大量词对的前缀和彼此相差 \(O(\lambda^n)\)；分箱计数给出 Lebesgue 测度至多 \(C/j\) 而 \(\mu_\lambda\)-质量至少 \(1/d\) 的集合，令 \(j\to\infty\) 便与绝对连续性矛盾，再用纯类型定出奇异。核心是反方向的实现引理（realization lemma）。先证 \(\lambda>1/2\) 时首比特的两个条件测度必有公共非零子测度（熵论证：只有 \(O(\lambda^{-n})\) 个量化格子，装不下前 \(n\) 个比特的 \(n\log 2\) 熵）；再由紧集中引理（compact concentration）把奇异性转化为至少 \(c2^n\) 个首比特为 0 的词，每个各有 \(Q(2\lambda)^n\) 个首比特为 1 的近邻。对其差向量 \(w\)（\(w_0=-1\)）分三步补全成合格多项式：先贪心逐位添系数（类似 \(\beta\)-展开）把多项式在 \(\lambda\) 处的残差指数级压小；再用紧性引理——有界系数多项式在 \(\lambda\) 右侧不能处处太平，否则极限幂级数在 \(\lambda\) 处各阶导数全为零，违背恒等定理——找到符号翻转点；最后用 \(\mathbb F_2\) 上算术进度中的素多项式定理（函数域 Riemann 猜想的特征和推论），在保留前 \(n\) 位系数的同时加上不可约性，对两个在 \(\lambda\) 处异号的补全式用介值定理取出根 \(r\in(\lambda,\lambda+4^{-n}/2]\)，它正是首 \(n\) 位系数等于 \(w\) 的代数单位。四次 Salem 定理绕开"Fourier 必衰减"的障碍：以 \(A_m=\prod_h(\beta^{k_h}-\beta^{-k_h})\) 为频率乘子，用鸽笼原理选 \(k_h\)，使 \(L_m=\log(1/\delta_m)\)（\(\delta_m\) 是单位圆共轭损耗）每步至少增至 \(2.1\) 倍，快于余弦损失总和的 \(2.0301\) 倍增速，故总损失 \(S_m=o(L_m)\)；迹恒等式把高频相位替换为整数加有限窗口内独立符号的相位，其带符号平均 \(F_m\) 在 \(\nu_{1/\beta}\) 下集中（均值不低于 \(e^{-L_m/20}\)），在 Lebesgue \(L^2\) 下却因频率间隔至少 \(\pi(\beta-1)\) 而趋于零；两者相减并用切比雪夫不等式取 \(\limsup\) 子列，即得满 \(\nu\)-测度的 Lebesgue 零测集。31 次多项式则依靠精细计数：词向量落入固定格点，箱子体积按 \(\mathcal M^N\)（\(\log\mathcal M-\log\beta<0.0002094\)）增长，比 \(\beta^N\) 略多；作者构造一族正的三角因子之积，其在展开坐标下的 Lebesgue 积分一致有界（由近三次关系 \(\beta^3-\beta^2-\beta-1=\beta^{-30}\) 驱动的有限自动机排除近平消的频率模式），却在概率趋于 1 的典型词上以超过 \(0.000220N\) 的速率指数增长；超额增益恰好吃掉格点的超额体积，最终覆盖的 Lebesgue 测度按 \(e^{-0.0000066N}\) 衰减而概率趋于 1，奇异性立得。

## 可信度与备注

本文主结果尚无 Lean 形式化证明，请以社区核验为准；按 OpenAI 官方声明，未经形式化的结果可能有问题。结果族 153 仅含这一篇手稿，但论文内部互相支撑：判据能原样复现 Erdős 的 Pisot 奇异性与 Garsia 的绝对连续性（文中第 4 节专门验证），两个非 Pisot 定理均独立直接证明，再由判据转译为对应的逼近性质。31 次多项式例的根隔离与矩不等式依赖附录中的有理数计算证书，该部分技术性较强，此处从略。

{% endraw %}
