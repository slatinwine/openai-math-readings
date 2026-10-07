---
layout: default
title: "Spectral scalar curvature and Urysohn width in dimension three"
family: "336"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Spectral scalar curvature and Urysohn width in dimension three

> 结果族 336：Spectral scalar curvature, Urysohn width, and macroscopic dimension　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明三维谱宽度定理：满足 \(-4\Delta+\mathrm{Scal}\ge\lambda>0\)（二次型意义）的任意完备无边三维流形都可连续映到一张图（一维复形），整根纤维直径 \(\le500/\sqrt\lambda\)，且不需要定向、spin、紧性或有界几何假设。

## 问题背景

正标量曲率下界不能约束三维流形的直径——\(\mathbb S^2\times\mathbb R\) 是基本反例——恰当的尺寸度量是 Urysohn \(1\)-宽度（Urysohn width）：允许流形沿一张图延伸，但每点原像必须小，且直径按整根纤维（fiber）计算，含不同连通分支之间的距离。Gromov 在《Four lectures》中用环面稳定化（torus stabilization）框架给出过三维图宽度定理，但限于可定向流形、且允许延拓中带平均凸边界；逐点曲率情形另有 Chodosh–Li 的加权 \(\mu\)-泡泡（\(\mu\)-bubble）切割，以及 Liokumovich–Maximo、Liokumovich–Wang 的 Morse 水平集估计。谱条件 \(-4\Delta+\mathrm{Scal}\ge\lambda\) 允许曲率局部为负，此前没有针对它的直接图宽度结论。难点有二：既不能换度量（纤维必须用原度量度量），又必须控制整根纤维而非各连通分支。

## 主要结果

定理：设 \((M^3,g)\) 连通完备无边，\(\lambda>0\)，且对一切紧支撑光滑 \(\phi\) 有

\[\int_M\bigl(4|\nabla_g\phi|_g^2+\mathrm{Scal}_g\phi^2\bigr)\,\mathrm{dvol}_g\ge\lambda\int_M\phi^2\,\mathrm{dvol}_g，\]

则存在维数至多 \(1\) 的单纯复形 \(K\) 与连续映射 \(f:M\to K\)，使 \(\diam_g f^{-1}(y)\le500/\sqrt\lambda\) 对所有 \(y\in K\) 成立。逐点下界 \(\mathrm{Scal}\ge\lambda\) 是特例；常数 \(500\) 只是方便的选取，未加优化。

## 证明思路

证明是 Schoen–Yau 稳定极小曲面方法的全面加权化。先由 Fischer-Colbrie–Schoen 型地态构造得到正上解 \(v\)，令 \(t=-2\log v\)，则 \(D(g,t)=\mathrm{Scal}+2\Delta t-|dt|^2\ge1\)；密度 \(e^{-t}\) 定义加权面积，而宽度始终用原度量度量。

第一步是加权稳定曲面估计。满足 \(H-\nu t=\mu\) 的稳定曲面的 Jacobi 算子有正第一特征函数，它把环境不等式传递成曲面上的二维不等式 \(D(k,U)\ge c\)（充分条件为 \(D(h,T)+\mu^2-2|d\mu|\ge c>0\)）；再用共形测地指标论证（Schoen–Yau 半径估计的加权版），把任意两点的原度量距离压到 \(2\pi/\sqrt c\)，闭稳定曲面因此只能是球面或射影平面，并有局部"逃逸"版本。

第二步沿极大稳定曲面族切割。用 Zorn 引理取"无有限子族断开 \(M\)"的极大局部有限族，切割后每块 \(P\) 中任何紧致双侧整齐嵌入（neatly embedded）超曲面都分离 \(P\)。证明在定向覆盖上做反称积分电流（integral current）极小化，以 Thom 形检测不分离性，用边界极小叶层的面积不增回缩把正则性延伸过切割边界，最后逃逸估计使检出的曲面自动紧致化，与极大性矛盾。

第三步加倍与 \(\mu\)-泡泡。把 \(P\) 沿边界加倍并相容磨光：加权切片密度的一阶法向导数在缝合处为零（这正由边界的加权极小性保证），反射加卷积磨光保住 \(D\ge1/2\) 且 \(\frac14g\le h\le4g\)；在距离环带内用余切压力 \(\mu=\cot\frac{\pi(\rho-a)}{b-a}\) 极小化加权周长减体积项，压力在带两端发散从而消除相位约束，正则性理论给出有限个分离界面 \(F_i\)，每个直径 \(\le4\pi\)。

第四步板层与图。诸余区域的关联图是树，故存在单一界面把基点与任一距离板层（slab）连通分量隔开；每条极小路径必穿过它且剩余长度 \(<93\)，于是板层分量直径 \(\le2\cdot93+4\pi<220\)。以重数 \(\le2\) 的板层覆盖与从属单位分解把每块映入局部有限图；切割面是球面或射影平面，其有限基本群在图的自由基本群中必平凡，故领域边界映射可零伦收缩，再按 Gromov 的有界界面粘合引理补新边。锚点控制保证整根纤维 \(\le440+2(2\pi+2)<500\)；一般 \(\lambda\) 由度量伸缩换算。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准；按 OpenAI 官方声明，未经形式化的结果可能有问题。它与两篇高维姊妹篇共享"谱到权"的转换（地态构造），但技术路线独立：高维走图方程拉伸加分区定理，本文走加权极小曲面切割——三维恰好使"闭稳定曲面直径有界"成立。三篇合并给出结果族 336 对 \(n\ge3\) 的完整谱宽度叙述。

{% endraw %}
