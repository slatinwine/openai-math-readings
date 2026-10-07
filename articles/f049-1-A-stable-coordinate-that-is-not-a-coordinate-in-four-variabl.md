---
layout: default
title: "A stable coordinate that is not a coordinate in four variables"
family: "049"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A stable coordinate that is not a coordinate in four variables

> 结果族 049：A stable-coordinate counterexample in four variables　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文构造出四变量五次多项式 \(f\)：添加一个独立变量后，\(R[w]\) 的自同构能把 \(f\) 送到 \(x_1\)，而 \(R\) 的自同构不能，从而在四变量情形推翻稳定坐标猜想；\(f\) 的每条纤维都同构于 \(\mathbb A^3\) 但嵌入不可矫正，一并否定环境维数 4 的 Abhyankar–Sathaye 嵌入猜想。

## 问题背景

多项式环 \(k[x_1,\ldots,x_n]\) 中的元素 \(f\) 称为坐标（coordinate），若存在 \(f_2,\ldots,f_n\) 使 \(k[x_1,\ldots,x_n]=k[f,f_2,\ldots,f_n]\)，等价于某个多项式自同构把 \(f\) 送到 \(x_1\)。若 \(f\) 在添加独立变量后成为坐标，则称稳定坐标（stable coordinate）；Shpilrain–Yu（2002）猜想：添加有限个变量后是坐标，则原本就是坐标。低维答案已知为肯定：单变量情形初等，二、三变量由 Shpilrain–Yu 借助 Abhyankar–Moh 嵌入定理、仿射曲面消去与 Kaliman 的定理证明，因此四变量是第一个可能出现反例的维数。几何侧的姊妹问题是 Abhyankar–Sathaye 嵌入猜想：特征零时，若 \(k[x_1,\ldots,x_n]/(g)\) 是多项式环（零超曲面同构于 \(\mathbb A^{n-1}\)），则 \(g\) 是坐标；即 \(\mathbb A^{n-1}\hookrightarrow\mathbb A^n\) 的嵌入总可被环境自同构拉直（rectifiable）。此前的卡点：四变量的 Vénèreau 多项式长期是试验场——Lewis（2013）证明第二个 Vénèreau 多项式是坐标，Blanc–Poloni（2022）对一族相关多项式证明了一稳定性；这说明"稳定化后是坐标"可以显式验证，而"原本不是坐标"一直缺少可行的方法。

## 主要结果

主定理（Theorem 1.1）：在 \(R=\mathbb C[x_1,x_2,x_3,x_4]\) 中令
\[Q=x_2^2-x_4^2+x_1x_3,\qquad f=x_1-2Q\bigl(Q(x_2+x_4)+x_1x_4\bigr).\]
则存在 \(R[w]\)（\(w\) 为新增独立变量）的 \(\mathbb C\)-代数自同构把 \(f\) 映为 \(x_1\)，但不存在 \(R\) 的这种自同构。换言之，\(f\) 是一稳定坐标（one-stable coordinate）而非坐标，给出稳定坐标猜想在四变量的反例。

推论（Corollary 1.2）：对每个 \(\lambda\in\mathbb C\)，超曲面 \(f^{-1}(\lambda)\subset\mathbb A^4\) 同构于 \(\mathbb A^3\)，且其嵌入不可矫正。这否定 Abhyankar–Sathaye 嵌入猜想在环境维数 4 的情形——即使所有纤维同时都是仿射空间，嵌入仍可能拉不直。

## 证明思路

