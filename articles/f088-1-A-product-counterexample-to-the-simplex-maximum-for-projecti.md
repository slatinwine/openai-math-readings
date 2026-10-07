---
layout: default
title: "A product counterexample to the simplex maximum for projection-body volume"
family: "088"
discipline: "Convex and metric geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A product counterexample to the simplex maximum for projection-body volume

> 结果族 088：Sharp projection-body inequalities and a counterexample to simplex maximization　·　学科：Convex and metric geometry（凸几何与度量几何）　·　验证状态：主结果已 Lean 形式化

## 一句话结论

构造出二十维的初等反例：两个十维单形的笛卡尔积 `@@M@@T_{10}\times T_{10}@@` 的规范化投影体体积严格超过二十维单形，推翻 Brannen 1996 年"单形使投影体体积最大"的猜想；且高维中超出的倍数随维数指数增长。

## 问题背景

投影体（projection body）`@@M@@\Pi K@@` 的支撑函数是 `@@M@@K@@` 在各方向超平面上正交投影的 `@@M@@(d-1)@@` 维体积，Petty 确立了其仿射协变性。归一化泛函 `@@M@@R_d(K)=|\Pi K|/|K|^{d-1}@@` 的极值是凸几何经典问题：谁最小、谁最大？该泛函在仿射变换下不变，极值体只能在仿射等价类中寻找，椭球与单形是两类天然候选。极小值一侧，Petty 猜想椭球唯一最小化（同族姊妹篇已在 `@@M@@n\ge4@@` 证明）。极大值一侧，Brannen 于 1996 年猜想单形最大化 `@@M@@R_d@@`；单形的值是 `@@M@@c_d=(d+1)d^d/d!@@`，猜想即 `@@M@@|\Pi K|\le c_d|K|^{d-1}@@`。陈-冯-李-席-徐证明了 `@@M@@d=3@@` 时上界 `@@M@@R_3\le18=c_3@@` 成立（四面体取等）；Feng–Hu–Liu–Xu 随后在每个 `@@M@@d\ge9@@` 用至多 `@@M@@d+2@@` 个面的多胞形给出反例，但构造依赖扰动立方体投影与 Minkowski 存在性定理，也没有精确值。本文给出一个完全初等、可精确计算的构造。

## 主要结果

主定理：取标准单形 `@@M@@T_{10}=\operatorname{conv}(0,e_1,\dots,e_{10})@@`，令 `@@M@@K=T_{10}\times T_{10}\subset\R^{20}@@`，则

`@@M@@D\frac{R_{20}(K)}{c_{20}}=\frac{121\binom{20}{10}}{21\cdot2^{20}}=\frac{22\,355\,476}{22\,020\,096}>1,@@`

整数证书为 `@@M@@121\cdot184\,756-21\cdot1\,048\,576=335\,380>0@@`——严格违反 Brannen 上界。一般地有乘积检验：`@@M@@R_{r+s}(T_r\times T_s)/c_{r+s}=\frac{(r+1)(s+1)}{r+s+1}\binom{r+s}{r}\frac{r^rs^s}{(r+s)^{r+s}}@@`，故 `@@M@@r+s@@` 维的任何普适上常数至少是 `@@M@@c_rc_s@@`。指数超出推论：存在 `@@M@@\lambda>1@@` 与 `@@M@@N\ge20@@`，使每个 `@@M@@n\ge N@@` 都有单形的笛卡尔积 `@@M@@K_n\subset\R^n@@` 满足 `@@M@@R_n(K_n)\ge\lambda^n c_n@@`。最优上常数与最大化体是什么，文中明确留作公开问题。

## 证明思路

证明完全初等，所有恒等式自证，骨架分四步。

