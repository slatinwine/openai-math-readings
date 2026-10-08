---
layout: default
title: "A CH obstruction to a prescribed categoricity threshold"
family: "240"
discipline: "Mathematical logic"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A CH obstruction to a prescribed categoricity threshold

> 结果族 240：Shelah's eventual categoricity and the prescribed-threshold obstruction　·　学科：Mathematical logic　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

一套积木说明书规定"怎样拼算合法"，零件数可以无限增加。数学家问：零件数固定时，合法拼法是唯一还是多样？"范畴性"猜想说，只要零件足够多就该唯一，还有人写死了"足够多"的具体门槛。本文证明：在连续统假设下，这个写死的门槛会失守。

**关键词卡片**

- 范畴性（categoricity）：给定基数下该类只有一个模型（精确到同构）——"尺寸固定则造型唯一"
- 抽象初等类（abstract elementary class, AEC）：比一阶理论更宽松的模型家族，只保留抽象的强子结构关系
- 连续统假设（CH）：断言实数恰有 `@@M@@\aleph_1@@` 个；它与 ZFC 独立，可作附加公理使用
- 指定阈值（prescribed threshold）：猜想写死的门槛 `@@M@@\beth_{(2^{\aleph_0})^+}@@`
- 不可证性（unprovability）：若 ZFC 自身无矛盾，则该命题不能由 ZFC 推出（注意是"不可证"，不是"独立"）

**看个具体例子**

在 ZFC＋CH 下构造类 `@@M@@K@@`（`@@M@@\mathrm{LS}(K)=\aleph_0@@`）：在 `@@M@@H(K)=\beth_{\omega_2}@@` 处恰有**两个**不同构模型（一个的基序不可数、一个可数），却在一切 `@@M@@\mu\ge\beth_{(2^{\aleph_1})^+}@@` 处唯一。于是在更高的范畴基数上，唯一性传不回门槛处；而 CH 下 `@@M@@\beth_{\omega_2}@@` 恰是猜想的指定阈值。推论：`@@M@@\mathrm{Con}(\mathrm{ZFC})\Rightarrow\mathrm{Con}(\mathrm{ZFC}+\neg\Phi)@@`——指定阈值形式的传递命题 `@@M@@\Phi@@` 在 ZFC 中不可证。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="26" text-anchor="middle" font-size="15">尺寸轴：小处出岔子，大处全唯一</text>
  <line x1="60" y1="150" x2="495" y2="150" stroke="#333" stroke-width="2"/>
  <polygon points="487,143 505,150 487,157" fill="#333"/>
  <line x1="320" y1="150" x2="488" y2="150" stroke="#2ca02c" stroke-width="7" stroke-linecap="round"/>
  <line x1="320" y1="95" x2="320" y2="205" stroke="#1f77b4" stroke-width="2" stroke-dasharray="5 5"/>
  <circle cx="230" cy="150" r="7" fill="#d62728"/>
  <text x="230" y="125" text-anchor="middle" font-size="13" fill="#d62728">beth ω₂ 处：两个模型</text>
  <text x="320" y="88" text-anchor="middle" font-size="13" fill="#1f77b4">Λ</text>
  <text x="405" y="128" text-anchor="middle" font-size="13" fill="#2ca02c">≥ Λ：处处唯一（范畴）</text>
  <text x="270" y="185" text-anchor="middle" font-size="13">模型尺寸（基数）</text>
  <text x="280" y="225" text-anchor="middle" font-size="12" fill="#555">CH 下 beth ω₂ 恰为猜想的指定门槛，却有两个模型</text>
</svg>

</div>

**为什么值得关心**

它没有推翻猜想的"定性版本"，而是精确定位：写死的具体常数越不过 ZFC 的能力边界；这个反例构造本身已被机器验证。

> 已 Lean 形式化

## 一句话结论

在连续统假设（CH）下构造出 Löwenheim–Skolem 数为 `@@M@@\aleph_0@@` 的抽象初等类：它在指定阈值 `@@M@@\beth_{\omega_2}=H(K)@@` 处有两个不同构模型，却在所有 `@@M@@\ge\beth_{(2^{\aleph_1})^+}@@` 的基数上范畴；故若 ZFC 相容，谢拉赫范畴性猜想的"指定阈值"形式在 ZFC 中不可证。

## 问题背景

Morley（1965）证明了可数语言完备一阶理论的 Morley 范畴性定理：在一个不可数基数上范畴，则在所有不可数基数上范畴。Shelah 在 1970 年代中期引入抽象初等类（abstract elementary class, AEC）框架，把讨论推广到未必一阶可公理化的模型类，并提出了范畴性传递猜想。该猜想有强弱两个版本：定性版本只要求存在某个仅依赖 `@@M@@\kappa\ge\LS(K)@@` 的一致阈值 `@@M@@\chi(\kappa)@@`；定量版本则指定阈值为 `@@M@@h(\kappa)=\beth_{(2^\kappa)^+}@@`，即所谓 Hanf 数式的界。此前文献中的向下传递定理（如 Vasey 2017）都需要融合性（amalgamation）、tameness 等额外结构假设；Espindola（2023）宣称对任意 AEC 证明了指定阈值处的传递。本文在 CH 下构造反例，说明这个具体的指定阈值并不足够。

## 主要结果

