---
layout: default
title: "A quadratic bound for Jacobsthal's function"
family: "021"
discipline: "Number theory"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A quadratic bound for Jacobsthal's function

> 结果族 021：A quadratic bound for Jacobsthal's function　·　学科：Number theory　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

把 1, 2, 3, … 排成一排座位，再圈出 n 的全部素因子当"禁忌名单"：座位号被名单里任何一个素数整除，就得站起来。问：最多能连续空多少个座位？这篇论文证明：名单有 k 个素数时，空位连排不超过约 k²/(log log k)² —— Erdős 1962 年记录的 Jacobsthal 问题（是否不超过 k² 的常数倍）得到肯定回答。

**关键词卡片**

- Jacobsthal 函数 j(n)：使"任意连续 m 个整数中必有与 n 互素者"成立的最小 m。
- 互素（coprime）：最大公因数为 1，即不被禁忌名单里的任何素数整除。
- 素因子个数（number of prime divisors）：名单长度，记 ω(n)；h(k) 是长度至多 k 的所有名单下最坏的空位连排加一。
- 筛法（sieve theory）：系统筛掉被各素数整除的位置、清点幸存者的核心技术。
- 中国剩余定理（Chinese remainder theorem）：让各素数的"禁座安排"互不干扰、自由组合。

**看个具体例子**

取 n=30（名单 2, 3, 5）：座位 24–28 连续五个全被挡（24、26、28 是偶数，25 被 5 整除，27 被 3 整除），直到 29 才出现与 30 互素的幸存者。任意连续 6 个整数必含幸存者，所以 j(30)=6。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 250">
  <text x="280" y="28" text-anchor="middle" font-size="16" fill="#333">n = 30（素因子 2, 3, 5）：谁与 30 互素？</text>
  <rect x="55" y="55" width="34" height="34" rx="6" fill="#f2c" stroke="#a66"/>
  <rect x="98" y="55" width="34" height="34" rx="6" fill="#f2c" stroke="#a66"/>
  <rect x="141" y="55" width="34" height="34" rx="6" fill="#f2c" stroke="#a66"/>
  <rect x="184" y="55" width="34" height="34" rx="6" fill="#bfe" stroke="#273" stroke-width="2"/>
  <rect x="227" y="55" width="34" height="34" rx="6" fill="#f2c" stroke="#a66"/>
  <rect x="270" y="55" width="34" height="34" rx="6" fill="#f2c" stroke="#a66"/>
  <rect x="313" y="55" width="34" height="34" rx="6" fill="#f2c" stroke="#a66"/>
  <rect x="356" y="55" width="34" height="34" rx="6" fill="#f2c" stroke="#a66"/>
  <rect x="399" y="55" width="34" height="34" rx="6" fill="#f2c" stroke="#a66"/>
  <rect x="442" y="55" width="34" height="34" rx="6" fill="#bfe" stroke="#273" stroke-width="2"/>
  <rect x="485" y="55" width="34" height="34" rx="6" fill="#f2c" stroke="#a66"/>
  <text x="72" y="77" text-anchor="middle" font-size="13" fill="#333">20</text>
  <text x="115" y="77" text-anchor="middle" font-size="13" fill="#333">21</text>
  <text x="158" y="77" text-anchor="middle" font-size="13" fill="#333">22</text>
  <text x="201" y="77" text-anchor="middle" font-size="13" fill="#273">23</text>
  <text x="244" y="77" text-anchor="middle" font-size="13" fill="#333">24</text>
  <text x="287" y="77" text-anchor="middle" font-size="13" fill="#333">25</text>
  <text x="330" y="77" text-anchor="middle" font-size="13" fill="#333">26</text>
  <text x="373" y="77" text-anchor="middle" font-size="13" fill="#333">27</text>
  <text x="416" y="77" text-anchor="middle" font-size="13" fill="#333">28</text>
  <text x="459" y="77" text-anchor="middle" font-size="13" fill="#273">29</text>
  <text x="502" y="77" text-anchor="middle" font-size="13" fill="#333">30</text>
  <path d="M227 97 L227 110 L433 110 L433 97" fill="none" stroke="#c33" stroke-width="1.5"/>
  <text x="330" y="128" text-anchor="middle" font-size="13" fill="#c33">连续 5 个被挡：23 与 29 是仅有的幸存者</text>
  <text x="280" y="165" text-anchor="middle" font-size="13" fill="#333">j(30) = 6：任取连续 6 个数，必含与 30 互素者。</text>
  <text x="280" y="195" text-anchor="middle" font-size="13" fill="#333">定理（大 k 尺度）：h(k) ≤ C·k² / (log log 3k)²，</text>
  <text x="280" y="218" text-anchor="middle" font-size="13" fill="#333">比 Iwaniec 1978 年的 k²·log²k 首次掐掉全部对数损失。</text>
