---
layout: default
title: "An exponential two-way deterministic state lower bound for one-way liveness"
family: "129"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | An exponential two-way deterministic state lower bound for one-way liveness

> 结果族 129：Exponential state costs for two-way automata　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

想象一个多层迷宫：从第 1 层的某个门出发，沿"允许的跳转"一路走到最后一层就算赢。会"猜路"的读者（非确定自动机）只需 `@@M@@h+3@@` 张便签就能应付层数为 `@@M@@h@@` 的这类题；而每步只有一种走法、虽然可以来回翻页重看的读者（双向确定自动机），便签数量必须随 `@@M@@h@@` 指数增长——这正是 1978 年 Sakoda–Sipser 状态简洁性问题第一个完全不受限的指数答案。

**关键词卡片**

- 双向确定自动机（two-way deterministic automaton）：读头可左右移动、每步走法唯一的识别器，状态数就是它的"便签"数。
- 非确定自动机（nondeterministic automaton）：每步可同时"猜"多条走法的识别器，猜中一条即算接受。
- 单向活性（one-way liveness）：给一串二元关系（层与层之间允许的跳转），问是否存在一条贯通路径。
- 状态数下界（state lower bound）：证明任何等价的确定机器至少需要多少状态。

**看个具体例子**

把 4 层、每层 3 个点的关系串画出来：只要存在一条从左到右的贯通路径（红线），这个字就被接受。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="26" text-anchor="middle" font-size="16" fill="#333">单向活性：一串关系层里有没有一条贯通的路？</text><line x1="80" y1="90" x2="220" y2="90" stroke="#bbb" stroke-width="2"/><line x1="80" y1="90" x2="220" y2="150" stroke="#bbb" stroke-width="2"/><line x1="80" y1="210" x2="220" y2="150" stroke="#bbb" stroke-width="2"/><line x1="220" y1="90" x2="360" y2="90" stroke="#bbb" stroke-width="2"/><line x1="220" y1="210" x2="360" y2="90" stroke="#bbb" stroke-width="2"/><line x1="220" y1="150" x2="360" y2="210" stroke="#bbb" stroke-width="2"/><line x1="360" y1="90" x2="500" y2="90" stroke="#bbb" stroke-width="2"/><line x1="360" y1="90" x2="500" y2="150" stroke="#bbb" stroke-width="2"/><line x1="360" y1="210" x2="500" y2="150" stroke="#bbb" stroke-width="2"/><line x1="80" y1="210" x2="220" y2="150" stroke="#d62728" stroke-width="4"/><line x1="220" y1="150" x2="360" y2="210" stroke="#d62728" stroke-width="4"/><line x1="360" y1="210" x2="500" y2="150" stroke="#d62728" stroke-width="4"/><circle cx="80" cy="90" r="8" fill="#fff" stroke="#345" stroke-width="1.5"/><circle cx="80" cy="150" r="8" fill="#fff" stroke="#345" stroke-width="1.5"/><circle cx="80" cy="210" r="8" fill="#fdd" stroke="#345" stroke-width="1.5"/><circle cx="220" cy="90" r="8" fill="#fff" stroke="#345" stroke-width="1.5"/><circle cx="220" cy="150" r="8" fill="#fdd" stroke="#345" stroke-width="1.5"/><circle cx="220" cy="210" r="8" fill="#fff" stroke="#345" stroke-width="1.5"/><circle cx="360" cy="90" r="8" fill="#fff" stroke="#345" stroke-width="1.5"/><circle cx="360" cy="150" r="8" fill="#fff" stroke="#345" stroke-width="1.5"/><circle cx="360" cy="210" r="8" fill="#fdd" stroke="#345" stroke-width="1.5"/><circle cx="500" cy="90" r="8" fill="#fff" stroke="#345" stroke-width="1.5"/><circle cx="500" cy="150" r="8" fill="#fdd" stroke="#345" stroke-width="1.5"/><circle cx="500" cy="210" r="8" fill="#fff" stroke="#345" stroke-width="1.5"/><text x="80" y="248" text-anchor="middle" font-size="14" fill="#555">第 1 层</text><text x="220" y="248" text-anchor="middle" font-size="14" fill="#555">第 2 层</text><text x="360" y="248" text-anchor="middle" font-size="14" fill="#555">第 3 层</text><text x="500" y="248" text-anchor="middle" font-size="14" fill="#555">第 4 层</text><text x="280" y="274" text-anchor="middle" font-size="13" fill="#777">灰线：关系允许的跳转；红线：一条"活"路径 ⇒ 接受</text></svg>

