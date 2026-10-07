---
layout: default
title: "The Gaussian free field limit of the balanced six-vertex model with variance multiplier 1/arcsin(c/2)"
family: "225"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Gaussian free field limit of the balanced six-vertex model with variance multiplier 1/arcsin(c/2)

> 结果族 225：Gaussian free field limits throughout the balanced six-vertex regime　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了方格六顶点模型在权重 `@@M@@a=b=1@@`、`@@M@@0<c\le2@@` 的整个临界区间内，其高度场在平衡环面极限定义的平面态下收敛到高斯自由场的常数倍，乘子平方恰为 `@@M@@1/\arcsin(c/2)@@`，首次把精确的 GFF 标度极限推广到全区间并覆盖端点 `@@M@@c=2@@`。

## 问题背景

六顶点模型（six-vertex model）在方格每条边上放一个箭头，并施加冰规则（ice rule）：每个顶点恰有两条箭头进入、两条离开。两条水平箭头同进或同出的顶点赋权 `@@M@@c@@`，其余四种赋权 `@@M@@1@@`；其高度函数（height function，约定箭头左侧格面比右侧高一）是一张离散随机曲面。Lieb 在 1967 年算出 `@@M@@c=1@@` 的方冰熵，物理上的 Coulomb-gas 方法（Di Francesco–Saleur–Zuber，1987）预言临界高度涨落是高斯自由场（Gaussian free field, GFF）并给出耦合常数。数学方面：自由费米点 `@@M@@c=\sqrt2@@` 可归约为二聚体，由 Kenyon 的保形不变性定理解决；`@@M@@1\le c\le2@@` 已知有对数离域（delocalization）；DKLM（2026）在 `@@M@@\sqrt3\le c\le2@@` 证明了带精确乘子的 GFF 定理，但依赖一条转动不变性输入，而整个 `@@M@@0<c<2@@` 区间的完整 GFF 收敛此前无人证明。本文补齐了这一空白。

## 主要结果

主定理：对每个固定的 `@@M@@c\in(0,2]@@`，先取环面 `@@M@@T_{M,L}@@` 的 `@@M@@M\to\infty@@`、再取偶数 `@@M@@L\to\infty@@` 所得的平衡平面态 `@@M@@\P_c@@` 存在（此前未处理区间上的存在性本身就是定理的一部分）。记 `@@M@@\Delta=1-c^2/2@@`，`@@M@@\sigma(c)^2=2/\arccos\Delta=1/\arcsin(c/2)@@`，则当格距 `@@M@@\delta\downarrow0@@` 取遍任意正实数时，重标高度场 `@@M@@h_\delta@@` 收敛于 `@@M@@\sigma(c)\Gamma@@`，其中 `@@M@@\Gamma@@` 是以 Green 核 `@@M@@-(2\pi)^{-1}\log|x-y|@@` 归一化的平面 GFF（模常数）。收敛在三重意义下成立：（1）对任意有限组总质量为零、有限能量（finite energy）的紧支撑符号测度，`@@M@@\langle h_\delta,\mu_j\rangle@@` 联合收敛到协方差为 `@@M@@\sigma(c)^2\mathcal E(\mu_i,\mu_j)@@` 的中心高斯向量；（2）在任意有界开集上的负正则 Besov/Sobolev 空间（模常数）中依律收敛且一致紧，不要求开集边界任何正则性；（3）相异点处高度增量的乘积收敛到由 Wick 配对给出的极限公式，且在任何紧集上一致。

## 证明思路

证明分四步走。先做有限行代数：把行转移矩阵写成带辅助标记的单阵（monodromy），用 Yang–Baxter/RTT 交换关系与代数 Bethe 拟设（algebraic Bethe ansatz）构造 Bethe 向量，再借助 Gaudin–Korepin 范数行列式与 Slavnov 标量积公式（三角与对角扭曲形式），把任何固定的"标记行词"的真空期望精确展开为行列式之和，且行列式尺寸只随词长增长、与链长无关——这是热力学极限能被一致控制的钥匙。其次做热力学极限：对 Bethe 根的尾部与 Gaudin 逆给一致估计（根尾控制加边缘最大值原理），证明角参数彼此远离的词解相关，从而得到带交换角行族的极限希尔伯特空间；其联合谱值是内函数（inner function），标记行扮演流（current）算子，谱在伸缩轨道上的质量 `@@M@@\kappa@@` 恰是对数高度协方差的系数。第三步证高斯性：把谱零点按 `@@M@@\delta@@` 与 `@@M@@1/\delta@@` 两个分离尺度拆开，构造全纯与反全纯的手征流 `@@M@@j_\pm@@`；先证其关联函数关于两种轴向排序全纯、在网格奇点处至多二阶增长，再证两个流碰撞时缩合成标量 `@@M@@-\kappa@@`（算子弱极限 `@@M@@K_\epsilon\rightharpoonup-\kappa I@@`），利用极点位置对谱点变量的非全纯依赖抹去"人工极点"，最后由 Liouville 定理导出收缩为 `@@M@@-\kappa/(z-z')^2@@` 的 Wick 递推。第四步定归一化：当 `@@M@@c<1@@` 时，均匀链对缝扭转（seam twist）的二阶微扰恒等式（Kohn 型刚度公式）给出 `@@M@@\kappa@@` 的下界，交错阵列真空态交叠的精确行列式渐近（化为 Toeplitz 符号的显式积分）给出上界，两界恰在 `@@M@@\kappa=1/(2\pi(\pi-\lambda))@@` 会合，即 `@@M@@4\pi\kappa=1/\arcsin(c/2)@@`；当 `@@M@@1\le c<2@@`，在收敛证毕之后引用 DKLM 的条件振幅定理锁定同一乘子。最后用能量–交换子矩估计与小波紧性（Besov 系数刻画）把流的收敛传递到测试测度、分离增量与负正则空间；端点 `@@M@@c=2@@` 由附录以 FK 回路的独立均匀定向补足所需的转动不变性。

## 可信度与备注

论文署名 OpenAI（2026 年 9 月 23 日），主结果暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。在本结果族内，本文与 DKLM（`@@M@@\sqrt3\le c\le2@@`）的姊妹工作互相支撑：一方面在 `@@M@@1\le c<2@@` 收敛建立后引用其自由能振幅定理确定乘子，另一方面把区间推广到全部 `@@M@@0<c\le2@@` 并补上 `@@M@@c=2@@` 端点的转动不变性输入。所得乘子与 1987 年 Coulomb-gas 物理预言（换算为单位高度步后）一致，是对该预言的数学证实。

{% endraw %}
