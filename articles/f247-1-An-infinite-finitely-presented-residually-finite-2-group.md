---
layout: default
title: "An infinite finitely presented residually finite 2-group"
family: "247"
discipline: "Group theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An infinite finitely presented residually finite 2-group

> 结果族 247：An infinite finitely presented residually finite 2-group and a finitely presented nil algebra　·　学科：Group theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

想鉴定一台无限大机器里的某个零件是不是"零号件"？把它塞进各种有限的小检测机里照 X 光：只要任何非单位元素总能在某一台机器上现形，这台机器就叫"剩余有限"。本文造出一个无限群：说明书只有有限页、经得起所有有限检测机的透视，而且每个元素转 2 的幂次圈就回到原点。

**关键词卡片**

- 周期群（periodic group）：每个元素的阶都有限的群。
- 有限呈现（finitely presented）：用有限个生成元加有限条关系式就能完整说明的群。
- 剩余有限（residually finite）：任何非单位元素都能在某个有限商群里与单位元区分开。
- 2-群（2-group）：每个元素的阶都是 2 的幂（群本身可以无限）。

**看个具体例子**

主角是 Steinberg 群 `@@M@@\mathrm{St}_{12}(R)@@` 的有限指标子群 `@@M@@G@@`。检测机就是"截断商"：把代数 `@@M@@R@@` 砍掉足够高的度数得到有限环，相应的 Steinberg 群是有限的 2-群；论文证明这些有限商合起来能现形一切非单位元（下图红点）。由 Zel'manov 定理，这类群的元素阶必然无界——2、4、8、16……一路涨上去。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><ellipse cx="165" cy="105" rx="115" ry="62" fill="none" stroke="#2c7fb8" stroke-width="2" stroke-dasharray="7 5"/><text x="165" y="30" font-size="14" fill="#2c7fb8" text-anchor="middle">Γ：无限、有限呈现</text><circle cx="110" cy="95" r="7" fill="#2c7fb8"/><circle cx="160" cy="115" r="7" fill="#c0392b"/><circle cx="215" cy="95" r="7" fill="#2c7fb8"/><circle cx="190" cy="130" r="7" fill="#2c7fb8"/><text x="248" y="140" font-size="14" fill="#2c7fb8">…</text><text x="160" y="160" font-size="13" fill="#c0392b" text-anchor="middle">元素 g≠1</text><circle cx="130" cy="226" r="30" fill="none" stroke="#666" stroke-width="2"/><text x="130" y="231" font-size="12" fill="#666" text-anchor="middle">有限商 1</text><circle cx="420" cy="226" r="30" fill="none" stroke="#c0392b" stroke-width="2"/><circle cx="433" cy="218" r="5" fill="#c0392b"/><text x="420" y="272" font-size="12" fill="#c0392b" text-anchor="middle">有限商 2：g 的像 ≠ 1，现形！</text><line x1="122" y1="150" x2="130" y2="194" stroke="#666" stroke-width="1.8"/><line x1="168" y1="121" x2="399" y2="204" stroke="#c0392b" stroke-width="2" stroke-dasharray="6 4"/></svg>

</div>

**为什么值得关心**

它与姊妹篇合起来，对"有限呈现的无限周期群是否存在"给出同时满足剩余有限的完整否定回答——此前 Grigorchuk 群剩余有限却无法有限呈现。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文证明姊妹篇构造的无限、有限呈现的周期群 `@@M@@\Gamma=\mathop{\mathrm{St}}\nolimits_{12}(R)@@` 是剩余有限的：其有限指标子群 `@@M@@G@@` 中每个元素的阶都是 `@@M@@2@@` 的幂，得到首个兼具"普通有限呈现＋剩余有限＋纯 `@@M@@2@@`-挠"的无限群，把有限呈现 Burnside 问题的否定回答又推进一层。

## 问题背景

1902 年 Burnside 问：有限生成的周期群（periodic group，每元有限阶）是否必有限？Golod（1964）与 Grigorchuk（1980）先后造出无限的反例，且都是剩余有限（residually finite，即可用有限商区分任意非单位元）的；但 Grigorchuk 群并非有限呈现（finitely presented），而"无限周期群能否有普通有限呈现"被 Ol'shanskii–Sapir（2003）明确列为公开问题（他们构造的有限呈现挠群都带无限循环商，本身不周期）。又由 Zel'manov 对限制 Burnside 问题（restricted Burnside problem）的解答，有限生成、剩余有限且指数有界的群必有限，故所求群的元素阶必然无界。姊妹篇已造出无限有限呈现的周期群，本文在其上补齐剩余有限性与纯 `@@M@@2@@`-幂挠这关键一步。

## 主要结果

主定理：存在无限、剩余有限、具普通有限呈现的群，其中每个元素的阶都是 `@@M@@2@@` 的幂（文中称 2-group，群本身可以无限）。其元素阶必然无界，且所有有限商都是有限 `@@M@@2@@`-群（由 Cauchy 定理，奇素数不能整除其阶）。

