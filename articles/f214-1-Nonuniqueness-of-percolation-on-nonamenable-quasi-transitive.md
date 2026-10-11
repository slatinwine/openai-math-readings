---
layout: default
title: "Nonuniqueness of percolation on nonamenable quasi-transitive graphs"
family: "214"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Nonuniqueness of percolation on nonamenable quasi-transitive graphs

> 结果族 214：The Benjamini–Schramm nonuniqueness conjecture　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

在方格渔网上，一旦网眼接通得够多，无穷大的连通块通常只有一片。但在"越分叉越宽"的网络上——比如无限家谱树——情况可以很不一样：中等接通概率下，可能同时存在很多片各自无穷大的网。本文证明：任何扩张得足够快（"非顺从"）的规则网络上，这种"群雄并起"的局面必然出现。

**关键词卡片**

- 非顺从（nonamenable）：图扩张太快、边界与体积同阶，无限树是原型；方格网不具备。
- 唯一性阈值 p_u：超过它，无穷开簇变成唯一。
- 非唯一性（nonuniqueness）：p_c 与 p_u 之间同时存在无穷多个无穷簇。
- 连接核阈值 p₂→₂：两点连接概率作为算子是否保持有界的分界线。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="70" font-size="14" text-anchor="middle" fill="#222">非顺从规则图（如无限树）上的渗流相图</text>
  <line x1="60" y1="140" x2="180" y2="140" stroke="#9aa0a6" stroke-width="9"/>
  <line x1="180" y1="140" x2="400" y2="140" stroke="#3a7ca5" stroke-width="9"/>
  <line x1="400" y1="140" x2="500" y2="140" stroke="#c0392b" stroke-width="9"/>
  <line x1="60" y1="126" x2="60" y2="154" stroke="#333" stroke-width="2"/>
  <line x1="180" y1="126" x2="180" y2="154" stroke="#333" stroke-width="2"/>
  <line x1="260" y1="126" x2="260" y2="154" stroke="#333" stroke-width="2"/>
  <line x1="400" y1="126" x2="400" y2="154" stroke="#333" stroke-width="2"/>
  <line x1="500" y1="126" x2="500" y2="154" stroke="#333" stroke-width="2"/>
  <text x="60" y="115" font-size="14" text-anchor="middle" font-style="italic" fill="#333">0</text>
  <text x="180" y="115" font-size="14" text-anchor="middle" font-style="italic" fill="#333">p_c</text>
  <text x="260" y="115" font-size="14" text-anchor="middle" font-style="italic" fill="#333">p₂→₂</text>
  <text x="400" y="115" font-size="14" text-anchor="middle" font-style="italic" fill="#333">p_u</text>
  <text x="500" y="115" font-size="14" text-anchor="middle" font-style="italic" fill="#333">1</text>
  <text x="118" y="175" font-size="13" text-anchor="middle" fill="#666">无无穷簇</text>
  <text x="290" y="175" font-size="13" text-anchor="middle" fill="#3a7ca5">同时存在无穷多个无穷簇</text>
  <text x="452" y="175" font-size="13" text-anchor="middle" fill="#c0392b">唯一无穷簇</text>
  <text x="280" y="225" font-size="12.5" text-anchor="middle" fill="#222">定理：p_c &lt; p₂→₂ ≤ p_u，区间内几乎必然无穷多无穷簇</text>
</svg>

</div>

定理给出的完整相图如上：`@@M@@p_c<p_{2\to2}\le p_u@@`，于是 `@@M@@(p_c,p_u)@@` 是一段非空区间，其间几乎必然同时出现无穷多个无穷簇。作为推论，任何非顺从有限生成群、任何生成元集给出的 Cayley 图都落入此范围；论文还顺带确立了平均场临界行为，例如敏感度 `@@M@@\chi(p)\asymp(p_c-p)^{-1}@@`。

**为什么值得关心**

仅凭"非顺从"这一个几何条件就打开相变区间，解决了悬置三十年的 Benjamini–Schramm 非唯一性猜想，并一并证明了更强的 Hutchcroft 算子阈值猜想。