</div>

非确定机沿红线"猜"着走，只要 `@@M@@h+3@@` 个状态；论文证明任何等价的双向确定机状态数 `@@M@@s@@` 必须满足 `@@M@@4(s+2)^2\ge 2^{\lfloor (h-2)/31\rfloor}@@`：`@@M@@h@@` 每加 31，需求就翻倍。代入 `@@M@@h=1862@@`：非确定机用 1865 个状态，确定机却至少要 `@@M@@2^{29}-2\approx 5.4@@` 亿个。字母表随 `@@M@@h@@` 增长（全部 `@@M@@h\times h@@` 二元关系），故结论是：不存在与字母表无关的多项式确定化模拟。

**为什么值得关心**

非确定性到底"贵不贵"是自动机理论四十多年的核心悬案；本文证明在状态数量上它本质昂贵，允许读头来回移动也救不了确定机器。

> 已 Lean 形式化

## 一句话结论

论文在增长的有限字母表上解决了 Sakoda–Sipser 状态简洁性问题：单向活性语言有 `@@M@@h+3@@` 状态、不用左移的非确定自动机，而任何等价的 `@@M@@s@@` 状态双向确定自动机满足 `@@M@@4(s+2)^2\ge2^{\lfloor(h-2)/31\rfloor}@@`，指数下界排除了与字母表无关的多项式确定化模拟。

## 问题背景

Rabin–Scott 与 Shepherdson 在 1959 年证明双向确定自动机识别的语言类与单向有限自动机相同，但允许读头回访符号可能大幅节省所需的有限控制。Sakoda 与 Sipser 1978 年由此提出核心的状态简洁性问题：把（单向或双向）非确定自动机转换为双向确定自动机需要多少状态？若存在多项式模拟，非确定性在这种度量下就是"廉价"的。此前的指数下界都限制确定目标的运动方式：Sipser 1980 年只对只能在端标记折返的扫掠式（sweeping）机器、Kapoutsis 2013 年对亚线性折返次数成立；对不受限制的双向确定目标，已知最好结果是 Chrobak 在单字母语言上的二次下界、Kapoutsis 2018 年对三字母承诺版本的 `@@M@@\Theta(h^2/\log h)@@`，以及 Adeogun–Kapoutsis 2026 年对单向活性的二次下界——后者还证明了自己的构造方法存在二次天花板。本文突破天花板，对完全不受限的确定目标给出指数下界。

## 主要结果

对 `@@M@@h\ge2@@`，字母表取 `@@M@@[h]=\{1,\ldots,h\}@@` 上全部二元关系（共 `@@M@@2^{h^2}@@` 个符号，随 `@@M@@h@@` 增长）。单向活性（one-way liveness，即 Sakoda–Sipser 的完全族 `@@M@@B_h@@`）语言 `@@M@@\OWL_h@@` 由满足按路径序乘积 `@@M@@R_1\cdots R_\ell\ne0@@` 的关系字组成。主定理：`@@M@@\OWL_h@@` 有 `@@M@@h+3@@` 状态、无左移的非确定自动机；而任何等价的 `@@M@@s@@` 状态双向确定自动机满足 `@@M@@4(s+2)^2\ge2^{\lfloor(h-2)/31\rfloor}@@`（若初始接受格局即计为接受，`@@M@@s+2@@` 可改进为 `@@M@@s+1@@`）。模型允许部分转移函数、停留移动和非接受的无限计算。取 `@@M@@n=h+3@@`，确定等价机至少需 `@@M@@2^{\frac12\lfloor(n-5)/31\rfloor-1}-2@@` 个状态，超过任何固定的 `@@M@@Cn^c@@`，故不存在与字母表无关的多项式模拟界。

## 证明思路

