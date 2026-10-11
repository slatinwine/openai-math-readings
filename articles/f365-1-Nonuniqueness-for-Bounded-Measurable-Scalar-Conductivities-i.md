---
layout: default
title: "Nonuniqueness for bounded measurable scalar conductivities in three dimensions"
family: "365"
discipline: "Partial differential equations"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Nonuniqueness for bounded measurable scalar conductivities in three dimensions

> 结果族 365：Joint metric and connection recovery from one boundary patch　·　学科：Partial differential equations　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

医生做 CT：从体外发信号、在体外接收，反推身体内部长什么样。这篇论文研究"电学版 CT"——在三维物体表面加电压、测电流，想推断内部材料导电的难易。结论出人意料：只要材料足够"粗糙"，就存在两种内部截然不同的材料，任何边界电学测量都分不出它们。

**关键词卡片**

- 电导率（conductivity）：材料各处导电的难易程度，正是想探测的内部信息。
- Dirichlet–to–Neumann 算子（Dirichlet-to-Neumann operator）：边界的"电压–电流对照表"，记录每种边界电压对应的全部电流响应。
- Calderón 问题（Calderón problem）：只凭这张对照表能否唯一重建内部电导率。
- 有界可测（bounded measurable）：最弱一档正则性：系数被夹在两个正数之间，可以剧烈震荡，不需要任何导数。
- 非唯一性（nonuniqueness）：不同材料给出逐字相同的对照表。

**看个具体例子**

在半径 3 的球里构造出两个电导率 `@@M@@\gamma_0\ne\gamma_1@@`：都取值于 `@@M@@[c,C]@@`、都在边界附近恒等于 1、在正测度集上不同，却满足 `@@M@@\Lambda_{\gamma_0}=\Lambda_{\gamma_1}@@`。更强的计数版本：区域内放 `@@M@@m@@` 个互不相交的小球，可造出 `@@M@@2^m@@` 个两两不同、共享同一张对照表的电导率——`@@M@@m=3@@` 时便有 8 种"电学双胞胎"。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="32" text-anchor="middle" font-size="16" fill="#333">边界的"电压–电流"测量完全相同</text>
  <circle cx="150" cy="150" r="92" fill="none" stroke="#333" stroke-width="2"/>
  <circle cx="150" cy="150" r="80" fill="none" stroke="#999" stroke-width="1" stroke-dasharray="5 4"/>
  <circle cx="135" cy="132" r="15" fill="none" stroke="#c0392b" stroke-width="2"/>
  <circle cx="172" cy="168" r="11" fill="none" stroke="#c0392b" stroke-width="2"/>
  <path d="M118 178 q16 -12 32 -2 q16 10 32 0" fill="none" stroke="#c0392b" stroke-width="2"/>
  <text x="150" y="265" text-anchor="middle" font-size="14" fill="#333">材料 γ₀（内部结构不同）</text>
  <circle cx="410" cy="150" r="92" fill="none" stroke="#333" stroke-width="2"/>
  <circle cx="410" cy="150" r="80" fill="none" stroke="#999" stroke-width="1" stroke-dasharray="5 4"/>
  <ellipse cx="398" cy="146" rx="36" ry="13" fill="none" stroke="#2471a3" stroke-width="2"/>
  <ellipse cx="422" cy="160" rx="18" ry="26" fill="none" stroke="#2471a3" stroke-width="2"/>
  <text x="410" y="265" text-anchor="middle" font-size="14" fill="#333">材料 γ₁</text>
  <text x="280" y="145" text-anchor="middle" font-size="22" fill="#333">=</text>
  <text x="280" y="205" text-anchor="middle" font-size="12" fill="#666">虚线圈：边界附近两者都恒等于 1</text>
</svg>

</div>

**为什么值得关心**

它给"电学 CT"划出能力红线：光滑材料可被唯一重建，降到有界可测就彻底失效，反问题的正则性门槛由此定界。

> 已 Lean 形式化

## 由浅入深：从类比走向定理

**第一级台阶**

入门导读把这项工作比作"电学 CT"：对象是一个三维的"身体"，内部每一点各有自己的导电难度；操作是在体表加电压、同时测量从体表流出的电流。要问的问题是：把所有可能的加压方案都试一遍并记录全部响应之后，内部的材料分布能否被唯一地"照"出来。

**第二级台阶**

把这句话精确化。设 `@@M@@\Omega@@` 为有界连通的 Lipschitz 区域，电导率 `@@M@@\gamma@@` 是 `@@M@@\Omega@@` 上被两个正常数夹住的有界可测函数——允许剧烈震荡，但不需要任何导数。对每个边界电压 `@@M@@f@@`，方程 `@@M@@\operatorname{div}(\gamma\nabla u)=0@@` 配上边值 `@@M@@u|_{\partial\Omega}=f@@` 有唯一弱解 `@@M@@u_f@@`；把 `@@M@@f@@` 映到相应电流响应的映射，就是 Dirichlet–to–Neumann 算子 `@@M@@\Lambda_\gamma@@`，即那张完整的"电压–电流对照表"。