主定理（在 ZFC+CH 中证明）：存在可数关系语言中的 AEC `@@M@@K@@`，满足：(i) `@@M@@\LS(K)=\aleph_0@@`；(ii) `@@M@@K@@` 在基数 `@@M@@\beth_{\omega_2}=H(K)=\beth_{(2^{\aleph_0})^+}@@` 处至少有两个不同构的模型；(iii) 记 `@@M@@\Lambda=\beth_{(2^{\aleph_1})^+}@@`，则 `@@M@@K@@` 在每个基数 `@@M@@\mu\ge\Lambda@@` 上范畴。于是在范畴基数 `@@M@@\lambda=\Lambda^+>H(K)@@` 处，范畴性无法向下传递到 `@@M@@H(K)@@`。推论（论文 Corollary 5.2 的精确一阶表述）：ZFC 证明 `@@M@@\mathrm{CH}\Rightarrow\Theta@@` 且 `@@M@@\Theta\Rightarrow\neg\Phi@@`，再由哥德尔相对相容性定理得 `@@M@@\mathrm{Con}(\mathrm{ZFC})\Rightarrow\mathrm{Con}(\mathrm{ZFC}+\neg\Phi)@@`——若 ZFC 相容，指定阈值形式的传递命题 `@@M@@\Phi@@` 不是 ZFC 的定理。注意这是一侧的不可证性，并未断言 `@@M@@\Phi@@` 独立于 ZFC。此外文中证明该类不满足融合性与联合嵌入（joint embedding），这解释了为何带结构假设的既有传递定理与此并不矛盾。

## 证明思路

结构有两个基本排序：索引序 `@@M@@I@@` 控制模型大小；基序 `@@M@@B@@` 是无端点稠密线序且每个有界区间可数（故 `@@M@@|B|\le\aleph_1@@`）。对 `@@M@@I@@` 的每个非空有限组（tuple），结构携带一族行纤维和一族列纤维：行纤维是以 `@@M@@[B]^{<\omega}@@`（对称差为加法）为平移群的 torsor，列纤维是 `@@M@@[\omega]^{<\omega}@@`-torsor，行与列之间有一个 mod 2 的比特关系。语言不命名任何原点：换行原点只改变该行有限个比特，换列原点只改变该列有限个比特。于是当 `@@M@@B@@` 可数时这些变换能吸收任意比特矩阵，同构由"矩阵差三角分解为行、列两族有限支撑平移"给出；而当 `@@M@@B@@` 不可数时，每列留下一个真实的颜色不变量，落在 `@@M@@2^\omega/=^*@@`（模有限差商）中。

颜色须通过"全子序列测试"：颜色解码为可数的外延（extensional）成员关系图，其秩标签低于 `@@M@@\omega_1@@`，且任意子组的图与全组图相容。关键的非对称设计是：对象条件只要求每个组有可数多个例外列，而强子结构（strong substructure）要求新增列对旧组的测试零例外——先靠有限行支撑保证测试在旧原点选取下不变，再据此逐条验证全部 AEC 公理（有向并、平滑性、向下 Löwenheim–Skolem 均成立）。

端点模型 `@@M@@M_u@@` 取 `@@M@@I=V_{\omega_2}@@`（由 `@@M@@|V_{\omega+\gamma}|=\beth_\gamma@@` 知大小为 `@@M@@\beth_{\omega_2}@@`）、`@@M@@B=\omega_1\times\mathbb Q@@`。颜色编码 `@@M@@V_{\omega_2}@@` 元素真实的成员关系图；真实秩（`@@M@@<\omega_2@@`）用一条 `@@M@@\omega_2@@` 长的尺度链 `@@M@@f_\alpha:\omega_1\to\omega_1@@`（模可数集严格递增，由对角递归构造）压成 `@@M@@\omega_1@@` 以下标签，使每个组的失败集可数。`@@M@@M_c@@` 用可数基序 `@@M@@\mathbb Q@@` 与全零颜色，大小相同；两者基序基数不同（`@@M@@\aleph_1@@` 对 `@@M@@\aleph_0@@`），故不同构。

尾部范畴性：若 `@@M@@B@@` 不可数且 `@@M@@|I|\ge\Lambda@@`，先用有限划分估计（Erdős–Rado 式端齐次方法，调色板 `@@M@@\le\xi=2^{\aleph_1}<\cf\Lambda@@`）抽出各元数的固定颜色模式 `@@M@@s_j@@`，并在可数个例外集之外选一个公共坐标 `@@M@@b@@` 使 `@@M@@s_j@@` 在 `@@M@@b@@` 处通过全部测试；但固定模式不可能存在——它会在某个 `@@M@@|X|>|V_{\omega_1}|@@` 的集合上拼出带 `@@M@@\omega_1@@` 以下秩标签的外延关系，Mostowski 式坍缩随之把 `@@M@@X@@` 单射进 `@@M@@V_{\omega_1}@@`，矛盾。故 `@@M@@B@@` 不可数时必有 `@@M@@|I|<\Lambda@@`，从而 `@@M@@\mu\ge\Lambda@@` 的模型都有可数基序和同尺寸索引序，由前述矩阵分解彼此同构。最后在 CH 下 `@@M@@H(K)=\beth_{\omega_2}@@`，与 `@@M@@\Lambda^+>H(K)@@` 合并即得不可证性推论。

## 可信度与备注

按本批任务元数据，该文主结果已附 Lean 形式化证明；同族姊妹篇在 ZFC 中证明了定性版本的 eventual categoricity（暂无形式化），两文合成完整图景：定性阈值存在，而具体的指定界 `@@M@@\beth_{(2^\kappa)^+}@@` 在 CH 下失效——本文构造的类自身在 `@@M@@\Lambda@@` 以上的尾部范畴，正说明障碍恰好只在这个指定端点。依据 OpenAI 官方声明，未经形式化的结果可能存在问题，故姊妹篇结论宜以社区核验为准，而本文因有形式化支撑更为可靠。另注：论文第 6 节还具体指出了先前所引证明中"稠密余筛可被大模型提升"一步的障碍，定位了分歧根源。

{% endraw %}