先建立面向量公式，即 Cauchy 投影公式（Cauchy's projection formula）的多胞形情形：满维多胞形 `@@M@@P@@` 的每个面 `@@M@@F@@` 贡献一条以原点为中心的线段，长度为面面积 `@@M@@s_F@@` 的一半、方向为外单位法向 `@@M@@\nu_F@@`，即 `@@M@@\Pi P=\sum_F[-s_F\nu_F/2,\,s_F\nu_F/2]@@`——投影体是区段和（zonotope）。证明靠两个观察：面 `@@M@@F@@` 到 `@@M@@u^\perp@@` 的投影的 Jacobian 是 `@@M@@|\langle\nu_F,u\rangle|@@`；除去零测集外，投影中每点恰由沿 `@@M@@u@@` 方向直线的"入射面"与"出射面"两个面的原像覆盖，对重数积分即得。

再证乘积恒等式。`@@M@@A\times B@@` 的暴露面是两因子暴露面的乘积，而当两个泛函都非零时积面余维至少为 2，故 `@@M@@A\times B@@` 的面恰为 `@@M@@F\times B@@` 与 `@@M@@A\times G@@` 两族，其面积-法向量为 `@@M@@(|B|s_F\nu_F,0)@@` 与 `@@M@@(0,|A|s_G\nu_G)@@`。代入面向量公式得 `@@M@@\Pi(A\times B)=(|B|\Pi A)\times(|A|\Pi B)@@`，体积相除即得 `@@M@@R_{r+s}(A\times B)=R_r(A)R_s(B)@@`——归一化投影体积在笛卡尔积下乘法化。

然后精确计算单形值。`@@M@@T_d@@` 的坐标面面积-法向量为 `@@M@@-e_i/(d-1)!@@`，斜面为 `@@M@@w/(d-1)!@@`（`@@M@@w=e_1+\cdots+e_d@@`），故 `@@M@@\Pi T_d@@` 是 `@@M@@([0,1]^d+[0,w])/(d-1)!@@` 的平移。关键一步是对"挤出体"`@@M@@Q+[0,w]@@` 的纤维论证：`@@M@@Q@@` 的每条平行于 `@@M@@w@@` 的纤维是区间，添上线段 `@@M@@[0,w]@@` 后长度恰增 `@@M@@\|w\|@@`，由 Fubini 定理得体积 `@@M@@=1+h_{\Pi Q}(w)=d+1@@`。再由仿射协变性 `@@M@@\Pi(LP)=|\det L|L^{-t}\Pi P@@` 知一切满维单形同取值 `@@M@@c_d@@`。

最后拼装。乘积恒等式给出 `@@M@@R_{20}(T_{10}\times T_{10})=c_{10}^2@@`，与 `@@M@@c_{20}@@` 的比较化为上面的精确整数不等式。指数超出推论把每个 `@@M@@n\ge20@@` 写成 `@@M@@n=10k+d_r@@`（`@@M@@d_r\in\{10,\dots,19\}@@`），取 `@@M@@K_n=T_{10}^{\,k}\times T_{d_r}@@` 得 `@@M@@R_n(K_n)=c_{10}^kc_{d_r}@@`；用级数估计 `@@M@@e<\beta=11/4@@` 给出 `@@M@@c_n<(n+1)\beta^n@@`，而精确算得 `@@M@@c_{10}/\beta^{10}>1@@`，选 `@@M@@\lambda\in(1,(c_{10}/\beta^{10})^{1/10})@@`，对十个剩余类各取阈值即得 `@@M@@\lambda^n@@` 倍超出。关于上常数随维数的增长，Henk 对中心对称体曾给出最优上常数的下界 `@@M@@2^d(9/8)^{\lfloor d/3\rfloor}@@`；本文的乘积迭代则从单形乘积一侧给出指数超出的直接证据。

## 可信度与备注

论文标注主结果已 Lean 形式化。它与同族姊妹篇《Petty's projection-volume conjecture in dimensions at least four》互补：那边证明椭球是 `@@M@@R_n@@` 的唯一最小化元，这边推翻"单形是最大化元"的猜想，一正一反界定了该泛函的极值行为。不同于 Feng–Hu–Liu–Xu 的扰动式构造，本文的乘积构造初等、数值精确，整数证书可直接机器复核。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文主结果已形式化，可信度高。

{% endraw %}