整个证明比较匹配图次数 `@@M@@k@@` 的上下两个界。第一步把确定机器局部编码进 Brauer 图幺半群（Brauer diagram monoid）`@@M@@\D{k}@@`：元素是左右各 `@@M@@k@@` 个端口上的完美匹配（perfect matching），乘法粘合相邻端口并收缩路径。构造上先新增一个汇状态 `@@M@@f@@`，把"接受"转化为从初始格局 `@@M@@c_0@@` 到指定格局 `@@M@@t@@` 的可达性；确定性使每个格局至多一个后继，因此 `@@M@@t@@` 所在的无向连通分量为树。给树的每条边配两个方向的"车道"，在每个顶点按入射的循环序把进站车道接到下一条出站车道，得到绕树一整圈的单一巡回（tour）——这一遍历手法承自 Sipser 的停机方法与 Lange–McKenzie–Tapp 的可逆模拟。难点是让每个格子的接线只依赖自身符号：在每个边界为每个可能的转移三元组预留"候选槽位"（candidate slot），未使用的槽位挂到专设的新鲜叶子上，加上左右端标记外侧引出的两条测试边，端口数共 `@@M@@k=4(s+2)^2@@`。接受当且仅当全输入图的乘积把左测试口与右测试口配对，等价于两个测试叶位于同一棵树。

第二步建立商映射：若两个字 `@@M@@u,v@@` 的图相同而关系乘积在某对 `@@M@@(i,j)@@` 上不同，用单点关系字母 `@@M@@\Id{\{i\}}@@`、`@@M@@\Id{\{j\}}@@` 作上下文即可使一个属语言而另一个不属，与图的上下文不可区分性矛盾。于是 `@@M@@d(w)\mapsto r(w)@@` 是由符号图生成的子幺半群到 `@@M@@\mathbb{R}{[h]}@@` 的保幺满同态。

第三步是代数核心：若 `@@M@@\D{k}@@` 的含幺子幺半群可保幺满射到 `@@M@@\mathbb{R}{H}@@`，则 `@@M@@k\ge L(h)=2^{\lfloor(h-2)/31\rfloor}@@`。图的秩（rank）是跨接两边的对数，乘法不减秩损失。主引理断言：若幂等图 `@@M@@a@@` 的像恰为 `@@M@@\Id{H}\cup\{(x,y)\}@@`（在恒等上添一个非对角对），则秩损失 `@@M@@m-\rank(a)\ge L(h)@@`，证明对 `@@M@@h@@` 归纳，取 `@@M@@t=16@@`。先用置换图的提升把 `@@M@@a@@` 共轭出 32 个分别添加 `@@M@@(u_i,z)@@`、`@@M@@(z,v_j)@@` 的幂等元；幂等图与恒等的差异处至多 `@@M@@2c@@` 个端口，故其支撑之并 `@@M@@\le4tc=64c@@`。再与像为 `@@M@@\Id{H\setminus\{z\}}@@` 的提升 `@@M@@b_0@@` 夹逼，得到 `@@M@@t^2=256@@` 个各添加一对 `@@M@@(u_i,v_j)@@` 的元素；经角（corner）收缩后它们共享一个大小 `@@M@@\le4tc@@` 的支撑集。沿嵌套幂等链把 256 对逐个加入，总秩损失被公共支撑控制为 `@@M@@\le4tc@@`；而每一步限制到保留 `@@M@@h-31@@` 个点的更小完整关系角后，由归纳假设该步至少损失 `@@M@@L(h-31)/2@@`。两相比较得 `@@M@@c\ge2L(h-31)=L(h)@@`。最后组装：`@@M@@k=4(s+2)^2\ge L(h)@@`。

## 可信度与备注

主结果已有 Lean 形式化证明（结果族 129 官方文档）。同族姊妹篇用分块二元关系（路径图）的独立论证证明同一语言的非确定补机也需指数状态（`@@M@@\tfrac12 2^{\lfloor(h-2)/127\rfloor}-1@@`），两文方法不同而结论互相印证，共同排除与字母表无关的多项式界。作者为 OpenAI，按其官方声明，未经形式化的结果可能有问题；本文主要结果已形式化，可信度高。

{% endraw %}
