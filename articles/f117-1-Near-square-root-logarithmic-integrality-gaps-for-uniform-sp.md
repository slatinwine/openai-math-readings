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

## 入门导读 🐣

估价师先给房子一个"乐观估值"（松弛问题的解），真实成交价（整数最优解）往往更高，两者的落差叫积分间隙。这篇论文盖了一整批"最稀疏割"的房子：乐观估值和成交价的落差随规模增长达到 `@@M@@\sqrt{\log n}@@` 量级——离理论上限只差一个 `@@M@@\log\log n@@` 的幂。

**关键词卡片**

- 半定规划松弛（semidefinite programming relaxation）：把离散的割放宽成"向量距离"问题，总能快速求解。
- 积分间隙（integrality gap）：松弛最优值与真实最优值之比的最大落差。
- 负型半度量（negative-type semimetric）：能实现为希尔伯特空间平方距离的距离结构。
- `@@M@@\ell_1@@` 嵌入（`@@M@@\ell_1@@` embedding）：把度量嵌进"曼哈顿距离"，从而舍入成割。
- 割锥对偶（cut-cone duality）：把距离结构翻译回图容量的对偶桥梁。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <line x1="70" y1="230" x2="510" y2="230" stroke="#333" stroke-width="2"/>
  <rect x="140" y="160" width="80" height="70" fill="none" stroke="#333" stroke-width="2"/>
  <text x="180" y="142" text-anchor="middle" font-size="14">SDP 松弛值 GL（小）</text>
  <rect x="350" y="60" width="80" height="170" fill="none" stroke="#333" stroke-width="2"/>
  <text x="390" y="42" text-anchor="middle" font-size="14">真实最优 OPT（大）</text>
  <line x1="228" y1="155" x2="342" y2="58" stroke="#c00" stroke-width="2"/>
  <polygon points="346,55 333,54 340,65" fill="#c00"/>
  <text x="272" y="78" text-anchor="middle" font-size="14">积分间隙</text>
  <text x="280" y="258" text-anchor="middle" font-size="13">比值 ≥ c·√log n / (loglog n)³，上界为 O(√log n)</text>
</svg>

</div>

数字版：构造的实例（每对顶点需求为 1）满足真实最优 `@@M@@\mathrm{OPT}\ge1@@`，而 SDP 值 `@@M@@\mathrm{GL}\le b/a@@`，于是

`@@M@@D\frac{\mathrm{OPT}}{\mathrm{GL}}\ \ge\ c\,\frac{\sqrt{\log n}}{(\log\log n)^3}@@`

构造思路是造一个"全局距离大、界面代价小"的距离结构：顶点标签来自参数立方体的分块取整，任何把点嵌进曼哈顿距离的收缩映射都被迫把平均距离压低约 `@@M@@\sqrt{\log n}@@` 倍，最后经割锥对偶翻译回图容量。对比 Arora–Rao–Vazirani 的上界 `@@M@@O(\sqrt{\log n})@@`：下界与上界几乎贴上了，只差 `@@M@@\log\log n@@` 的一个幂。

**为什么值得关心**

它宣告均匀需求下"SDP 常数间隙"彻底无望、ARV 的 `@@M@@\sqrt{\log n}@@` 阶本质上已最优——此前已知下界只有 `@@M@@\log\log n@@` 量级，这是一次大幅跃进。

> 已 Lean 形式化

# 由浅入深：从类比走向定理 —— Near-square-root logarithmic integrality gaps for uniform sparsest cut

## 由浅入深：从类比走向定理

**第一级台阶**

入门导读用"乐观估值对成交价"作比：估价师把离散的割放宽成向量距离问题，快速给出一个偏乐观的数；真实最优往往更高，落差叫积分间隙。翻译一下：对象是"把顶点分两块、使跨越容量相对被拆点对数尽量小"的图问题；乐观估值来自把割换成一种可连续调节的距离结构；论文造出一批图，使这两个数的落差随规模增长到 `@@M@@\sqrt{\log n}@@` 量级——离理论上限只差一个 `@@M@@\log\log n@@` 的幂。

**第二级台阶**

