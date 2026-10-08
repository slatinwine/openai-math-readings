---
layout: default
title: "The Gaussian propeller bound in every dimension"
family: "096"
discipline: "Convex and metric geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Gaussian propeller bound in every dimension

> 结果族 096：The Gaussian propeller conjecture in every dimension　·　学科：Convex and metric geometry　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

往平面上撒一团雾：原点最浓、越远越稀，浓淡按钟形曲线（高斯）分布。现在随你把平面切成有限块——歪的、斜的都行——每块雾的"净漂移矢量"（块内所有位置按浓淡加权加总）先求长度平方，再把各块加起来，最大能到多少？论文证明上界是 `@@M@@9/(8\pi)\approx0.358@@`，而且最优切法就是三片张角 120° 的"螺旋桨"扇叶。

**关键词卡片**

- 高斯测度（Gaussian measure）：按钟形曲线分配质量的概率分布。
- 一阶矩／质心（first moment / centroid）：块内位置按概率加权的总和；注意不除以质量。
- 可测分割（measurable partition）：把空间分成有限个互不重叠的可测块。
- 螺旋桨（propeller）：平面内张角 `@@M@@2\pi/3@@` 的三个扇形拼成的取等构型。

**看个具体例子**

极坐标一算，就能看到 `@@M@@9/(8\pi)@@` 从哪来：半张角 `@@M@@\alpha@@` 的扇形，质心长度恰为 `@@M@@\sin\alpha/\sqrt{2\pi}@@`。取 `@@M@@\alpha=\pi/3@@`：每叶质心长 `@@M@@\frac{\sqrt3/2}{\sqrt{2\pi}}\approx0.345@@`，平方为 `@@M@@\frac{3}{8\pi}@@`；三叶相加：`@@M@@3\cdot\frac{3}{8\pi}=\frac{9}{8\pi}\approx0.358@@`。当维数 `@@M@@d\ge2@@`、胞格数 `@@M@@\ge3@@` 时这已是最优常数；更高维无非把平面扇形再乘一个正交的欧氏因子，胞格数再多也占不到便宜。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <path d="M 278 148 L 373.3 93 A 110 110 0 0 0 182.7 93 Z" fill="#cfe8ff" stroke="#345" stroke-width="1.5"/>
  <path d="M 278 148 L 182.7 93 A 110 110 0 0 0 278 258 Z" fill="#ffe3c1" stroke="#345" stroke-width="1.5"/>
  <path d="M 278 148 L 278 258 A 110 110 0 0 0 373.3 93 Z" fill="#d8f0d0" stroke="#345" stroke-width="1.5"/>
  <circle cx="262" cy="132" r="1.8" fill="#667"/>
  <circle cx="296" cy="140" r="1.8" fill="#667"/>
  <circle cx="272" cy="166" r="1.8" fill="#667"/>
  <circle cx="256" cy="158" r="1.5" fill="#778"/>
  <circle cx="290" cy="160" r="1.5" fill="#778"/>
  <circle cx="246" cy="142" r="1.5" fill="#778"/>
  <circle cx="278" cy="148" r="3" fill="#222"/>
  <line x1="278" y1="148" x2="278" y2="92" stroke="#c00" stroke-width="2.5"/>
  <path d="M 278 88 L 282 98 L 274 98 Z" fill="#c00"/>
  <line x1="278" y1="148" x2="230" y2="176" stroke="#c00" stroke-width="2.5"/>
  <path d="M 226 180 L 232.7 171.5 L 236.7 178.5 Z" fill="#c00"/>
  <line x1="278" y1="148" x2="326" y2="176" stroke="#c00" stroke-width="2.5"/>
  <path d="M 330 180 L 321.3 178.5 L 325.3 171.5 Z" fill="#c00"/>
  <text x="20" y="28" font-size="14" fill="#123">平面撒标准高斯雾（原点最浓）</text>
  <text x="348" y="46" font-size="14" fill="#123">每叶张角 2π/3</text>
  <text x="348" y="68" font-size="14" fill="#123">三叶平方和＝9/(8π)≈0.358</text>
  <text x="20" y="242" font-size="14" fill="#123">红箭头＝该叶质心，长度</text>
  <text x="20" y="264" font-size="14" fill="#123">sin(π/3)/√(2π)≈0.345</text>