> 暂无形式化证明（AI 结果待核验）

# 过渡 | Nonuniqueness of percolation on nonamenable quasi-transitive graphs

## 由浅入深：从类比走向定理

**第一级台阶**

导读说"越分叉越宽的网络（如无限家谱树）上，中等接通概率下可能群雄并起：多片各自无穷大的网同时存在"。翻译过来：对象是一张扩张极快的规则网络；操作仍是每条边独立以概率 `@@M@@p@@` 开通；要问的是参数落在中间一段时，无穷大的开连通块是否必然不止一片——甚至无穷多片。

**第二级台阶**

用本科术语精确化。非顺从：图的顶点等周常数 `@@M@@h_V>0@@`，即任何有限顶点集的边界与体积同阶，无限树是原型，方格网不是。两个经典阈值：`@@M@@p_c@@` 是出现无穷开簇的临界值，`@@M@@p_u@@` 是无穷开簇变唯一的唯一性阈值。连接核 `@@M@@T_p(x,y)=\mathbb{P}_p(x\leftrightarrow y)@@` 可看作 `@@M@@\ell^2(V)@@` 上的算子，其有界性阈值记为 `@@M@@p_{2\to2}@@`。相图的中心问题是这三者谁大谁小。

**第三级台阶**

定理的语境：`@@M@@G@@` 无限、连通、局部有限、拟传递且 `@@M@@h_V(G)>0@@`。结论是 `@@M@@T_{p_c}@@` 在 `@@M@@\ell^2@@` 上有界，且 `@@M@@p_c<p_{2\to2}\le p_u@@`，于是 `@@M@@(p_c,p_u)@@` 非空，其间几乎必然同时存在无穷多个无穷开簇。假设"非顺从"挡住顺从图——如 `@@M@@\mathbb{Z}^d@@` 上无穷簇一旦出现即唯一；"拟传递"挡住质量输运与一致估计需要的对称性。结论用相图的话说：临界与唯一之间被算子阈值 `@@M@@p_{2\to2}@@` 撑出一段实打实的共存区间，顺带确立平均场临界指数。

## 一句话结论

证明 Benjamini–Schramm 1996 年渗流非唯一性猜想：任何无限、连通、局部有限、非顺从而拟传递的图上，Bernoulli 键渗流必有一段参数使几乎必然同时出现无穷多个无穷开簇；并证得更强的 Hutchcroft 算子阈值猜想 `@@M@@p_c<p_{2\to2}\le p_u@@`。

## 问题背景

Bernoulli 键渗流（bond percolation）让图中每条边以概率 `@@M@@p@@` 独立开放；无穷开簇何时出现、何时唯一，分别由临界值 `@@M@@p_c@@` 与唯一性阈值 `@@M@@p_u@@` 刻画。在格点 `@@M@@\mathbb Z^d@@` 上两者重合，而在非顺从（nonamenable，即顶点等周常数 `@@M@@h_V>0@@`）的图上，指数扩张的几何可能让多个无穷簇长期共存。Benjamini 与 Schramm 在 1996 年猜想：轨道有限的非顺从图上必有 `@@M@@p_c<p_u@@`，正则树即原型。此前肯定结果均需附加额外假设——平面性、大围长、Gromov 双曲、调和 Dirichlet 函数、恰当生成元集等；仅凭非顺从性本身打开间隙是三十年来的核心障碍。

## 主要结果

