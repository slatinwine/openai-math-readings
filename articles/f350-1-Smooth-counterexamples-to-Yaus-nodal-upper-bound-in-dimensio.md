---
layout: default
title: "Smooth counterexamples to Yau's nodal upper bound in dimensions three and four"
family: "350"
discipline: "Differential geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Smooth counterexamples to Yau's nodal upper bound in dimensions three and four

> 结果族 350：Yau's nodal bounds: surfaces and higher dimensions　·　学科：Differential geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论
论文构造出与三维球面标准度量任意接近的光滑度量，以及 \(S^2\times\mathbb T^2\) 上的光滑度量，使得同一个固定度量下存在精确特征函数序列，其节点测度除以 \(\sqrt\lambda\) 趋于无穷——Yau 节点上界猜想在光滑情形的三、四维被推翻。

## 问题背景
对闭光滑黎曼流形上的实特征函数 \(-\Delta_g u=\lambda u\)，丘成桐 1982 年猜想其节点集（nodal set）\(Z_u\) 的 \((d-1)\) 维测度被 \(c_g\sqrt\lambda\le\mathcal H^{d-1}(Z_u)\le C_g\sqrt\lambda\) 双侧控制。实解析度量情形由 Donnelly–Fefferman 解决；光滑情形下，Hardt–Simon 给出非多项式上界，Logunov 证明了多项式上界（\(d\ge3\)）与锐下界，但多项式与 \(\sqrt\lambda\) 之间的鸿沟一直未被排除。另一条线索是"度量柔性"：Enciso–Peralta-Salas 等能随意指定节点集的拓扑，但没有给出同一固定度量下归一化节点测度无界的例子。本文正是补上这一击。

## 主要结果
定理一：在三维球面 \(\mathbb S^3\) 上，标准度量 \(g_*\) 的任意 \(C^\infty\) 邻域内都存在光滑度量 \(g_\infty\)，以及精确特征函数 \(u_j\) 与 \(\lambda_j\to\infty\)，使得
\[\frac{\mathcal H^2_{g_\infty}(Z_{u_j})}{\sqrt{\lambda_j}}\longrightarrow\infty.\]
定理二：\(S^2\times\mathbb T^2\) 上存在光滑度量实现同样的违反（节点测度为 \(\mathcal H^3\)）。两个定理都不宣称幂律超出，也不与下界矛盾。结合族内曲面正向定理并取乘积，得到精确的维数分界：上界不等式对所有闭光滑流形成立当且仅当 \(d=2\)。

## 证明思路
两个分支共享同一条逻辑链：放大轮廓——构造波——计数符号——精确化——收敛到单个度量。

先放大振幅轮廓（profile）。背景取球面及其显式特征函数 \(w_n=\operatorname{Re}(x_1+ix_2)^n\)（\(\Lambda_n=n(n+2)\)），扰动全部集中在一个坐标方体内、外区保持干净。振幅包络 \(e^{n\phi}\) 的相位 \(\phi\) 需同时满足两个表面冲突的要求：供波构造使用的 Hessian 严格性条件，与任意大的梯度积分 \(\int_\Omega|\nabla\phi|\)（它决定节点面积下界的大小）。核心的"均值梯度放大"命题化解冲突：每轮先用周期微扰把 \(\phi\) 在固定比例的梯度质量上做成"满"（full）的，再在两个横向变量上叠加 \(\mathbb Z^2\) 周期的径向波纹（corrugation），使梯度积分每轮至少乘 \(1+\eta\)，而 \(C^0\) 改动任意小、严格性与临界点结构原样保留。

再用有限复波与随机叠加造出"符号很多"的实拟特征函数。以 \(z=a+ib\) 型初值构造截断到有限阶的复相位 WKB 波（complex-phase WKB）\(Z=\zeta e^{nS}V\)，其相位 Hessian 满足 \(Qz=0\)、\(\Re Q<\operatorname{Hess}\phi-4\kappa g\)，加权残差做到 \(n^{-D}e^{n\phi}\)，并按 \(\Re S-\phi\le n^{-1/2}\mathrm{dist}-c\,\mathrm{dist}^2\) 高斯式局部化。把 \(O(n^3)\) 个中心的波用独立复高斯系数叠加到 \(w_n\) 上：以趋于 1 的概率，实值与一阶导数处处联合非零（多项式下界，指数 \(B=110\)），且符号泛函 \(\mathcal F_n\)（沿长度 \(\epsilon/(nL)\) 的短坐标线段统计两端异号的平均计数）满足期望 \(\ge c_{\rm sign}\,n\int_\Omega L\,dx\)，\(L=(1+|\nabla\phi|^2)^{1/2}\)。要害是常数 \(c_{\rm sign}\) 不依赖轮廓：轮廓先放大、频率后选取，于是存在一个实现同时达到 \(\mathcal F_n(U_n)\ge c_{\rm wave}n\int_\Omega L\,dx\)。而每条异号线段内部必有零点，投影的 Lipschitz 界给出 \(\mathcal F_n(f)\le C_{\rm area}\mathcal H^2(\{f=0\})\)——无需零点集任何正则性。

接着是精确化（exactification）：把拟特征函数变成某个真正黎曼度量的精确特征函数且逐点保留符号。三维分支先用标量传导率 \(b\) 与密度 \(s\) 把方程修正为 \(\Delta_b U+\Lambda sU=0\)（\(b,s=1+O(n^{-P})\)）；因度量的传导率与密度须满足三维行列式恒等式（determinant identity），用除以某个半线性椭圆方程的正解来强制成立，残余缺陷在干净环带内用横截的无迹张量变化修补。四维分支则用线性化为 \(\Delta_h-2\lambda\)（强制）的共形标量修正，辅以与水平集相切的度量变化强制四维恒等式。

最后收敛到单个度量。在干净环带内做保持所选特征函数不变（\(K\nabla u=0\)、\(\operatorname{tr}K=0\)）的无迹扰动，使目标特征值变简单；简单性保证符号得分的严格下界在度量的 \(C^\infty\) 邻域内延续。嵌套的度量邻域逐层保留旧证据、插入新证据，取极限即得单个光滑度量 \(g_\infty\)，其上 \(\mathcal H^2(Z_{u_j})/\sqrt{\lambda_j}\to\infty\)。

## 可信度与备注
本篇主结果已 Lean 形式化。它在结果族 350 中承担"三维、四维反例"一翼：与曲面篇的正面定理合并恰好给出维数分界 \(d=2\)，而族内另一篇五维幂律反例则把违反加强到固定指数级。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇已有形式化证明，可信度较高。

{% endraw %}
