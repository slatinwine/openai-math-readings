---
layout: default
title: "Constant-factor hardness of uniform sparsest cut"
family: "117"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Constant-factor hardness of uniform sparsest cut

> 结果族 117：Uniform sparsest cut: hardness and semidefinite gaps　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

办派对要把嘉宾分进两个厅，横跨两厅的"老交情"会被拆散。主办方想选一种分法，让"被拆断的交情总重 ÷ 被拆散的人数对"尽量小——这就是最稀疏割。论文证明：哪怕只想要一个固定倍数（比如 1.01 倍）的近似方案，这问题也已经和最难的 NP 问题一样无望。

**关键词卡片**

- 最稀疏割（sparsest cut）：把图分成两块，最小化"跨割容量 ÷ 被拆散点对数"。
- 均匀需求（uniform demand）：每对不同顶点间需求都是 1 的设定。
- NP-难（NP-hard）：若能多项式时间解决它，就能解决一切 NP 问题。
- 不可近似性（hardness of approximation）：连"近似到固定倍数"都做不到的更强难度。
- 无条件（unconditional）：不依赖唯一博弈猜想等任何未证明的复杂度假设。

**看个具体例子**

定义 `@@M@@\Phi(G)=\min_S\ \frac{\text{跨割边容量和}}{|S|\,(N-|S|)}@@`。拿 4 点方框图（每条边容量 1）试刀：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <circle cx="180" cy="80" r="20" fill="none" stroke="#333" stroke-width="2"/>
  <text x="180" y="86" text-anchor="middle" font-size="15">1</text>
  <circle cx="360" cy="80" r="20" fill="none" stroke="#333" stroke-width="2"/>
  <text x="360" y="86" text-anchor="middle" font-size="15">2</text>
  <circle cx="360" cy="210" r="20" fill="none" stroke="#333" stroke-width="2"/>
  <text x="360" y="216" text-anchor="middle" font-size="15">3</text>
  <circle cx="180" cy="210" r="20" fill="none" stroke="#333" stroke-width="2"/>
  <text x="180" y="216" text-anchor="middle" font-size="15">4</text>
  <line x1="200" y1="80" x2="340" y2="80" stroke="#333" stroke-width="2"/>
  <line x1="360" y1="100" x2="360" y2="190" stroke="#333" stroke-width="2"/>
  <line x1="340" y1="210" x2="200" y2="210" stroke="#333" stroke-width="2"/>
  <line x1="180" y1="190" x2="180" y2="100" stroke="#333" stroke-width="2"/>
  <line x1="270" y1="45" x2="270" y2="245" stroke="#c00" stroke-width="2" stroke-dasharray="8,6"/>
  <text x="270" y="32" text-anchor="middle" font-size="14">割：左厅 {1,4}，右厅 {2,3}</text>
  <text x="55" y="150" font-size="13">左半 2 点</text>
  <text x="465" y="150" font-size="13">右半 2 点</text>
  <text x="280" y="268" text-anchor="middle" font-size="13">切断容量 1+1=2，拆散点对 2×2=4，比值 2/4 = 1/2</text>
</svg>

</div>

切 `@@M@@\{1,4\}@@`：跨割容量 `@@M@@2@@`，拆散 `@@M@@4@@` 对，比值 `@@M@@\tfrac12@@`；切单点 `@@M@@\{1\}@@`：容量 `@@M@@2@@`，拆散 `@@M@@3@@` 对，比值 `@@M@@\tfrac23@@`。故此图 `@@M@@\Phi(G)=\tfrac12@@`。定理说：对任何固定 `@@M@@C>1@@`，从 3-SAT 出发能造出图，满足"公式可满足则 `@@M@@\Phi\le a@@`，不可满足则 `@@M@@\Phi>Ca@@`"——区分二者是 NP-难的。

**为什么值得关心**

均匀需求是最难啃的情形：分母只依赖割的大小，无法借需求结构制造间隙。此前的近似下界都背着"复杂度假设"的包袱，本文第一次无条件封死了均匀最稀疏割的常数比近似，其证明链横跨函数域塔、PCP 式比特测试与有理装配，堪称组合构造的重型机械。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
证明对任意固定 `@@M@@C>1@@`，把均匀最稀疏割近似到 `@@M@@C@@` 因子是 NP-难的，且实例容量为非负有理数、每对不同顶点需求恰为 `@@M@@1@@`。这是不依赖任何复杂度假设的常因子不可近似性，封死了该问题的多项式时间常数比近似。

