---
layout: default
title: "Strong diffeomorphic approximation in three dimensions for p>2"
family: "368"
discipline: "Partial differential equations"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Strong diffeomorphic approximation in three dimensions for p>2

> 结果族 368：The three-dimensional Ball–Evans approximation problem　·　学科：Partial differential equations　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明了三维 Ball–Evans 逼近问题余下的区间 \(p>2\)：任意有界区域之间的 \(W^{1,p}\) 同胚都可被映满同一目标域的光滑微分同胚在 \(W^{1,p}\) 中强逼近；与处理 \(1\le p\le2\) 的姊妹篇合起来，三维问题宣告完整解决。

## 问题背景

固定目标的 Ball–Evans 逼近问题源自非线性弹性：单射表达物质不可穿透，弱导数刻画局部形变，问题由 Evans 提出、Ball 系统阐述。二维情形已由 Iwaniec–Kovalev–Onninen 与 Hencl–Pratelli 解决；\(n\ge4\) 存在 Campbell–Hencl–Tengvall 的行列式变号反例，三维遂成最后的空档。\(p>2\) 带来额外分析结构（球面 Sobolev 嵌入、几乎处处 Fréchet 可微），但也有独特困难：秩一、秩二点集的像虽是零测集，它在源域上携带的 \(\int|Df|^p\) 能量未必小，当例外集丢弃就会丢掉逼近定理本身，必须正面保留并复原其梯度。

## 主要结果

主定理：设 \(\Omega,\Lambda\subset\R^3\) 为有界域，\(2<p<\infty\)，\(f:\Omega\to\Lambda\) 为 \(W^{1,p}\) 同胚，则存在 \(C^\infty\) 微分同胚 (diffeomorphism) \(f_j:\Omega\to\Lambda\)，每个都属于 \(W^{1,p}\)，使

\[\int_\Omega\bigl(|f_j-f|^p+|Df_j-Df|^p\bigr)\,dx\longrightarrow0 .\]

同样不假设边界正则性、逆映射的 Sobolev 正则性或 Jacobi 非零；每个逼近映满固定目标 \(\Lambda\)。

## 证明思路

总体仍是"先造局部双 Lipschitz 同胚、再光滑化"，而全文的关键区分是：只有两个"保留标量参数"的导数进入主能量估计，填补其余腔室的同胚导数不进入。第一步是准备与压平：正则点引理用 \(p>2\) 的球面 Sobolev 嵌入与映射的开性，证明几乎每点处 \(f\) Fréchet 可微且均值守恒、秩亏点的像零测，\(p\ge3\) 时还满足体积 Lusin 性质 (Lusin property) \(N\)。再借助 Alberti–Marchese 的可分解丛 (decomposability bundle) 与 De Philippis–Rindler 的 Rademacher 逆定理，在输送测度中找到横截方向；经 Alberti–Csörnyei–Preiss 式图零集与"薄带"论证，把保留的秩一、秩二数据用一个接近恒等的 Lipschitz 目标自映射压平到彼此分离的平坦"板"上，切向导数仅扰动 \(C\lambda\) 倍。随后构造"载体 (carrier)" \(F_b\)：一个连续真满射 \(\Omega\to\Lambda\)，在指定目标开集上严格等于仿射或 PL 同胚。植入靠"方体切割"：把二维方体骨架经 Hirsch 浸入定理以公共尺度 \(s\) 浸入，提升 \(i(H)=h\circ i\) 中两个尺度因子相消，得到只差常数倍的能量估计；Schoenflies 定理填补拓扑洞，再塌缩掉不可控的填充，遗留的驯顺球纤维之后可重新打开。

第二步是凸量化器 (quantizer)：构造强凸势 \(\psi=|x|^2/2+b_1+b_2\)，其中 Poisson 扰动 \(b_2\) 使 \(\Delta\psi<0\) 在精确区域之外成立，从而把凸包络的接触点全部逼入精确区域；Legendre 对偶与障碍上包络 \(G\) 给出单值 \(c^{-1}\)-Lipschitz 映射 \(T=(\partial G)^{-1}\)，其三维输入块全部落在载体的精确区域，其余输出集中在一个多面体二维复形（幂图胞腔结构）。每个受保护斜率配有两个接触点 \(q\pm dn\)（双井扰动造出），使保留数据被安放在矩形面上；面上的两个坐标是 \(t=L_D\log r\)（归一化径向分数的对数）与周长弧长 \(s\)，且 \(Dq_0\) 与 \(Df\) 几乎重合。

第三步用"墙"实现这两个坐标：源域环状墙对应径向水平、盘状墙对应周长水平。对角线路由（法曲面理论式换接，参数 \(d=a-u+v\) 沿斜率 \(\pm1\) 的部分等距匹配）消除多余圆交，既不累积导数因子也不损失横向参数长度。一族称为"卫兵 (guards)"的参考纤维路径钉住实现的标签：放错位置的墙会在太多小球上强制固定的正路径代价，该下界随网格尺度趋零而增长——此处本质地用到 \(p>2\)。

第四步是网格与装配：两色墙邻域配备同时乘积坐标；"snapping"坐标替换消除薄中间组态造成的大参数斜率，展宽后直接求导得到近锐标量界。装配时先固定 \(\int G^p\) 型容量再选卫兵与最终网格；在"饱和方体"上，两个标量参数的近锐能量上界、被边界积分钉住的平均梯度，与 Clarkson 型一致凸性不等式 \(c_p|Z-D_0|^p\le|Z|^p-|D_0|^p-p|D_0|^{p-2}D_0:(Z-D_0)\) 相结合，把"能量近乎极小 + 平均梯度正确"升级为强梯度逼近：\(\int|D(P_0Th)-Df|^p\le C_p(\eta+\gamma)(1+E)\) 加可任意小的误差。\(2<p<3\) 时标记例外内部由单独的源压缩处理，\(p\ge3\) 由 Lusin 性质直接消除；保留的满秩方体最后用各自的仿射比较映射修正；再套用与姊妹篇共享的光滑化定理（附录 A），即得映满固定目标的光滑微分同胚逼近。

## 可信度与备注

主结果暂无 Lean 形式化证明。本篇与 \(1\le p\le2\) 姊妹篇互补拼满全部有限指数；两文共享同一光滑化定理（本篇附录 A 完整重证），但构造彼此独立、互不引用对方区间结论。按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。

{% endraw %}
