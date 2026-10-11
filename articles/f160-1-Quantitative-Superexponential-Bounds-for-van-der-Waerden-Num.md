---
layout: default
title: "Quantitative Superexponential Bounds for van der Waerden Numbers"
family: "160"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Quantitative Superexponential Bounds for van der Waerden Numbers

> 结果族 160：Superexponential van der Waerden numbers　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

把 1、2、3、… 想成一排格子，你拿红蓝两支笔涂色，目标是：不许出现"颜色相同且间距相等"的三个格子（比如第 1、5、9 格全红）。van der Waerden 定理说格子足够长时你必输；能安全撑到的长度记作 `@@M@@W_r(k)@@`。这篇论文回答了 Erdős 1980 年的提问：这个"必输长度"随数列长度 k 的增长比任何指数都快——是超指数增长。

**关键词卡片**

- van der Waerden 数（van der Waerden number）：`@@M@@W_r(k)@@`，用 r 种颜色涂格子、保证出现单色 k 项等差数列的最短格子数。
- 单色等差数列（monochromatic arithmetic progression）：同一种颜色、等间距的一串格子，如 3、10、17、24。
- 超指数增长（superexponential）：比任何 `@@M@@C^k@@`（固定 C）都快，等价于 `@@M@@W_r(k)^{1/k}\to\infty@@`。
- 局部引理（local lemma）：概率方法的经典工具——彼此牵连不多的坏事件，不太可能同时发生。

**看个具体例子**

感受"必输时刻"：下图是一种能安全涂完前 8 格的方案，但第 9 格涂什么都不行。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <rect x="66" y="80" width="44" height="44" fill="#d84a3f"/>
  <rect x="114" y="80" width="44" height="44" fill="#3f7ad8"/>
  <rect x="162" y="80" width="44" height="44" fill="#3f7ad8"/>
  <rect x="210" y="80" width="44" height="44" fill="#d84a3f"/>
  <rect x="258" y="80" width="44" height="44" fill="#d84a3f"/>
  <rect x="306" y="80" width="44" height="44" fill="#3f7ad8"/>
  <rect x="354" y="80" width="44" height="44" fill="#3f7ad8"/>
  <rect x="402" y="80" width="44" height="44" fill="#d84a3f"/>
  <rect x="450" y="80" width="44" height="44" fill="#ffffff" stroke="#d84a3f" stroke-width="2" stroke-dasharray="6 4"/>
  <text x="88" y="145" font-size="14" text-anchor="middle" fill="#a83232">1</text>
  <text x="136" y="145" font-size="14" text-anchor="middle" fill="#2f5da8">2</text>
  <text x="184" y="145" font-size="14" text-anchor="middle" fill="#2f5da8">3</text>
  <text x="232" y="145" font-size="14" text-anchor="middle" fill="#333333">4</text>
  <text x="280" y="145" font-size="14" text-anchor="middle" fill="#a83232">5</text>
  <text x="328" y="145" font-size="14" text-anchor="middle" fill="#2f5da8">6</text>
  <text x="376" y="145" font-size="14" text-anchor="middle" fill="#333333">7</text>
  <text x="424" y="145" font-size="14" text-anchor="middle" fill="#333333">8</text>
  <text x="472" y="145" font-size="14" text-anchor="middle" fill="#999999">?</text>
  <text x="280" y="182" font-size="14" text-anchor="middle" fill="#a83232">第 9 格涂红：1、5、9 连成全红等差数列</text>
  <text x="280" y="207" font-size="14" text-anchor="middle" fill="#2f5da8">第 9 格涂蓝：3、6、9 连成全蓝等差数列</text>
  <text x="280" y="245" font-size="15" font-weight="bold" text-anchor="middle" fill="#333333">W₂(3) = 9：涂到第 9 格，同色三项等差必然出现</text>
</svg>

</div>

主定理（数字版）：存在绝对常数 `@@M@@c=10^{-5}@@`，使 `@@M@@W_r(k)>k^{c\,k\lfloor\log_2 r\rfloor}@@`。一旦 k 超过某个绝对阈值，指数 `@@M@@ck@@` 随 k 线性上涨：`@@M@@k=10^6@@` 时下界已达 `@@M@@(10^6)^{10}=10^{60}@@`，任何固定底数的指数函数终将被甩开。构造思路：先在高维环形网格上用圆环坐标给格子贴标签、随机涂色，再以极稀疏的随机"翻转"补刀，杀掉漏网的单色数列。

**为什么值得关心**

Erdős 悬置 46 年的超指数增长问题（含两色情形）得到定量正面解决。

> 已 Lean 形式化

# 过渡 | Quantitative Superexponential Bounds for van der Waerden Numbers

