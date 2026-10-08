---
layout: default
title: "An Upper Bound of 9/4 for the Matrix Multiplication Exponent"
family: "107"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | An Upper Bound of 9/4 for the Matrix Multiplication Exponent

> 结果族 107：Matrix multiplication with exponent at most 9/4　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

两个 `@@M@@n\times n@@` 矩阵相乘，课本方法老老实实做 `@@M@@n^3@@` 次乘法；1969 年 Strassen 发现 2×2 的小矩阵可以偷一次懒，从此全人类开始挤这个指数，五十年只从 3 挤到 2.37 附近。这篇论文干脆换赛道，丢下统治领域三十年的旧框架，一口气把纪录砍到 2.25。

**关键词卡片**

- 矩阵乘法指数 ω（matrix multiplication exponent）：让 `@@M@@n\times n@@` 乘法只需 `@@M@@O(n^{\omega+\varepsilon})@@` 的最小 `@@M@@\omega@@`；已知 `@@M@@2\le\omega\le3@@`
- 张量（tensor）：三元多项式形式的"广义矩阵"；矩阵乘法本身就是一张张量
- 张量秩（tensor rank）：把张量拆成纯三乘积的最少份数，秩小就是乘法次数少
- 渐近谱理论（asymptotic spectrum）：Strassen 发明的不变量工具，像体温计一样给秩下界打分
- 退化（degeneration）：对张量三条腿做带参数的线性代换，实现"批发价"式的比较

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="280" y="30" text-anchor="middle" font-size="14">矩阵乘法指数 ω 的下降阶梯（示意）</text>
<rect x="50" y="58" width="86" height="8" fill="#345"/>
<text x="93" y="48" text-anchor="middle" font-size="12">3.0｜课本竖式</text>
<line x1="136" y1="62" x2="152" y2="98" stroke="#999" stroke-width="2"/>
<rect x="152" y="96" width="86" height="8" fill="#345"/>
<text x="195" y="134" text-anchor="middle" font-size="12">2.807｜Strassen 1969</text>
<line x1="238" y1="100" x2="254" y2="136" stroke="#999" stroke-width="2"/>
<rect x="254" y="134" width="86" height="8" fill="#345"/>
<text x="297" y="120" text-anchor="middle" font-size="12">2.376｜CW 1990</text>
<line x1="340" y1="138" x2="356" y2="174" stroke="#999" stroke-width="2"/>
<rect x="356" y="172" width="86" height="8" fill="#345"/>
<text x="399" y="204" text-anchor="middle" font-size="12">2.371｜2026 前纪录</text>
<line x1="442" y1="176" x2="458" y2="212" stroke="#c33" stroke-width="3"/>
<rect x="458" y="210" width="86" height="8" fill="#c33"/>
<text x="501" y="198" text-anchor="middle" font-size="13" fill="#c33" font-weight="bold">2.25｜本文</text>
<line x1="40" y1="248" x2="524" y2="248" stroke="#567" stroke-width="1.5" stroke-dasharray="6,5"/>
<polygon points="532,248 520,242 520,254" fill="#567"/>
<text x="280" y="268" text-anchor="middle" font-size="12" fill="#567">理论下界：ω ≥ 2（输出本身就有 n² 个数）</text>
</svg>

</div>

先看节省是怎么发生的：按定义算 `@@M@@2\times2@@` 乘法要 8 次乘法，Strassen 精简到 7 次；把大矩阵层层二分、反复套用，指数便从 3 落到 `@@M@@\log_2 7\approx2.807@@`。渐近账单：`@@M@@n=2^{100}@@`（约 `@@M@@10^{30}@@` 规模）时，`@@M@@n^{2.25}@@` 与 `@@M@@n^{2.371}@@` 相差约 `@@M@@10^{12}@@` 倍。已知下界只有 `@@M@@\omega\ge2@@`，2.25 离地板尚有距离，但已是无先例的一跃。

