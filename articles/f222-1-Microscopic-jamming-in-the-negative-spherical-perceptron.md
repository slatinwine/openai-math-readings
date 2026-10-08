---
layout: default
title: "Microscopic jamming in the negative spherical perceptron"
family: "222"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Microscopic jamming in the negative spherical perceptron

> 结果族 222：Perceptron free energies and microscopic jamming exponents　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

往行李箱里塞衣服，塞到刚刚好、再也塞不进任何一件的那一刻，衣服之间会留下许多极小的缝、产生许多极轻的互相挤压。这篇论文研究的正是高维版"塞满那一刻"（堵塞）：它严格证明了塞满的临界点存在，还算出了那些小缝和小挤压力到底有多"小"——精确到小数点后六位的两个指数。

**关键词卡片**

- 堵塞（jamming）：随机约束系统从"放得下"变为"放不下"的临界现象，像行李箱被塞满。
- 球面感知机（spherical perceptron）：旋钮不限于 ±1、但总长度固定的感知机，代表高维球的堵塞普适类。
- 间隙（gap）：某条约束离"贴上"还差多少，即缝的大小。
- 力（force）：已经贴上的约束之间的挤压强度。
- 等静性（isostaticity）：塞满瞬间接触数恰好等于自由度数，不多不少的"刚好卡住"。

**看个具体例子**

定理的数字版：间隙分布 `@@M@@G_J(u)=u^{1-\gamma}@@`，力分布 `@@M@@F_J(s)=s^{1+\theta}@@`，其中 `@@M@@\gamma\approx0.4126933@@`，`@@M@@\theta\approx0.4231075@@`，且 `@@M@@\gamma=\dfrac{1}{2+\theta}@@`。代入感受一下：把缝的上限 `@@M@@u@@` 缩小 100 倍，缝那么小的概率只降约 15 倍（`@@M@@100^{1-\gamma}\approx15@@`），而不是 100 倍——缝"消失得异常慢"，这正是堵塞的奇异标志。

**为什么值得关心**

物理学家靠数值模拟猜了十年的这两个指数，本文第一次从微观模型出发严格证明，还附上带数学误差界的计算机辅助证书。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

在 margin 为 `@@M@@-1@@`、二次惩罚的球面感知机中，本文严格证明了精确可行性阈值、等静性（isostaticity）与极限间隙/力分布，并定出堵塞指数 `@@M@@\gamma=(2+\theta)^{-1}@@`，`@@M@@0.4126930<\gamma<0.4126934@@`、`@@M@@0.4231063<\theta<0.4231088@@`，附带计算机辅助的有限数值证书。

## 问题背景

堵塞（jamming）把随机约束系统可行性的消失与小间隙、弱力的奇异分布联系起来。Franz–Parisi（2016）指出负 margin 球面感知机代表高维球的堵塞普适类，并预言等静性与间隙、力指数；Charbonneau–Kurchan–Parisi–Urbani–Zamponi（2014）的全副本对称破缺（full replica-symmetry breaking）硬球解给出指数的数值来源；Franz–Parisi–Sevelev–Urbani–Zamponi（2017）从不可满足侧导出零温标度；Parisi–Zamponi（2026）在假定全 RSB 剖面存在且标度展开匹配的前提下解析证明了指数关系。数学上的空白是：此前没有工作从微观模型出发同时证明阈值存在、识别极限间隙与力分布并选定指数——Stojnic 与 Montanari–Zhong–Zhou 只有单侧或仅到首阶的可行性界。

## 主要结果

模型：`@@M@@x\in\mathbb S_N=\{x:\|x\|^2=N\}@@`，`@@M@@A@@` 为 `@@M@@M\times N@@` 随机矩阵，坐标独立、可为标准高斯或方差 `@@M@@1\pm\varepsilon@@` 的等权混合 `@@M@@\nu_\varepsilon@@`；势 `@@M@@V(z)=\frac12(-1-z)_+^2@@`，能量 `@@M@@H_N(x)=\sum_{\mu=1}^M V\big((Ax)_\mu/\sqrt N\big)@@`。`@@M@@H_N\equiv0@@` 即 `@@M@@Ax\ge-\mathbf1@@`：margin `@@M@@-1@@` 的球面存储问题。间隙律 `@@M@@G_J@@` 与归一化力律 `@@M@@F_J@@` 的极限依次取 `@@M@@N\to\infty@@`、逆温度 `@@M@@\beta\to\infty@@`、密度 `@@M@@\alpha\downarrow\alpha_c@@`（自 UNSAT 侧），小截断与零点最后取。

