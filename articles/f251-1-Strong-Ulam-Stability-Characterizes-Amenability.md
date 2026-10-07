---
layout: default
title: "Strong Ulam Stability Characterizes Amenability"
family: "251"
discipline: "Group theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Strong Ulam Stability Characterizes Amenability

> 结果族 251：Amenability, unitarizability, and strong Ulam stability　·　学科：Group theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明可数离散群强 Ulam 稳定（strongly Ulam stable）当且仅当顺从：非顺从群上可造出缺陷任意小的酉近似表示，却与同一 Hilbert 空间上一切真表示保持 `@@M@@>1/10@@` 的距离，肯定回答了 Burger–Ozawa–Thom 之问。

## 问题背景

Ulam 稳定性追问：近似同态能否被一致校正为真同态。对群 `@@M@@G@@` 上满足 `@@M@@\mu(e)=I@@` 的酉值映射，记缺陷 `@@M@@\mathrm{def}(\mu)=\sup_{g,h}\|\mu(gh)-\mu(g)\mu(h)\|@@`；若对每个 `@@M@@\varepsilon>0@@` 存在 `@@M@@\delta>0@@`，使任何复 Hilbert 空间（含无穷维）上 `@@M@@\mathrm{def}(\mu)\le\delta@@` 的 `@@M@@\mu@@` 都一致接近同一空间上的真酉表示，则称 `@@M@@G@@` 强 Ulam 稳定。Kazhdan 1982 年证明顺从蕴含强 Ulam 稳定；Burger–Ozawa–Thom 2013 年证明含非交换自由子群的群不稳定，并明确提出"强 Ulam 稳定是否刻划顺从性"的问题；Alpeev 又处理了花环积（wreath product）情形。注意不带"强"字的有限维版本是另一回事：高秩格点等非顺从群可以是有限维 Ulam 稳定的，故无穷维空间的纳入是本质的。遗留困难是在不含自由子群的非顺从群上，直接在无穷维空间里构造几乎表示并阻断一切校正。

## 主要结果

**定理**：可数离散群 `@@M@@G@@` 强 Ulam 稳定当且仅当 `@@M@@G@@` 顺从。新方向为"非顺从 `@@M@@\Rightarrow@@` 不稳定"，且是显式量化的：对每个非顺从可数群 `@@M@@G@@` 与每个 `@@M@@\delta>0@@`，存在可分 Hilbert 空间 `@@M@@H@@` 与归一化映射 `@@M@@\mu:G\to\mathcal U(H)@@`，`@@M@@\mathrm{def}(\mu)<\delta@@`，但对每个酉表示 `@@M@@\rho:G\to\mathcal U(H)@@` 都有 `@@M@@\sup_{g\in G}\|\mu(g)-\rho(g)\|>1/10@@`。这既是 Kazhdan 顺从稳定性定理的逆定理，也回答了 Burger–Ozawa–Thom 的问题。

## 证明思路

第一步把非顺从性译成组合旗标。由 Furstenberg 边界（boundary）理论，非顺从群有非平凡紧边界 `@@M@@K@@`：作用极小（minimal）且强邻近（strongly proximal）。借助"强邻近 + Hahn–Banach 分离 + Riesz 表示"的均匀列表引理，逆向递归构造出 `@@M@@N@@` 阶段的步表，每步带旗标 E 或 F，满足三条性质：固定出发点时 F 步占比至多 `@@M@@\beta@@`；固定到达点时 E 步占比至多 `@@M@@\beta@@`；沿路径一旦出现 E 步，此后各步必为 E。

第二步是与维数无关的线性代数。用 Haar 正交矩阵与集中不等式，取两族正交基之并 `@@M@@\{a_x\}@@`，使其在任意小子集上几乎正交，且带符号恒等式 `@@M@@\sum_x f(x)a_xa_x^*=0@@` 成立；再用 Jordan–Wigner 弦构造一族两两反对易（anticommuting）的对合（involution）`@@M@@\gamma_d@@`，令 `@@M@@D=\frac1{\sqrt L}\sum_d\gamma_d@@`，各层内积从 `@@M@@G_0=I+\frac12D@@` 逐层过渡到恒等。

第三步搭主构造。Hilbert 空间按层与群元素分层：`@@M@@H=\bigoplus_k\bigoplus_{w\in G}(E_k,G_k)@@`，左平移给出真酉表示 `@@M@@U@@`。称旗标的平移为构型（configuration）；对至多三个构型的集合，标出旗标不一致的可换边，用逐层交换子空间的酉电路 `@@M@@W_p@@`，令 `@@M@@\mu(g)=V_{b,gb}U(g)@@`，其中 `@@M@@V@@` 是两个电路之差。核心估计是：向一对构型再添入第三个，比较算子只改变 `@@M@@Ch+CN\eta+CNh\eta@@`，于是三元组合的恒等式给出 `@@M@@\mathrm{def}(\mu)@@` 的同阶小界。真正的难点在于：每层交换的两子空间坐标相同而内积有微差，误差逐层求和必然失控；作者为此设计优先等距，使坐标转移几乎固定下一层要用的子空间，再用截断引理把修正后的误差搬到互相正交的层上，让范数按最大值而非求和组合。

第四步是障碍。对任何真表示 `@@M@@\rho@@`，符号抵消使二次型取值 `@@M@@\langle\psi,(D\otimes I)\psi\rangle=0@@`；而初始层向量族 `@@M@@r@@` 满足 `@@M@@\langle r,(D\otimes I)r\rangle=\frac12@@`，故 `@@M@@\|r-\psi\|\ge1/4@@`。另一方面，传输引理表明绝大多数标号的路径被 `@@M@@\mu@@` 近似送回初始向量。若有 `@@M@@\rho@@` 一致接近 `@@M@@\mu@@` 到 `@@M@@1/10@@`，三角不等式将给出 `@@M@@\|r-\psi\|<1/5@@`，矛盾。参数按 `@@M@@L@@` 大、`@@M@@\eta@@` 小、`@@M@@\beta<\min(\beta_0(\eta),1/(3200N))@@` 选取。

## 可信度与备注

本篇暂无形式化证明，请以社区核验为准；按 OpenAI 官方声明，未经形式化的结果可能有问题。姊妹篇（可酉化蕴含顺从）的主结果已 Lean 形式化，与本篇技术同源：同样以稀疏指派、随机符号向量的稀疏化估计为骨架，只是障碍分别取核能量与反对易二次型，两文互相印证，共同构成族 251 的完整图景。

{% endraw %}