## 由浅入深：从类比走向定理

**第一级台阶**

入门导读把整数想成一排格子，涂色时禁止出现"同色且等间距"的一串格子。半数学地说：对象是前 N 个正整数，操作是用 r 种颜色给每个数上色，约束是不出现同色、步长固定的 k 个数；要问的是：不违规的染色最长能把 N 撑到多大。

**第二级台阶**

用本科术语精确化：保证任何 r 染色都含单色 k 项等差数列的最小区间长度叫 van der Waerden 数 `@@M@@W_r(k)@@`；增长超指数指快于任何固定底数的 `@@M@@C^k@@`，等价于 `@@M@@W_r(k)^{1/k}\to\infty@@`。Erdős 1980 年明确问过两色时这个极限是否成立，悬置四十余年。卡点在方法：局部引理的常规概率用法天然只产出指数级下界。

**第三级台阶**

主定理（标签 main:intro）在"结构加扰动"的语境下陈述：存在绝对阈值 `@@M@@K_0@@`，对一切 `@@M@@k\ge K_0@@` 与一切 `@@M@@r\ge2@@` 有 `@@M@@W_r(k)>k^{ck\lfloor\log_2 r\rfloor}@@`，其中 `@@M@@c=10^{-5}@@`。阈值不依赖颜色数，挡住了此前结果（如 Fox–Hunter 需要 `@@M@@r\ge(\log k)^6@@`）的颜色数限制；`@@M@@k@@` 充分大则挡住小长度处的构造困难。结论用这些术语说：固定颜色数时 `@@M@@W_r(k)^{1/k}\to\infty@@`，Erdős 1980 年两色超指数提问得到定量正解；另一极端下固定 `@@M@@k@@`、让颜色数增长，与伴侣论文的上界配合可把增长夹在超多项式与拟多项式之间。

## 一句话结论

证明对一切 `@@M@@k\ge K_0@@`、`@@M@@r\ge2@@` 有 `@@M@@W_r(k)>k^{ck\lfloor\log_2 r\rfloor}@@`（`@@M@@c@@` 绝对），故 `@@M@@W_r(k)^{1/k}\to\infty@@`，定量解决Erdős超指数增长问题，含两色。

## 问题背景

van der Waerden 定理（1927）断言：把区间 `@@M@@[N]=\{1,\dots,N\}@@` 任意染成 `@@M@@r@@` 种颜色，只要 `@@M@@N@@` 足够大，就必然出现单项颜色（monochromatic）的 `@@M@@k@@` 项等差数列；满足此性质的最小长度记作 van der Waerden 数 `@@M@@W_r(k)@@`。下界问题反过来问：不出现单色 `@@M@@k@@` 项等差数列的染色，最长能维持多大的区间？Erdős 在 1980 年明确提问：两色时 `@@M@@W_2(k)^{1/k}@@` 是否趋于无穷，即增长是否超指数（superexponential）。此前的最好结果——Berlekamp 的代数构造 `@@M@@W_2(p+1)>p2^p@@`、Szabó 的 `@@M@@W_2(k)\ge 2^k/k^\varepsilon@@`、Kozik–Shabanov 的 `@@M@@W_r(k)\ge\beta r^{k-1}@@`，以及 2026 年 Campos–Fox–Schildkraut 的 `@@M@@W_2(k)\ge(1-o(1))k2^{k-1}@@`——都停留在指数量级；最后一项虽推出 `@@M@@W_2(k)/2^k\to\infty@@`，却给不出完整的超指数极限。卡点在于：经典概率方法（如局部引理的常规用法）天然只产生指数级下界，突破必须依靠结构完全不同的构造加稀疏随机扰动。

## 主要结果

主定理（引言中 Theorem，标签 main:intro）：存在绝对整数 `@@M@@K_0@@`，使得对每个整数 `@@M@@k\ge K_0@@` 与每个整数 `@@M@@r\ge2@@`，
`@@M@@DW_r(k)>k^{ck\lfloor\log_2 r\rfloor},\qquad c=10^{-5}.@@`
特别地，固定任一 `@@M@@r\ge2@@` 都有 `@@M@@\lim_{k\to\infty}W_r(k)^{1/k}=\infty@@`；且阈值 `@@M@@K_0@@` 不依赖 `@@M@@r@@`，界对一切颜色数一致成立，这严格强于"`@@M@@W_2(k)/2^k\to\infty@@`"。另一极端（定理 transfer:large-r）：对一切 `@@M@@r\ge256@@`、`@@M@@k\ge3@@`，`@@M@@W_r(k)>\exp\bigl((\log r)^2/(64\log 2)\bigr)@@`，即固定公项长度时 `@@M@@W_r(k)@@` 随颜色数超多项式（superpolynomial）增长；与伴侣论文的拟多项式（quasipolynomial）上界配合，固定 `@@M@@k\ge3@@`、`@@M@@r\to\infty@@` 时增长被夹在超多项式与拟多项式之间。

