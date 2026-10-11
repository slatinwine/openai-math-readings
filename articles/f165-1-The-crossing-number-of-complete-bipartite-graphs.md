---
layout: default
title: "The crossing number of complete bipartite graphs"
family: "165"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The crossing number of complete bipartite graphs

> 结果族 165：The Harary–Hill and Zarankiewicz crossing-number formulas　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

1944 年，数学家 Turán 在布达佩斯附近的一家砖厂里盯着铁轨出神：m 座窑炉和 n 个货场要两两铺轨，轨道交叉处就得建桥。桥最少要几座？这就是完全二部图 `@@M@@K_{m,n}@@` 的交叉数问题。Zarankiewicz 在 1955 年给出"沿两条垂直坐标轴摆点"的构图并宣称最优，但证明有漏洞。这篇论文把漏洞补上了：那个直觉构图真的无懈可击。

**关键词卡片**

- 完全二部图 `@@M@@K_{m,n}@@`（complete bipartite graph）：顶点分两摞，只有跨摞的两两连边；窑炉×货场。
- 交叉数（crossing number）：所有画法中交叉点的最小个数。
- Zarankiewicz 构图（axis construction）：顶点摆在两条垂直数轴上、直线连边的画法。
- 秩不等式（rank inequality）：把"交叉够不够多"翻译成"矩阵秩够不够大"的代数工具。

**看个具体例子**

定理：`@@M@@\operatorname{cr}(K_{m,n})=\lfloor\frac m2\rfloor\lfloor\frac{m-1}2\rfloor\lfloor\frac n2\rfloor\lfloor\frac{n-1}2\rfloor@@`。代入 `@@M@@m=n=3@@` 得 1：下图正是轴构图，三条横轨对三条竖轨，九条连线只有一个交叉；`@@M@@m=n=4@@` 时公式给出 4。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <line x1="60" y1="140" x2="500" y2="140" stroke="#dddddd" stroke-width="2"/>
  <line x1="280" y1="25" x2="280" y2="255" stroke="#dddddd" stroke-width="2"/>
  <line x1="100" y1="140" x2="280" y2="50" stroke="#8899aa" stroke-width="2"/>
  <line x1="100" y1="140" x2="280" y2="105" stroke="#8899aa" stroke-width="2"/>
  <line x1="100" y1="140" x2="280" y2="235" stroke="#8899aa" stroke-width="2"/>
  <line x1="190" y1="140" x2="280" y2="50" stroke="#8899aa" stroke-width="2"/>
  <line x1="190" y1="140" x2="280" y2="105" stroke="#8899aa" stroke-width="2"/>
  <line x1="190" y1="140" x2="280" y2="235" stroke="#8899aa" stroke-width="2"/>
  <line x1="420" y1="140" x2="280" y2="50" stroke="#8899aa" stroke-width="2"/>
  <line x1="420" y1="140" x2="280" y2="105" stroke="#8899aa" stroke-width="2"/>
  <line x1="420" y1="140" x2="280" y2="235" stroke="#8899aa" stroke-width="2"/>
  <circle cx="212" cy="118" r="11" fill="none" stroke="#e0a000" stroke-width="2.5"/>
  <circle cx="100" cy="140" r="8" fill="#4a6fa5"/>
  <circle cx="190" cy="140" r="8" fill="#4a6fa5"/>
  <circle cx="420" cy="140" r="8" fill="#4a6fa5"/>
  <circle cx="280" cy="50" r="8" fill="#c0642c"/>
  <circle cx="280" cy="105" r="8" fill="#c0642c"/>
  <circle cx="280" cy="235" r="8" fill="#c0642c"/>
  <text x="52" y="122" font-size="13" fill="#4a6fa5">窑炉（横轴）</text>
  <text x="292" y="40" font-size="13" fill="#c0642c">货场（纵轴）</text>
  <text x="280" y="268" font-size="14" text-anchor="middle" fill="#333333">K₃,₃ 的九条轨道只有 1 个交叉（黄圈）——恰是公式的最小值</text>
