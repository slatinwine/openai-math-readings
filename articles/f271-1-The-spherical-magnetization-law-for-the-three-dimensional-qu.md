---
layout: default
title: "The spherical magnetization law for the three-dimensional quantum Heisenberg ferromagnet"
family: "271"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The spherical magnetization law for the three-dimensional quantum Heisenberg ferromagnet

> 结果族 271：Bloch's law, its lattice correction, and the spherical magnetization law　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明三维近邻各向同性量子海森堡铁磁体在固定低温下，对称零场 Gibbs 态的磁化按矩收敛到"方向均匀、长度确定"的球面分布，长度恰为压强零场右导数 \(m\)，且全程无需联合测量不对易观测量。

## 问题背景

各向同性铁磁体在零场下没有优先方向，有限周期体积里的 Gibbs 态因此是旋转不变的——哪怕在存在磁化平衡态的低温区也是如此。有序相的自然图像是：磁化向量长度固定、方向均匀分布；但旋转不变本身推不出这一图像，它同样容许"不同长度的混合"。真正的问题是：对称的有限体积态是否选出单一长度？该长度是否就是无穷小外场选出的磁化？此前的答案都不完整：Ueltschi（2017）在三维循环模型框架下、在关于宏观循环长度服从 Poisson–Dirichlet 律的猜想前提下导出同样的球面变换 \(\sinh(hm)/(hm)\)；Björnberg–Fröhlich–Ueltschi（2020）在完全图（complete graph）量子海森堡模型上证明了球面变换。在最近邻三维格点上、不做任何循环长度分布假设地证明此律，正是本文的贡献。

## 主要结果

在偶数边长 \(L\) 的环面 \(\Lambda_L=(\Z/L\Z)^3\) 上取近邻各向同性哈密顿量 \(H_{S,L}=-\sum_{\{x,y\}}\sum_{a=1}^3S_x^aS_y^a\)，总自旋分量 \(M_L^a=\sum_xS_x^a\)，Gibbs 期望 \(\langle\cdot\rangle_{\beta,L}\)；压强 \(p_{S,\beta}(h)\) 与 \(m_{S,\beta}=p'_{S,\beta}(0+)\) 同前两篇。**定理（球面磁化律，spherical magnetization law）**：对每个固定 \(S\in\{\tfrac12,1,\tfrac32,\ldots\}\) 存在 \(\beta_0(S)\)，使得每个固定 \(\beta\ge\beta_0(S)\) 都有 \(m=m_{S,\beta}>0\)，且对一切 \(t\in\R^3\)
\[\lim_{\substack{L\to\infty\\L\text{ 偶}}}\Bigl\langle\exp\Bigl(\frac1V\sum_{a=1}^3t_aM_L^a\Bigr)\Bigr\rangle_{\beta,L}=\frac1{4\pi}\int_{\mathbb S^2}e^{mt\cdot n}\,d\sigma(n)=\frac{\sinh(m|t|)}{m|t|}.\]
同时二阶矩收敛 \(\lim_{L\to\infty}\frac1{V^2}\sum_{x,y}\langle\boldsymbol S_x\cdot\boldsymbol S_y\rangle_{\beta,L}=m^2\)。陈述只使用自旋分量的自伴线性组合，回避了对不对易可观测量（noncommuting observables）的联合测量；自旋与正温度在整个体积极限中固定不动。

## 证明思路

证明的枢纽是总自旋（total spin）标号 \(J_L\)：哈密顿量与整体 \(SU(2)\) 对易，Gibbs 迹在每个自旋 \(J\) 不可约表示上是标量，故 \(\sum_a\langle(M_L^a)^2\rangle=\E[J_L(J_L+1)]\)，且给定 \(J_L=J\) 时任一方向的分量在 \(-J,\ldots,J\) 上均匀分布。于是只需两端夹逼：上尾 \(\PP(J_L/V>m+\epsilon)\to0\) 由 \(m\) 的场导数定义经指数 Markov 不等式直接得到；下界 \(\liminf\E[J_L(J_L+1)]/V^2\ge m^2\) 是全文主体。两者合起来逼出 \(J_L/V\to m\)（概率收敛），而条件 Laplace 变换是黎曼和，收敛到 \(\frac12\int_{-1}^1e^{m|t|u}du=\sinh(m|t|)/(m|t|)\)，再由一致可积性取期望即得球面积分。下界靠两个新事实。其一（空间比较）：大局部盒子上的磁化平方被整个环面上的磁化平方控制，误差随尺度消失——磁化不能靠更大尺度上的空间振荡自我抵消；其工具是对矩形分划中零和检验函数 \(f\) 的弱指数估计 \(\log\langle e^{\theta_RD_f}\rangle\le C_\beta b_RV\)（\(b_R\asymp R^{-5/2}\)，\(\theta_R=\kappa b_R\log R\)），经交换循环、垂直方向强度 \(b_R\) 的微扰场（它使带湮灭的单粒子核预解式可逆）、稀疏钉扎（sparse pin）控制空穴、零和比较，再经无零点复带（Asano–Ruelle 收缩，属 Lee–Yang 传统）从方差界升级为指数界。其二（长度识别）：每个平移遍历平衡态（translation-ergodic equilibrium state，Lanford–Robinson 变分框架）的磁化向量长度恰为 \(m\)；实现方式是把微扰 Gibbs 算子写成作用在每格 \(2S\) 个自旋 \(\tfrac12\) 槽上的实矩阵随机乘积，证明归一化迹 \(Z(z)\) 在 \(\Re z>0\) 无零点，用共享高斯变量把矩与复制品压强耦合，取 \(\log|Z(z)|\) 的调和极限——长度为 \(a\) 的遍历态对压强切线贡献仿射函数 \(xa-a^2\)，大正 \(x\) 选出支 \(xm-m^2\)，而该支的解析延拓不可能在一切正 \(x\) 处被更短长度的支处处压倒，故不同磁化长度不能共存。\(m\) 的正性则直接来自环面版稀疏钉扎估计。

## 可信度与备注

本文以家族首篇（Bloch 律，提供压强磁化的低温渐近与回归估计）和排序伴稿（\(d\ge3\) 近邻模型的低温泉化平衡态存在性）为输入，自身补上环面空间控制与排除不同磁化长度的压强论证。家族三篇合读：首篇与第二篇给 \(m(\beta)\) 的逐阶渐近，本文证明对称零场态确以单一长度 \(m\)、均匀方向实现磁化，闭合了整个图像。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文主结果暂无 Lean 形式化证明，请以社区核验为准。

{% endraw %}