主定理：设 `@@M@@G@@` 无限、连通、局部有限、拟传递（quasi-transitive，自同构群只有有限多条顶点轨道）且 `@@M@@h_V(G)>0@@`，则两点连接核 `@@M@@T_p(x,y)=\mathbb P_p(x\leftrightarrow y)@@` 作为 `@@M@@\ell^2(V)@@` 上的算子在临界点有界，且 `@@M@@p_c(G)<p_{2\to2}(G)\le p_u(G)@@`，其中 `@@M@@p_{2\to2}@@` 是 `@@M@@T_p@@` 在 `@@M@@\ell^2@@` 上有界的阈值。由此存在 `@@M@@p_c<p_1<p_2<1@@`，使标准耦合下对每个 `@@M@@p\in[p_1,p_2]@@` 几乎必然同时出现无穷多个无穷开簇。推论：任何非顺从有限生成群、任何有限对称生成元集所给的 Cayley 图上同样有 `@@M@@p_c<p_{2\to2}\le p_u@@`。并确立临界三角条件（triangle condition）`@@M@@\nabla_{p_c}(v)\le\|T_{p_c}\|_{2\to2}^3<\infty@@` 与平均场指数：敏感度（susceptibility）`@@M@@\chi_v(p)\asymp(p_c-p)^{-1}@@`、渗流概率 `@@M@@\theta_v(p)\asymp p-p_c@@`、簇尺寸尾 `@@M@@\mathbb P_{p_c}(|C_v|\ge n)\asymp n^{-1/2}@@`、内外蕴半径尾均 `@@M@@\asymp n^{-1}@@`；且 `@@M@@p_c<p_{2\to2}\le p_{\exp}@@`——无穷簇已出现的区间里连接概率仍指数衰减。

## 证明思路

证明分四步。先归约：非单模情形直接引用 Hutchcroft 的非单模算子定理，新论证只处理单模自同构群；再设图为简单图、临界簇几乎必然有限。

再证临界簇的"良态性"（goodness）：尺寸 `@@M@@\le M@@` 的临界簇以 `@@M@@1-e^{-M^\epsilon}@@` 的概率满足——任意删点后，各余块内分隔两点的桥（bridge）数被其与删除集的接触数乘 `@@M@@M^{1/2+\epsilon}@@` 控制；证明以独立顶点标记（ghost field）与中心化边得分的集中不等式（Aizenman–Kesten–Newman 波动方法）控制关键边（pivotal edge）各阶矩，再移植成上述控制。

接着反证放大：设某个 `@@M@@0<\alpha<1/2@@` 的临界尺寸矩发散，则在固定轨道上构造"局部端点映射"——读有限球内渗流位、在簇内选端点的协变规则，靠在独立渗流场间拼接有限簇块实现；良态性控制桥数，得端点核 `@@M@@K@@` 满足 `@@M@@(\log(1/u)+\log M)/\log(1/\|K\|)\to0@@`。再在 `@@M@@p<p_c@@` 运行该映射：小范数迫使迭代把端点质量推出按尺寸加权的独立采样簇，由此得敏感度的微分不等式，与矩发散矛盾，故 `@@M@@\sup_x\mathbb E_{p_c}|C_x|^\alpha<\infty@@`，进而 `@@M@@\chi_{\max}(p)\le C_\eta(p_c-p)^{-1-\eta}@@`；双探索比较另给三角图（triangle diagram）次幂界 `@@M@@\sup_x\nabla_p(x)\le C_\eta(p_c-p)^{-\eta}@@`。

最后是走廊形变与谱矛盾：把 `@@M@@k@@` 步对称懒游走经时序擦圈（loop erasure）得到简单路，凡整条成为连接之关键"走廊"（内部顶点无其他开边）者施以指数惩罚；校准权重使算子范数至多损失 `@@M@@2t\rho^k\|T_p\|^2@@`（`@@M@@\rho<1@@`），行和的下降率则由两端在删走廊后的形变敏感度下界控制，且路径两端常有短"逃逸"、删走廊影响甚小。若 `@@M@@\|T_{p_c}\|=\infty@@`，洒水（sprinkling）比较给 `@@M@@\|T_p\|\ge c(p_c-p)^{-1}@@`，结合前两步可取 `@@M@@k=o(\log(1/(p_c-p)))@@` 使范数仍大而行和二次下降——行和兜不住残存范数，矛盾。再经洒水与比较得 `@@M@@p_c<p_{2\to2}\le p_u@@`，有限修改补出同时区间。

## 可信度与备注