用本科术语说：负型半度量是可实现为 Hilbert 空间平方距离 `@@M@@d(i,j)=|x_i-x_j|^2@@` 且满足一切三角不等式的距离；Goemans–Linial 松弛 `@@M@@\mathrm{GL}(C)=\min\{\sum_{i<j}c_{ij}d(i,j):\sum_{i<j}d(i,j)=1,\ d\ \text{负型}\}@@`。均匀最优 `@@M@@\mathrm{OPT}(C)=\min_B\frac{\sum_{i\in B,j\notin B}c_{ij}}{|B|(n-|B|)}@@`。割距离归一化后可行，故 `@@M@@\mathrm{GL}\le\mathrm{OPT}@@`，积分间隙即二者之比；`@@M@@\ell_1@@` 嵌入与割锥对偶（`@@M@@\ell_1@@` 距离=割度量的非负组合）负责把距离结构翻译回容量。

**第三级台阶**

定理（thm:main）在此陈述：存在绝对常数 `@@M@@c>0@@` 与顶点数 `@@M@@n_j\to\infty@@` 的容量实例 `@@M@@C^{(j)}@@`（每对不同顶点需求为 `@@M@@1@@`、容量为非负实数），`@@M@@\mathrm{GL}>0@@` 且 `@@M@@\mathrm{OPT}/\mathrm{GL}\ge c\,\frac{\sqrt{\log n_j}}{(\log\log n_j)^3}@@`。"均匀需求"这一假设意味着必须构造对所有点对平均距离的阻碍——最坏点对失真不够用；"容量取非负实数"则把结论定位为松弛本身的信息论缺陷而非复杂度陈述。结论与 Arora–Rao–Vazirani 的 `@@M@@O(\sqrt{\log n})@@` 上界只差 `@@M@@\log\log n@@` 的一个幂。

## 一句话结论
构造了一列每对顶点需求恰为 `@@M@@1@@` 的最稀疏割实例，其 Goemans–Linial 半定松弛的积分间隙至少为 `@@M@@c\sqrt{\log n}/(\log\log n)^3@@`，把均匀需求下的已知下界推进到近乎匹配 Arora–Rao–Vazirani 的 `@@M@@O(\sqrt{\log n})@@` 上界。

## 问题背景
最稀疏割的松弛与有限度量几何深度相连：Linial–London–Rabinovich 证明 `@@M@@\ell_1@@` 度量恰为割度量的非负组合，故把度量嵌入 `@@M@@\ell_1@@` 即可舍入成割；均匀需求下的关键量是非扩张映射保持的平均距离（Rabinovich 的平均失真框架）。一般需求下，Goemans–Linial 猜想（常数积分间隙）已被 Khot–Vishnoi 以及 Heisenberg 群几何系列工作（Lee–Naor、Cheeger–Kleiner、CKN）否定，Naor–Young 给出 `@@M@@\Omega(\sqrt{\log n})@@`，Chang–Naor–Ren 证明匹配上界。但这些是最坏点对失真，不蕴含均匀需求的结论——CKN 明确指出其有界倍增例子到直线的平均失真是常数，无法产生发散的均匀间隙。均匀需求下此前的最好下界是 Devanur–Khot–Saket–Vishnoi 的 `@@M@@\Omega(\log\log n)@@`（否定均匀常数间隙猜想）与 Kane–Meka 的 `@@M@@\exp(\Omega(\sqrt{\log\log n}))@@`；而 ARV 的 `@@M@@O(\sqrt{\log n})@@` 上界是标杆。本文把指数做到 `@@M@@1/2@@`。

## 主要结果
记均匀目标 `@@M@@\mathrm{OPT}(C)=\min_{\varnothing\ne B\subsetneq[n]}\frac{\sum_{i\in B,j\notin B}c_{ij}}{|B|(n-|B|)}@@`，Goemans–Linial 半定松弛 `@@M@@\mathrm{GL}(C)@@` 为：在所有满足三角不等式、`@@M@@\sum_{i<j}d(i,j)=1@@` 的负型半度量（negative-type semimetric）`@@M@@d(i,j)=|x_i-x_j|^2@@` 上最小化 `@@M@@\sum_{i<j}c_{ij}d(i,j)@@`。主定理：存在绝对常数 `@@M@@c>0@@` 与顶点数 `@@M@@n_j\to\infty@@` 的实例 `@@M@@C^{(j)}@@`（每对不同顶点需求为 `@@M@@1@@`、容量为非负实数），使得 `@@M@@\mathrm{GL}(C^{(j)})>0@@` 且 `@@M@@\mathrm{OPT}/\mathrm{GL}\ge c\,\frac{\sqrt{\log n_j}}{(\log\log n_j)^3}@@`。与 ARV 上界只差 `@@M@@\log\log n@@` 的一个幂。