## 证明思路

第一步在循环群上构造。取大于 `@@M@@k@@` 的素数 `@@M@@P@@`（由中心二项式系数的初等论证给出，`@@M@@k<P\le2k^2@@`），令 `@@M@@q@@` 为 `@@M@@P@@` 的、至少 `@@M@@k^{ck/D}@@` 的最小方幂，维数 `@@M@@D=\lceil k^{1/10}\rceil@@`，则 `@@M@@N=q^D\ge k^{ck}@@`，目标是造 `@@M@@\mathbb{Z}/N\mathbb{Z}@@` 上无单色 `@@M@@k@@` 项数列的二染色。第 7 节的"数字乘积"命题再把循环染色搬回整数区间：把 `@@M@@n@@` 写成 `@@M@@N@@` 进制，用各数位颜色组成的向量作新颜色；若出现单色等差数列，取整除公差的最大幂 `@@M@@N^i@@`，第 `@@M@@i@@` 位数字恰构成非零步长的循环单色数列，矛盾。于是 `@@M@@W_{2^m}(k)>N^m@@`，取 `@@M@@m=\lfloor\log_2 r\rfloor@@` 即覆盖一切 `@@M@@r\ge2@@`。

第二步搭几何骨架（第 2 节）。用同态 `@@M@@x_i(n)=n/q^i\bmod 1@@` 与 `@@M@@y_i(n)=\lambda x_i(n)@@`（`@@M@@1\le i\le D@@`）给出两套圆环坐标，其中伸缩 `@@M@@\lambda@@` 吸收了每个周期 `@@M@@h\le 2M=2\lceil k^{1/2}\rceil@@` 在小素数处的全部素幂分量；于是任何约化分母要么是 `@@M@@1@@`、要么超过 `@@M@@h_0=D^2@@`，短周期与长周期被干净分离。`@@M@@y@@` 坐标圆被切成在切割点 `@@M@@1/2@@` 附近指数式加密的自适应网格，群元素按坐标所在的区间盒获得标签（label）；对标签随机赋色，用论文自证的有限非对称局部引理（asymmetric local lemma）挑出平衡外层染色 `@@M@@c_*@@`：轻位置足够多的数列与合格模式中，两色各占至少四分之一。

第三步证明二分法（第 5 节）：任一循环 `@@M@@k@@` 项数列要么两色各出现至少 `@@M@@\gamma k@@` 次，要么其全部居中 `@@M@@y@@` 坐标可整体提升为实仿射（affine）序列 `@@M@@\tilde y(n_j)=A+jB@@`。枢轴是出现超过 `@@M@@k/M@@` 次的"重标签"：最近回访给出有理周期 `@@M@@h\le2M@@` 与微小漂移，而宽度不足 `@@M@@1@@` 的盒内三点强迫仿射；当 `@@M@@h\le h_0@@` 时 `@@M@@h\mid\lambda@@`，步长落在格 `@@M@@q^{-i}\mathbb{Z}@@` 上，与网格宽度比较后要么各标签互异（与重标签矛盾）、要么整体仿射；当 `@@M@@h>h_0@@` 时按周期 `@@M@@h@@` 分块，每块都是外层平衡的合格模式，两色各占至少 `@@M@@h/8@@`，累计仍得 `@@M@@\gamma k@@` 次。

第四步用稀疏扰动（第 6 节）消灭残余情形。给每个"键"（`@@M@@y@@` 坐标盒连同范数带 `@@M@@\lfloor\|q\tilde y(n)\|_2^2\rfloor@@`）挂独立的 Bernoulli(`@@M@@p=k^{-1/20}@@`) 翻转，最终颜色 `@@M@@C(n)=c_0(n)+E_{\kappa(n)}\bmod 2@@`。沿任一数列，同一盒内的点共线且两两距离至少 `@@M@@1@@`，而范数带与每条半直线至多交出长度 `@@M@@1@@`（Behrend 式几何），故每键出现至多 `@@M@@4@@` 次。于是平衡数列变单色需 `@@M@@\gamma k/4@@` 个键同时翻转，概率 `@@M@@p^{\gamma k/4}@@`，对至多 `@@M@@q^{2D}@@` 条数列取并界，指数系数 `@@M@@2c-\gamma/80<0@@`，故为 `@@M@@o(1)@@`；仿射数列则按"签名"计数：平方范数是 `@@M@@j@@` 的二次式，与不超过 `@@M@@Dq^2/4@@` 的整数比较构成三维超平面安排（hyperplane arrangement），签名总数对数 `@@M@@O(k^{9/10}\log k)=o(pk)@@`，相同签名规定同一事件，并界亦为 `@@M@@o(1)@@`。两概率之和小于 `@@M@@1@@`，故存在翻转选择使一切单色数列消失。第 3 节的全局与锚定模式计数（如 `@@M@@(CDh)^{6D}@@`）为平衡性提供定量输入，技术性较强，此处从略。