定理：(i) 存在 `@@M@@\alpha_c\in(0,\infty)@@`，可满足概率在固定 `@@M@@\alpha<\alpha_c@@` 下趋于 1、在 `@@M@@\alpha>\alpha_c@@` 下趋于 0；(ii) 上述有序极限全部存在，且对一切足够小的固定 `@@M@@\varepsilon@@` 与坐标律 `@@M@@\nu_\varepsilon@@` 无关；(iii) `@@M@@F_J@@` 是均值 1 概率律的分布函数、零处无原子，且当 `@@M@@u\downarrow0@@`、`@@M@@s\downarrow0@@` 时
`@@M@@DG_J(u)=u^{1-\gamma+o(1)},\qquad F_J(s)=s^{1+\theta+o(1)},\qquad \gamma=\frac1{2+\theta}.@@`
极限间隙律在零处有质量 `@@M@@1/\alpha_c@@` 的接触原子，乘以约束密度恰为每个自由度一个接触，即等静性。

## 证明思路

先建立高斯压强的变分公式：Guerra 插值给上界，Aizenman–Sims–Starr 块空腔（Chen 的球面实现）给下界，行泛函的凹性提供插值符号。再对单行指数加小扰动 `@@M@@d\psi@@`：若上界在 `@@M@@d=0@@` 处对两种符号都触及压强，经验行律被钉死，判别测试族进而识别它。随后用 Lindeberg 光滑函数替换比较高斯与混合坐标，对质量集中在少数坐标的构型补充熵论证，得到混合 universality。可行性方面，在略高密度先证最小能量次指数小，删去固定比例的行并在目标密度处精确修复剩余约束，得到阈值以下的精确可满足性。

第三步过零温与临阈值：引入敏感性剖面 `@@M@@\chi:[0,1)\to(0,1]@@`（布朗时间 `@@M@@t@@` 的函数）与表示残差力的非负布朗鞅（Brownian martingale），在同一个 Wiener 空间上用联合凸性与唯一性论证识别临界剖面；强端点收敛与小截断估计保证接触质量与力的归一化在层层取极限后存活。

最后处理临界奇异性与指数选择。端点机制给出：令 `@@M@@\tau=1-t@@`、`@@M@@w(t)=\int_t^1\chi(v)^{-2}\,dv@@`，间隙与残差力的特征尺度分别是 `@@M@@\sqrt\tau@@` 与 `@@M@@\sqrt{w(t)}@@`，而这两个尺度之下的概率质量都与 `@@M@@\chi(t)@@` 同阶，即 `@@M@@G_J(\sqrt\tau)\asymp\chi(t)@@`、`@@M@@F_J(c_f\sqrt{w(t)})\asymp\chi(t)@@`。于是若 `@@M@@\chi(1-\tau)=\tau^{a+o(1)}@@`，两个累积幂必为 `@@M@@2a@@` 与 `@@M@@2a/(1-2a)@@`。对对数平移端点时间后的所有可能极限解，先用量化壁垒将其困在紧区域内，再用严格压缩（contraction）迫使敏感性斜率取唯一的标量根 `@@M@@a_*@@`：`@@M@@a_*@@` 由定态参考解 `@@M@@M_a@@`（满足 `@@M@@-1\le M_a'\le0@@`、`@@M@@M_a''>0@@` 的二阶方程的唯一解）与算子 `@@M@@\mathcal H_a=-\frac12\frac{d^2}{dz^2}+\frac12(B_a^2+B_a')@@` 的最低特征值方程 `@@M@@\lambda(a)=a@@` 刻画，落在 `@@M@@(0.2936533,0.2936535)@@`。根的括界由有限数值证书加数学误差界验证，最终 `@@M@@\gamma=1-2a_*@@`、`@@M@@\theta=\frac{2a_*}{1-2a_*}-1@@`。

## 可信度与备注

按任务标注本文主结果未形式化；指数区间属计算机辅助证明：解析蕴含与有限证书的误差界在文中分开证明，解析部分（压缩与刚性命题）依赖证书节验证的有限不等式。它与族内两篇自由能论文共享 Guerra 插值与空腔机架，压强公式部分互为支撑。OpenAI 官方声明"未经形式化的结果可能有问题"，数值证书部分尤待独立复算核验。

{% endraw %}