</svg>

</div>

下界证明把画法的几何信息压进带号交叉矩阵：二部图的四边形结构导出矩阵间的循环差关系，再用拉格朗日插值造出"秩探测器"，最后由子空间维数不等式收网——交叉若少于公式值，线性代数就会自相矛盾。

**为什么值得关心**

Turán 的砖厂之问悬挂八十余年后闭合，与完全图姊妹篇互相印证，且已 Lean 形式化。

> 已 Lean 形式化

# 过渡 | The crossing number of complete bipartite graphs

## 由浅入深：从类比走向定理

**第一级台阶**

入门导读讲 Turán 的砖厂故事：窑炉与货场两两铺轨、交叉处要建桥，桥最少几座？半数学地说：对象是顶点分两摞、只在两摞之间连边的完全二部图；操作是把它画进平面、边为允许交叉的连续弧；交叉数是一切画法中交叉点数的最小值。Zarankiewicz 1955 年给出沿两条垂直数轴摆点的构图并宣称最优，但最优性论证一直有洞。

**第二级台阶**

用本科术语精确化：记 `@@M@@d_r=\lfloor r/2\rfloor\lfloor\frac{r-1}2\rfloor@@`，Zarankiewicz 猜想即 `@@M@@\operatorname{cr}(K_{m,n})=d_md_n@@`。带号交叉给每个交叉点按定向记正负号，配上顶点处辐条循环序的修正项得到符号矩阵 `@@M@@J@@`；二部图的四边形结构把 `@@M@@J@@` 的块约束进"行加列"矩阵空间。秩不等式则负责把"交叉够不够多"翻译成"矩阵秩之和够不够大"的代数问题。

**第三级台阶**

主定理陈述：对一切正整数 `@@M@@m,n@@` 公式成立，且下界对任意连续弧画法不设限制。证明分模块、各自挡住一类麻烦：子空间维数不等式（常数最优）挡住代数一侧的精度；秩探测器 `@@M@@\Phi@@` 消灭行加列与对角矩阵、又把辐条序的半符号矩阵映为可逆阵，挡住"局部序信息提不出来"的困难；装配时对角块满秩、非对角块秩受控于交叉数，交叉若少于公式值线性代数便自相矛盾。结论：Turán 砖厂之问悬置八十余年后闭合，主结果已 Lean 形式化。

## 一句话结论

论文证明了 Zarankiewicz 猜想、解决了 Turán 1944 年提出的砖厂问题（brickyard problem）：完全二部图 `@@M@@K_{m,n}@@` 的普通交叉数恰为 `@@M@@\lfloor\frac m2\rfloor\lfloor\frac{m-1}2\rfloor\lfloor\frac n2\rfloor\lfloor\frac{n-1}2\rfloor@@`，经典的"坐标轴构图"在一切连续弧画法中被证明全局最优。

## 问题背景

1944 年，Turán 在布达佩斯附近一家砖厂看到连接窑炉与货场的铁轨频频相交，由此提出完全二部图（complete bipartite graph）`@@M@@K_{m,n}@@` 的交叉数问题。Zarankiewicz 在 1955 年给出沿两条坐标轴布点的构图并断言其最优，但最优性论证存在漏洞。此后 Kleitman 用排列论证解决了较小顶点类至多 6 个顶点的情形；Woodall 发展循环序图（cyclic-order graphs）方法并计算机验证了 `@@M@@K_{7,7}@@` 与 `@@M@@K_{7,9}@@`；半定规划与旗代数（flag algebras）给出 `@@M@@\operatorname{cr}(K_{n,n})\ge 0.9118\,d_n^2+o(n^4)@@` 的渐近下界。与完全图情形同病：对完全不受限的画法，下界始终无人能证。

## 主要结果