</svg>

</div>

**为什么值得关心**

它与素数间隙、区间覆盖、筛法核心难题同源；悬置近半世纪的"去对数"一步终于完成，且主定理与关键引理均已通过 Lean 形式化，属本系列验证等级最高的成果之一。

> 已 Lean 形式化

# 由浅入深：从类比走向定理（f021 · Jacobsthal 函数的二次上界）

## 由浅入深：从类比走向定理

**第一级台阶**

导读的座位图换成半数学语言：对象是一段连续的整数位置，和一份"禁忌名单"——名单里每个素数各自圈定一整类被禁的位置（被它整除者）；操作是清点哪些位置侥幸躲开全部禁忌。问题问的是：名单长度固定为 k 时，连续的空位最长能拖多长才必然出现一个幸存者。

**第二级台阶**

用本科术语：Jacobsthal 函数 j(n) 是使"任意 m 个连续整数中必有与 n 互素者"成立的最小 m；记 ω(n) 为 n 的不同素因子个数，h(k) 定义为 ω(n)≤k 的一切 n 上 j(n) 的上确界。中国剩余定理保证各素数的禁座安排互不干扰，于是 h(k)−1 恰等于至多 k 个素数的整除类所能覆盖的最长区间长度——一个纯有限覆盖问题，与筛法及素数间隙同源。

**第三级台阶**

定理的语境：存在绝对常数 C 使对一切 k≥1 有 h(k)≤C·k²/(log log 3k)²，界对素数的大小与区间位置完全一致。一致性假设不可省：Hajdu–Saradha 发现前 k 个素数之积并非总是最坏情形（j(P₂₄)<h(24)），故必须对任意素数集、任意平移一并证明。心脏是一个定量幸存者估计——无论怎样为每个小素数任意指定禁止剩余类，长度约 z²/log²z 的区间里至少留住约 cY·(log w)/L² 个数；证明分参考计算（把真实计数换成理想值，进入连续模型，用线性筛函数与更新定理在临界参数 2 处榨出 B⁻² 尺度的正余量）与真实比较（大偏差迫使禁止类与某固定有理数模 p 对齐，在对齐分支上"停车"反而多出幸存者）两大块，最后装配成主定理。

## 一句话结论

对任何至多有 `@@M@@k@@` 个不同素因子的 `@@M@@n@@`，长度 `@@M@@\ll k^2/(\log\log(3k))^2@@` 的任意连续整数区间必含与 `@@M@@n@@` 互素的数。这肯定了 Jacobsthal 的二次上界问题，并在 Iwaniec 的 `@@M@@k^2\log^2 k@@` 之上首次去掉全部对数损失。

## 问题背景

Jacobsthal 函数 `@@M@@j(n)@@` 是使"任意 `@@M@@m@@` 个连续整数中必有与 `@@M@@n@@` 互素者"的最小 `@@M@@m@@`；令 `@@M@@h(k)=\sup_{\omega(n)\le k}j(n)@@`，其中 `@@M@@\omega(n)@@` 记不同素因子个数。Jacobsthal 自 1960 年起研究它，Erdős 于 1962 年记录了他的问题：是否 `@@M@@h(k)\ll k^2@@`？由中国剩余定理（Chinese remainder theorem），`@@M@@h(k)-1@@` 恰是能用至多 `@@M@@k@@` 个素数的整除类覆盖的最长区间长度，因此这是有限覆盖问题，与筛法（sieve theory）及素数间隙紧密相关。Brun 筛先给出多项式上界，Vaughan（1977）证明 `@@M@@j(n)\ll\omega(n)^2\log^4(2\omega(n))@@`，Iwaniec（1978）用移位筛改进为 `@@M@@h(k)\ll k^2\log^2 k@@`——此后近半个世纪无人去掉这两个对数，障碍在于一维筛的模数被限制在区间长度的平方根附近，正落在临界参数 2 上。此外 Hajdu 与 Saradha 发现 `@@M@@j(P_{24})=234<236=h(24)@@`（`@@M@@P_k@@` 为前 `@@M@@k@@` 个素数之积），说明素数积并非总是最坏情形，故必须对任意素数集、任意平移一致地证明。

## 主要结果