**为什么值得关心**

`@@M@@\omega@@` 同时给行列式、矩阵求逆、解方程组等基本线性代数运算定价。而且这不是修修补补：旧框架三十年的精化已趋饱和，新赛道重新开出一整片可耕耘的地，单次降幅就超过 0.12。

> 已 Lean 形式化

## 一句话结论
本文证明复数域上矩阵乘法指数满足 `@@M@@\omega\le 9/4=2.25@@`：对任意 `@@M@@\varepsilon>0@@`，两个 `@@M@@n\times n@@` 复矩阵只需 `@@M@@O_\varepsilon(n^{9/4+\varepsilon})@@` 次算术运算即可相乘。这比此前 2.371177 的世界纪录下降逾 0.12，而且完全绕开了统治该领域三十余年的 Coppersmith–Winograd 框架，是路线级的突破。

## 问题背景
两个 `@@M@@n\times n@@` 矩阵相乘，朴素算法需 `@@M@@n^3@@` 次乘法；矩阵乘法指数 `@@M@@\omega@@` 是使 `@@M@@O(n^{\tau+\varepsilon})@@` 次算术运算可行的最小 `@@M@@\tau@@`，它同时决定行列式、矩阵求逆等基本线性代数运算的复杂度。Strassen 于 1969 年用 `@@M@@2\times2@@` 矩阵的七次乘法算法证明 `@@M@@\omega\le\log_2 7\approx2.81@@`；此后 Bini 的近似—精确转换、Schönhage 的渐近和不等式与 Strassen 的激光方法确立了张量框架，Coppersmith 与 Winograd 在 1990 年结合 CW 张量与无等差数列集合把纪录推进到 2.375477。近十余年，Stothers、Vassilevska Williams、Le Gall、Alman–Vassilevska Williams、Duan–Wu–Zhou 等在同一框架内层层精化，Dupont 等人于 2026 年用大规模优化得到 2.371177。这条路线的改进已趋饱和，且被怀疑存在内在壁垒。本文彻底更换赛道：回到 Strassen 的渐近谱理论，转而分析多项式乘法张量，一举把指数压到 2.25。

## 主要结果
主定理：对每个 `@@M@@\varepsilon>0@@`，两个 `@@M@@n\times n@@` 复矩阵可用 `@@M@@O_\varepsilon(n^{9/4+\varepsilon})@@` 次标量算术运算相乘；特别地 `@@M@@\omega\le 9/4@@`。作者说明这是渐近算术复杂度意义下的结果，证明不指定有竞争力的有限矩阵规模；另由秩分解方程组具有有理系数及 Nullstellensatz，算法系数可取在 `@@M@@\overline{\mathbb Q}@@` 的一个数域中。

## 证明思路
证明的主轴是把指数问题转化为对一族数值不变量的一致估计。张量视为三线性型（trilinear form），其三组变量称为腿；限制（restriction）在每条腿上独立做线性代换，张量秩 `@@M@@\mathrm R(A)@@` 是满足 `@@M@@m\ge A@@` 的最小整数。记精确秩指数 `@@M@@\nu=\inf_n\log_n\mathrm R(T_n)@@`。Strassen 渐近谱理论中的张量特征（tensor character）`@@M@@\lambda@@` 是在直和下可加、张量积下可乘、限制下单调且 `@@M@@\lambda(1)=1@@` 的数值泛函。关键的探测引理（detecting characters，附录用有限维分离、紧性与 Schauder–Tychonoff 不动点定理证明）指出：只要 `@@M@@k<d^\nu@@`，就存在特征使 `@@M@@\lambda(T_d)\ge k@@`。于是只需证明每个特征都满足 `@@M@@\lambda(T_d)\le d^{9/4}@@`。

