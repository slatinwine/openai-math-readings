---
layout: default
title: "An algebra of infinite little finitistic dimension"
family: "198"
discipline: "Algebra"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | An algebra of infinite little finitistic dimension

> 结果族 198：A counterexample to finitistic-dimension finiteness　·　学科：Algebra　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

把一个代数对象"拆解"成标准零件（投射模）时，有的永远拆不完，有的拆有限步就停。Bass 在 1960 年猜想：凡是能拆完的，步数该有个统一上限——好比说"这家公司所有能结清的账，结算轮数总有个天花板"。这篇论文造出一家没有天花板的"公司"：同一个代数里，总有账单要拆任意多轮才能结清。

**关键词卡片**

- 有限维代数（finite-dimensional algebra）：作为向量空间只有有限维的乘法系统
- 投射模（projective module）：最像"标准件"的模块，其他模块都能借助它来分解
- 投射维数（projective dimension）：把模块拆成标准件所需的最短分解长度
- 小有限维数（little finitistic dimension）：所有"拆得完"的模块中投射维数的上确界；Bass 猜想它总有限

**看个具体例子**

定理：存在复数域上一个固定的有限维代数 `@@M@@A@@`，使得对每个 `@@M@@m\ge1@@` 都有有限维模 `@@M@@N_m@@` 满足

`@@M@@D2m-2\ \le\ \operatorname{pd}_A N_m\ <\ \infty .@@`

关键在量词顺序：`@@M@@A@@` 先固定，`@@M@@m@@` 可以任意大——"拆得完，但要多拆有多拆"：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<line x1="60" y1="230" x2="510" y2="230" stroke="#555" stroke-width="2"/>
<line x1="60" y1="230" x2="60" y2="40" stroke="#555" stroke-width="2"/>
<rect x="90" y="215" width="50" height="15" fill="#48a"/>
<rect x="180" y="185" width="50" height="45" fill="#48a"/>
<rect x="270" y="150" width="50" height="80" fill="#48a"/>
<rect x="360" y="110" width="50" height="120" fill="#48a"/>
<rect x="450" y="65" width="50" height="165" fill="#48a"/>
<text x="95" y="252" font-size="14" fill="#222">N₁</text>
<text x="185" y="252" font-size="14" fill="#222">N₂</text>
<text x="275" y="252" font-size="14" fill="#222">N₃</text>
<text x="365" y="252" font-size="14" fill="#222">N₄</text>
<text x="455" y="252" font-size="14" fill="#222">N₅…</text>
<text x="120" y="48" font-size="14" fill="#d33">没有天花板</text>
<line x1="115" y1="53" x2="160" y2="53" stroke="#d33" stroke-width="1.5" stroke-dasharray="6 5"/>
<line x1="195" y1="53" x2="240" y2="53" stroke="#d33" stroke-width="1.5" stroke-dasharray="6 5"/>
<line x1="275" y1="53" x2="320" y2="53" stroke="#d33" stroke-width="1.5" stroke-dasharray="6 5"/>
<line x1="355" y1="53" x2="400" y2="53" stroke="#d33" stroke-width="1.5" stroke-dasharray="6 5"/>
<line x1="435" y1="53" x2="480" y2="53" stroke="#d33" stroke-width="1.5" stroke-dasharray="6 5"/>
<text x="310" y="205" font-size="14" fill="#888">拆解步数 ≥ 2m−2，可任意大</text>
</svg>

</div>

**为什么值得关心**

小有限维数猜想悬置六十余年，是同调代数最著名的公开问题之一；此反例宣告它在有限维代数上整体失败，并连带说明该代数上"内射生成"性质失效。同一构造思路还带出极端不对称的姊妹结论：存在另一个代数，其左侧的小、大维数均为无穷，右侧却均为零。

> 已 Lean 形式化

# 过渡 | An algebra of infinite little finitistic dimension

## 由浅入深：从类比走向定理