主定理：存在绝对常数 `@@M@@C>0@@`，使对一切 `@@M@@k\ge1@@` 有
`@@M@@Dh(k)\le C\,\frac{k^2}{(\log\log(3k))^2}.@@`
该界对素因子大小与区间位置（含负起点、含零）完全一致。核心是定量幸存者估计：取 `@@M@@L=\log z@@`，`@@M@@Y=\lfloor z^2/L^2\rfloor@@`，`@@M@@w=L/(\log L)^2@@`，`@@M@@B=L/\log w@@`，`@@M@@V_0=\prod_{p\le w}(1-1/p)@@`，则当 `@@M@@z@@` 充分大时，无论怎样为每个素数 `@@M@@p\le z@@` 指定禁止剩余类 `@@M@@a_p\bmod p@@`，`@@M@@[1,Y]@@` 中避开全部禁止类的整数至少有 `@@M@@cYV_0/B^2@@` 个；由 Mertens 定理这 `@@M@@\sim e^{-\gamma}cY\log w/L^2@@`。禁止类是任意指定的，不假设随机。随后取截断 `@@M@@z=A_0\,k\log k/\log\log k@@`，此时 `@@M@@Y\asymp k^2/(\log\log k)^2@@`；再用一个上界筛逐个删除大于 `@@M@@z@@` 的剩余素因子（至多 `@@M@@k@@` 个，每个至多删去 `@@M@@O(1+X/\log X)@@` 个幸存者，`@@M@@X=Y/z@@`），取 `@@M@@A_0@@` 充大便仍剩正数，故区间内有与 `@@M@@n@@` 互素的整数。有限个小 `@@M@@k@@` 用容斥平凡界 `@@M@@(k+1)2^k+1@@` 吸收进常数 `@@M@@C@@`。

## 证明思路

证明分"参考计算"与"真实比较"两大块。先建递减素数树：把被覆盖整数按最小违规素数分类，迭代得到由 `@@M@@(w,z]@@` 内严格递减素数组成的节点 `@@M@@d@@`，其计数满足精确恒等式 `@@M@@S_d(b)=N_d-\sum_p S_{dp}(x(p))@@`，其中 `@@M@@x(p)=\log p/\log w@@`。奇偶交替给出 Bonferroni 型符号：偶数层展开是下界。再在奇数层施加准入规则 `@@M@@r-x\ge\max(2x,x+2)@@`（`@@M@@r@@` 为间隙参数），保证保留的等差数列长度 `@@M@@\ge w^{1/100}@@`，可被一个绝对一致的上界筛控制。

再算参考树：把真实计数 `@@M@@N_d@@` 换成理想值 `@@M@@\mu_d=(Y/d)V_0@@`，得带调和权重 `@@M@@1/p@@` 的递推；继而把素数和换成积分 `@@M@@\int dx/x@@` 进入连续模型。经典线性筛函数 `@@M@@f,F@@`（满足时滞方程 `@@M@@(sf(s))'=F(s-1)@@` 等）给出基准。真正的难点在根处：其比值 `@@M@@2-a_\star/B@@` 恰落在 `@@M@@f@@` 取零的临界参数 2 之下，基准贡献为负的 `@@M@@-a_\star e^\gamma B^{-2}@@`，正余量只能来自截断值 2 处的边界差异。为评估这个 `@@M@@B^{-2}@@` 尺度的量，作者用 `@@M@@f,F@@` 的导数定义权 `@@M@@\phi@@`，把调和转移改造成概率核（一次测度变换），利用过程的再生结构（regeneration）配合关键更新定理（key renewal theorem）求得极限占据测度，再迁移回素数路径。边界异常 `@@M@@\delta_i@@` 以 `@@M@@\exp(-cr\log r)@@` 衰减；与全乘积 `@@M@@1/2@@` 比较并按"首次被遗漏的叶子"展开，得到带号修正积分 `@@M@@I@@`：前几项可显式积分，尾项被控制，严格有理算术给出 `@@M@@I>0.14@@`（细算超过 `@@M@@0.2229@@`），最终 `@@M@@B^2P_\mathrm e(r_0,B)/e^\gamma\to-a_\star+2I/M_g>0.02@@`，参考余量为正。

第三步做真实—参考比较。长数列上由筛法基本引理（fundamental lemma of sieve theory）保证 `@@M@@N_d@@` 接近 `@@M@@\mu_d@@`；大的相对偏差必沿路径末端某条"见证边"显现。把这些路径装入素数箱相互独立的盒子后，反演估计（inverse estimate）表明大量异常边迫使孤立素数与某个固定有理数 `@@M@@A/D@@` 对齐：`@@M@@Da_p\equiv A\pmod p@@`。其证明组合了小系数高度的多项式插值、Jarník 凸弧格点界 `@@M@@O(D_0^4(1+S^{2/3}))@@` 与 Gallagher 大筛（larger sieve）的对偶计数，即"模集中迫使代数结构"的原理。方差估计（奇异级数平均的截断形式）进一步说明只有小模数、小截距的有理数才能解释大量异常端点；随后在这些对齐分支的合适偶节点处"停车"，对对齐素数求平均会得到比参考子树更多的幸存者，而标记更新（marked renewal）论证保证几乎所有异常路径质量都会到达停车点。