</svg>

</div>

**为什么值得关心**

这个常数不只是几何趣味：它决定核聚类近似算法的精确难度阈值——损失因子低于 `@@M@@\frac{8\pi}{9}(1-\frac1k)@@` 的确定性多项式算法是 NP-难的，与已知的舍入保证恰好咬合。证明走反证法，把无限维优化压成有限项数值核对，全部比较有精确有理数区间证书兜底。

> 已 Lean 形式化

## 一句话结论

论文证明了高斯螺旋桨猜想（Gaussian propeller conjecture）：任何有限可测分割的各胞格高斯一阶矩长度平方之和不超过 `@@M@@9/(8\pi)@@`，当 `@@M@@d\ge 2@@`、`@@M@@k\ge 3@@` 时由三个 `@@M@@2\pi/3@@` 平面扇形取等，从而补全所有维度的缺口，并确立核聚类近似的精确难度阈值。

## 问题背景

设 `@@M@@\gamma_n@@` 为 `@@M@@\mathbb R^n@@` 上的标准高斯测度。可测集 `@@M@@A@@` 的高斯一阶矩 `@@M@@z(A)=\int_A x\,d\gamma_n(x)@@` 称为质心（centroid），注意它不除以测度。对可测分割 `@@M@@\mathcal A=(A_1,\dots,A_k)@@`，问 `@@M@@\mathcal F(\mathcal A)=\sum_i\|z(A_i)\|^2@@` 最大能到多少。该问题源于 Khot 与 Naor 对近似核聚类（kernel clustering）的研究：这个泛函的最优值直接决定近似算法的损失因子与 Unique Games 硬性。他们证明极值分割可取质心张成空间中的锥分割（conical partition），并确定了三胞格时的值；Heilman、Jagannath、Naor 又以计算机辅助的球面几何方法证得 `@@M@@\mathbb R^3@@` 情形。悬而未决之处在于：这是一个无限维优化，胞格的形状与概率同时自由变化，胞格数也不固定；Heilman 的另一条路线还须附加噪声稳定性（noise stability）假设且限于至多四个胞格。

## 主要结果

主定理：对一切正整数 `@@M@@d,k@@` 与任意可测分割 `@@M@@(A_1,\dots,A_k)@@`，均有 `@@M@@\sum_{i=1}^k\left\|\int_{A_i}x\,d\gamma_d(x)\right\|^2\le 9/(8\pi)@@`，允许空胞格；当 `@@M@@d\ge2,k\ge3@@` 时常数最优，由平面内张角 `@@M@@2\pi/3@@` 的三个扇形——即"螺旋桨"——乘以正交欧氏因子取等。极坐标计算给出张角 `@@M@@2\alpha@@` 的扇形之质心为 `@@M@@\frac{\sin\alpha}{\sqrt{2\pi}}(1,0)@@`，取 `@@M@@\alpha=\pi/3@@` 求和即 `@@M@@3\sin^2(\pi/3)/(2\pi)=9/(8\pi)@@`。

对偶形式给出高斯最大值不等式的推论：`@@M@@\mathbb E\max_i\langle v_i,g\rangle\le\frac{3}{2\sqrt{2\pi}}\bigl(\sum_i\|v_i-\bar v\|^2\bigr)^{1/2}@@`，常数在平面三向量时已最优，于是任意有限中心化联合高斯向量的期望最大值都被同一常数控制。

最后一节是复杂性应用：固定 `@@M@@k\ge3@@`，对有理数、中心化、半正定（positive semidefinite）输入的恒等目标（identity-target）核聚类问题，结合 Khot–Naor 的低影响定理与姊妹篇《The Unique Games Theorem》，任何损失因子（loss factor）严格小于 `@@M@@\alpha_k=\frac{8\pi}{9}(1-\frac1k)@@` 的确定性多项式近似算法都是 NP-难的，与已知的高斯舍入保证恰好匹配。

## 证明思路

