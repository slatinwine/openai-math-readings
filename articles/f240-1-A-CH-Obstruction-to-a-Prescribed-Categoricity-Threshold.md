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

## 一句话结论

在连续统假设（CH）下构造出 Löwenheim–Skolem 数为 \(\aleph_0\) 的抽象初等类：它在指定阈值 \(\beth_{\omega_2}=H(K)\) 处有两个不同构模型，却在所有 \(\ge\beth_{(2^{\aleph_1})^+}\) 的基数上范畴；故若 ZFC 相容，谢拉赫范畴性猜想的"指定阈值"形式在 ZFC 中不可证。

## 问题背景

Morley（1965）证明了可数语言完备一阶理论的 Morley 范畴性定理：在一个不可数基数上范畴，则在所有不可数基数上范畴。Shelah 在 1970 年代中期引入抽象初等类（abstract elementary class, AEC）框架，把讨论推广到未必一阶可公理化的模型类，并提出了范畴性传递猜想。该猜想有强弱两个版本：定性版本只要求存在某个仅依赖 \(\kappa\ge\LS(K)\) 的一致阈值 \(\chi(\kappa)\)；定量版本则指定阈值为 \(h(\kappa)=\beth_{(2^\kappa)^+}\)，即所谓 Hanf 数式的界。此前文献中的向下传递定理（如 Vasey 2017）都需要融合性（amalgamation）、tameness 等额外结构假设；Espindola（2023）宣称对任意 AEC 证明了指定阈值处的传递。本文在 CH 下构造反例，说明这个具体的指定阈值并不足够。

## 主要结果

主定理（在 ZFC+CH 中证明）：存在可数关系语言中的 AEC \(K\)，满足：(i) \(\LS(K)=\aleph_0\)；(ii) \(K\) 在基数 \(\beth_{\omega_2}=H(K)=\beth_{(2^{\aleph_0})^+}\) 处至少有两个不同构的模型；(iii) 记 \(\Lambda=\beth_{(2^{\aleph_1})^+}\)，则 \(K\) 在每个基数 \(\mu\ge\Lambda\) 上范畴。于是在范畴基数 \(\lambda=\Lambda^+>H(K)\) 处，范畴性无法向下传递到 \(H(K)\)。推论（论文 Corollary 5.2 的精确一阶表述）：ZFC 证明 \(\mathrm{CH}\Rightarrow\Theta\) 且 \(\Theta\Rightarrow\neg\Phi\)，再由哥德尔相对相容性定理得 \(\mathrm{Con}(\mathrm{ZFC})\Rightarrow\mathrm{Con}(\mathrm{ZFC}+\neg\Phi)\)——若 ZFC 相容，指定阈值形式的传递命题 \(\Phi\) 不是 ZFC 的定理。注意这是一侧的不可证性，并未断言 \(\Phi\) 独立于 ZFC。此外文中证明该类不满足融合性与联合嵌入（joint embedding），这解释了为何带结构假设的既有传递定理与此并不矛盾。

## 证明思路

结构有两个基本排序：索引序 \(I\) 控制模型大小；基序 \(B\) 是无端点稠密线序且每个有界区间可数（故 \(|B|\le\aleph_1\)）。对 \(I\) 的每个非空有限组（tuple），结构携带一族行纤维和一族列纤维：行纤维是以 \([B]^{<\omega}\)（对称差为加法）为平移群的 torsor，列纤维是 \([\omega]^{<\omega}\)-torsor，行与列之间有一个 mod 2 的比特关系。语言不命名任何原点：换行原点只改变该行有限个比特，换列原点只改变该列有限个比特。于是当 \(B\) 可数时这些变换能吸收任意比特矩阵，同构由"矩阵差三角分解为行、列两族有限支撑平移"给出；而当 \(B\) 不可数时，每列留下一个真实的颜色不变量，落在 \(2^\omega/=^*\)（模有限差商）中。

颜色须通过"全子序列测试"：颜色解码为可数的外延（extensional）成员关系图，其秩标签低于 \(\omega_1\)，且任意子组的图与全组图相容。关键的非对称设计是：对象条件只要求每个组有可数多个例外列，而强子结构（strong substructure）要求新增列对旧组的测试零例外——先靠有限行支撑保证测试在旧原点选取下不变，再据此逐条验证全部 AEC 公理（有向并、平滑性、向下 Löwenheim–Skolem 均成立）。

端点模型 \(M_u\) 取 \(I=V_{\omega_2}\)（由 \(|V_{\omega+\gamma}|=\beth_\gamma\) 知大小为 \(\beth_{\omega_2}\)）、\(B=\omega_1\times\mathbb Q\)。颜色编码 \(V_{\omega_2}\) 元素真实的成员关系图；真实秩（\(<\omega_2\)）用一条 \(\omega_2\) 长的尺度链 \(f_\alpha:\omega_1\to\omega_1\)（模可数集严格递增，由对角递归构造）压成 \(\omega_1\) 以下标签，使每个组的失败集可数。\(M_c\) 用可数基序 \(\mathbb Q\) 与全零颜色，大小相同；两者基序基数不同（\(\aleph_1\) 对 \(\aleph_0\)），故不同构。

尾部范畴性：若 \(B\) 不可数且 \(|I|\ge\Lambda\)，先用有限划分估计（Erdős–Rado 式端齐次方法，调色板 \(\le\xi=2^{\aleph_1}<\cf\Lambda\)）抽出各元数的固定颜色模式 \(s_j\)，并在可数个例外集之外选一个公共坐标 \(b\) 使 \(s_j\) 在 \(b\) 处通过全部测试；但固定模式不可能存在——它会在某个 \(|X|>|V_{\omega_1}|\) 的集合上拼出带 \(\omega_1\) 以下秩标签的外延关系，Mostowski 式坍缩随之把 \(X\) 单射进 \(V_{\omega_1}\)，矛盾。故 \(B\) 不可数时必有 \(|I|<\Lambda\)，从而 \(\mu\ge\Lambda\) 的模型都有可数基序和同尺寸索引序，由前述矩阵分解彼此同构。最后在 CH 下 \(H(K)=\beth_{\omega_2}\)，与 \(\Lambda^+>H(K)\) 合并即得不可证性推论。

## 可信度与备注

按本批任务元数据，该文主结果已附 Lean 形式化证明；同族姊妹篇在 ZFC 中证明了定性版本的 eventual categoricity（暂无形式化），两文合成完整图景：定性阈值存在，而具体的指定界 \(\beth_{(2^\kappa)^+}\) 在 CH 下失效——本文构造的类自身在 \(\Lambda\) 以上的尾部范畴，正说明障碍恰好只在这个指定端点。依据 OpenAI 官方声明，未经形式化的结果可能存在问题，故姊妹篇结论宜以社区核验为准，而本文因有形式化支撑更为可靠。另注：论文第 6 节还具体指出了先前所引证明中"稠密余筛可被大模型提升"一步的障碍，定位了分歧根源。

{% endraw %}