主定理：对一切正整数 `@@M@@m,n@@`，记 `@@M@@d_r=\lfloor\frac r2\rfloor\lfloor\frac{r-1}2\rfloor@@`，则

`@@M@@D\operatorname{cr}(K_{m,n})=d_m d_n.@@`

即 `@@M@@\lfloor\frac m2\rfloor\lfloor\frac{m-1}2\rfloor\lfloor\frac n2\rfloor\lfloor\frac{n-1}2\rfloor@@`。下界对任意画法成立，上界由古典构图达到，Zarankiewicz 猜想从而成立。

## 证明思路

证明由三个彼此独立的模块加一次组合装配构成。

模块一（纯代数）：若 `@@M@@N@@` 维实向量空间中的子空间（subspace）满足 `@@M@@U_i\cap V_i=\{0\}@@`，则 `@@M@@\sum_{i,j}\dim(U_i\cap V_j)\le\lfloor m^2/4\rfloor N@@`，且常数最优。证明用多项式插值：考察系数取值于子空间、在各节点处满足约束的多项式按次数形成的滤过，非节点处的赋值维数稳定；多项式矩阵子式（minor）的度数受列次数控制，而它在每个节点处的秩亏损迫使相应幂次的 `@@M@@(\xi-t_j)@@` 整除行列式，零点重数与度数比较后求和即得。再取线性映射的图（graph），交维数化为矩阵差之核的维数，得到实用的秩和不等式：当各 `@@M@@X_i-Y_i@@` 可逆时，`@@M@@\sum_{i\ne j}\operatorname{rank}(X_i-Y_j)\ge 2d_m d@@`。

模块二（几何）：与姊妹篇共享同一个带号交叉矩阵 `@@M@@J@@`——内部交叉的带号交和（signed intersection）加上公共端点处辐条循环序的半修正项；圈配对引理 `@@M@@z^{\mathsf T}Jy=0@@` 及其证明（闭折线走道、锥到一点）逐字相同。新的一步是用二部图的四圈（four-cycle）把几何信息压成矩阵关系：块 `@@M@@J^{ik}=J(ip,kq)@@` 满足循环差 `@@M@@J^{ik}-J^{i1}-J^{1k}+J^{11}@@` 的所有矩形差为零，故落在"行加列"矩阵空间 `@@M@@\mathcal L@@` 中。

模块三（秩探测器）：当 `@@M@@n=2s+1@@` 时构造线性映射 `@@M@@\Phi@@` 把 `@@M@@n\times n@@` 矩阵送到 `@@M@@s^2\times s^2@@` 矩阵，基砖是拉格朗日重心权（barycentric weights）`@@M@@(x_p-x_q)/(F'(x_p)F'(x_q))@@` 乘单项式赋值向量得到的秩一矩阵。`@@M@@\Phi@@` 消灭一切行加列矩阵与对角矩阵；把单个非对角元映为秩至多 1 的矩阵；把任一线性辐条序的半符号矩阵 `@@M@@S_\prec@@` 映为可逆矩阵——最后一点归结为"双三角"格点上的插值唯一性，用归纳法剥去整行整列的因子。

装配：取归一化极小画法，令 `@@M@@R_{ik}=\Phi(J^{ik})@@`。模块二保证 `@@M@@R_{ik}=X_i-Y_k@@` 具差形式；对角块 `@@M@@R_{ii}@@` 恰是顶点 `@@M@@a_i@@` 处辐条序的半符号矩阵之像，由探测器的可逆性满秩 `@@M@@d=s^2@@`；非对角块的秩不超过两颗星（star）之间的交叉点数。代入秩和不等式得 `@@M@@2d_m d\le 2c(D)@@`，即下界 `@@M@@d_m d_n@@`（奇数 `@@M@@n@@`）；偶数 `@@M@@n@@` 由删点计数 `@@M@@(n-2)c(D)\ge n\,d_m d_{n-1}@@` 归结为奇数情形。上界用古典轴构图：两坐标轴上尽量均分放置顶点、直线连边，每个象限贡献 `@@M@@\binom u2\binom v2@@` 个交叉，总和恰为 `@@M@@d_m d_n@@`；一般位置选取排除三线共点。