## 可信度与备注

本批任务元数据标注该主结果已有 Lean 形式化证明；论文自含全部所需工具，包括局部引理的完整证明与初等上界附录。组合计数细节集中于第 3 节，本解读未逐条复述。本批次中该结果族仅此一篇手稿；其引用的伴侣论文给出固定 `@@M@@k@@` 时关于 `@@M@@r@@` 的拟多项式上界，与本文下界共同夹出该方向的成长阶。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本篇主结果已形式化，可信度较高。

---

# 深究 | Quantitative Superexponential Bounds for van der Waerden Numbers

## 深入探讨：像审稿人一样追问 🔍

**问 1：证明中最关键、也最脆弱的一步是哪里？**

答：第 5 节的二分法：任一循环 `@@M@@k@@` 项数列要么外层两色各占正比例（`@@M@@\gamma k@@` 次），要么其居中 `@@M@@y@@` 坐标整体提升为实仿射序列。枢纽是高频重复的"重标签"经最近回访给出有理周期 `@@M@@h\le 2\lceil k^{1/2}\rceil@@`，再靠伸缩 `@@M@@\lambda@@` 吸收小素数处的素幂分量后分 `@@M@@h\le h_0=D^2@@` 与 `@@M@@h>h_0@@` 两路处理；短长周期分离稍有泄漏，后一步扰动的并界就收不拢。

**问 2：为什么经典随机方法到不了超指数？**

答：局部引理的常规用法只产生指数级下界——Berlekamp 的 `@@M@@p2^p@@`、Kozik–Shabanov 的 `@@M@@\beta r^{k-1}@@`、乃至 Campos–Fox–Schildkraut 的 `@@M@@(1-o(1))k2^{k-1}@@` 全是指数底数之争。本文换成确定性圆环坐标标签先造外层平衡染色，再叠加参数 `@@M@@p=k^{-1/20}@@` 的稀疏独立翻转，结构负责"大多数数列两色平衡"，随机只负责清点残敌。

**问 3：与 2026 年 Campos–Fox–Schildkraut 等最新工作相比，真正的新意是什么？**

答：CFS 解决的是 `@@M@@W_2(k)/2^k\to\infty@@`（比值发散），给不出完整的 `@@M@@1/k@@` 次幂极限；Fox–Hunter 的超指数式改进需 `@@M@@r\ge(\log k)^{3/\varepsilon}@@` 的颜色数门槛。本文首次在两色及一切 `@@M@@r\ge2@@` 上一致给出 `@@M@@k^{ck\lfloor\log_2 r\rfloor}@@`，且阈值 `@@M@@K_0@@` 与颜色数无关。

**问 4：这种 AI 参与生成的证明最可能在哪里出错？**

答：维数随 `@@M@@k@@` 增长时的常数失控。作者自己点明定量障碍：若计数常数任意依赖维数则构造失效，关键估计 `@@M@@(CDh)^{6D}@@` 必须对 `@@M@@q@@`、`@@M@@\lambda@@` 与锚区间宽度一致。"常数是否真绝对"是 AI 证明最易埋雷处；所幸主结果已附 Lean 形式化证明。

**问 5：`@@M@@c=10^{-5}@@` 这个常数质量如何？界紧吗？**

答：`@@M@@c@@` 是让扰动概率并界的指数系数 `@@M@@2c-\gamma/80<0@@` 成立的工程选择，远非紧的；`@@M@@r@@` 方向与伴侣论文的上界配合可把增长夹在超多项式与拟多项式之间，但 `@@M@@k@@` 方向上下界之间仍隔指数级鸿沟，论文未声称最优性。

**问 6：谁会用到这个结果？**

答：Ramsey 论下界社区——凡研究 van der Waerden 数增长阶、密度 Hales–Jewett 数、或"结构加随机扰动"构造技术的人都会引用；其范数带扰动延续了 Behrend 式几何传统，也可能被借鉴到无平方和集合等邻域。论文未展开对多维或多项式数列版本的推广。

**总评**

46 年悬案的定量正解，"几何骨架 + 稀疏翻转"的方法组合有真正新意，且带形式化背书；最大风险集中在第 3 节计数与二分法中对维数一致的绝对常数的细节核验。

{% endraw %}