## 证明思路
要完成两个任务：先造一个平均距离很大的负型半度量，再迫使每个 `@@M@@\ell_1@@` 收缩映射（contraction）在相同测度下平均距离很小，最后经割锥对偶（cut-cone duality）转成容量实例。

先建公共参数空间与图卡。固定大整数 `@@M@@m@@` 与参数立方体 `@@M@@U=(-2,2)^m@@`；每个图卡 `@@M@@s@@` 把线性映射 `@@M@@\theta\mapsto(\langle u_{s,i},\theta\rangle)_i@@` 的各坐标取整到格距 `@@M@@\tau@@`，得到标签 `@@M@@v_s(\theta)=(s,X_s(\theta))@@`。方向在收缩映射选定之前固定，并满足同时保证：每个单位方向在至少一半图卡中与全部法向量的投影都小；由此顶点数 `@@M@@|V|\le\exp(Cm\log m)@@`。

再构造距离。用一个公共的光滑特征映射造 Hilbert 向量，其平方距离逼近 `@@M@@c_*\sqrt m\,|\theta-\eta|@@` 且带一致加性误差；附加 Fourier 分量使导数剖面与特征向量近似正交，从而控制图卡界面处改变一个取整坐标的代价。但所得平方距离未必满足全部三角不等式，须用 Gaussian 正定核的尺度积分（Schoenberg 原理）修复：局部角度估计不可或缺，否则全局误差会淹没界面处的微小费用。修复后，不同图卡中相同参数的标签距离至多 `@@M@@Cr@@`（`@@M@@r=m^{-8}@@`），而 `@@M@@T=(-1,1)^m@@` 上独立均匀参数的期望第一图卡距离至少 `@@M@@cm@@`——即"全局距离大、界面代价小"。

再约束收缩映射。对任一收缩 `@@M@@F:V\to\ell_1^D@@`，各图卡函数经平滑后彼此接近、梯度也接近；界面处的小跳跃把每个标量梯度表为该图卡法向量的组合，系数总预算 `@@M@@Cm(\log m)^2@@`；在有利图卡中小投影再贡献因子 `@@M@@C\sqrt{(\log m)/m}@@`；最后用 Maurey–Pisier 高斯旋转法证明方体上与维数无关的一阶矩不等式，得 `@@M@@\mathbb E\|F(v_1(\theta))-F(v_1(\eta))\|_1\le C\sqrt m\,(\log m)^{5/2}@@`，对目标维 `@@M@@D@@` 一致。

最后换成精确均匀需求。把第一图卡上的测度用重数逼近，同时给每个顶点保留至少一份拷贝（同顶点拷贝距离为零，故拷贝上的收缩诱导整个 `@@M@@V@@` 上的收缩，所有图卡的约束都得以保留）；割锥对偶引理由线性规划对偶给出容量：最大化 `@@M@@\sum|S|(n-|S|)t_S@@`、受 `@@M@@\sum t_S\delta_S\le d@@` 约束的原始问题的对偶可行容量满足 `@@M@@\mathrm{OPT}\ge1@@`、`@@M@@\mathrm{GL}\le b/a@@`。尺寸与间隙换算为 `@@M@@\mathrm{gap}\gtrsim\frac{m}{\sqrt m(\log m)^{5/2}}@@`、`@@M@@\log n\asymp m\log m@@`，恰好得到 `@@M@@\sqrt{\log n}/(\log\log n)^3@@` 中的三次幂。

## 可信度与备注
本文主结果已 Lean 形式化，可信度较高。姊妹篇证明均匀最稀疏割任意固定因子近似的无条件 NP-难度（未形式化），两篇一负一正互相支撑：姊妹篇排除多项式时间常因子算法，本文进一步说明 ARV 型 `@@M@@\sqrt{\log n}@@` 阶在均匀需求下本质最优（至迭代对数因子），半定规划路线无从侥幸。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文主结果已形式化，风险较低，姊妹篇则仍待社区核验。

---

