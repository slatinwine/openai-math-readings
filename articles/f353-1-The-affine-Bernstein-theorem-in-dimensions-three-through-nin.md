---
layout: default
title: "The affine Bernstein theorem in dimensions three through nine"
family: "353"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The affine Bernstein theorem in dimensions three through nine

> 结果族 353：Affine Bernstein rigidity through dimension nine and a smooth dimension-ten counterexample　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
论文证明当 \(3\le n\le9\) 时，诱导欧氏度量完备的光滑局部一致凸仿射极值图必为椭圆抛物面——定义域必是全空间、函数必是正定二次多项式；仿射完备 (affine-complete) 的经典仿射极大浸入超曲面亦得同样结论。配合姊妹篇的十维反例，范围恰好封闭。

## 问题背景
仿射 Bernstein 问题问：完备的局部一致凸 (locally uniformly convex) 仿射极大超曲面是否必为椭圆抛物面 (elliptic paraboloid)？"完备"在此有两种不等价的含义——图从欧氏空间诱导的度量完备，与仿射 Berwald–Blaschke 度量完备；Trudinger 与 Wang 证明仿射完备蕴含欧氏完备，反之不然。Chern 1979 年提出二维整图问题，Calabi 1982 年在双完备假设下证明二维刚性，Trudinger–Wang 2000 年去掉仿射完备性证得欧氏完备的二维定理。他们的高维路线（内估计加截面重标度）本对任意维数有效，唯独缺一块拼图：图与切平面分离的一致严格凸性模 (modulus of strict convexity) 在归一化下保持一致——二维靠凸极限与接触集的细致分析获得，高维一直无人补齐。本篇在不加任何增长或积分条件下补上这一环。

## 主要结果
主定理：设 \(3\le n\le9\)，\(\Omega\subset\R^n\) 非空凸开，\(u\in C^\infty(\Omega)\) 的 Hessian 正定且解仿射极值方程 \(U^{ij}w_{ij}=0\)（\(U^{ij}=\det(D^2u)(D^2u)^{-1}_{ij}\)，\(w=(\det D^2u)^{-(n+1)/(n+2)}\)）。若图关于诱导欧氏度量 \(g_{ij}=\delta_{ij}+u_iu_j\) 完备，则 \(\Omega=\R^n\) 且 \(u(x)=\tfrac12x^{\mathsf T}Ax+b\cdot x+c\)，\(A\) 正定，即标准椭圆抛物面的可逆仿射像。论文明确指出这涵盖整图断言，且不设增长条件、不断言仿射度量完备。推论：\(3\le n\le9\) 时，连通、开（非紧无边界）、仿射完备、经典仿射极大的局部一致凸浸入超曲面也是椭圆抛物面的可逆仿射像。

## 证明思路
证明分三段。先做纯几何：欧氏完备迫使 \(u\) 在有限边界点处趋于 \(+\infty\)，上境图 (epigraph) 的每个"帽子"（切平面以下的截体）都紧。对上境图全体可逆仿射像取局部极限，定义具 \(k\) 个非负方向 \(s_i\ge0\) 的"\(k\)-模型"，其横截纤维 \(K_s\) 紧；取方向数 \(k\) 达最大的模型。若纤维无一致居中 \(-K_s\subset C_*K_s\)，则用 John 椭球 (John's ellipsoid) 归一化一列愈发不对称的纤维，其极限纤维以原点为边界点，再经一次"薄切片"仿射重标度即可造出 \((k+1)\)-模型，与最大性矛盾——故居中必一致。再排除 \(k\ge2\)，此处才真正用到方程：在纤维的支撑函数 (support function) 坐标下，平稳性化为对数坐标中的加权积分恒等式；将两个恒等式按参数 \(\lambda\) 组合后，剩余二次型的 \(2\times2\) 矩阵行列式在 \(\lambda=1\) 时等于 \((n-2)(10-n)/16\)，恰在 \(3\le n\le9\) 上为正（固定 \(\lambda=15/16\) 可行）——这是维度限制唯一进入的地方。强制性给出对数测度 \(\sigma\) 的指数增长不等式；另一面，\((\det D^2g)^{n/(n+2)}\) 的凹性配合平稳性经局部凸扰动比较给出帽子面积的一致正下界，帽子恒等式 (cap identity) 控制逆 Hessian 加权积分，Hessian 子式估计加 Hölder 插值给出每个对数胞腔的一致质量上界，合计只允许多项式增长 \(\sigma(Q_L)\le C(L+1)^k\)。指数与多项式矛盾，故最大方向数 \(k=1\)。最后刚性收尾：\(k=1\) 等价于所有切截面 (tangent section) 有统一平衡 \(-\rho K_a(t)\subset K_a(t)\)，对一切基点与高度一致；沿射线迭代得倍增估计 \(g(\beta r)\le Ag(r)\)，迫使每条射线可无限延伸，故 \(\Omega=\R^n\)。归一化后的截面族共享一个严格凸性模，套用 Trudinger–Wang 对维数不变的内估计 (interior estimates) 得 \(|D^3v_t(0)|\le C_0\)，换回原坐标得 \(|D^3u(0)|\le Ct^{-1/2}\to0\)；基点任意，故 \(D^3u\equiv0\)，\(u\) 是正定二次多项式。

## 可信度与备注
主结果未形式化，请以社区核验为准。强制性行列式 \((n-2)(10-n)/16\) 在 \(n=10\) 恰好归零，与姊妹篇在该维构造的光滑非二次整图精确互补：方法失效的临界点正是反例所在，故"三至九维"在当前框架下不可再加强。按 OpenAI 官方声明，未经形式化的结果可能存在问题。

{% endraw %}
