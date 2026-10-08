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

## 入门导读 🐣

想象你站在原点反复掷硬币：正面走一步、反面退一步，而且每步长度按固定比例 λ 缩短。走完无穷多步后，你会停在哪里？这篇论文给"停点分布"做全面体检：它是摊成一段有密度的光滑分布，还是缩成一层没有密度的"灰尘"。

**关键词卡片**

- Bernoulli 卷积（Bernoulli convolution）：掷硬币随机走步后，最终停点的概率分布。
- 奇异（singular）：概率堆在零长度的集合上，画不出密度曲线。
- 绝对连续（absolutely continuous）：概率摊得很匀，可以用密度函数描述。
- Pisot 数（Pisot number）：一种特殊代数整数，其余"同伴根"（共轭）都缩在单位圆内。
- Salem 数（Salem number）：同伴根分布在单位圆内外的代数整数，比 Pisot 数更难对付。

**看个具体例子**

只走三步，把 8 种可能落点画出来：λ=0.5 时均匀铺开；λ=0.4 时裂成两堆，中间出现一条大缝——"灰尘"的征兆。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="35" text-anchor="middle" font-size="16">掷三步硬币后的 8 种可能落点</text><text x="280" y="70" text-anchor="middle" font-size="15">λ = 0.5：落点均匀铺开</text><line x1="80" y1="100" x2="480" y2="100" stroke="#999"/><circle cx="105" cy="100" r="5" fill="#333"/><circle cx="155" cy="100" r="5" fill="#333"/><circle cx="205" cy="100" r="5" fill="#333"/><circle cx="255" cy="100" r="5" fill="#333"/><circle cx="305" cy="100" r="5" fill="#333"/><circle cx="355" cy="100" r="5" fill="#333"/><circle cx="405" cy="100" r="5" fill="#333"/><circle cx="455" cy="100" r="5" fill="#333"/><text x="280" y="150" text-anchor="middle" font-size="15">λ = 0.4：裂成两堆，中间出现大缝</text><line x1="80" y1="185" x2="480" y2="185" stroke="#999"/><circle cx="124" cy="185" r="5" fill="#333"/><circle cx="156" cy="185" r="5" fill="#333"/><circle cx="204" cy="185" r="5" fill="#333"/><circle cx="236" cy="185" r="5" fill="#333"/><circle cx="324" cy="185" r="5" fill="#333"/><circle cx="356" cy="185" r="5" fill="#333"/><circle cx="404" cy="185" r="5" fill="#333"/><circle cx="436" cy="185" r="5" fill="#333"/><line x1="236" y1="197" x2="236" y2="207" stroke="#c0392b"/><line x1="324" y1="197" x2="324" y2="207" stroke="#c0392b"/><line x1="236" y1="202" x2="324" y2="202" stroke="#c0392b"/><text x="280" y="230" text-anchor="middle" font-size="14" fill="#c0392b">中缝：永远填不上的空隙（奇异征兆）</text></svg>

</div>

λ 小于 1/2 时缝隙越走越多，奇异是显然的；λ=0.5 恰是均匀分布；难的是中间地带。论文给出覆盖一切 λ∈(0,1) 的算术判据，并证明新的奇异参数：任何四次 Salem 数的倒数（如 x⁴−x³−x²−x+1 的大于 1 的根），以及一个 31 次多项式的某个非 Pisot 根的倒数处，分布都奇异——Pisot 之外首次有了确凿例子。

**为什么值得关心**

Erdős 1939 年发现 Pisot 奇异例之后，"非 Pisot 参数是否也可能奇异"悬置多年，本文给出全参数判据并首次拿下非 Pisot 例子。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

论文为无偏 Bernoulli 卷积（Bernoulli convolution）`@@M@@\nu_\lambda@@` 建立了覆盖全部 `@@M@@\lambda\in(0,1)@@` 的奇异性算术判据——一个用显式有限代数单位集表达的单侧逼近条件，并证明了 Pisot 之外的奇异参数：一切四次 Salem 数的倒数、以及一个 31 次多项式的非 Pisot 根的倒数处均奇异，回答了近期文献记录的公开问题。

## 问题背景