全篇采用反证法。先归约：高斯乘积分解与补充空胞格把问题化为 `@@M@@n\ge4@@` 维、`@@M@@n+1@@` 个胞格的情形；范数对偶把最优值的平方根等同于总平方范数为 1 的得分列表之期望最大得分（Khot–Naor 引理 3.7 的向量形式），球面紧性保证极值分割存在。再取活跃胞格数最少的极值分割：合并两胞格使目标改变 `@@M@@2\langle z_i,z_j\rangle@@`，最优性与极小性迫使质心两两内积严格为负，且每个胞格几乎处处就是对应得分 `@@M@@\langle z_i,x\rangle@@` 最大的锥 `@@M@@K_i@@`，质心张成 `@@M@@m-1@@` 维空间。若 `@@M@@m\le4@@`，维数落入 Heilman–Jagannath–Naor 三维定理的射程，故反例必有 `@@M@@m\ge5@@`。

再立标量约束。令 `@@M@@r_i=\|z_i\|/\sqrt C@@`、`@@M@@P_i@@` 为胞格概率，则 `@@M@@\sum r_i^2=\sum P_i=1@@`。重排（rearrangement）论证——同测度集合中以半空间最大化方向矩，`@@M@@m=5@@` 时改用四维球面重排——给出二次下界 `@@M@@P_i\ge Ar_i^2@@`（`@@M@@A=0.929@@` 或 `@@M@@0.884@@`）。另一条界来自删去一个得分、把其余得分重新居中：极值对偶不等式给出期望最大值损失的下界，而 Ehrhard 高斯 Minkowski 不等式使锥的平移测度经 `@@M@@\Phi^{-1}@@` 后成为凹函数，给出损失的上界；两界比较，配合辅助函数 `@@M@@G@@` 的单调性并经有限区间有理验证，得线性–二次下界 `@@M@@P_i\ge0.415r_i+0.15r_i^2@@`。

接着做几何竞争。取质心最短的胞格，把其余得分分解为沿该方向的分量与正交残余 `@@M@@Y_j@@`（与该方向得分 `@@M@@T@@` 独立）。此胞格的矩恒等式 `@@M@@\mathbb E[\mathbf 1_KT]=\sqrt C\,t@@`、`@@M@@\mathbb E[\mathbf 1_KY_j]=0@@`，配上二维高斯密度上界（分母含残余协方差行列式平方根 `@@M@@D_{jk}@@`）与三角形区域上的初等积分 `@@M@@(3s)^3/6@@`，导出两两约束 `@@M@@D_{jk}\le\frac3\pi t(1+a_j)(1+a_k)@@`；对三个最大半径求和并利用协方差矩阵行和为零、非对角元为负的结构，化为关于三大半径 `@@M@@L,c@@` 与最小半径 `@@M@@t@@` 的两条不等式。

最后是消元阶段：概率质量预算 `@@M@@\sum_j\delta_j=1-A@@` 与上述诸界不相容——先证 `@@M@@\sqrt c>0.23@@`、`@@M@@t>0.066@@`，再证第四位以后的半径不超过 `@@M@@0.42@@` 并逼出 `@@M@@t<0.12@@`，最终预算迫使 `@@M@@c>2.6t@@`；代入第二条约束得 `@@M@@10(3/\pi)^2t^2\ge1.5(2.6-0.12)^2t^2@@`，而 `@@M@@1.5(2.6-0.12)^2-10(3/\pi)^2>0.106@@`，矛盾。全部有限数值比较由附录中的精确有理数区间证书完成。

## 可信度与备注

按任务文件标注，主结果已有 Lean 形式化证明；论文另将全部有限数值比较的精确有理数区间证书列于附录。几何证明只引用两个外部定理——三维螺旋桨定理与 Ehrhard 不等式——其余估计均为本文自证。核聚类 NP-硬度是独立一节的应用，还需 Khot–Naor 的定理与同族姊妹篇《The Unique Games Theorem》支撑；高斯不等式本身不依赖任何复杂性论证。依 OpenAI 官方声明，未经形式化的结果可能存在问题；本文主结果已形式化，但硬度一节的端点舍入保证按理想化形式引用，未给出有限精度实现。

{% endraw %}
