---
layout: default
title: "A classification of finite Euclidean Ramsey configurations"
family: "172"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A classification of finite Euclidean Ramsey configurations

> 结果族 172：Classification of finite Euclidean Ramsey configurations　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

给（足够高维的）空间里每个点随意上色，有些几何图案怎么染都躲不掉——总会冒出一只颜色纯正、尺寸分毫不差的原样拷贝。哪些图案有这种"宿命"？这就是欧几里得 Ramsey 理论的核心问题；本文交出了第一份完整的判据表。

**关键词卡片**

- 欧几里得 Ramsey 集（Euclidean Ramsey set）：任何有限染色都躲不开其单色全等拷贝的点集
- 全等拷贝（congruent copy）：形状尺寸完全相同，不许缩放
- 球面集（spherical）：所有点落在同一球面上，是 Ramsey 性的必要条件
- 子传递（subtransitive）：能嵌入对称性足够丰富（群作用传递）的有限点集
- 张量条件（tensor condition）：坐标域上一组矩阵方程，可解当且仅当点集是 Ramsey 的

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="24" text-anchor="middle" font-size="16" fill="#333">风筝形 K_a：单位圆的内接四边形</text>
  <circle cx="280" cy="150" r="90" fill="none" stroke="#999" stroke-width="1.2" stroke-dasharray="5 4"/>
  <polygon points="190,150 311,66 370,150 311,234" fill="none" stroke="#c0392b" stroke-width="2"/>
  <circle cx="190" cy="150" r="4.5" fill="#333"/>
  <circle cx="370" cy="150" r="4.5" fill="#333"/>
  <circle cx="311" cy="66" r="4.5" fill="#333"/>
  <circle cx="311" cy="234" r="4.5" fill="#333"/>
  <text x="178" y="172" text-anchor="end" font-size="13" fill="#333">(-1, 0)</text>
  <text x="382" y="172" font-size="13" fill="#333">(1, 0)</text>
  <text x="322" y="56" font-size="13" fill="#333">(a, √(1−a²))</text>
  <text x="322" y="256" font-size="13" fill="#333">(a, −√(1−a²))</text>
  <text x="280" y="272" text-anchor="middle" font-size="14" fill="#555">定理：它是 Ramsey 的，却不是子传递集</text>
</svg>

</div>

风筝形 `@@M@@K_a=\{(-1,0),(1,0),(a,\pm\sqrt{1-a^2})\}@@`：对每个超越数 `@@M@@a\in(-1,1)@@`，定理证明它是 Ramsey 的，却不是子传递集——直接推翻了 Leader–Russell–Walters 刻画的必要性方向。反方向也用得上：九个代数独立选取的圆上点、以 Liouville 常数为旋转角的三个同心正方形，都因不满足张量条件而被判为非 Ramsey。判据的分野极微妙：把张量方程"乘开"只能得到球面条件，必须在相乘之前的张量环里可解，才真正保证 Ramsey 性。

**为什么值得关心**

欧氏 Ramsey 理论五十余年来首次拿到充要判据；据此圆上任取不超过五个点的集合全部判为 Ramsey。

> 已 Lean 形式化

## 一句话结论
论文证明：有限欧氏点集是 Ramsey 集，当且仅当其坐标域上一组张量方程可解；据此圆上至多五个点的集合全是 Ramsey 的，而某些 Ramsey 的圆内接四边形并非子传递集，推翻了 Leader–Russell–Walters 猜想的必要性方向。

## 问题背景
1973 年 Erdős、Graham 等六人开创欧几里得 Ramsey 理论 (Euclidean Ramsey theory)：有限点集 `@@M@@A@@` 称为 Ramsey 的，若对任意色数 `@@M@@r@@` 存在维数 `@@M@@D@@`，使 `@@M@@\mathbb{R}^D@@` 的任何 `@@M@@r@@`-染色都含与 `@@M@@A@@` 全等 (congruent)、保持原尺度的单色拷贝。他们证明 Ramsey 集必为球面集 (spherical)，Graham 猜想其逆。此后 Frankl–Rödl、Kříž、Cantwell 等陆续证明单纯形、可解传递集、正多胞体等大批正例；Leader–Russell–Walters 提出另一刻画：Ramsey 当且仅当可嵌入有限传递集 (transitive set)，即子传递 (subtransitive)。近期 Pálvölgyi 用七点圆构型推翻了球面猜想，而完全判据一直缺失，本文补上这块拼图。

