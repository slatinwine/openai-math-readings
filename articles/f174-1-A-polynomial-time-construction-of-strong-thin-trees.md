---
layout: default
title: "A polynomial-time construction of strong thin trees"
family: "174"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A polynomial-time construction of strong thin trees

> 结果族 174：Deterministic construction of strong thin trees　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

想象一座防守森严的城市：道路网结实到想把它拦腰切断，必须同时炸掉至少 k 条路。数学家早已证明这样的路网里藏着一条"纤细但连通"的骨架线路，可那条证明像一张存在性支票——保证金库里有这笔钱，却取不出来。这篇论文造出了"取款机"：一个确定性算法，能在多项式时间里把这条细骨架真正算出来。

**关键词卡片**

- 生成树（spanning tree）：用 n−1 条边把全部顶点连通起来的最小骨架，像地铁基础线网。
- 割（cut）：把顶点分成两堆时横跨两堆的边集合；想切断图，就得砍光一个割里的边。
- k-边连通（k-edge-connected）：任意砍掉 k−1 条边图仍连通，即每个割至少含 k 条边。
- 细树（thin tree）：在每个割里只占约 C/k 比例的生成树——连通全城，却不垄断任何一处要道。
- 多项式时间（polynomial time）：计算量只随输入长度的多项式增长，规模再大也实际可算。

**看个具体例子**

定理说算法输出的树 T 满足 `@@M@@|\delta_T(S)|\le\frac{C}{k}\,|\delta_G(S)|@@`。代入 k=100、某个横跨 200 条边的割：树只派至多 2C 条边跨线。下图中虚线是一个割，灰线是图的边，红线是算法造出的细生成树——它在割处只留 2 条。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<line x1="280" y1="25" x2="280" y2="235" stroke="#999" stroke-width="2" stroke-dasharray="8,6"/>
<line x1="80" y1="60" x2="400" y2="60" stroke="#c8c8c8" stroke-width="1.5"/>
<line x1="70" y1="150" x2="490" y2="150" stroke="#c8c8c8" stroke-width="1.5"/>
<line x1="120" y1="220" x2="440" y2="220" stroke="#c8c8c8" stroke-width="1.5"/>
<line x1="80" y1="60" x2="390" y2="170" stroke="#c8c8c8" stroke-width="1.5"/>
<line x1="120" y1="220" x2="390" y2="170" stroke="#c8c8c8" stroke-width="1.5"/>
<line x1="70" y1="150" x2="400" y2="60" stroke="#c8c8c8" stroke-width="1.5"/>
<line x1="160" y1="80" x2="490" y2="150" stroke="#c8c8c8" stroke-width="1.5"/>
<line x1="80" y1="60" x2="70" y2="150" stroke="#d62728" stroke-width="3"/>
<line x1="70" y1="150" x2="120" y2="220" stroke="#d62728" stroke-width="3"/>
<line x1="120" y1="220" x2="170" y2="170" stroke="#d62728" stroke-width="3"/>
<line x1="170" y1="170" x2="160" y2="80" stroke="#d62728" stroke-width="3"/>
<line x1="400" y1="60" x2="450" y2="80" stroke="#d62728" stroke-width="3"/>
<line x1="450" y1="80" x2="490" y2="150" stroke="#d62728" stroke-width="3"/>
<line x1="490" y1="150" x2="440" y2="220" stroke="#d62728" stroke-width="3"/>
<line x1="160" y1="80" x2="450" y2="80" stroke="#d62728" stroke-width="4"/>
<line x1="170" y1="170" x2="390" y2="170" stroke="#d62728" stroke-width="4"/>
<circle cx="80" cy="60" r="6" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="70" cy="150" r="6" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="120" cy="220" r="6" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="170" cy="170" r="6" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="160" cy="80" r="6" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="400" cy="60" r="6" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="450" cy="80" r="6" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="490" cy="150" r="6" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="440" cy="220" r="6" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="390" cy="170" r="6" fill="#fff" stroke="#333" stroke-width="2"/>
<text x="288" y="40" fill="#777" font-size="13">虚线 = 一个割</text>
<text x="288" y="252" fill="#555" font-size="13">灰 = 图的边；红 = 算法输出的细生成树（跨割仅 2 条）</text>
</svg>

</div>

**为什么值得关心**

细树是网络设计与近似算法的关键零件，把"存在"变成"可算"才真正可用；即使平行边以二进制紧凑编码，算法依然多项式时间完成。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
给出确定性多项式时间算法：对任意 `@@M@@k@@`-边连通多重图（重边多重数可用二进制编码），构造出对每个割至多占 `@@M@@C/k@@` 比例的生成树。它把姊妹篇证出的强细树猜想变成可执行构造，运行时间对输入的二进制长度是多项式的。