## 可信度与备注

主结果已 Lean 形式化（结果族 165 的说明附有 Lean 文档链接）。姊妹篇《完全图的交叉数》与本文共享归一化附录与圈配对引理，两文在同一"带号交叉 + 插值"框架下分别解决 Harary–Hill 与 Zarankiewicz 两大猜想，互相印证。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇主结果已形式化，属可信度最高一档，具体细节仍建议以社区核验为准。

---

# 深究 | The crossing number of complete bipartite graphs

## 深入探讨：像审稿人一样追问 🔍

**问 1：证明中最关键、也最脆弱的一步是哪里？**

答：秩探测器 `@@M@@\Phi@@` 的可逆性——它把任一线性辐条序的半符号矩阵映为可逆矩阵，证明归结为"双三角"格点上的插值唯一性，须归纳地剥去整行整列的因子。若某个辐条序漏网，装配处对角块 `@@M@@R_{ii}@@` 不满秩，`@@M@@2d_md\le 2c(D)@@` 的链条立即断开。

**问 2：Zarankiewicz 1955 年的论证究竟缺什么，本文怎么补？**

答：缺的是对不受限画法的下界。此前只有 Kleitman 解决一类至多 6 点的情形、Woodall 计算机验证 `@@M@@K_{7,7}@@` 与 `@@M@@K_{7,9}@@`、SDP 与 flag algebras 给出渐近比 0.9118 的 `@@M@@d_n^2@@` 型下界。本文不做任何画法限制，用带号交叉加插值的代数路线直接在任意画法上闭合下界。

**问 3：与完全图姊妹篇共享了多少，真正新的是什么？**

答：共享归一化附录与圈配对引理（论文注明论证一致）；新装置有二：二部图四圈导出的循环差关系，把 `@@M@@J@@` 的块压进"行加列"矩阵空间；以及奇节点秩探测器——姊妹篇用的是偶节点版。两文各自独立成立，同属"带号交叉加插值"框架。

**问 4：这种 AI 参与生成的证明最可能在哪里出错？**

答：带号计数的单向不等式处。结论一节明言：两条独立边即使反复交叉，带号和的相消只会减少非零贡献，故 `@@M@@\operatorname{rank}R_{ik}\le c_{ik}@@` 仍成立。这个"只减不增"若在退化位形（相邻边交叉未消尽、对角局部项）处理失当，秩上界漏气、下界失效。归一化引理与探测器消灭对角项正是为堵这些口子；主结果已附 Lean 形式化证明。

**问 5：为什么偶数 `@@M@@n@@` 要绕道删点计数？**

答：探测器只对奇数 `@@M@@n=2s+1@@` 构造，目标空间维数 `@@M@@s^2=d_n@@`。偶数情形沿用 Kleitman–Woodall 式删点计数 `@@M@@(n-2)c(D)\ge n\,d_md_{n-1}@@`：每个交叉的两条边第二类端点不同，恰在 `@@M@@n-2@@` 个删点后的画法中留存，除以 `@@M@@n-2@@` 即得公式。

**问 6：谁会用到它？**

答：图可视化与布线社区——`@@M@@K_{m,n}@@` 交叉数是 VLSI 双层布线成本的原型模型，精确公式为启发式算法提供理论下界标尺；与姊妹篇合并，"带号交叉加插值"框架向完全多部图的推广成为显然的下一题。论文按普通点计数工作，pair/odd 等交叉数变体未在本文处理。

**总评**

Turán 砖厂之问八十余年后的完整闭合，与 Harary–Hill 姊妹篇在同一框架下互相印证、同享形式化背书；最大风险集中在探测器可逆性的归纳细节，所幸已有机器验证兜底。

{% endraw %}
