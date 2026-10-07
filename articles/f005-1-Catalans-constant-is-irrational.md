---
layout: default
title: "Catalan's constant is irrational"
family: "005"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Catalan's constant is irrational

> 结果族 005：Irrationality of Catalan's constant　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文证明卡塔兰常数（Catalan's constant）\(G=\sum_{j\ge0}(-1)^j/(2j+1)^2\) 是无理数（irrational）。做法是对一族 \(48N\) 阶行列式同时给出"素数赋值下界"与"实侧上界"，两条界随 \(N\) 增长必不相容，故 \(G\) 不可能是有理数。

## 问题背景

卡塔兰常数是狄利克雷 beta 函数（Dirichlet beta function）\(\beta(s)=\sum_{j\ge0}(-1)^j/(2j+1)^s\) 在 \(s=2\) 处的值，即模 \(4\) 奇二次特征的 \(L(2,\chi_{-4})\)。奇数点的 beta 值是 \(\pi\) 相应幂的有理倍，偶数点的算术性质却长期未知。Rivoal 与 Zudilin（2003）证明无穷多个偶 beta 值无理、且 \(\beta(2),\ldots,\beta(14)\) 中至少一个无理；Zudilin（2019）、Lai–Zhou（2022）又把范围缩到 \(\beta(2),\ldots,\beta(10)\) 中至少一个，但始终指不出具体是哪个。对单个值，经典阿佩里（Apéry）策略需要整数线性形式 \(A_mG-B_m\to0\)：对 \(G\) 的既有构造（类阿佩里递推、连分数、二重积分，均属 Zudilin 2003）虽有收敛极快的有理逼近，通分后误差却不趋于零——这一"分母代价"障碍正是本文要绕开的困难。另注：Sun（2026）也独立宣布了同一结论，本文未使用其任何结果。

## 主要结果

**定理：\(G\) 是无理数。**

证明骨架是构造 \(n\times n\)（\(n=48N\)）行列式 \(\Delta_N\)：条目由两个初等积分核的矩组成，每个矩可写成"有理部分 \(+\;4G\cdot(\cdots)+\zeta(2)\cdot(\cdots)\)"的组合；行多项式的设计使 \(\zeta(2)\) 项在所有条目中恰好相消，于是**只要假设 \(G\in\mathbb Q\)，\(\Delta_N\) 就是有理数**。对归一化量
\[\mathcal L_N=\frac{\log|\Delta_N|}{(48N)^2}-\tfrac12\log2,\]
论文给出两条不相容的界：其一，在"\(G\) 有理"假设下，素数赋值给出 \(\liminf\mathcal L_N>-2.29084\)（沿 \(\Delta_N\ne0\) 的序列，且可取 \(N\) 为素数）；其二，不依赖任何假设的实侧估计给出 \(\limsup\mathcal L_N\le-2.290939875<-2.2909\)。矛盾，故 \(G\) 无理。引言还指出，结论一节由同一论证推出：恰有两个尖点（cusp）的可定向完备有限体积双曲三维流形（hyperbolic three-manifold）之最小体积无理，以及某些算术双曲体积无理。

## 证明思路

全文逻辑是"先造行列式，再算下界与非零性，最后压上界"。

先看构造与有理化。作者经代换 \(t=2w/(1+w^2)\) 定义行多项式 \(R_r=(1-t)^h t^{C-1}w^{r-g}\) 及其对称化 \(P_r\)、\(D_r\)（皆为切比雪夫多项式 Chebyshev polynomials 的组合），关键是一条"接触"恒等式 \(tP_r/f-D_r=O(t^L)\)。矩 \(M(i,j),Z(i,j)\) 满足递归，边界初值恰为 \(K^-_0=K^+_0=4G\) 与 \(K^+_1=\pi^2/4=\tfrac32\zeta(2)\)——这正是 \(G\) 与 \(\zeta(2)\) 进入条目的通道；接触恒等式使每个条目中 \(\zeta(2)\) 的系数为零，故 \(G\in\mathbb Q\) 蕴含 \(\Delta_N\in\mathbb Q\)。

再算下界。非零有理数的绝对值由其素数赋值（prime valuation）决定，故分母估计给出 \(\log|\Delta_N|\) 的下界。在 \(p=2\) 处，把矩级数 \(2\)-adic 化并将每列拆成三类，用柯西–比内公式（Cauchy–Binet）与超度量不等式得 \(v_2(\Delta_N)\ge-\tfrac{505}{4608}n^2-O_G(n\log n)\)。在奇素数处，"数字约减"引理借二项式系数同余把大矩阵逐层约化：配对列求和把分母 \(p^2\) 降为 \(p\)，对 \(p>H/2\) 再用中心层消去引理清点剩余坏列；对损失函数分段积分并用素数定理（prime number theorem）\(\theta(y)\sim y\) 求和，得总损失 \(\int_0^{65}d(x)\,dx=\tfrac{8609}{2}\)，从而下界 \(>-2.29084\)。但下界只对非零行列式有效：作者取 \(N=p\) 为大素数，用弗罗贝尼乌斯（Frobenius）映射与两组回文多项式基，把矩阵模 \(p\) 约化成 \(I_p\otimes\mathcal B_0+\Pi^T\otimes\mathcal B_1\) 的克罗内克积（Kronecker product）结构，行列式分解为三个 \(48\times48\) 固定有理矩阵 \(\mathcal B_0,\mathcal B_0\pm\mathcal B_1\) 的乘积；后三者的非零性由模 \(101\) 的精确高斯消元主元表证明，于是 \(v_p(\Delta_p)=-96p\ne\infty\)。

最后压上界，这一步不需要任何有理性假设：安德烈夫恒等式（Andréief identity）与柯西双交错行列式（Cauchy double alternant）把 \(\Delta_N\) 写成双行列式积分并分离出范德蒙德（Vandermonde）因子；在坐标 \(x=t/(1+\sqrt{1-t^2})\) 下，行按 \(x<0\)、\(x>0\) 分成两个"叶"。混合求值行列式分两种情形：满足某能量条件时，用哈代空间（Hardy space \(H^2\)）的压缩与有界解析插值函数 \(h_*\)（以形如布拉斯克乘积 Blaschke product 的 \(B(z)=\prod_i\frac{z-x_i}{1-x_iz}\) 配合柯西积分粘合构造）得到 \((1+K_0n)^n\) 型因子，且插值行列式被代数消去，避开了病态的逆范德蒙德估计；条件失效时改用哈达玛不等式（Hadamard's inequality）。随后用切比雪夫展开把对数核写成负二次型，阻尼正则化控制对角与端点后，以显式有理试验系数把二次型换成两个单变量上确界；最终由有理数据证书穷举驻点得 \(\limsup\mathcal L_N\le-2.290939875\)。两条界不相容，\(G\) 无理。

## 可信度与备注

本批任务将本篇标注为 formalized: false，故验证状态为"暂无形式化证明，请以社区核验为准"；族元数据另附一份 Lean 说明文档（lean/docs/005.md），声称其形式化范围即标题断言并列出比较器文件 Catalan.lean，读者可自行核对两者出入。论文内部各环节互相支撑：非零性论证为下界补足"沿素数序列非零"的前提，第 7 节的有理数据证书支撑实侧上界（certificate 与 conclusion 两节不在本次精读范围内，其数值常数取自引言的陈述）。OpenAI 官方声明：未经形式化的结果可能有问题。

{% endraw %}
