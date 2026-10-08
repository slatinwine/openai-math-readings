---
layout: default
title: "Weak and strong normalization in pure type systems"
family: "245"
discipline: "Mathematical logic"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Weak and strong normalization in pure type systems

> 结果族 245：Weak normalization implies strong normalization in pure type systems　·　学科：Mathematical logic　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

化简 (2+3)×4 时，可以先算括号再乘，也可以先分配展开——不同走法都到 20。"每个式子至少有一条路能算到底"叫弱规范化；"随便怎么乱走都必然算到底"叫强规范化。本文证明：对纯类型系统这一大类类型系统，前者一旦成立，后者自动成立。

**关键词卡片**

- 纯类型系统（pure type system, PTS）：统一描述一大类 λ 演算类型系统的框架，简单类型 λ 演算、System F、构造演算都是特例。
- β-归约（β-reduction）：把 (λx.M)N 一步代入化简的基本动作。
- 弱／强规范化（weak/strong normalization）：存在某条归约路径到达范式／任何归约序列都必然终止。
- 范式（normal form）：再也化不动的最简形态。

**看个具体例子**

看玩具：下图中两条化简走法都终止于同一个范式。定理说，只要系统中每个合法表达式都"有路可走"（弱），就不存在任何能无限走下去的表达式（强）——哪怕专挑刁钻顺序乱化简。这解决了 Geuvers 1993 年提出的 β-Barendregt–Geuvers–Klop 猜想，此前所有结果都需要分层、泛函性等附加条件。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><rect x="200" y="28" width="160" height="42" fill="none" stroke="#2c7fb8" stroke-width="2"/><text x="280" y="54" font-size="14" fill="#333" text-anchor="middle">(λx.x+x)(2+1)</text><rect x="60" y="118" width="150" height="42" fill="none" stroke="#2c7fb8" stroke-width="2"/><text x="135" y="144" font-size="14" fill="#333" text-anchor="middle">(2+1)+(2+1)</text><rect x="350" y="118" width="150" height="42" fill="none" stroke="#2c7fb8" stroke-width="2"/><text x="425" y="144" font-size="14" fill="#333" text-anchor="middle">(λx.x+x)3</text><text x="140" y="102" font-size="13" fill="#666" text-anchor="middle">先分配展开</text><text x="425" y="102" font-size="13" fill="#666" text-anchor="middle">先算括号</text><rect x="205" y="196" width="150" height="42" fill="none" stroke="#2c7fb8" stroke-width="2"/><text x="280" y="222" font-size="14" fill="#333" text-anchor="middle">3+3</text><line x1="245" y1="70" x2="182" y2="114" stroke="#666" stroke-width="1.8"/><line x1="315" y1="70" x2="378" y2="114" stroke="#666" stroke-width="1.8"/><line x1="185" y1="160" x2="247" y2="194" stroke="#666" stroke-width="1.8"/><line x1="375" y1="160" x2="313" y2="194" stroke="#666" stroke-width="1.8"/><line x1="280" y1="238" x2="280" y2="252" stroke="#666" stroke-width="1.8"/><polygon points="280,260 276,250 284,250" fill="#666"/><text x="280" y="276" font-size="14" fill="#c0392b" text-anchor="middle">6（范式）</text></svg>

</div>

**为什么值得关心**

强规范化是证明助手类型检查必然终止的逻辑基石；此结果在最大的一般性下把"弱"与"强"之间的鸿沟填平。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了对任意纯类型系统（pure type system），只要每个合法表达式都弱 β-规范化，就必然强 β-规范化：一切 β-归约序列终止。这一举解决了 Geuvers 1993 年提出的 β-Barendregt–Geuvers–Klop 猜想，且对公理与乘积规则不加任何泛函性假设。

## 问题背景

纯类型系统（Pure Type System, PTS）是 Barendregt 创立的统一框架，由排序（sorts）、公理（axioms）与乘积规则（product rules）构成的三元组 `@@M@@\mathcal P=(\mathcal S,\mathcal A,\mathcal R)@@` 指定，简单类型 λ-演算、System F、构造演算都是其特例。弱规范化（weak normalization）指每个合法表达式*存在某条*归约路径到达范式；强规范化（strong normalization）指*任何*归约序列都有限。对证明助手与语言实现，强规范化保障类型检查可终止、逻辑可靠。Geuvers 在 1993 年博士论文（猜想 8.1.2）中提出系统层面的猜想：弱规范化蕴含强规范化。此前最好的结果——Sørensen 的续译（CPS）构造、Barthe–Hatcliff–Sørensen 与 Mull 的非依赖及分层定理、Roux–van Doorn 与 Mull 的结构变换——无不依赖 sort 层级、泛函规则或可否定性（negatability）等附加条件；而一般规格连类型唯一性都不成立，既有的保型翻译路线全部失效。