本文是该结果族的主证明：非唯一性猜想与更强的算子阈值猜想在同一框架内一并证明；临界行为推论以 Hutchcroft 早先的条件定理为输入，新贡献是验证算子条件对全类图成立。主结果暂无 Lean 形式化证明，请以社区核验为准；OpenAI 官方亦声明"未经形式化的结果可能有问题"。

---

# 深挖 | Nonuniqueness of percolation on nonamenable quasi-transitive graphs

## 深入探讨：像审稿人一样追问 🔍

**问 1：证明里最关键、最脆弱的一步是哪里？**

答：末段的谱矛盾。把 `@@M@@k@@` 步对称懒游走做时序擦圈，凡整条路成为连接之关键"走廊"（内部顶点无其他开边）者施以指数惩罚；校准权重使算子范数至多损失 `@@M@@2t\rho^k\|T_p\|^2@@`，行和的下降率由删走廊后的形变敏感度下界控制。若 `@@M@@\|T_{p_c}\|=\infty@@`，洒水比较给 `@@M@@\|T_p\|\ge c(p_c-p)^{-1}@@`，可取 `@@M@@k=o(\log(1/(p_c-p)))@@` 使范数仍大而行和二次下降，矛盾。权重的校准与形变下界的常数是全证明最容易悄悄失配的地方。

**问 2：非顺从这个假设为什么不能去掉？**

答：顺从的传递图（如 `@@M@@\mathbb{Z}^d@@`）上无穷簇一旦出现即唯一，`@@M@@p_c=p_u@@`，结论直接失效；非顺从（`@@M@@h_V>0@@`）正是让边界够宽、多个无穷簇能长期共存的几何来源。拟传递性也不能省：质量输运、一致敏感度估计和到单模情形的归约全靠有限多条轨道。

**问 3：与已有工作相比真正的新意是什么？**

答：此前的肯定结果都要附加假设——平面性、大围长、Gromov 双曲、调和 Dirichlet 函数、恰当生成元集；仅凭非顺从本身打开间隙是三十年障碍。本文一并证明更强的 Hutchcroft 算子阈值猜想 `@@M@@p_c<p_{2\to2}\le p_u@@`，还得到 `@@M@@p_{2\to2}\le p_{\exp}@@`：无穷簇已出现的区间里连接概率仍指数衰减。

**问 4：这类 AI 生成证明最可能在哪里出错？**

答：两处中等概率技术最可疑。其一是"良态性"移植：用独立顶点标记与中心化边得分的集中不等式（Aizenman–Kesten–Newman 波动方法）控制关键边各阶矩，再改写成桥数控制，常数层层传递。其二是"局部端点映射"：读有限球内渗流位、在独立渗流场间拼接有限簇块构造协变端点规则，协方差结构稍有差错，端点核的小范数与敏感度微分不等式就立不住。本文暂无形式化核验，这两处应逐行复查。

**问 5：反证放大一步为什么必要？**

答：它把"某个 `@@M@@0<\alpha<1/2@@` 的临界尺寸矩发散"这个假设，经局部端点映射在 `@@M@@p<p_c@@` 的迭代压成敏感度微分不等式，与矩发散矛盾，从而得到 `@@M@@\sup_x\mathbb{E}_{p_c}|C_x|^\alpha<\infty@@` 与 `@@M@@\chi_{\max}(p)\le C_\eta(p_c-p)^{-1-\eta}@@`、三角图次幂界——这些正是末段谱矛盾需要的量化输入。

**问 6：谁会用到它？**

答：任何非顺从有限生成群、任何有限对称生成元集的 Cayley 图直接落入结论；平均场指数（敏感度 `@@M@@\chi\asymp(p_c-p)^{-1}@@`、渗流概率 `@@M@@\asymp p-p_c@@`、簇尺寸尾 `@@M@@n^{-1/2}@@`）给粗几何与群上随机过程研究提供现成标度。

**总评**

三十年的 Benjamini–Schramm 猜想被仅凭"非顺从"一个条件关闭，且附赠算子阈值与平均场行为，分量极大；最大风险在关键边矩控制与场拼接两段长链条的组合记账，未经形式化前需谨慎引用。

{% endraw %}