**第三级台阶**

定理在此语境中陈述：在三维球 `@@M@@B(0,3)@@` 上存在两个这样的电导率 `@@M@@\gamma_0,\gamma_1@@`，都在边界的一个邻域内恒等于 `@@M@@1@@`、在正测度集上不同，但作为 `@@M@@H^{1/2}(\partial B)@@` 到 `@@M@@H^{-1/2}(\partial B)@@` 的有界算子满足 `@@M@@\Lambda_{\gamma_0}=\Lambda_{\gamma_1}@@`。一致正性假设挡住了方程退化、保证每个电压的解存在唯一；边界邻域等于 `@@M@@1@@` 挡住了"差异就在门口"的平庸解释。结论于是意味着：即便对照表完整、即便门口的材料已知，仅有界可测正则性时重建仍然失败。

## 一句话结论
在三维球上构造出两个不同的有界可测标量电导率（一致正、都在边界附近等于 1），它们的完整 Dirichlet–to–Neumann 算子却完全相同：仅有有界可测正则性时，标量 Calderón 唯一性在三维即告失败。

## 问题背景
Calderón 1980 年正是对有界可测、一致正的标量电导率（scalar conductivity）提出确定问题。`@@M@@n\ge3@@` 的光滑情形由 Sylvester–Uhlmann 证明唯一性，此后正则性要求一路下调：Haberman 达到 `@@M@@W^{1,n}@@`，Caro–Rogers 达到 Lipschitz；二维情形 Astala–Päivärinta 证明了有界可测唯一性。但三维及以上在"有界可测、无任何导数假设"层面是否有唯一性长期未决，本文给出否定回答，并说明对所有 `@@M@@n\ge3@@` 量化的唯一性命题为假。它与同族两篇光滑唯一性文章形成鲜明对照：光滑时一个补丁就够，可测时全边界也不唯一。

## 主要结果
**定理**：存在实值函数 `@@M@@\gamma_0,\gamma_1\in L^\infty(B(0,3))@@` 与常数 `@@M@@0<c<C<\infty@@`，使得：`@@M@@c\le\gamma_j\le C@@` 几乎处处；两者都在边界的一个邻域内恒等于 1；`@@M@@\gamma_0\ne\gamma_1@@` 于正测度集；且作为 `@@M@@H^{1/2}(\partial B)\to H^{-1/2}(\partial B)@@` 的有界算子，全弱意义 DN 算子（Dirichlet-to-Neumann operator）满足 `@@M@@\Lambda_{\gamma_0}=\Lambda_{\gamma_1}@@`。**推论（局部化非唯一性）**：任一有界连通 Lipschitz 区域内任取 `@@M@@m@@` 个两两不交的球，可造 `@@M@@2^m@@` 个两两不同的一致正有界可测电导率（球外恒为 1），共享同一个全边界 DN 算子。

## 证明思路
构造分三层。第一层是**精确标量化定理**（finite-field scalarization）：在局部光滑与梯度秩条件下，把一致椭圆对称张量 `@@M@@A@@` 连同两个指定解 `@@M@@u_1,u_2@@` 替换为一个有界正的标量系数 `@@M@@\gamma@@`，同时精确保持两个解的边界迹与整条法向通量泛函——这是对两个指定输入的完整响应，而非同质化近似。工具是坐标联结（coordinate join）的积式树叶分层（Marino–Spagnolo 式各向同性逼近的经典算术）、Raiță 多项式位势法产生的局部化通量波逐次修正，以及 Kirchheim 开创、Astala–Faraco–Székelyhidi 移植到椭圆方程的 Baire 连续点论证，用以选取满足两条本构关系的强极限。第二层造**分岔块**（branching block）：一个边界由三个环面（一亲两子）组成的区域，各配一个概率测度；标量化后它能实现任何零和电流三元组 `@@M@@p=(p_0,p_-,p_+)@@`，通量恰为 `@@M@@p_i@@` 乘相应测度。块内先在柱形平坦端上解变分问题，跨"秩一墙"修正小残差，再把一个衰减模通过逐次倍增的角频率转移到有限距离处消失，使两个电流向量张成零和平面。第三层把块按相似比 `@@M@@s@@`（`@@M@@2s^3<1@@`，保证剩余嵌套集零体积）自相似地嵌满球内，定义全局 `@@M@@\gamma@@`。对任一有界 `@@M@@\gamma@@`-调和函数 `@@M@@u@@`，用块位势作检验并由互易性得三个表面平均与零和平面正交、故相等，迭代推出 `@@M@@u@@` 在所有胞腔表面共享同一平均 `@@M@@u_*@@`。随后赋予符号电荷（每层总量恒为 2），相应级数在 `@@M@@L^\infty@@` 与 `@@M@@H^1@@` 中收敛到非零位势 `@@M@@w\in H^1_0\cap L^\infty@@`，支集远离外边界。关键恒等式在于：`@@M@@w@@` 的源虽然非零，却在一切乘积 `@@M@@(u-u_*)\phi@@`（`@@M@@u@@` 有界调和、`@@M@@\phi@@` 光滑紧支）上消失，这由公共平均与胞腔直径按 `@@M@@s^N@@` 缩小保证。于是取 `@@M@@\rho=1+\delta w@@`（`@@M@@\tfrac12\le\rho\le\tfrac32@@`）、`@@M@@\tilde\gamma=\rho^2\gamma@@`、`@@M@@\tilde u=u_*+(u-u_*)/\rho@@`：直接计算得通量 `@@M@@\tilde\gamma\nabla\tilde u=\rho\gamma\nabla u-(u-u_*)\gamma\nabla\rho@@` 无散，且外领区内 `@@M@@\rho=1@@`，边界响应不变；光滑边值的调和延拓有界，再由稠密性把等式扩张到整个 DN 算子。与依赖奇异变换的隐身构造不同，这里电导率始终一致椭圆，两个电导率在正测度集上确有差别。