# 深入探讨：像审稿人一样追问 🔍 —— Near-square-root logarithmic integrality gaps for uniform sparsest cut

## 深入探讨：像审稿人一样追问 🔍

**问 1：构造里最关键、最脆弱的一步是哪里？**

答：度量修复（metric 一节）。特征映射给出的平方距离逼近 `@@M@@c_*\sqrt m\,|\theta-\eta|@@`，却未必满足全部三角不等式；修复用 Gaussian 正定核的尺度积分（Schoenberg 原理）完成。论文自己强调：局部角度估计不可或缺——仅有界全局误差会淹没格子界面处的微小费用，修复必须做到总规模有界且界面处只损失一个对数因子。这一步同时扛着"全局距离大"与"界面代价小"两个相互拉扯的要求。

**问 2：为什么一般需求的 `@@M@@\Omega(\sqrt{\log n})@@` 下界不蕴含本文结论？**

答：一般需求下界（Khot–Vishnoi、Naor–Young）是最坏点对失真；均匀需求要求对所有点对的平均距离设障。引言明确引 Cheeger–Kleiner–Naor 的说明：其有界倍增例子到直线的平均失真是常数（CKN09 Remark 1.1），造不出发散的均匀间隙。最坏对与平均的鸿沟正是本文要跨的障碍。

**问 3：与已有工作相比真正的新意是什么？**

答：均匀需求下此前最好下界是 `@@M@@\Omega(\log\log n)@@`（Devanur–Khot–Saket–Vishnoi）与 `@@M@@\exp(\Omega(\sqrt{\log\log n}))@@`（Kane–Meka）；本文把 `@@M@@\log n@@` 的指数做到 `@@M@@1/2@@`，与 ARV 的 `@@M@@O(\sqrt{\log n})@@` 上界只差 `@@M@@(\log\log n)^3@@`，且针对的是基本 Goemans–Linial SDP 而非加强松弛。

**问 4：容量允许取非负实数，这个设定为什么重要、又留下什么缺口？**

答：容量由割锥对偶从距离结构里读出，天然取实数，这使结论是纯几何/信息论的积分间隙陈述，不附带算法复杂度含义。反过来它不给出 NP-硬度——多项式时间不可近似性由未形式化的姊妹篇承担；本文亦未讨论容量有理化后的位数问题。

**问 5：`@@M@@(\log\log n)^3@@` 的损失从哪来，还能压掉吗？**

答：换算是 `@@M@@\mathrm{gap}\gtrsim\frac{m}{\sqrt m(\log m)^{5/2}}@@`、`@@M@@\log n\asymp m\log m@@`：收缩映射的平均 `@@M@@\ell_1@@` 距离界 `@@M@@C\sqrt m(\log m)^{5/2}@@` 里的 `@@M@@(\log m)^{5/2}@@` 与规模换算里的 `@@M@@\log m@@` 合起来正好产生三次幂。能否改进论文未讨论；Maurey–Pisier 一阶矩不等式本身看起来不是瓶颈，损失主要在平滑与界面预算。

**问 6：这类几何构造最可能在哪里出错？AI 风险如何？**

答：高危点是层层常数接力：方向族的同时保证、法向量系数总预算 `@@M@@Cm(\log m)^2@@`、有利图卡中 `@@M@@C\sqrt{(\log m)/m}@@` 的因子、以及"对目标维 `@@M@@D@@` 一致"的断言。据结果族元信息，本文主定理已附 Lean 形式化证明，这类"常数错一位、指数塌一截"的经典风险已大幅降低；残余风险在形式化覆盖之外的讨论与文献定量比对。

**问 7：谁会用到它？**

答：做图划分近似与度量嵌入的人：它宣告均匀需求下 Goemans–Linial SDP 的常数间隙彻底无望、ARV 的 `@@M@@\sqrt{\log n}@@` 阶本质上最优，为 SDP 路线划界；收缩映射约束与图表取整的构造手法对负型度量几何研究亦有独立参考价值。

**总评**

这是把均匀需求积分间隙从 `@@M@@\log\log@@` 量级一把推到近乎匹配 ARV 的跃进之作，且主定理经 Lean 形式化，可信度在本族中最高；剩余悬念集中在 `@@M@@(\log\log n)^3@@` 损失能否收紧，以及与姊妹篇硬度合流后该问题近似图景的最终定型。

{% endraw %}
