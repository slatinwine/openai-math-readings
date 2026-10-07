---
layout: default
title: "Finite angular cylinder covers below the half-area bound"
family: "100"
discipline: "Convex and metric geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Finite angular cylinder covers below the half-area bound

> 结果族 100：Cylinder coverings below the half-area bound　·　学科：Convex and metric geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文为正四面体构造出有限个圆柱组成的覆盖，其垂直底面（均为紧三角形）的总面积严格小于该四面体最小正交投影面积（minimal orthogonal projection area）的一半，从而推翻归于 Bang 的半面积圆柱覆盖猜想，并经仿射不变性否定更强的方向归一化半界猜想。

## 问题背景

这个问题是 Tarski 木板问题（plank problem）的圆柱类比。Bang 在 1951 年证明凸体的有限木板覆盖的总宽度不小于其最小宽度，Ball 又对中心对称体给出按方向归一化的精化。在三维中把木板换成圆柱 \(C=B+\R u\)（底面 \(B\) 位于与轴垂直的平面内），Bezdek 与 Bezdek–Litvak 记录了归于 Bang 的问题：任何有限圆柱覆盖是否总有 \(\sum_i|B_i|\ge\tfrac12 A_{\min}(K)\)？正四面体的两圆柱覆盖（两轴平行于一对对棱）恰好取等，暗示 \(\tfrac12\) 可能是最优常数。Bezdek–Litvak 证明了方向化下界 \(\mathcal R\ge\tfrac13\)（椭球体则 \(\ge1\)），Bezdek–Khan 进一步提出 \(\mathcal R\ge\tfrac12\) 的"1-余维圆柱覆盖猜想"（1-Codimensional Cylinder Covering Conjecture）；Verreault 的 2026 年综述仍把半面积问题列为未决。卡点在于：取等的例子看似刚性，没人知道能否扰动它以压低成本而不留缝隙。

## 主要结果

论文取棱长 \(2\) 的正四面体 \(K\)（顶点 \((\pm1,0,0)\)、\((0,\pm1,H)\)，\(H=\sqrt2\)）。主定理断言：\(A_{\min}(K)=\sqrt2\)，且对每个 \(0<\eps\le1/2000\)，闭四面体 \(K\) 容许由 \(m=2\lceil2/\eps^2\rceil\) 个具紧三角形垂直底的圆柱覆盖，其总面积满足 \(\frac{1}{\sqrt2}\sum_i|B_i|=\frac12-\frac{13}{6000}\eps^2+O(\eps^4)\)（余项绝对值至多 \(2\eps^4\)），故严格小于 \(A_{\min}(K)/2\)。推论：任何非退化四面体 \(T\) 都容许有限覆盖使 \(\sum_i|B_i|/|\pi_{u_i^\perp}T|<\tfrac12\)，即 1-余维圆柱覆盖猜想不成立；其证明是验证方向化比值在可逆仿射映射下不变（分子分母同乘 \(|\det L|\)）。扩展章节还允许径向余量随倾角趋于零，得到规范化成本 \(\tfrac12-\tau^2/240+(25/2)\tau^3+O(\tau^4)\)，覆盖对 \(0<\tau\le1\) 成立，严格节省对 \(0<\tau\le1/4000\) 成立。

## 证明思路

构造从 Bang 的等式覆盖出发：下半段 \(t\le1/2\) 由平行 \(x\) 轴的圆柱覆盖，上半段 \(t\ge1/2\) 由平行 \(y\) 轴的圆柱覆盖，两个底三角形面积各为 \(H/4\)，总成本恰为 \(A_{\min}/2\)。核心想法是把两个三角形底面按斜率参数 \(q\) 细分成 \(n\) 个窄的角度扇区（angular sector），给每个扇区配一条自己的微倾轴线 \((1,\eps\alpha_j,H\eps\beta_j)\)：倾斜使垂直底面乘上小于 \(1\) 的投影因子 \([1+\eps^2(\alpha_j^2+2\beta_j^2)]^{-1/2}\)，从而省面积；但相邻扇区之间、两族之间可能开缝。防缝有两套机制。其一是共享边界匹配：规定边界位移 \(\phi(q)=(1-q^2)/4\)，解端点方程 \(\alpha_j-q\beta_j=\phi(q)\) 得 \(\alpha_j=(1+q_jq_{j+1})/4\)、\(\beta_j=(q_j+q_{j+1})/4\)，使相邻扇区的轴在公共侧边处张成同一平面。角度方向的覆盖用"首次跨越"论证：序列 \(F_i\) 的首尾为 \(-t\le y\le t\)，取第一个 \(F_i\ge y\) 的指标即把 \(y\) 夹住——全程不要求 \(F_i\) 单调。其二是径向预算：在两族交界 \(t\approx1/2\) 处，两个选定截面的径向高度一阶变化恰好相反（\(-\eps xy\) 与 \(+\eps xy\)，正源于 \(\beta_j\simeq q/2\) 的选择），相加后只剩二阶项。于是把每个扇区径向外扩 \(\eps^2M_j\)（\(M_j=\eta+\max d\)，\(d(q)=q^2(1+q^2)/16\)，\(\eta=1/1000\)），再证两个选定圆柱不可能同时失效：否则径向预算恒等式导出 \(0>2\eta-(2+2\eta)\eps-\eps^2/4>0\) 的矛盾，覆盖对闭四面体的每一点（含面、棱、顶点）成立。最后算账：对精确面积公式 \(S/H=\sum_j\Delta T_j^2[1+\eps^2(\alpha_j^2+2\beta_j^2)]^{-1/2}\) 关于 \(z=\eps^2\) 做一致 Taylor 展开（二阶导一致有界 \(59/64\)），再把 Riemann 和换成积分——网格 \(\Delta\le\eps^2\) 保证圆柱数目增长不侵蚀误差，总误差 \(O(\eps^4)\)。积分值 \(\int d=1/15\)、\(\int A=17/30\) 给出 \(S/\sqrt2=\tfrac12+(2\eta-\tfrac1{240})\eps^2+O(\eps^4)\)；代入 \(\eta=1/1000\) 得负系数 \(-13/6000\)，即外扩的面积代价小于倾斜的收益。最小投影面积本身由 Cauchy 投影公式的面积向量形式逐面验证。

## 可信度与备注

本文未形式化，主结果应以社区核验为准。它在结果族 100 中给出最直接、完全自足的显式构造：姊妹篇《Finite cylinder approximation of ruled sets》提供"连续线段族到有限圆柱"的抽象机器，《Slope-field perturbations of the two-cylinder covering》用斜率场给出独立的流场构造；本文零余量极限的二次系数 \(-1/240\) 与后者平方零构造的系数一致，三篇互相印证同一否定结论。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
