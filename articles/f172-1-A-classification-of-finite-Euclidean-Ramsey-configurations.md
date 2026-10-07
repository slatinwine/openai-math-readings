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

## 一句话结论
论文证明：有限欧氏点集是 Ramsey 集，当且仅当其坐标域上一组张量方程可解；据此圆上至多五个点的集合全是 Ramsey 的，而某些 Ramsey 的圆内接四边形并非子传递集，推翻了 Leader–Russell–Walters 猜想的必要性方向。

## 问题背景
1973 年 Erdős、Graham 等六人开创欧几里得 Ramsey 理论 (Euclidean Ramsey theory)：有限点集 \(A\) 称为 Ramsey 的，若对任意色数 \(r\) 存在维数 \(D\)，使 \(\mathbb{R}^D\) 的任何 \(r\)-染色都含与 \(A\) 全等 (congruent)、保持原尺度的单色拷贝。他们证明 Ramsey 集必为球面集 (spherical)，Graham 猜想其逆。此后 Frankl–Rödl、Kříž、Cantwell 等陆续证明单纯形、可解传递集、正多胞体等大批正例；Leader–Russell–Walters 提出另一刻画：Ramsey 当且仅当可嵌入有限传递集 (transitive set)，即子传递 (subtransitive)。近期 Pálvölgyi 用七点圆构型推翻了球面猜想，而完全判据一直缺失，本文补上这块拼图。

## 主要结果
设 \(A=\{a_1,\dots,a_s\}\subset\mathbb{R}^d\)（\(s\ge2\)）仿射张满 \(\mathbb{R}^d\)，令 \(p_i=\binom{1}{a_i}\)，坐标域 (coordinate field) \(F=\mathbb{Q}(\text{全部坐标})\)，\(B=F\otimes_\mathbb{Q}F\)，乘法映射 \(m_F(x\otimes y)=xy\)。分类定理 (Classification)：\(A\) 是 Ramsey 集当且仅当存在矩阵 \(P\in\operatorname{Mat}_{d+1}(B)\) 满足
\[(p_i\otimes1)^{\mathsf T}P(1\otimes p_i)=0\ (1\le i\le s),\qquad m_F(P_{\alpha\beta})=\delta_{\alpha\beta}\ (1\le\alpha,\beta\le d).\]
对第一组等式施加 \(m_F\) 便得球面方程 \(\|a_i\|^2+\ell\cdot a_i+c=0\)；关键在于等式须在相乘之前的张量环 \(B\) 中成立——这正是球面性与 Ramsey 性的分野。由此推出：每个 Ramsey 集都是球面集；子传递集都是 Ramsey 的；圆上任取至多五个点的非空集（特别地，每个圆内接四边形）都是 Ramsey 的；而对每个超越数 \(a\in(-1,1)\)，风筝形 \(K_a=\{(-1,0),(1,0),(a,\pm\sqrt{1-a^2})\}\) 是 Ramsey 的却非子传递。反向地，代数独立参数给出的九个圆上点、以 Liouville 常数为旋转角的三个同心坐标正方形（十二点）均不满足张量条件，故非 Ramsey。

## 证明思路
先证必要性。把矩阵条件等价改写为 \(\mathbb{Q}\) 上对称张量 \(T\) 的条件：各点求值 \((e_i\otimes e_i)(T)=0\) 且梯度 Gram 矩阵 \(G(T)=I_d\)（经 \(B\subset\mathbb{R}\otimes_\mathbb{Q}\mathbb{R}\) 的自由模分解完成下降）。若无此张量，则用 \(\mathbb{Q}\)-线性泛函把目标元 \((0,\dots,0,I_d)\) 从像空间分离，得到纯代数泛函 \(h_i\) 与 \(L\)，使任何维数中任何全等拷贝 \((b_i)\) 都满足 \(\sum_iH_i(b_i)=-1\)，而单点处 \(\sum_iH_i(z)=0\)。按各 \(H_i(z)\) 模 \(2\) 落入的区间染色，至多 \((2s+1)^s\) 色即可在一切维数避开 \(A\)：单色拷贝迫使 \(-1\) 等于偶数加绝对值小于 \(1\) 的误差，矛盾。

充分性分三步。第一步把张量恒等式经 Laurent 多项式环的 \(\mathfrak{m}\)-进完备化与形式对数变换，转写为格 \(\mathbb{Z}^k\) 上有限支撑的有理权函数：每个求值陪集上正、负权各自精确抵消，二阶矩等于给定矩阵 \(C\)。再用协方差从 \(S\) 连续变到 \(S+C\) 的高斯密度平均做光滑化，离散卷积并取有理逼近，得到两尺度结论：\(\|f_i-f_j\|^2=\|a_i-a_j\|^2\)、\(\|g_i-g_j\|^2=q\|a_i-a_j\|^2\)（\(q>0\) 可任意小），且 \(g_i\) 恰是 \(f_i\) 的坐标重排，距离与多重集均精确。

第二步建立路径判据 (path criterion)：在以有限支撑序列为生成元的自由群上，路径由权为零的对角因子与权为尺度平方的拷贝因子组成；同端点而权重比任意小的两条路径蕴含 Ramsey 性。Hales–Jewett 线的可变位置数 \(t\) 预先未知是主要障碍，故先用同步引理预备权重 \(1,\dots,1/n\) 的同端点路径，再用超滤子 (ultrafilter) 角群把群乘积实现为有限字符串，公共因子在各角色取同一字符串，\(t\) 个可变位置各贡献 \(\|a_i-a_j\|^2/t\)，恰合成原尺度；紧性把结论拉回有限维。

第三步用置换平均把两尺度路径的群元差压入可校正子群，追加单位尺度拷贝路径修正，校正权重相对原权重任意小，拼出判据所需的等端点路径对。全部论证在 ZFC 中完成。

## 可信度与备注
任务元数据标明主结果已有 Lean 形式化证明。本文各推论（子传递集、圆上五点集、风筝形 \(K_a\)）均由同一张量判据导出，九点、十二点反例亦是其直接应用。按 OpenAI 官方声明，未经形式化的结果可能存在问题：主定理已形式化，但具体例子中的行列式与导子计算细节仍以论文推导与社区核验为准；论文并注明 Pálvölgyi 文中附录未经其本人核验。

{% endraw %}