论文交替使用同一四变量多项式环的两种呈现。先把它写成五变量环 \(P=k[p,s,u,F,J]\) 中的超曲面 \(A=P/(H)\)，其中 \(x=s^2-u^2+pF\)，\(H=x^2F-(1+2sx)J-pJ^2-u\)。一个保行列式的 \(2\times2\) 矩阵变换（形如 \(M\mapsto(I_2-2ne^{\mathsf t})M\)，幂零性保证行列式不变）把 \(H\) 变成对某坐标线性，从而 \(A\cong k[p',s',F',J]\)，且 \(p\) 恰变为定理中的 \(f\)。再证稳定化：在局部坐标中取 \(\Delta=-p\,\partial_u\)，逐项验证它是局部幂零导子（locally nilpotent derivation）且 \(\Delta(H)=p\)；于是 \(\exp(w\Delta)\) 是 \(P[w]\) 的多项式自同构，固定 \(p\) 并把 \(H\) 送到 \(H+pw\)；再做一次行列式为 1 的线性替换并平移 \(w'=w+Q_0\)，即可消去一个变量而得 \(P[w]/(H+pw)\cong k[p,s,u,N,w']\)，故 \(p\) 是 \(A[w]\) 的坐标。同样的计算顺带识别出所有纤维：\(\lambda=0\) 时 \(A/(p)\cong k[s,u,N]\)，\(\lambda\ne0\) 时 \(A/(p-\lambda)\cong k[x,y,z]\)，每条纤维都是 \(\mathbb A^3\)。

真正困难的是证明 \(p\) 不是 \(A\) 的坐标。第一步：给 \(P\) 的生成元赋权 \((p,s,u,F,J)\mapsto(-1,0,0,1,1)\)——\(p\) 的权为负，负指标滤过必不可少——商滤过的伴随分次环（associated graded ring）形如 \(G=B[\tau,I/\tau]\subset B[\tau,\tau^{-1}]\)，其中 \(B=k[x,y,z,u]/(xy-z(z+1))\) 是二次曲面环，\(\tau\) 是 \(p\) 的初始形式，\(I=(f_0,g_0)\) 是 \(B\) 中两生成元的显式理想；这是 Kaliman–Zaidenberg 意义下的仿射修正（affine modification）。若 \(p\) 是坐标，对其余坐标变量之一求导给出 \(A\) 上非零局部幂零导子 \(D\)；\(D\) 在滤过上诱导齐次导子 \(D_0\)，再降到 \(B\) 上得到非零局部幂零导子 \(E\)，其核含有 \(I\) 中某个非零元 \(h\)。

第二步把这一障碍搬到线丛上排除。令 \(C=k[a,d,b,c,u]/(ac-bd-1)\)（几何上是 \(\mathrm{SL}_2\) 商去对角环面再乘 \(\mathbb A^1\)），\(\Spec C\to\Spec B\) 是某线丛去掉零截面，且理想 \(I\) 扩到 \(C\) 后变为主理想 \((v)\)，\(v=a^3b+a^2u^2-d^2\)。由"线丛上的加法群作用可线性化"的提升引理（Brion 式论证），\(E\) 的指数作用可提升为与纤维缩放交换的线性作用，微分后得到 \(C\) 上保持纤维权（\(\mathrm{wt}(a,d,b,c,u)=(1,1,-1,-1,0)\)）的局部幂零导子 \(\widetilde E\)；由 \(h=vq\) 与"杀死乘积必杀死每个因子"的引理得 \(\widetilde E(v)=0\)。最后是刚性矛盾：再引入辅助分次 \((0,1,-1,0,1)\)，取 \(\widetilde E\) 的最高齐次分量 \(E'\)（仍是保权的局部幂零导子），条件归结为 \(E'(a^2u^2-d^2)=0\)；平方差分解 \((au-d)(au+d)\) 迫使 \(E'\) 固定 \(a,d,u\)。微分 \(ac-bd=1\) 得 \(E'(b)=aq\)、\(E'(c)=dq\)；在 \(k(a,d,u)\) 上局部化后剩余代数是 \(K[b]\)，局部幂零性迫使 \(q\in K\)，再用两个坐标卡相交得 \(q\in k[a,d,u]\)。但保纤维权要求 \(q\) 的权为 \(-2\)，而 \(k[a,d,u]\) 的生成元权只有 \(1,1,0\)——不可能，矛盾完成证明。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准；按 OpenAI 官方声明，未经形式化的结果可能有问题。正面部分（稳定化自同构、纤维同构于 \(\mathbb A^3\)）全部是显式多项式替换，可独立复核；否定部分是"滤过—线丛提升—刚性"的导子障碍链，论文引言说明定理所需的每个构造与障碍均在文中证明，策略改编自族内关于仿射空间消去问题的姊妹文章（文中引作 Cancellation2026）。同族九月的姊妹篇（零纤维为 \(\mathbb A^3\) 的非坐标多项式）主结果已 Lean 形式化；本文将其加强为"所有纤维都是 \(\mathbb A^3\) 且不可矫正"，并首次给出稳定坐标猜想的反例。

{% endraw %}