## 主要结果
设 `@@M@@A=\{a_1,\dots,a_s\}\subset\mathbb{R}^d@@`（`@@M@@s\ge2@@`）仿射张满 `@@M@@\mathbb{R}^d@@`，令 `@@M@@p_i=\binom{1}{a_i}@@`，坐标域 (coordinate field) `@@M@@F=\mathbb{Q}(\text{全部坐标})@@`，`@@M@@B=F\otimes_\mathbb{Q}F@@`，乘法映射 `@@M@@m_F(x\otimes y)=xy@@`。分类定理 (Classification)：`@@M@@A@@` 是 Ramsey 集当且仅当存在矩阵 `@@M@@P\in\operatorname{Mat}_{d+1}(B)@@` 满足
`@@M@@D(p_i\otimes1)^{\mathsf T}P(1\otimes p_i)=0\ (1\le i\le s),\qquad m_F(P_{\alpha\beta})=\delta_{\alpha\beta}\ (1\le\alpha,\beta\le d).@@`
对第一组等式施加 `@@M@@m_F@@` 便得球面方程 `@@M@@\|a_i\|^2+\ell\cdot a_i+c=0@@`；关键在于等式须在相乘之前的张量环 `@@M@@B@@` 中成立——这正是球面性与 Ramsey 性的分野。由此推出：每个 Ramsey 集都是球面集；子传递集都是 Ramsey 的；圆上任取至多五个点的非空集（特别地，每个圆内接四边形）都是 Ramsey 的；而对每个超越数 `@@M@@a\in(-1,1)@@`，风筝形 `@@M@@K_a=\{(-1,0),(1,0),(a,\pm\sqrt{1-a^2})\}@@` 是 Ramsey 的却非子传递。反向地，代数独立参数给出的九个圆上点、以 Liouville 常数为旋转角的三个同心坐标正方形（十二点）均不满足张量条件，故非 Ramsey。

## 证明思路
先证必要性。把矩阵条件等价改写为 `@@M@@\mathbb{Q}@@` 上对称张量 `@@M@@T@@` 的条件：各点求值 `@@M@@(e_i\otimes e_i)(T)=0@@` 且梯度 Gram 矩阵 `@@M@@G(T)=I_d@@`（经 `@@M@@B\subset\mathbb{R}\otimes_\mathbb{Q}\mathbb{R}@@` 的自由模分解完成下降）。若无此张量，则用 `@@M@@\mathbb{Q}@@`-线性泛函把目标元 `@@M@@(0,\dots,0,I_d)@@` 从像空间分离，得到纯代数泛函 `@@M@@h_i@@` 与 `@@M@@L@@`，使任何维数中任何全等拷贝 `@@M@@(b_i)@@` 都满足 `@@M@@\sum_iH_i(b_i)=-1@@`，而单点处 `@@M@@\sum_iH_i(z)=0@@`。按各 `@@M@@H_i(z)@@` 模 `@@M@@2@@` 落入的区间染色，至多 `@@M@@(2s+1)^s@@` 色即可在一切维数避开 `@@M@@A@@`：单色拷贝迫使 `@@M@@-1@@` 等于偶数加绝对值小于 `@@M@@1@@` 的误差，矛盾。

充分性分三步。第一步把张量恒等式经 Laurent 多项式环的 `@@M@@\mathfrak{m}@@`-进完备化与形式对数变换，转写为格 `@@M@@\mathbb{Z}^k@@` 上有限支撑的有理权函数：每个求值陪集上正、负权各自精确抵消，二阶矩等于给定矩阵 `@@M@@C@@`。再用协方差从 `@@M@@S@@` 连续变到 `@@M@@S+C@@` 的高斯密度平均做光滑化，离散卷积并取有理逼近，得到两尺度结论：`@@M@@\|f_i-f_j\|^2=\|a_i-a_j\|^2@@`、`@@M@@\|g_i-g_j\|^2=q\|a_i-a_j\|^2@@`（`@@M@@q>0@@` 可任意小），且 `@@M@@g_i@@` 恰是 `@@M@@f_i@@` 的坐标重排，距离与多重集均精确。

第二步建立路径判据 (path criterion)：在以有限支撑序列为生成元的自由群上，路径由权为零的对角因子与权为尺度平方的拷贝因子组成；同端点而权重比任意小的两条路径蕴含 Ramsey 性。Hales–Jewett 线的可变位置数 `@@M@@t@@` 预先未知是主要障碍，故先用同步引理预备权重 `@@M@@1,\dots,1/n@@` 的同端点路径，再用超滤子 (ultrafilter) 角群把群乘积实现为有限字符串，公共因子在各角色取同一字符串，`@@M@@t@@` 个可变位置各贡献 `@@M@@\|a_i-a_j\|^2/t@@`，恰合成原尺度；紧性把结论拉回有限维。

第三步用置换平均把两尺度路径的群元差压入可校正子群，追加单位尺度拷贝路径修正，校正权重相对原权重任意小，拼出判据所需的等端点路径对。全部论证在 ZFC 中完成。

## 可信度与备注
任务元数据标明主结果已有 Lean 形式化证明。本文各推论（子传递集、圆上五点集、风筝形 `@@M@@K_a@@`）均由同一张量判据导出，九点、十二点反例亦是其直接应用。按 OpenAI 官方声明，未经形式化的结果可能存在问题：主定理已形式化，但具体例子中的行列式与导子计算细节仍以论文推导与社区核验为准；论文并注明 Pálvölgyi 文中附录未经其本人核验。

{% endraw %}
