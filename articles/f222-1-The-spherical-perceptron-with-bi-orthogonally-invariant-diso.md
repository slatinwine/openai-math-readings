---
layout: default
title: "The spherical perceptron with bi-orthogonally invariant disorder"
family: "222"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The spherical perceptron with bi-orthogonally invariant disorder

> 结果族 222：Perceptron free energies and microscopic jamming exponents　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文把球面感知机自由能的严格变分公式推广到双正交不变（bi-orthogonally invariant）、奇异谱紧支撑且无离群值的随机矩阵：极限由 Haar 子空间上的角压强与输入范数在谱块间的最优分配显式给出，谱可为任意紧分布。

## 问题背景

球面感知机问：在球 \(\{x:\|x\|^2=N\}\) 上，线性测量 \((Ax)_r\) 经有界势 \(f\) 加权后的配分函数有多大？Gardner 与 Gardner–Derrida 开创存储体积研究；Shcherbina–Tirozzi 严格证明了非负 margin 硬约束的副本对称体积公式；Györgyi–Reimann 与 Montanari–Zhou 给出有限温度交叠路径变分公式的物理推导；Kabashima 与 Shinzato–Kabashima 研究过带预定奇异谱的相关模式推断模型。但一般势下的严格极限公式此前只对独立高斯模式成立（族内姊妹篇）。推广到固定奇异值加 Haar 奇异基的矩阵有两个障碍：矩阵元素不再独立，个别测量的标量协方差不再决定模型；用高斯张成替代正交子空间会引入改变熵的辅助向量。

## 主要结果

定理：设 \(A_N\) 的分布左右正交不变，经验奇异值分布依概率收敛到紧支撑测度 \(\nu\) 且最大离群距离趋于零，则压强
\[F_N(A,f)=\frac1N\log\int_{\|x\|^2=N}\exp\Big\{\sum_{r=1}^M f\big((Ax)_r\big)\Big\}\,d\sigma_N(x)\]
依概率与均值收敛到确定性值 \(F_{\alpha,\nu}(f)\)，且 \(f=\beta\phi\) 覆盖正逆温度。其值等于谱网格加细的极限
\[\sup_{\substack{\rho_i>0\\ \sum_i\rho_i=1}}\Big\{\frac12\sum_i v_i\log\frac{\rho_i}{v_i}+\alpha P_p^f\big((s_j^2\rho_j/\alpha)_j\big)\Big\},\]
其中 \(v_j=\alpha p_j\) 是各奇异值块占输出的比例（\(\alpha<1\) 时补输入零空间块 \(v_0=1-\alpha\)），\(\rho_i\) 是输入平方范数的块间分配，\(P_p^f(a)\) 是互相正交的 Haar 子空间 \(E_j\) 中半径平方 \(Ma_j\) 球测度下的角压强（angular pressure）。角压强又由带投影见证（witness）的高斯模型显式计算：嵌套 Haar 旗上的单侧距离检验以小正指数 \(\theta\) 积分，\(\theta\) 只在取大维数极限之后才趋于零，再经软罚对偶化为矩阵路径的变分泛函 \(\mathcal G_{\theta,p}\)。

## 证明思路

第一步角化。把 \(Ax\) 按奇异值块分解并条件于每块分到的范数，剩余自由度是各 Haar 子空间中的方向。关键的结构事实是加权壳比较（majorization 引理）：按 \(a_j/p_j\) 排序后，把平方范数向更早的块搬运不会增加极限加权壳体积；证明靠 Haar 子空间的随机细分传递加权体积，即使势把质量集中也成立。这保证单侧投影检验能恢复角压强，而无需势的凹性。

第二步高斯公式。对 Stiefel 列模型（外列为物理向量、内列为见证列），幂配分函数 \(\mathcal Z_{M,\theta}\) 的压强收敛到矩阵路径变分泛函：单模式值 \(V_D(q)\) 是沿矩阵协方差路径 \(q\) 的高斯递归，熵 \(S_\theta(q)\) 带敏感性/精度（susceptibility/precision）行列式，并在共享水平 \(\theta\) 处发生活动空间的维数切换。上界实现 Mourrat 富化超解接触点方法，插值参数是模式数与矩阵协方差增量；经标量化核与标签交叠的联合 Ghirlanda–Guerra 恒等式、Dovbysh–Sudakov 表示与 Panchenko 超度量性，以及消去反对称部分的齐次抽头论证，得到 Loewner 序下非降、在 \(\theta\) 处钉住共享坐标的矩阵分位路径。熵的可达性由一个典范对偶引理给出：最优高斯乘子的倾斜协方差恰为变分最小子，核心是跨冻结水平成立的逆恒等式（Schur 补计算）。

第三步下界与同步。恢复两个独立模式以识别作用在新坐标上的场协方差；高斯计算预言新坐标的交叠路径，空间旋转不变性预言原系统的交叠路径，在厚壳上比较两条分布律迫使二者一致（向量自旋同步，synchronization），从而识别熵并完成下界。

最后取径向与谱极限，把有限谱近似推进到一般紧谱；附录放宽到任意维数序列，并在附加假设下处理连续次二次与有界 Borel 势。

## 可信度与备注

按任务标注，本文主结果未形式化，请以社区核验为准。文中说明与族内标量球面论文共享方法机架但"不引用其任何定理"，两篇互为独立印证；定理需要紧谱、无离群值与有界连续势，附录解释了这些条件为何不可省。OpenAI 官方声明"未经形式化的结果可能有问题"，宜以批判眼光复核。

{% endraw %}