## 可信度与备注
本文是族内唯一主结果已获 Lean 形式化证明的一篇，可信度最高。它为同族两篇光滑唯一性定理划出了正则性边界：从 `@@M@@C^\infty@@`（甚至 Lipschitz）降到有界可测，三维标量 Calderón 问题由唯一翻转为不唯一。据 OpenAI 官方声明，未经形式化的结果可能存在问题；本篇不在其列。

---

## 深入探讨：像审稿人一样追问 🔍

**问 1：从"块只控制有限个输入"走到"整个 DN 算子相等"，证明中最脆弱的一步在哪里？**

（答：在源消没恒等式。级数位势 `@@M@@w@@` 的源并非为零，却在一切乘积 `@@M@@(u-u_*)\phi@@`（`@@M@@u@@` 为有界 `@@M@@\gamma@@`-调和、`@@M@@\phi@@` 光滑紧支）上积分为零——引言明言这是"从块的有限受控输入到完整反问题的一步"。若此恒等式失效，构造至多匹配有限个输入，恰如 Rondi 引用的圆盘例子：`@@M@@\diag(a,b)@@` 是标量系数的 `@@M@@H@@`-极限，却没有相同边界映射的一致正标量代表。）

**问 2：两个电导率都要求在边界附近恒等于 1，这个假设能去掉吗？**

（答：论文未讨论其必要性。它在构造中承担具体功能：变换因子 `@@M@@\rho=1+\delta w@@` 支集远离外边界，故外领区内新旧解与通量逐点相同。作为结论的一部分它反而是加强项——即便把门口材料告知测量者，非唯一性依旧。）

**问 3：与已有隐身/非唯一构造相比，真正的新意是什么？**

（答：此前的各向异性反例（Miller 构造及 Daudé–Kamran–Nicoleau）依赖退化或奇异的变换；本文给出标量、一致椭圆、全边界数据下的精确非唯一。Marino–Spagnolo 的积式树叶、Raiță 的多项式位势、Kirchheim–Astala–Faraco–Székelyhidi 的 Baire 论证只是方法先例；同时对两个指定解保持完整 Cauchy 数据的精确标量化定理（第 3 节）是本文证明的。）

**问 4：Haberman 的 `@@M@@W^{1,n}@@` 与 Caro–Rogers 的 Lipschitz 唯一性为何止步？论文解释机制了吗？**

（答：论文未正面分析唯一性证明的障碍，但构造暗示了机制：可测系数允许振荡逼近（`@@M@@G@@`-收敛式树叶分层）在有限个场上变成精确等式。正则性门槛由此被两端夹住——Lipschitz 以上唯一、`@@M@@L^\infty@@` 不唯一，中间的正则性带在本文中保持开放。）

**问 5：作为 AI 生成的证明，最可能出错的模式是什么？**

（答：按 OpenAI 声明，未形式化结果可能存在问题；本文主定理已获 Lean 形式化，是族内可信度最高的一篇。残余风险集中在形式化未必覆盖的部分：局部化推论（`@@M@@2^m@@` 个电导率）里"复制入球并在界面迹上极小化能量"的论证，以及技术引理与形式化陈述的逐字吻合度——论文本身未说明形式化的确切范围。）

**问 6：为什么只在三维球上构造？四维及以上自动成立吗？**

（答：论文明确说明定理"不宣称在每个更高维给出构造"：三维的反例已足以否定"对一切 `@@M@@n\ge3@@` 的量化唯一性命题"，但 `@@M@@n\ge4@@` 的可测标量 Calderón 问题在本文中悬而未决。）

**问 7：谁会用到这个结果？**

（答：反问题正则性理论——它把标量 Calderón 问题从"光滑下唯一"推到"有界可测下不唯一"，为后续唯一性研究划线；电阻抗成像（EIT）的算法与稳定性理论则得到一条能力红线：可测正则性下不存在任何唯一重建。）

**总评**

这是把 Calderón 问题正则性门槛钉死在下端的一篇硬构造，主定理有 Lean 形式化背书，分量十足；最大风险在形式化范围之外的技术引理与局部化推论。

{% endraw %}