## 问题背景
强细树猜想说 `@@M@@k@@`-边连通图必有 `@@M@@C/k@@`-细的生成树，姊妹篇已证明其存在性，但那条路线经过紧性论证与 Brouwer 不动点，只保证某个快捷矩阵存在，不给任何统一的有限搜索界，因此无法直接变成算法。算法化另有三道难关：其一，证明中的"白化"（whitening）会产生无理数矩阵，多项式位算法必须全程用有理数并逐一控制精度损失；其二，矩阵划分步骤原先用的是 Marcus–Spielman–Srivastava 的存在性定理，需要换成能真正算出符号的构造版本；其三，若平行边多重数以二进制书写，图的实际边数可达输入长度的指数倍，逐条展开不可行。

## 主要结果
定理（算法版强细树）：存在绝对常数 `@@M@@C@@` 与确定性算法，输入至少一个顶点、`@@M@@k\ge1@@` 的 `@@M@@k@@`-边连通无环多重图 `@@M@@G@@`，输出满足
`@@M@@D|\delta_T(S)|\le \frac Ck\,|\delta_G(S)|\qquad(\varnothing\ne S\subsetneq V(G))@@`
的生成树 `@@M@@T@@`；运行时间对输入的二进制编码长度是多项式，无论边被逐条显式列出，还是多重数以二进制给出；单顶点图输出空树。作为附带收获，算法还给出"费用与割同时舍入"（Corollary：给定每割质量至少为 1 的非负有理边权与任意非负有理费用，可在正支撑中找到割负载与总费用均为相应分数量的常数倍的树），且不需要费用满足任何度量假设。

## 证明思路
框架沿用姊妹篇的"打包—稀疏化—迭代"，但把三处存在性论证替换为有限计算。

先用 Nash–Williams–Tutte 定理装出 `@@M@@\lfloor k/2\rfloor@@` 棵边不相交生成树。核心的稀疏化引理把含 `@@M@@r@@` 棵树的显式图 `@@M@@H@@` 变为子图 `@@M@@H'@@`：仍含 `@@M@@r'\in[r/4,\,r/2]@@` 棵树，每个割缩至 `@@M@@a_r=\tfrac12+3C_sr^{-1/8}@@` 倍，且比值损失 `@@M@@a_r/(r'/r)\le1+C_1r^{-1/16}@@`。由于 `@@M@@r_i@@` 每步至少减半，`@@M@@\sum_i r_i^{-1/16}@@` 被几何级数控制，累积损失是一绝对常数；迭代到只剩 `@@M@@O(1)@@` 棵树时图仍连通，任取其生成树即为 `@@M@@C/k@@`-细。这一数值结构与存在性证明完全平行。

第一处替换处理自指问题：快捷矩阵须与"由它自身决定的划分"相容，而紧性/不动点不给有限界。改在度量锥（metric cone，中心化半正定矩阵加平方距离三角不等式）上优化——该锥的约束数是多项式的；用连续的容量"坡道"代替硬阈值选边，经 uncrossing 把障碍归约到一条划分链，再用椭球法（ellipsoid method）做精确有理分离，配合构造性图拟阵划分（graphic matroid partition）取出整数装填。

第二处替换无理白化：按 Barthe 的变分方法做对数行列式归一化，把堆叠向量有理逼近后，将其协方差精确补全为单位阵。第三处替换存在性矩阵划分：采用 Ezeunala–Jiang 的公开构造性符号化方法，附录给出带常数的定量实现；有理证书保证下一步所需的全部割与装填估计，且迭代中乘法损失乘积保持有界。

二进制多重数单独归约：令 `@@M@@c'_{uv}=\min\{c_{uv},k\}@@`、`@@M@@a_{uv}=\lfloor 2n^2c'_{uv}/k\rfloor@@`，得到少于 `@@M@@n^4@@` 条显式边、每个割至少 `@@M@@n^2@@` 的显式图 `@@M@@\widetilde G@@`；在 `@@M@@\widetilde G@@` 上跑显式算法，输出树在 `@@M@@\widetilde G@@` 中 `@@M@@C/n^2@@`-细，映射回原图即 `@@M@@2C/k@@`-细。归约中的算术只依赖 `@@M@@\log k@@`、多重数编码长度与 `@@M@@n@@`。

## 可信度与备注
本文暂无形式化证明；姊妹篇的存在性定理已 Lean 形式化，且本文以其层级几何为主要输入，两篇互相支撑。按 OpenAI 官方声明，未经形式化的结果可能存在问题，本文算法部分的常数与精度控制尤其需要社区核验。

{% endraw %}
