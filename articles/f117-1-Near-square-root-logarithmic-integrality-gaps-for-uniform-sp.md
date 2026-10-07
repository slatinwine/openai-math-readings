---
layout: default
title: "Near-square-root logarithmic integrality gaps for uniform sparsest cut"
family: "117"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Near-square-root logarithmic integrality gaps for uniform sparsest cut

> 结果族 117：Uniform sparsest cut: hardness and semidefinite gaps　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 一句话结论
构造了一列每对顶点需求恰为 \(1\) 的最稀疏割实例，其 Goemans–Linial 半定松弛的积分间隙至少为 \(c\sqrt{\log n}/(\log\log n)^3\)，把均匀需求下的已知下界推进到近乎匹配 Arora–Rao–Vazirani 的 \(O(\sqrt{\log n})\) 上界。

## 问题背景
最稀疏割的松弛与有限度量几何深度相连：Linial–London–Rabinovich 证明 \(\ell_1\) 度量恰为割度量的非负组合，故把度量嵌入 \(\ell_1\) 即可舍入成割；均匀需求下的关键量是非扩张映射保持的平均距离（Rabinovich 的平均失真框架）。一般需求下，Goemans–Linial 猜想（常数积分间隙）已被 Khot–Vishnoi 以及 Heisenberg 群几何系列工作（Lee–Naor、Cheeger–Kleiner、CKN）否定，Naor–Young 给出 \(\Omega(\sqrt{\log n})\)，Chang–Naor–Ren 证明匹配上界。但这些是最坏点对失真，不蕴含均匀需求的结论——CKN 明确指出其有界倍增例子到直线的平均失真是常数，无法产生发散的均匀间隙。均匀需求下此前的最好下界是 Devanur–Khot–Saket–Vishnoi 的 \(\Omega(\log\log n)\)（否定均匀常数间隙猜想）与 Kane–Meka 的 \(\exp(\Omega(\sqrt{\log\log n}))\)；而 ARV 的 \(O(\sqrt{\log n})\) 上界是标杆。本文把指数做到 \(1/2\)。

## 主要结果
记均匀目标 \(\mathrm{OPT}(C)=\min_{\varnothing\ne B\subsetneq[n]}\frac{\sum_{i\in B,j\notin B}c_{ij}}{|B|(n-|B|)}\)，Goemans–Linial 半定松弛 \(\mathrm{GL}(C)\) 为：在所有满足三角不等式、\(\sum_{i<j}d(i,j)=1\) 的负型半度量（negative-type semimetric）\(d(i,j)=|x_i-x_j|^2\) 上最小化 \(\sum_{i<j}c_{ij}d(i,j)\)。主定理：存在绝对常数 \(c>0\) 与顶点数 \(n_j\to\infty\) 的实例 \(C^{(j)}\)（每对不同顶点需求为 \(1\)、容量为非负实数），使得 \(\mathrm{GL}(C^{(j)})>0\) 且 \(\mathrm{OPT}/\mathrm{GL}\ge c\,\frac{\sqrt{\log n_j}}{(\log\log n_j)^3}\)。与 ARV 上界只差 \(\log\log n\) 的一个幂。

## 证明思路
要完成两个任务：先造一个平均距离很大的负型半度量，再迫使每个 \(\ell_1\) 收缩映射（contraction）在相同测度下平均距离很小，最后经割锥对偶（cut-cone duality）转成容量实例。

先建公共参数空间与图卡。固定大整数 \(m\) 与参数立方体 \(U=(-2,2)^m\)；每个图卡 \(s\) 把线性映射 \(\theta\mapsto(\langle u_{s,i},\theta\rangle)_i\) 的各坐标取整到格距 \(\tau\)，得到标签 \(v_s(\theta)=(s,X_s(\theta))\)。方向在收缩映射选定之前固定，并满足同时保证：每个单位方向在至少一半图卡中与全部法向量的投影都小；由此顶点数 \(|V|\le\exp(Cm\log m)\)。

再构造距离。用一个公共的光滑特征映射造 Hilbert 向量，其平方距离逼近 \(c_*\sqrt m\,|\theta-\eta|\) 且带一致加性误差；附加 Fourier 分量使导数剖面与特征向量近似正交，从而控制图卡界面处改变一个取整坐标的代价。但所得平方距离未必满足全部三角不等式，须用 Gaussian 正定核的尺度积分（Schoenberg 原理）修复：局部角度估计不可或缺，否则全局误差会淹没界面处的微小费用。修复后，不同图卡中相同参数的标签距离至多 \(Cr\)（\(r=m^{-8}\)），而 \(T=(-1,1)^m\) 上独立均匀参数的期望第一图卡距离至少 \(cm\)——即"全局距离大、界面代价小"。

再约束收缩映射。对任一收缩 \(F:V\to\ell_1^D\)，各图卡函数经平滑后彼此接近、梯度也接近；界面处的小跳跃把每个标量梯度表为该图卡法向量的组合，系数总预算 \(Cm(\log m)^2\)；在有利图卡中小投影再贡献因子 \(C\sqrt{(\log m)/m}\)；最后用 Maurey–Pisier 高斯旋转法证明方体上与维数无关的一阶矩不等式，得 \(\mathbb E\|F(v_1(\theta))-F(v_1(\eta))\|_1\le C\sqrt m\,(\log m)^{5/2}\)，对目标维 \(D\) 一致。

最后换成精确均匀需求。把第一图卡上的测度用重数逼近，同时给每个顶点保留至少一份拷贝（同顶点拷贝距离为零，故拷贝上的收缩诱导整个 \(V\) 上的收缩，所有图卡的约束都得以保留）；割锥对偶引理由线性规划对偶给出容量：最大化 \(\sum|S|(n-|S|)t_S\)、受 \(\sum t_S\delta_S\le d\) 约束的原始问题的对偶可行容量满足 \(\mathrm{OPT}\ge1\)、\(\mathrm{GL}\le b/a\)。尺寸与间隙换算为 \(\mathrm{gap}\gtrsim\frac{m}{\sqrt m(\log m)^{5/2}}\)、\(\log n\asymp m\log m\)，恰好得到 \(\sqrt{\log n}/(\log\log n)^3\) 中的三次幂。

## 可信度与备注
本文主结果已 Lean 形式化，可信度较高。姊妹篇证明均匀最稀疏割任意固定因子近似的无条件 NP-难度（未形式化），两篇一负一正互相支撑：姊妹篇排除多项式时间常因子算法，本文进一步说明 ARV 型 \(\sqrt{\log n}\) 阶在均匀需求下本质最优（至迭代对数因子），半定规划路线无从侥幸。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文主结果已形式化，风险较低，姊妹篇则仍待社区核验。

{% endraw %}