## 问题背景
均匀最稀疏割（uniform sparsest cut）问：给定带非负容量 `@@M@@c_{ij}@@` 的图，求非空真割 `@@M@@S@@`，使跨越容量与被分离点对数之比 `@@M@@\Phi(G)=\min_{S}\frac{\sum_{i\in S,j\notin S}c_{ij}}{|S|(N-|S|)}@@` 最小，即每对顶点需求恰为 `@@M@@1@@`。它是图划分的范式问题，经多商品流与半定规划（semidefinite programming）分别催生 Leighton–Rao 的 `@@M@@O(\log N)@@` 与 Arora–Rao–Vazirani 的 `@@M@@O(\sqrt{\log N})@@` 近似。精确求解的 NP 难度早已知晓（Matula–Shahrokhi 1990；Bonsma 等 2012），但"常数因子近似是否可能"长期悬而未决：此前的近似下界全部依赖复杂度假设——PTAS 会给出 `@@M@@2^{n^\varepsilon}@@` 时间的 SAT 算法（Ambühl–Mastrolilli–Svensson）；小集合扩张假设下有平衡分离器的常因子间隙（Raghavendra–Steurer 及 RST）；唯一博弈猜想（Unique Games Conjecture）下有非均匀版本的常因子硬度（Chawla 等）。均匀需求的特殊困难在于分母只依赖 `@@M@@|S|@@`，无法借需求结构制造间隙，而且割可以任意小，一切误差必须相对被分离的需求而非固定容差来控制。

## 主要结果
主定理：对每个固定实常数 `@@M@@C>1@@`，存在从 3CNF 可满足性到有限无向图的多项式时间归约，输出非负有理容量、每对不同顶点需求恰为 `@@M@@1@@` 的图以及正有理阈值 `@@M@@a@@`：公式可满足则 `@@M@@\Phi(G)\le a@@`，不可满足则 `@@M@@\Phi(G)>Ca@@`。归约不使用任何未证明的复杂度假设；图规模与所有输出数的二进制位数均为公式规模的多项式（指数可依赖 `@@M@@C@@`）。因此，对均匀最稀疏割做任意固定因子的近似都是 NP-hard 的，除非 `@@M@@P=NP@@`。

## 证明思路
归约分四个接口：满足赋值给出低费用割；反之，费用相对其被分离需求很小的割必须解码出满足赋值。难点是被分离需求可以任意小。

先构造代数测试系统：核心是"二次求值铅笔"（quadratic evaluation pencil）引理——用 Garcia–Stichtenoth 函数域塔（function field tower）构造列表 `@@M@@u_1,\dots,u_m\in\mathbb F_q^d@@`，长度 `@@M@@m=O(d)@@`、含全部标准基向量，且任何不在此列表上恒零的齐次二次型至多在 `@@M@@\lambda_0 m@@` 个点取零。证明通过塔在各奇点的局部分支分析、整格判别式阶与受控极点函数空间的维数下界完成零点计数；应用时 `@@M@@d=O(\log n)@@`，构造时间为多项式。

再基于此构建比特测试（属 PCP 框架）：各查询概率受一致界控制，辅助的奇偶查询律有精确均匀边际与强混合性；谓词（predicate）是整个证明位指派的布尔函数，估值（valuation）须满足校准（calibration，均值符合规定）与保序；文中证明近似校准、近似保序的估值能解码出满足赋值。

关键一步是稀有事件提取：考察布尔响应 `@@M@@W@@` 在 `@@M@@t@@` 个独立采样谓词之合取上的表现，其成功概率可小至 `@@M@@p_*^t@@`。条件于成功并暴露公共前缀，得到近极端熵的密度；与常一谓词比较，再经显式截断把密度逼向 `@@M@@0@@` 与某个固定正常数两值；取一个前缀加一个阈值，即得同时满足全部校准与比较律的单一估值，且常数不依赖谓词个数与最小原子概率。

再从割方差导出成功事件：分数（score）是依赖有界多个证明位的有界实函数，候选割是分数的可测 `@@M@@\{0,1\}@@` 染色，需求律度量染色方差 `@@M@@\nu=\mathrm{Var}_\mu(h)@@`，比较测度对分数对的分歧收费。需求分数是多个尺度上独立随机振幅的稀有谓词之和：小的重采样代价迫使染色保留至少一个振幅的信号，平滑比较路径把信号传递成上述成功合取响应，且一切误差都与 `@@M@@\nu@@` 成比例，故对任意小的正需求质量有效。

最后装配有限图：把分数取整到有理网格得到"键"（key，真值表加本质位名表）；有理编译引理给出容量的有理上逼近（总盈余 `@@M@@\le 1@@`）与需求的有理下质量（总损失 `@@M@@\le 10^{-6}@@`）；键按质量复制成顶点簇，簇内重边禁止割裂，零质量键以系绳边挂到需求上；方差转移不等式把小割转成与可靠性矛盾的染色；完备性由随机阈值割给出，全程保持精确分母 `@@M@@|S|(N-|S|)@@`。

## 可信度与备注
本文暂无形式化证明，请以社区核验为准；其证明链横跨函数域塔、PCP、熵截断与有理积分，技术环节极多，社区复核尤为重要。姊妹篇（结果族 117 另一篇）从正面构造 Goemans–Linial SDP 的 `@@M@@\sqrt{\log n}/(\log\log n)^3@@` 积分间隙且已 Lean 形式化，两者互补：本文说没有多项式时间的常因子近似算法，姊妹篇说标准半定松弛本身也做不到常数比。按 OpenAI 官方声明，未经形式化的结果可能有问题，本文恰属此类，宜以审慎态度等待核验。

{% endraw %}
