---
layout: default
title: "An infinite finitely presented periodic group"
family: "247"
discipline: "Group theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An infinite finitely presented periodic group

> 结果族 247：An infinite finitely presented residually finite 2-group and a finitely presented nil algebra　·　学科：Group theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文构造了首个具普通有限呈现的无限周期群 `@@M@@\mathop{\mathrm{St}}\nolimits_{12}(R)@@`，并同批造出有限呈现、无穷维、逐元素幂零却不幂零的结合代数，一并否定有限呈现 Burnside 问题、Ufnarovskij 幂零代数问题与 Kurosh 问题的有限呈现版本。

## 问题背景

Burnside（1902）问：每个元素皆有限阶的有限生成群（周期群，periodic group）是否必有限？Golod 与 Novikov–Adian 先后给出无限反例，但都不是有限呈现（finitely presented）；Ol'shanskii–Sapir（2003）明确把"无限周期群可否有普通有限呈现"列为独立公开问题。代数一侧有平行的问题：结合代数逐元素幂零（nil）是否推出整体幂零（nilpotent，即 `@@M@@A^N=0@@`）？Ufnarovskij 问有限呈现的幂零代数是否必幂零，Amitsur 问 Jacobson 根（Jacobson radical）版本，Kurosh 问（域含于中心时）有限生成的代数代数（algebraic algebra）是否必有限维，其有限呈现版本更强且长期未决。难点在于 Golod–Shafarevich 式的无限性论证与"只允许有限条定义关系"几乎天然冲突，而群与代数两侧必须一次解决。

## 主要结果

定理：存在无限周期群具普通有限呈现。具体地，构造无限、有限呈现的单结合 `@@M@@\mathbb F_2@@`-代数 `@@M@@R=\mathbb F_2\oplus I@@`（`@@M@@I@@` 为正度理想），则 Steinberg 群（Steinberg group）`@@M@@\mathop{\mathrm{St}}\nolimits_{12}(R)@@` 无限、有限呈现且周期。

推论：该群具 Kazhdan 性质 (T)（Kazhdan's property (T)，由 Ershov–Jaikin-Zapirain 的定理得出），因而非顺从（nonamenable）。

代数推论：理想 `@@M@@I@@` 是无限维、非幺（nonunital）、有限呈现的幂零代数，同时是 Jacobson 根但非幂零；其单位化（unitization）有限呈现、代数的且无穷维。这三件分别否定 Ufnarovskij 问题、Amitsur 问题与 Kurosh 问题的有限呈现版本。

## 证明思路

一切系于理想 `@@M@@I@@` 的矩阵幂零性（matrix-nil）：任意尺寸、系数取自 `@@M@@I@@` 的矩阵逐个幂零。有了它，`@@M@@\GL_n(R)@@` 中矩阵模 `@@M@@I@@` 归约到有限群 `@@M@@\GL_n(\mathbb F_2)@@`，特征 `@@M@@2@@` 下逐次平方给出矩阵群周期；剩下证 Steinberg 核 `@@M@@J_{12}(R)@@` 是挠群，则任何群元先乘某幂落进核、再乘一幂回到单位元。

环 `@@M@@R@@` 由自相似局部规则层级构造。字母是 `@@M@@ch@@` 比特串（`@@M@@c=10000@@`），"干净块"含 `@@M@@q_h@@` 个核心格、一张调色板（palette）与一个停止格，总长 `@@M@@L_h=2q_h+1@@`；上层字母经代入 `@@M@@E_h@@` 编码为下层规范块串。关系只有等长替换 `@@M@@v=v'@@` 与零声明 `@@M@@v=0@@`，长度至多 `@@M@@k=10@@`。规则表本身是自指地定义的：块内的验证者头（verifier head）用 Cook 计算表（computation tableau）式的三文字局部子句核查"替换证书"，而验证程序由 Kleene 不动点 `@@M@@a=s(t,t)@@` 指定——程序 `@@M@@a@@` 恰好认证以 `@@M@@a@@` 为代码的规则表（先例是 Durand–Romashchenko–Shen 的自模拟瓦片构造）。由此证得：干净编码保持非零词；每个足够长的非零词有唯一的 token 分解，各 token 可孤立地规范化为规范块串。

矩阵幂零性靠消没证明：给每字母指定数值矩阵，词取其有序乘积（Schützenberger 加权自动机）。长词中必含长度 `@@M@@\ge q/100@@` 的可换色段（eligible run），段内颜色互异、相邻字母可任意换位；对该段内的整块做全体置换，特征 `@@M@@2@@` 下交错和 `@@M@@\sum_\sigma X_{\sigma(1)}\cdots X_{\sigma(m)}=0@@`（`@@M@@m>d^2@@`，且证明无须除 `@@M@@m!@@`）。当调色板相对测试维数不够大时，经 token 分解把测试提升一层，再用有限状态矩阵自动机把块测试还原为字母测试（维数增大）；层级指数增长保证若干层后直接消没成立。最后引入中心未定元把"因子个数"与"词长"分开，抽取系数即得每个固定矩阵幂零。

群侧按 Krstić–McCool 方法给出 `@@M@@\mathop{\mathrm{St}}\nolimits_n(R)@@`（`@@M@@n\ge 5@@`）的普通有限呈现：生成元 `@@M@@g_{ij}(w)@@`（`@@M@@|w|\le 2@@`），长词根递归定义为换位子，一条三因子换位子恒等式保证定义与分裂方式无关。核的挠性：经分次嵌入 `@@M@@\gamma:R\to R[t]@@` 把 `@@M@@t@@` 代入 `@@M@@2@@` 幂阶循环移位矩阵 `@@M@@C_N@@`，基变换三角化后得 `@@M@@W=\iota_1(u)^N@@`；再用"环绕消去"证明循环移位与截断移位在 Steinberg 群内相等（误差收集进矩阵映射单射的条带），后者恰为 `@@M@@\mathbb F_2@@` 上核元素之积、为挠，故 `@@M@@u@@` 稳定后为挠；最后由标架复形（frame complex）的有理稳定性（rational stability，`@@M@@n\ge 12@@`）把挠性拉回 `@@M@@J_{12}(R)@@`：一切到 `@@M@@\mathbb Q@@` 的同态都杀死 `@@M@@u@@`，故 `@@M@@u@@` 挠。

## 可信度与备注

本文主结果暂无形式化证明（任务元数据 formalized=false），请以社区核验为准。姊妹篇"An infinite finitely presented residually finite 2-group"（2026-10-05）显式引用本文的代数与层级命题，把结论加强为剩余有限 `@@M@@2@@`-群，两文互相支撑。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文最复杂、最值得核验的是自指规则表（Kleene 不动点与计算表子句）及逐层消没的组合细节。

{% endraw %}