具体实现：设 `@@M@@R=\mathbb F_2\oplus I@@` 为姊妹篇构造的无限有限呈现分次代数，正度理想 `@@M@@I@@` 是矩阵幂零（matrix-nil）的：任意有限尺寸、系数取自 `@@M@@I@@` 的矩阵皆幂零。取 Steinberg 群（Steinberg group）`@@M@@\Gamma=\mathop{\mathrm{St}}\nolimits_{12}(R)@@`，则 `@@M@@\Gamma@@` 无限、有限呈现、剩余有限；令 `@@M@@G=\ker(\Gamma\to\mathop{\mathrm{St}}\nolimits_{12}(\mathbb F_2))@@`（由分次的零度投影诱导），则 `@@M@@G@@` 是有限指标子群，无限、有限呈现（Reidemeister–Schreier 定理）、剩余有限，且每元为 `@@M@@2@@` 幂阶——`@@M@@G@@` 即主定理中的群。

## 证明思路

有限商来自度截断：`@@M@@R_{\ge d}=\bigoplus_{b\ge d}R_b@@` 是理想，商环 `@@M@@R/R_{\ge d}@@` 有限；`@@M@@\mathop{\mathrm{St}}\nolimits_{12}(R/R_{\ge d})@@` 有限——其到矩阵群的核中心、中心有限指标，Schur 定理给出有限导群，而该群完美。截断立刻区分矩阵像不同的元素，真正的难点是区分 Steinberg 核 `@@M@@J(R)@@`。

先在稳定群 `@@M@@\mathop{\mathrm{St}}\nolimits(R)@@` 中工作。第一步用分次同态 `@@M@@\gamma:R\to R[t]@@`，`@@M@@a_b\mapsto a_bt^b@@`，把核元素 `@@M@@z@@` 的代表词多项式化，再把 `@@M@@t@@` 代入 `@@M@@L\times L@@` 循环移位矩阵（cyclic shift）`@@M@@C_L@@`，得 `@@M@@W_z(C_L)\in J(R)@@`（思想源自 Weibel 的分次 `@@M@@K@@`-理论转移）。本文的直接 Steinberg 计算表明：若 `@@M@@z@@` 在 `@@M@@\mathbb F_2@@` 上平凡，则对一切充分大的 `@@M@@L@@` 有 `@@M@@W_z(C_L)=1@@`；取 `@@M@@L@@` 为 `@@M@@2@@` 的幂便知这类 `@@M@@z@@` 是 `@@M@@2@@` 幂挠。

第二步是本文的新装置：相位（phase）。姊妹篇的规则层级给每个足够长的非零词 `@@M@@w@@` 规定起始相位 `@@M@@\sigma(w)\in\mathbb Z/L@@` 与终止相位 `@@M@@\tau(w)=\sigma(w)+|w|@@`，`@@M@@L@@` 可取任意大的奇数；相位只依赖词的基类，相位失配的乘积必为零。若 `@@M@@z@@` 被所有截断漏掉，可先把它写成根之积、且每根系数都是长词（用备用坐标把长系数拆成换位子而长度不减）；再用秩一映射 `@@M@@\rho(w)=u_{\sigma(w)}v_{\tau(w)}w@@` 把每根两端搬到以相位编号的新坐标（relocation 引理，误差收集进矩阵映射单射的条带子群）。此时 `@@M@@C_L@@` 求值恰好分解为 `@@M@@L@@` 个平移副本，中心性使每个副本都等于 `@@M@@z@@`，故 `@@M@@W_z(C_L)=z^L@@`。先选奇数 `@@M@@L@@` 使第一步为零，再选足够长的代表使第二步成立：`@@M@@z^L=1@@` 与 `@@M@@z^{2^a}=1@@` 互素，故 `@@M@@z=1@@`。于是度截断分离 `@@M@@\mathop{\mathrm{St}}\nolimits(R)@@` 的全部元素；再经稳定性定理（`@@M@@\mathop{\mathrm{St}}\nolimits_{12}(R)\hookrightarrow\mathop{\mathrm{St}}\nolimits(R)@@` 单射，文中用有序标架给出直接同调证明）回到秩 12。最后对 `@@M@@g\in G@@`：其矩阵像为 `@@M@@\Id+A@@`、`@@M@@A\in M_{12}(I)@@` 幂零，特征 `@@M@@2@@` 下 `@@M@@(\Id+A)^{2^a}=\Id@@`，故 `@@M@@g^{2^a}@@` 落入核，再用相对挠命题与单射性把它杀死，得 `@@M@@g@@` 为 `@@M@@2@@` 幂阶。

## 可信度与备注

本文主结果暂无形式化证明（任务元数据 formalized=false），请以社区核验为准。本文与姊妹篇"An infinite finitely presented periodic group"紧密咬合：群、代数、有限呈现与词层级全部引自姊妹篇（其定理 3.7 与层级命题被显式引作输入），本文新增相位分析、检测定理与剩余有限性，两文合成对"有限呈现＋剩余有限周期群"问题的完整否定回答。按 OpenAI 官方声明，未经形式化的结果可能存在问题；最值得优先核验的是相位引理与 relocation 步骤的细节。

{% endraw %}