对 `@@M@@0<\lambda<1@@`，`@@M@@\nu_\lambda@@` 是随机级数 `@@M@@Y_\lambda=\sum_{n\ge0}\varepsilon_n\lambda^n@@`（符号独立、取 `@@M@@\pm1@@` 各半）的分布。Jessen 与 Wintner（1935）证明它具有纯类型（pure type）：要么奇异（singular）要么绝对连续（absolutely continuous），故每个参数都有明确的分类问题。`@@M@@\lambda<1/2@@` 时覆盖论证直接给出奇异性，`@@M@@\lambda=1/2@@` 是均匀分布，真正的困难集中在 `@@M@@(1/2,1)@@`。Erdős（1939）证明当 `@@M@@\lambda^{-1}@@` 是 Pisot 数（Pisot number，其余共轭模长均小于 1 的实代数整数）时奇异，依据是 Fourier 变换不趋于零；Garsia（1962）对另一算术类证明绝对连续。此后 Solomyak、Hochman、Shmerkin、Varjú 的几乎处处理论（如可能奇异的参数集 Hausdorff 维数为零）把例外压缩到极小集合，却无法判定具体参数的类型。更棘手的是 Salem（1943）证明只要 `@@M@@\lambda^{-1}@@` 不是 Pisot 数，Fourier 变换必趋于零，Erdős 的方法对 Salem 数（Salem number，共轭含 `@@M@@\beta^{-1}@@` 与单位圆上的复对）天然失效；是否存在倒数非 Pisot 的奇异例子，被近期文献明确列为公开问题。

## 主要结果

论文有三项定理。**算术判据（定理 2.1）**：对整数 `@@M@@n\ge1@@`、`@@M@@d\ge2@@`，令 `@@M@@R(n,d)@@` 为度数 `@@M@@dn@@`、极小多项式系数全在 `@@M@@\{-1,0,1\}@@`、模 2 不可约、常数项为 `@@M@@-1@@` 的实代数单位（algebraic unit）`@@M@@r\in(1/2,1)@@` 构成的有限集；把与 `@@M@@r@@` 距离不超过 `@@M@@4^{-n}@@` 的同类单位的系数前缀向量收集为 `@@M@@W_n(r;d)@@`。若至少 `@@M@@2^n/d@@` 个坐标卦限（orthant）内各含不少于 `@@M@@j(2r)^n@@` 个不同向量，则称 `@@M@@r@@` 被保留。定理断言：`@@M@@\nu_\lambda@@` 奇异当且仅当对某个固定的 `@@M@@d@@`、一切 `@@M@@j@@` 和无穷多个 `@@M@@n@@`，存在保留单位 `@@M@@r@@` 使 `@@M@@r-4^{-n}\le\lambda<r@@`。这是无穷的单侧逼近条件，而非有限的成员判定算法；把 `@@M@@\limsup@@` 换成 `@@M@@\liminf@@` 结论不变。**四次 Salem 定理（定理 5.1）**：任何四次 Salem 数 `@@M@@\beta\in(1,2)@@` 都使 `@@M@@\nu_{1/\beta}@@` 奇异；显式特例为 `@@M@@x^4-x^3-x^2-x+1@@` 与 `@@M@@x^4-2x^3+x^2-2x+1@@` 的大于 1 的实根。**31 次多项式定理（定理 6.1）**：多项式 `@@M@@p(t)=t^{31}-2t^{30}+\sum_{j=0}^{9}(t^{3j+1}-t^{3j})@@`（满足 `@@M@@(t^2+t+1)p(t)=t^{33}-t^{32}-t^{31}-t^{30}-1@@`）在 `@@M@@(1.8392,1.8393)@@` 内有唯一实根 `@@M@@\beta@@`；它有一对模长平方约 `@@M@@1.000209@@` 的共轭复根落在单位圆外，故不是 Pisot 数，而 `@@M@@\nu_{1/\beta}@@` 奇异。文中还从判据重新推出 Erdős 的 Pisot 奇异性与 Garsia 参数的绝对连续性两类经典结果。

## 证明思路