**第一级台阶**

入门导读把投射分解讲成"拆账单"：模块是要结算的账，标准零件是投射模，拆解所需最少层数是它的"结算轮数"。Bass 猜想说：同一家公司里，凡能结清的账，轮数总有统一天花板。本文的操作就是造出一家没有天花板的"公司"——同一个固定的代数里，对任意多的层数，都有一笔账恰好要拆那么多轮才能结清。

**第二级台阶**

用本科术语说：域 k 上的有限维代数 A 既是一个环、又是有限维向量空间；左 A-模是其上的"表示空间"。投射模是最接近自由模的标准件；模 N 的投射维数 pd_A N 是其最短投射分解的长度。小有限维数 findim A 定义为所有满足 pd 有限的有限生成模的 pd 的上确界；放宽到全部模则得大有限维数 Findim A，二者分别对应"拆得完的账"在两个口径下的天花板。

**第三级台阶**

定理陈述：存在复数域上一个固定的有限维含幺代数 A，使得对每个整数 m≥1 都有有限维模 N_m 满足 2m−2 ≤ pd_A N_m < ∞。量词顺序是灵魂：A 先于 m 固定，而层数可以任意大——这正是与 Huisgen-Zimmermann 那些"维数有限、代数随 n 变"的例子的分野。各假设分工：A 有限维排除了无穷维的花招；N_m 有限维且投射维数有限，说明这些都是"拆得完"的账，病态恰恰出在上界而非个别模块。结论是 findim A=∞，从而 Findim A=∞；再经 Rickard 定理反推，其内射模不生成无界导出范畴。

## 一句话结论

构造出一个复数域上的有限维代数 `@@M@@A@@`：对任意 `@@M@@m\ge1@@` 都有有限维模 `@@M@@N_m@@` 满足 `@@M@@2m-2\le\pd_A N_m<\infty@@`。同一个代数上有限投射维数无上界，Bass 提出的有限维代数小有限维数猜想（little finitistic-dimension conjecture）被否定。

## 问题背景

对域 `@@M@@k@@` 上的有限维代数 `@@M@@A@@`，其小有限维数（little finitistic dimension）`@@M@@\findim A@@` 是诸有限生成左模中投射维数（projective dimension）有限者的上确界；把范围放宽到所有左模，就得到大有限维数（big finitistic dimension）`@@M@@\Findim A@@`。Bass 于 1960 年普及了这一问题，其猜想断言：每个有限维代数都有 `@@M@@\findim A<\infty@@`。它允许个别投射分解永不终止，只问"会终止的分解"长度是否一致有界。已知的正面情形包括单项代数（monomial algebra）、根基三次幂为零的 Artin 代数与表示维数（representation dimension）至多 `@@M@@3@@` 的代数；Huisgen-Zimmermann 1992 年的例子有 `@@M@@\findim=n@@`、`@@M@@\Findim=n+1@@`，否定了二者相等，但维数仍有限。卡点是：能否在同一个代数上让有限投射维数任意大？本文造出这样的代数，否定猜想。

## 主要结果

主定理：存在复数域上的有限维含幺代数 `@@M@@A@@`，使得对每个整数 `@@M@@m\ge1@@` 都有有限维左 `@@M@@A@@`-模 `@@M@@N_m@@` 满足 `@@M@@2m-2\le\pd_A N_m<\infty@@`。关键在量词顺序：`@@M@@A@@` 先于 `@@M@@m@@` 固定，故其有限生成模有长度无界的终止投射分解，`@@M@@\findim A=\infty@@`；又因小维数不超过大维数，`@@M@@\Findim A=\infty@@`，反驳了 Artin 代数的普遍有限性断言。由 Rickard 定理（内射生成（injective generation）蕴含大维数有限）知其内射左模不生成无界导出范畴。结合 Cummings 的三角矩阵构造还得到极端左右不对称的推论：存在 `@@M@@\Lambda@@`，其左小、大维数均为 `@@M@@\infty@@`，右侧均为 `@@M@@0@@`。