最后装配：比较恒等式
`@@M@@DL_{\mathrm{stop}}-YV_0P_\mathrm e(r_0,B)=\sum_{d\in\mathcal T}(-1)^{\omega(d)}(N_d-\mu_d)+\sum_{d\in\mathcal S}\bigl(S_d(b_d)-\mu_dP_\mathrm e(r_d,b_d)\bigr)@@`
把按预算分配的各小量误差加总，得 `@@M@@S_1(B)\ge(c_L/2)YV_0/B^2@@`，证得幸存者定理，进而按上节方式导出主定理。

## 可信度与备注

论文标注主结果及关键中间定理（幸存者估计）已有 Lean 形式化证明（结果族 021 对应 lean/docs/021.md），属该系列中验证等级较高的工作；文中数值性步骤（如 `@@M@@I>0.14@@`、`@@M@@e^{0.70}<2.014@@`）均以严格有理算术核验。依据 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。本结果族以本文为核心，其 Lean 形式化与论文互为印证；而 Ford–Green–Konyagin–Maynard–Tao 的下界 `@@M@@j(P_k)\gg k(\log k)^2\log\log\log k/\log\log k@@` 表明真实阶可能远低于二次，Vaughan 更猜想 `@@M@@j(n)\ll_\eps\omega(n)^{1+\eps}@@`，留待后续。

---

# 深入探讨：像审稿人一样追问（f021 · Jacobsthal 函数的二次上界）

## 深入探讨：像审稿人一样追问 🔍

**问 1：证明真正的心脏在哪里？**

（答：参考树根处。其比值 2−a*/B 恰落在线性筛函数 f 取零的临界参数 2 之下，基准贡献是负的 −a*e^γB⁻²，全部正余量只能来自截断值 2 处的边界差异——一个 B⁻² 尺度的微小量。作者用 f、F 的导数定义权 φ，把调和转移改造成概率核，借助过程的再生结构与关键更新定理求极限占据测度，再迁移回素数路径，最终严格有理算术给出带号修正积分 I>0.14（细算超 0.2229）。这是全文最精微、最脆弱的一步。）

**问 2：为什么必须对任意素数集与任意平移一致地证明？**

（答：因为最坏情形未必是素数积：Hajdu–Saradha 算出 j(P₂₄)=234<236=h(24)，说明某个非前 24 素数的组合比素数积更毒。只对 P_k 证明或只对随机平移平均证明都不够，禁止剩余类是 adversary 任意指定的，不假设任何随机性。）

**问 3：与 Iwaniec 1978 相比，真正的突破是什么？**

（答：Iwaniec 的移位筛给出 h(k)≪k²log²k，近半世纪无人去掉这两个对数。障碍在一维筛的模数被限制在区间长度的平方根附近，正落在临界参数 2 上——参数化后刚好卡死。本文绕开的方式是双块结构：参考侧用更新定理在临界点下榨正余量，比较侧用"模集中迫使代数结构"的反演估计处置大偏差。Erdős 1962 年记录的 Jacobsthal 二次上界问题就此肯定。）

**问 4：AI 生成证明在这篇上最可能的出错模式？**

（答：数值级联与拼装。I>0.14、e^0.70<2.014 这类显式有理算术步骤，以及反演估计中"小系数高度多项式插值 + Jarník 凸弧格点界 O(D₀⁴(1+S^{2/3})) + Gallagher 大筛对偶计数"的三件套拼接，都是"每步都对、合起来差一个常数"的高发区。缓解：主定理与幸存者估计均已 Lean 形式化（formalized: true），验证等级在本批结果中最高。）

**问 5：这个界离真相多远？**

（答：可能还很远。Ford–Green–Konyagin–Maynard–Tao 的下界 j(P_k)≫k(log k)²logloglog k/loglog k 表明素数积情形的真实阶远低于二次；Vaughan 更猜想 j(n)≪_ε ω(n)^{1+ε}。本文解决的是"是否二次"的定性问题，最优阶仍完全开放。）

**问 6：谁会用到它？**

（答：三个方向：素数间隙与覆盖问题（h(k)−1 本身就是整除类覆盖问题的量）；筛法理论——在临界参数 2 处榨正余量的技术是线性筛的一般性进展；以及任何需要"区间内必有近乎互素元素"的均匀性引理的应用（如某些算法数论与 CRT 反演场景）。）

**总评**

（半世纪老题的定性解决、关键步骤经 Lean 形式化，可信度属本批最高一档；剩余风险在形式化覆盖之外的反演—停车装配细节，且二次上界大概率远非终态。）

{% endraw %}
