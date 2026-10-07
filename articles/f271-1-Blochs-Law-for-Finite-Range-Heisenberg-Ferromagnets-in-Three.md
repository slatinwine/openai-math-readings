---
layout: default
title: "Bloch's Law for Finite-Range Heisenberg Ferromagnets in Three Dimensions"
family: "271"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Bloch's Law for Finite-Range Heisenberg Ferromagnets in Three Dimensions

> 结果族 271：Bloch's law, its lattice correction, and the spherical magnetization law　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

严格证明了三维量子海森堡铁磁体在一切固定自旋 \(S\)、一切非负对称有限程耦合下的 Bloch \(T^{3/2}\) 律，低温磁化缺陷的系数由单磁振子色散的二次型行列式精确给出，解决了 Lieb 记录多年的公开问题。

## 问题背景

1930 年 Bloch 从自旋波（spin wave）图像预言：三维铁磁体的自发磁化（spontaneous magnetization）在低温下低于饱和值一个正比于 \(T^{3/2}\) 的量。Holstein 与 Primakoff 的玻色表示和 Dyson 1956 年的经典工作把低温展开系统化，Dyson 还识别出磁振子相互作用的首个贡献在 \(T^4\) 阶，但他对高阶余项的估计并非固定自旋下的严格证明。严格理论随后分岔推进：Mermin–Wagner 定理排除了一、二维有限程模型的正温磁序，红外束缚（infrared bound）证明了经典模型的连续对称破缺，Dyson–Lieb–Simon 建立了一类量子反铁磁体的序；唯独三维量子铁磁体的磁化律长期悬置，被 Lieb 于 1999 年记录为公开问题，近年文献仍如此表述。自由能方向已有 Conlon–Solovej 与 Tóth（自旋 \(\tfrac12\)）的界，以及 Correggi–Giuliani–Seiringer（2015，任意固定自旋、近邻模型自由能主阶）的严格渐近；但零场自由能估计无法控制定义自发磁化的零场单侧场导数——这正是本文要补的缺口。

## 主要结果

设自旋 \(S\in\{\tfrac12,1,\tfrac32,\ldots\}\)，耦合 \(J:\Z^3\to[0,\infty)\) 有限支撑、对称 \(J(z)=J(-z)\)、\(J(0)=0\)，且支撑生成 \(\Z^3\)（允许各向异性，也允许不含常规近邻键）。在立方体 \(\Lambda_N\) 上取自由边界的哈密顿量 \(H^J_{S,N}=-\frac12\sum_{x,y}J(y-x)\boldsymbol S_x\cdot\boldsymbol S_y\)，总磁化 \(M_{S,N}=\sum_xS_x^z\)。压强（pressure）\(p_\beta(h)=\lim_{N\to\infty}\frac1{\beta|\Lambda_N|}\log\Tr e^{-\beta(H^J_{S,N}-hM_{S,N})}\)，自发磁化定义为其零场右导数 \(m_{S,J}(\beta)=\partial_h^+p_\beta(0)\)。由单磁振子色散（one-magnon dispersion）
\[\varepsilon_{S,J}(k)=S\sum_zJ(z)\bigl(1-\cos(k\cdot z)\bigr)=k^{\mathsf T}D_{S,J}k+O(|k|^4)\]
定义正定矩阵 \(D_{S,J}=\frac S2\sum_zJ(z)zz^{\mathsf T}\)。**定理（Bloch 律）**：对每个固定 \(S\) 与每个满足上述条件的 \(J\)，
\[\lim_{\beta\to\infty}\beta^{3/2}\bigl(S-m_{S,J}(\beta)\bigr)=\frac{\zeta(3/2)}{8\pi^{3/2}\sqrt{\det D_{S,J}}}.\]
极限次序是断言的一部分：先热力学极限，再 \(h\downarrow0\)，最后 \(\beta\to\infty\)。近邻耦合 \(J(\pm e_j)=1\) 时 \(D_{S,J}=SI\)，系数还原为熟悉的 \(\zeta(3/2)/(8\pi^{3/2}S^{3/2})\)。

## 证明思路

骨架是 Tóth 的随机交换表示（random interchange）：每个自旋 \(S\) 格点拆成 \(\ell=2S\) 个自旋 \(\tfrac12\) 的"槽"，槽对之间以速率 \(J(z)/2\) 独立泊松交换，周期末端做均匀缝合置换，轨线织成时间圆上的有向循环，配分函数恰为循环着色之和（高自旋由 Nachtergaele 的对称槽实现）。先强制穿过边界及若干指定槽-时间点的循环全部取"上色"（钉扎，pinning），则未钉扎槽的自旋向下概率有精确恒等式 \(d_E(i)=r/(1+r)\)，其中 \(r\) 是从该槽出发的线在撞上钉集前回到自身的概率——磁化问题被化归为随机周期环境中的首回归（first return）问题。再由暴露分解（exposure disintegration）与外幂、行列式恒等式，把条件化的循环规律换成"新鲜游走"（fresh walk）：环境周期重复，游走每次穿越却使用崭新的转移随机性；多点同时钉扎由 Borcea–Brändén–Liggett 的稳定多项式（stable polynomial）负相依理论控制。几何上，先取三条线性无关的相互作用向量生成有限指标子格，在每个陪集上得到一份普通立方格，从而可搬用 Nash 能量方法与单位流（unit flow）做扩散光滑化；再对钉集做向下归纳的稀疏钉扎（sparse-pin）自助论证（bootstrap），不依赖任何有限程排序定理即获得足够的扩散时间。为拿到尖锐系数，让理想游走以速率 \(SJ(z)\) 跳跃，其热核满足 \(p_t^{S,J}(x,x)\sim\kappa t^{-3/2}\)，\(\kappa=(4\pi)^{-3/2}(\det D_{S,J})^{-1/2}\)；把二次首中恒等式在 \(K\) 个周期处截断，已扩散约 \(K\beta\) 时间的质量经流逃逸只需能量 \(C(K\beta)^{-1/2}\)，余项为 \(CK^{-1/2}\beta^{-3/2}\)；在起点周围无钉邻域内比较实际与理想回归，得到双侧夹逼，有限和 \(\kappa\sum_{n\le K}n^{-3/2}\) 便逼近 Bloch 系数 \(\kappa\zeta(3/2)\)。最后把正磁场表示为额外随机钉的混合——任一给定槽被选中的概率至多 \(1-e^{-\beta h}\)，故所需邻域无钉的概率随 \(h\downarrow0\) 趋于 1——先积分有限体积导数界，再依次取 \(N\to\infty\)、\(h\downarrow0\)、\(\beta\to\infty\)、\(K\to\infty\)，上下界同收敛于同一常数。

## 可信度与备注

本文是结果族 271 的首篇，其"钉扎—回归—压强"机制被第二篇（晶格修正）与第三篇（球面磁化律）作为直接输入引用；另有一篇排序伴稿提供稳定交换符号等有限集代数与格几何工具。三篇合力把三维量子铁磁体的低温磁化从"存在性"推进到"精确渐近与完整分布"。按 OpenAI 官方声明，未经形式化（Lean formalization）的结果可能有问题；本文主结果暂无形式化证明，请以社区核验为准。

{% endraw %}