## 证明思路

证明分三步，把"逐次挑选"的群论过程翻译成同调代数，再压进一个固定代数。

第一阶段构造熄灭时间任意长的选择过程（selection process）。文中给出源于 Abels 型矩阵群的有限表现群 `@@M@@G@@`：生成元 `@@M@@T_1,T_2,T_3@@` 共轭时平移三族生成元 `@@M@@U_i(r),V_i(r),W_{ij}(r)@@` 的下标。核心产物是一族中心对合（central involution）`@@M@@z_N=[U_i(a),V_i(b)]@@`（`@@M@@a+b=N@@`），以及把 `@@M@@z_N@@` 平移到 `@@M@@z_{N+1}@@` 的自同构。取群代数（group algebra）`@@M@@R=\mathbb{C} G@@` 与中心幂等元（central idempotent）`@@M@@e=(1+z_0)/2@@`，令 `@@M@@H(Y)={}_\alpha(eY)@@`（取 `@@M@@eY@@` 并拉回作用），迭代满足 `@@M@@H^{\circ j}(Y)\cong{}_{\alpha^j}(e_0\cdots e_{j-1}Y)@@`。对每个 `@@M@@m@@`，用 `@@M@@\F_2[t]/(t^m-1)@@` 上的矩阵造有限商群，使 `@@M@@z_0,\ldots,z_{m-1}@@` 的像独立生成 `@@M@@(\mathbb{Z}/2)^m@@`；再以特征标（character）取模 `@@M@@Y_m@@`，使前 `@@M@@m-1@@` 个幂等元恒等、第 `@@M@@m@@` 个为零，则 `@@M@@H@@` 恰在第 `@@M@@m@@` 次迭代后熄灭。

第二阶段把选择实现为一次导出张量（derived tensor product）。先把 `@@M@@R@@` 的二次表现齐次化为三点有向代数 `@@M@@B@@`，无长度三的路径使 `@@M@@B@@` 有限维且 `@@M@@\gldim B\le2@@`；再在同伦范畴中反转两条特殊箭头，得 Verdier 商（Verdier quotient）范畴，`@@M@@R@@` 作用于其上。障碍有二：幂等元在商范畴中未必分裂，"奇双层"引理表明 `@@M@@U\oplus U[3]@@` 反而同构于真实对象，故改而实现 `@@M@@eY\oplus(eY)[3]@@`；商范畴的态射是分式，需一次性"通分"提升回同伦范畴，关系只余链同伦（chain homotopy）意义。三列微分矩阵把这些同伦编入真实的 `@@M@@B@@`-双模（bimodule）复形 `@@M@@P@@`；无更长路径，故无高阶相干障碍。最后 `@@M@@\gldim B\le2<4@@` 迫使截断三角形分裂，得到对一切 `@@M@@Y@@` 一致的 `@@M@@P\otL_B M(Y)\simeq M(H(Y))\oplus M(H(Y))[3]@@`。

第三阶段换成普通代数。用根基平方零的链代数记录 `@@M@@P@@` 的各项与微分得普通双模，在积代数 `@@M@@D@@` 上取 `@@M@@X@@`，使两步导出张量 `@@M@@F^2@@` 恰是一次实现；再取平方零扩张（square-zero extension）`@@M@@A=D\ltimes X@@`。bar 分解按单词中 `@@M@@X@@` 的个数拆分出 `@@M@@D\otL_A N\simeq\bigoplus_{r\ge0}(F^rN)[r]@@`（`@@M@@X^2=0@@` 保证不混合）。于是 `@@M@@F^{2m}N_m\simeq0@@` 经极小投射分解（minimal projective resolution）与 Nakayama 引理给出 `@@M@@\pd_A N_m<\infty@@`，而 `@@M@@F^{2m-2}N_m\not\simeq0@@` 给出下界 `@@M@@2m-2@@`。