## 主要结果

定理（β-Barendregt–Geuvers–Klop 猜想）：设 `@@M@@\mathcal P=(\mathcal S,\mathcal A,\mathcal R)@@` 为任意纯类型系统。若在每个合法上下文（valid context）中，`@@M@@\mathcal P@@` 的每个合法表达式（legal expression，即可导出类型判断的主目或类型一侧）都弱 β-规范化，则每个这样的表达式都强 β-规范化。归约作用于全标注语法（full annotated syntax）：允许在 λ-抽象的类型标注内部及 Π-类型的两个分量内部归约；上下文可以是开的。定理不要求 `@@M@@\mathcal A@@`、`@@M@@\mathcal R@@` 具有泛函性（functionality）。还需注意量词的层次：两个性质都是对整个系统量化的，定理并不断言"单个拥有范式的项强规范化"——证明中可以使用*其他*表达式的弱规范性；结论仅关于 β-归约，不涉及 η。

## 证明思路

先做约化并搭好基础设施：反例的类型推导只用到有限多个 sort 与规则，故可化归到有限规格；在弱规范化假设下用并行收缩与完全展开（complete development）的标准方法证合流性（confluence），于是每个合法表达式有唯一范式 `@@M@@M^\#@@`。关键新工具是"sort 剖面"（sort profile）`@@M@@\pi_\Gamma(T)=\{s:\Gamma\vdash T^\#:s\}@@`，即正规类型可打上的全部 sort 之集：以集合代替单一 sort，恰好绕开非泛函规格下类型不唯一的困难；代替类型唯一性的，是剖面在类型化代换下只增不减。可行剖面构成一个有限带号有向图：每个乘积三元组 `@@M@@(I,J,K)@@` 贡献负边 `@@M@@I\to K@@` 与正边 `@@M@@J\to K@@`，对应"域反转包含、陪域保持包含"的对偶变异性。

再沿 Tait–Girard 可归约性候选（reducibility candidates）路线推进：候选是夹在"通过一切测试栈的项集 `@@M@@G_T@@`"与"强规范化项集 `@@M@@\top_T@@`"之间、对头部展开（head expansion）封闭的集合；论文显式建立其完全格与乘积测试性质，而不要求归约封闭性。每个强连通分量只需实现三条件接口——不变性、双向的乘积等式、特化性——一条传输引理即可把不变式 `@@M@@G_T=\top_T@@` 在该分量上建立；所有分量处理完后取极小反例，它必是应用 `@@M@@f\,n@@` 且两个分量已强规范化，与 `@@M@@G_T=\top_T@@` 矛盾。

最后分而治之：无奇闭路的分量按奇偶赋号，在混合包含序的格上以 Tarski 不动点定理解方程；无全内部剖面三元组的分量用比特参数化的极值候选加支撑/极性追踪；剩下的困难分量采用"观察空间"（observation spaces）构造，其定义方程循环，对部分剖面用良基递归（well-founded recursion）、其余用交替有限阶段求解，并对固定项的所有观察给出一致有界。该构造条件于一个图排除：若禁止构型当真出现，其中的乘积规则便足以支撑一个小型公式演算，并按 Geuvers 的表述实现 Hurkens 良基悖论的关系版本，构造出带证明/数据模式标签的项 `@@M@@P:F_b@@`；另一方面，擦除（erasure，保留全部类型标注、只删模式标签）使普通归约可提升回带标签层，弱规范化便给出 `@@M@@P@@` 的正规擦除，这与"该上下文中不存在带正规擦除的证明模式项"的直接语法下降引理冲突。矛盾排除构型，接口补全，主定理得证。

## 可信度与备注

本篇是结果族 245 的主文，主结果暂无 Lean 形式化证明，请以社区核验为准；论文对所用元理论（合流性、主体归约、类型化代换、生成引理等）均给出完整证明，并采用"接口—实现"分离的结构，便于逐层审查。依据 OpenAI 官方声明，未经形式化的结果可能存在问题。文献中已确立的非依赖与分层特例（Sørensen、Barthe–Hatcliff–Sørensen、Mull 等）与本文主定理相容，可视为旁证；猜想更强的 βη-版本仍未解决。

{% endraw %}