判据的一个方向是纯测度论计数：若保留单位满足 `@@M@@r-4^{-n}\le\lambda<r@@`，则其近邻单位的系数前缀 `@@M@@w@@` 都满足 `@@M@@|\sum_{i<n}w_i\lambda^i|\le B\lambda^n@@`（因 `@@M@@4^{-n}=o(\lambda^n)@@`），于是大量词对的前缀和彼此相差 `@@M@@O(\lambda^n)@@`；分箱计数给出 Lebesgue 测度至多 `@@M@@C/j@@` 而 `@@M@@\mu_\lambda@@`-质量至少 `@@M@@1/d@@` 的集合，令 `@@M@@j\to\infty@@` 便与绝对连续性矛盾，再用纯类型定出奇异。核心是反方向的实现引理（realization lemma）。先证 `@@M@@\lambda>1/2@@` 时首比特的两个条件测度必有公共非零子测度（熵论证：只有 `@@M@@O(\lambda^{-n})@@` 个量化格子，装不下前 `@@M@@n@@` 个比特的 `@@M@@n\log 2@@` 熵）；再由紧集中引理（compact concentration）把奇异性转化为至少 `@@M@@c2^n@@` 个首比特为 0 的词，每个各有 `@@M@@Q(2\lambda)^n@@` 个首比特为 1 的近邻。对其差向量 `@@M@@w@@`（`@@M@@w_0=-1@@`）分三步补全成合格多项式：先贪心逐位添系数（类似 `@@M@@\beta@@`-展开）把多项式在 `@@M@@\lambda@@` 处的残差指数级压小；再用紧性引理——有界系数多项式在 `@@M@@\lambda@@` 右侧不能处处太平，否则极限幂级数在 `@@M@@\lambda@@` 处各阶导数全为零，违背恒等定理——找到符号翻转点；最后用 `@@M@@\mathbb F_2@@` 上算术进度中的素多项式定理（函数域 Riemann 猜想的特征和推论），在保留前 `@@M@@n@@` 位系数的同时加上不可约性，对两个在 `@@M@@\lambda@@` 处异号的补全式用介值定理取出根 `@@M@@r\in(\lambda,\lambda+4^{-n}/2]@@`，它正是首 `@@M@@n@@` 位系数等于 `@@M@@w@@` 的代数单位。四次 Salem 定理绕开"Fourier 必衰减"的障碍：以 `@@M@@A_m=\prod_h(\beta^{k_h}-\beta^{-k_h})@@` 为频率乘子，用鸽笼原理选 `@@M@@k_h@@`，使 `@@M@@L_m=\log(1/\delta_m)@@`（`@@M@@\delta_m@@` 是单位圆共轭损耗）每步至少增至 `@@M@@2.1@@` 倍，快于余弦损失总和的 `@@M@@2.0301@@` 倍增速，故总损失 `@@M@@S_m=o(L_m)@@`；迹恒等式把高频相位替换为整数加有限窗口内独立符号的相位，其带符号平均 `@@M@@F_m@@` 在 `@@M@@\nu_{1/\beta}@@` 下集中（均值不低于 `@@M@@e^{-L_m/20}@@`），在 Lebesgue `@@M@@L^2@@` 下却因频率间隔至少 `@@M@@\pi(\beta-1)@@` 而趋于零；两者相减并用切比雪夫不等式取 `@@M@@\limsup@@` 子列，即得满 `@@M@@\nu@@`-测度的 Lebesgue 零测集。31 次多项式则依靠精细计数：词向量落入固定格点，箱子体积按 `@@M@@\mathcal M^N@@`（`@@M@@\log\mathcal M-\log\beta<0.0002094@@`）增长，比 `@@M@@\beta^N@@` 略多；作者构造一族正的三角因子之积，其在展开坐标下的 Lebesgue 积分一致有界（由近三次关系 `@@M@@\beta^3-\beta^2-\beta-1=\beta^{-30}@@` 驱动的有限自动机排除近平消的频率模式），却在概率趋于 1 的典型词上以超过 `@@M@@0.000220N@@` 的速率指数增长；超额增益恰好吃掉格点的超额体积，最终覆盖的 Lebesgue 测度按 `@@M@@e^{-0.0000066N}@@` 衰减而概率趋于 1，奇异性立得。

## 可信度与备注

本文主结果尚无 Lean 形式化证明，请以社区核验为准；按 OpenAI 官方声明，未经形式化的结果可能有问题。结果族 153 仅含这一篇手稿，但论文内部互相支撑：判据能原样复现 Erdős 的 Pisot 奇异性与 Garsia 的绝对连续性（文中第 4 节专门验证），两个非 Pisot 定理均独立直接证明，再由判据转译为对应的逼近性质。31 次多项式例的根隔离与矩不等式依赖附录中的有理数计算证书，该部分技术性较强，此处从略。

{% endraw %}