## 可信度与备注

按任务文件标注，本文主结果已通过 Lean 形式化验证。结果族 198 的姊妹篇在特征 `@@M@@2@@` 情形用投射–内射分解的逐次余核独立构造出小、大有限维数均无穷的反例，与本复数域反例方法不同、结论互证。依 OpenAI 官方声明，未经形式化的结果可能存在问题，故文中其余构造细节仍应以社区核验为准。

---

# 深挖 | An algebra of infinite little finitistic dimension

## 深入探讨：像审稿人一样追问 🔍

**问 1：证明中最脆弱的一环在哪里？**

答：第二阶段"对一切 Y 一致"的导出实现。在同伦范畴里反转两条特殊箭头得到 Verdier 商后，幂等元 e 选出的直和项未必自身可提升——奇双层引理（odd-double）只能实现 eY⊕(eY)[3]；态射是分式，须在选定测试模之前对一整张有限图"通分"提升回同伦范畴，且关系只在链同伦意义下成立，还要靠三列微分矩阵"整流"成真正的双模复形。这一连串修补环环相扣，任何一处相容性断裂，一致的 P⊗M(Y)≃M(H(Y))⊕M(H(Y))[3] 就不复存在。

**问 2：哪些假设看似技术性、实则撤掉就崩？**

答：三处。B 无长度三的路径（gldim B≤2）：这保证无高阶相干障碍、且 2<4 的间隙让截断三角形分裂；X 的平方零（A=D⋉X 的平方零扩张）：bar 分解据此按 X 出现次数干净分裂为 ⊕(F^rN)[r]，不发生混合；还有群商取 F₂[t]/(t^m−1) 上的矩阵群：它恰好检测出 m 个中心对合的独立段，少了它"熄灭时间任意长"无从谈起。

**问 3：与已有工作相比真正的新意是什么？**

答：Huisgen-Zimmermann 1992 年的例子 findim=n、Findim=n+1，但维数有限且代数随 n 变化；Green–Kirkman–Kuzmanovich、rad³=0、Igusa–Todorov 表示维数 ≤3 等都是类内有限性。本文首次在单一固定代数上让有限投射维数无界，把六十年悬案整体否定。姊妹篇（特征二、投射–内射逐次余核）方法独立、结论互证。

**问 4：量词顺序为什么是灵魂？**

答：定理是"存在 A，使得对一切 m……"，而非"对一切 m 存在 A"。后者 Huisgen-Zimmermann 已经给出。A 先固定意味着所有 N_m 的极小投射分解都发生在同一屋檐下，天花板概念的失效是系统性的，不是靠换房子堆出来的。

**问 5：AI 生成证明最可能出错的模式？**

答：三阶段拼接（群论选择过程→导出张量→普通代数）之间全靠"相容性"契约维系，而引言自己承认分裂"只对单个对象成立、无自然选择"——逐对象、非函子化的论证正是 AI 高发错误区。移位与维数的换算也极险：F^{2m}N_m≃0 与 F^{2m−2}N_m≠0 之间差两步，对应 pd≥2m−2 的下界，差一次迭代结论就塌。主结果已 Lean 形式化，兜住了大骨架。

**问 6：谁会用到它？**

答：表示论与同调代数社区：它宣告 Igusa–Todorov 型syzygy 不变量方法有本质边界；经 Rickard 定理给出"内射生成失败"的具体代数，直接波及导出范畴与 tilting 理论；结合 Cummings 的等价定理还产出极端左右不对称的推论——一个代数左侧两个维数均为 ∞、右侧均为 0。

## 总评

否定 Bass 六十年猜想、机制横跨群论与导范畴技术，是有分量的一击。最大风险藏在 Verdier 商提升这类"逐图整流"的细致论证里，以及三阶段契约的隐式相容性。

{% endraw %}