先看特征的取值如何参数化。对点积张量 `@@M@@B_X(m)@@`，乘法性论证给出幂律 `@@M@@\lambda(B_X(m))=m^{p_X}@@`；三个取向的点积之积同构于 `@@M@@T_m@@`，故 `@@M@@\lambda(T_m)=m^{3t}@@`，其中 `@@M@@t=(p_X+p_Y+p_Z)/3>0@@`。目标于是等价于证明 `@@M@@t\le 3/4@@`。

核心是分离引理。设张量由 `@@M@@M@@` 个块求和而成，各块共享 `@@M@@X@@` 腿，而 `@@M@@Y@@`、`@@M@@Z@@` 扇区两两配对且互不相交。取 `@@M@@L=5M@@` 份拷贝，以 `@@M@@L@@` 次单位根做 Fourier 线性代换，使存活项满足 `@@M@@u-v+2(g-h)=0@@`；再给变量赋权 `@@M@@g^2@@`、`@@M@@hu-h^2@@`、`@@M@@-hv@@`，则存活项的总权恰为 `@@M@@(g-h)^2\ge0@@`。退化取权零部分后只有 `@@M@@g=h@@` 的正确标签存活，得到完整直和 `@@M@@\bigoplus_h(A_h\otimes B_X(M))@@`——每块还附带一个 `@@M@@M@@` 维点积。配合固定频率计数与 Stirling 公式，得熵不等式 `@@M@@\lambda(T)\ge e^{p_XH(q)}\prod_i\lambda(T_i)^{q_i}@@`。这里难点在于"共享变量的块无法直接直和"，Fourier 投影与平方失配权重的组合恰好把共享腿撕开，而输出块数在指数尺度上补偿了拷贝代价。

接着把熵不等式用于多项式乘法张量 `@@M@@C(a,b)=\sum x_iy_jz_{i+j}@@`，其秩恰为 `@@M@@a+b-1@@`。对六种腿置换取几何平均定义对称化轮廓 `@@M@@P(a,b)@@`，则 `@@M@@P(1,b)=b@@`、`@@M@@P(a,b)\le(a+b-1)^{1/t}@@`。再添两条组合性质：其一用基于一次 Clebsch–Gordan 正合列的行列式滤波（determinant filtration）构造退化，得离散凹性 `@@M@@2P(a,b)\ge P(a,b+1)+P(a,b-1)@@`；其二把指标区间切成左中右三扇区、对中间扇区赋 `@@M@@\pm1@@` 权，得平移三倍式 `@@M@@P(a,3h+a-1)\ge3P(a,h)@@`。

最后是纯离散推理：凹性使相邻增量不增，三倍式迫使归一化对角增量 `@@M@@H_a\ge\prod_{m<a}(1+1/3m)@@`，再用初等不等式 `@@M@@(1+1/3m)^3\ge1+1/m@@` 放大得 `@@M@@P(a,a)\ge a^{4/3}@@`。与上界比较并令 `@@M@@a\to\infty@@` 得 `@@M@@t\le3/4@@`，于是每个特征满足 `@@M@@\lambda(T_d)\le d^{9/4}@@`；由探测引理即 `@@M@@\nu\le9/4@@`。收尾的算术转换是标准的：固定一个维数 `@@M@@u@@` 的精确秩分解做递归，即得 `@@M@@O_\varepsilon(n^{9/4+\varepsilon})@@` 算法。

## 可信度与备注
论文宣称的主结果已有 Lean 形式化证明，可信等级最高。它是结果族 107 的旗舰篇：姊妹篇"低于 2.258 的复矩阵乘法与矩形界"给出特征零域上的 `@@M@@\omega<2.258@@`、`@@M@@\alpha>0.465@@` 及矩形界并做正特征转移，另一篇"错峰抽取"在所有固定域上给出 `@@M@@\omega<2.371055@@`；三者的共同主题都是"以辅助代价换取共享变量的分离"。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本文主定理已形式化，可放心引用，但证明为存在性论证，未给出可实现的算法常数。

{% endraw %}
