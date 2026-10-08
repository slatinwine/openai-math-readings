---
layout: default
title: "Simple $F_\\infty$ overgroups of groups with decidable word problem"
family: "250"
discipline: "Group theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Simple `@@M@@F_\infty@@` overgroups of groups with decidable word problem

> 结果族 250：Boone–Higman embeddings with higher finiteness　·　学科：Group theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

上一篇导读说，字问题可判定的群能搬进"说明书有限"的单群；这一篇把装修标准推向极致：房子不仅说明书有限，而且每一层楼（每一个维数）只用了有限块砖，楼层却可以无限向上。论文证明：任何字问题可判定的有限生成群，都能搬进这样一栋"每层都精简"的通透公寓——即类型 `@@M@@F_\infty@@` 的单群。

**关键词卡片**

- 类型 F∞（type F∞）：拥有"每维只含有限多胞腔"的分类空间；`@@M@@F_1@@` 即有限生成、`@@M@@F_2@@` 即有限呈现
- 单群（simple group）：没有非平凡正规子群、"内部无隔间"的群
- 字问题（word problem）：算法能否判定一个词代表单位元
- 高传递作用（highly transitive action）：任意长度的互异有序点组都能被搬到任一同长点组的作用
- 扭曲 Brin–Thompson 群（twisted Brin–Thompson group）：由高传递作用组装出的单群，证明的终点站

**看个具体例子**

`@@M@@\mathbb{Z}@@` 的分类空间是圆周：一个 0 维砖块加一个 1 维砖块，更高维一块不用，所以 `@@M@@\mathbb{Z}@@` 是 `@@M@@F_\infty@@`。而输入群 `@@M@@G@@` 可能连有限呈现都不是（关系无穷多）。定理数字版：这样的 `@@M@@G@@` 照样嵌入某个非平凡单群 `@@M@@H@@`，且 `@@M@@H@@` 的分类空间每一维只有有限个胞腔；`@@M@@H@@` 甚至可由两个有限阶元素生成。作为推论，"字问题可判定的有限生成群"恰好就是 `@@M@@F_\infty@@` 单群的全部有限生成子群。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="20" y="30" font-size="15" fill="#333333">F∞ 单群 H：每层砖块有限，楼层无限</text>
  <rect x="110" y="60" width="230" height="34" fill="#eceff1" stroke="#546e7a"/>
  <text x="122" y="82" font-size="13" fill="#455a64">3 维：5 块砖（关系之间的关系）</text>
  <rect x="110" y="94" width="230" height="34" fill="#e3f2fd" stroke="#1565c0"/>
  <text x="122" y="116" font-size="13" fill="#0d47a1">2 维：3 块砖（有限呈现）</text>
  <rect x="110" y="128" width="230" height="34" fill="#e8f5e9" stroke="#2e7d32"/>
  <text x="122" y="150" font-size="13" fill="#1b5e20">1 维：2 块砖（有限生成）</text>
  <line x1="225" y1="60" x2="225" y2="42" stroke="#90a4ae" stroke-dasharray="4 3"/>
  <text x="240" y="54" font-size="12" fill="#78909c">更高维继续，每层仍有限</text>
  <circle cx="450" cy="150" r="52" fill="#fff3e0" stroke="#ef6c00" stroke-width="2"/>
  <text x="420" y="144" font-size="13" fill="#e65100">任意字问题</text>
  <text x="420" y="162" font-size="13" fill="#e65100">可判定的群 G</text>
  <line x1="398" y1="150" x2="348" y2="150" stroke="#ef6c00" stroke-width="2"/>
  <polygon points="348,150 360,144 360,156" fill="#ef6c00"/>
</svg>

</div>

**为什么值得关心**

`@@M@@F_\infty@@` 蕴含有限呈现，故它顺手给出 Boone–Higman 猜想的另一证明，并把"单群能造得多精简"推到理论极限；此前除若干特殊群族外，一般情形无从下手。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
证明了 Boone–Higman 猜想的高阶有限性强化：每个字问题（word problem）可判定的有限生成群，都嵌入一个 `@@M@@F_\infty@@` 型的非平凡单群——即拥有每维只含有限多个胞腔的分类空间。由于 `@@M@@F_\infty@@` 蕴涵有限呈现，这同时给出了原猜想的另一条证明，并把单超群的有限性推到同伦的每一维。

## 问题背景
1974 年 Boone 与 Higman 证明：有限生成群字问题可判定当且仅当 `@@M@@G\leq H\leq K@@`，`@@M@@H@@` 单、`@@M@@K@@` 有限呈现，并问 `@@M@@H@@` 能否取有限呈现——即 Boone–Higman 猜想。一个更强的自然问题是要求 `@@M@@H@@` 具有类型 `@@M@@F_\infty@@`（type `@@M@@F_\infty@@`）：拥有一个在每个维数只含有限多个胞腔的类分类空间（classifying space）`@@M@@K(H,1)@@`（`@@M@@F_1@@` 即有限生成、`@@M@@F_2@@` 即有限呈现）。该问题出现在 BBMZ 综述 Question 5.6 之后的讨论中。此前只知一些局部结果：Brown 证明 Thompson–Higman 群族是 `@@M@@F_\infty@@`；Belk–Zaremsky 造出含一切右角 Artin 群的 `@@M@@F_\infty@@` 单群、Belk–Hyde–Matucci 造出含一切可数交换群的 `@@M@@F_\infty@@` 单群，但都没有从字问题算法出发的一般构造。障碍也是具体的：FFKLZ 定理表明，有限虚上同调维数群或可数线性群的寡态作用必有某个有限子集稳定子不是 `@@M@@F_\infty@@`——所以作用群与稳定子必须一并从头建造。

## 主要结果
主定理：每个字问题可判定的有限生成群 `@@M@@G@@` 都可单射同态入某个非平凡单群 `@@M@@H@@`，且 `@@M@@H@@` 具有类型 `@@M@@F_\infty@@`。输入群不必有限呈现，判定算法运行时间任意。结合 Kuznetsov 方向的经典论证（非平凡有限呈现单群字问题可判定且遗传给有限生成子群），这类群恰好就是 `@@M@@F_\infty@@` 单群的有限生成子群。附加结论：同一超群 `@@M@@H@@` 还可由两个有限阶元素生成。论文的核心中间定理是一个高传递作用：存在含 `@@M@@G@@` 的群 `@@M@@\Lambda@@`，在可数无限集上忠实作用，且对每个固定长度的互异有序点组传递（highly transitive），同时 `@@M@@\Lambda@@` 与每个有限点组的逐点稳定子都是 `@@M@@F_\infty@@`——这恰好凑齐 Belk–Zaremsky 扭曲 Brin–Thompson 定理的全部输入。

## 证明思路
先定路线：Belk–Zaremsky 定理说，若 `@@M@@\Lambda@@` 忠实、寡态（oligomorphic，即在每个固定基数的有限子集上只有有限多个轨道）地作用于可数集 `@@M@@S@@`，且 `@@M@@\Lambda@@` 与每个有限子集的集型稳定子均为 `@@M@@F_\infty@@`，则扭曲 Brin–Thompson 群 `@@M@@SV_\Lambda@@` 非平凡、单、`@@M@@F_\infty@@` 且含 `@@M@@\Lambda@@`。高传递远强于寡态，故任务化为造作用并证所有稳定子 `@@M@@F_\infty@@`。再构造作用：取有限呈现环 `@@M@@B@@`，令 `@@M@@Q=\mathrm E_7(B)@@` 作用于列集 `@@M@@X=B^7@@`；用"压缩对角"引理把形如 `@@M@@D_1(1+\phi^2(v-1))@@` 的单位嵌入初等矩阵群（在 `@@M@@\mathrm{GE}_r/\mathrm E_r@@` 的交换商里，靠四个两两正交又等价的幂等元把类压成 `@@M@@c=c^2@@`），得到相容单射 `@@M@@\delta:Q\to Q@@`、`@@M@@\sigma:X\to X@@`；取直极限并附加层级平移 `@@M@@t@@`，得到上升环面（ascending torus）`@@M@@\Lambda=N\rtimes\langle t\rangle@@`。压缩后每列集中于第一坐标，前缀算子 `@@M@@S_xT_x@@` 两两正交，使 `@@M@@Q@@` 能实现 `@@M@@\sigma(X)@@` 的任意有限支撑置换，于是两组同长有序点组推进一层即可互送，得高传递；忠实性靠非平凡矩阵必动某基列、以及层级严格增长识别出 `@@M@@t@@`。然后是全文核心的上升环面判据：设单射自同态 `@@M@@f:U\to U@@` 经过有限呈现群分解（保证 `@@M@@T(U,f)=\langle U,t\mid t^{-1}ut=f(u)\rangle@@` 有限呈现），且对 `@@M@@\ell=2,3@@` 各有一组以 `@@M@@\{0,1\}^{\mathbb N}@@` 前缀算子导出的幂等元为指标的同态 `@@M@@h_E@@`，正交时像交换且保持乘法分解，则 `@@M@@T(U,f)@@` 是 `@@M@@F_\infty@@`。证明走 Bieri–Eckmann 乘积模判据：只需对一切指标集 `@@M@@\mathcal I@@` 证 `@@M@@H_n(J,(\mathbb ZJ)^{\mathcal I})=0@@`（`@@M@@n\ge2@@`）。关键新工具是"单纯形类型"的控制：以有限对称集为界的单纯形在左平移下只有有限多个类型；先用 Alexander–Whitney 对角与 shuffle 映射（mitotic 群对角论证的受控版）建立加性引理，再归纳证明存在统一的幂次 `@@M@@k@@` 与公共输出界，使 `@@M@@f^k@@` 把给定界内一切约化 `@@M@@n@@`-圈链都变为边界——统一的精髓在于控制类型而非链长与系数。继而对同调类 `@@M@@z_E=[(h_Ef^k)_*z]@@` 套用幂等引理（三份 `@@M@@M_3(\mathbb F_\ell)@@` 的对角幂等元上的加性关系迫使 `@@M@@\ell z_I=0@@`），2 与 3 两套系统分别湮灭同一类，故 `@@M@@z_I=0@@`；最后用陪集 `@@M@@jU@@` 构成的 `@@M@@J@@`-树给出上升 HNN 同调正合列，`@@M@@F@@` 的局部幂零性使 `@@M@@1-F@@` 可逆，完成消灭。最后组装稳定子：逐点稳定子被识别为上升环面 `@@M@@T(U,f)@@`，`@@M@@f(u)=a\delta(u)a^{-1}@@`；其分解经有限呈现的 Steinberg 群 `@@M@@\mathrm{St}_6(B)@@`——用姊妹篇的 Steinberg 核湮灭定理把 `@@M@@B^\times@@` 的同态提升到 `@@M@@\mathrm{St}_6(B)@@`（配合 Krstić–McCool 的有限呈现定理），再用交换矩阵 `@@M@@E=e_{12}(d)e_{21}(-d)e_{12}(d)@@` 把单位从坐标 1 挪到坐标 2 而不动标记列，使第二个分解因子把整个 Steinberg 群送进稳定子。集型稳定子是逐点稳定子的有限指数扩张，封闭性引理保证仍为 `@@M@@F_\infty@@`。至于环 `@@M@@B@@` 本身，其单元既编码 `@@M@@G@@` 又编码 `@@M@@\mathrm E_7(B)@@` 作用的指定扩充——这一自指由姊妹篇的有限编译器加长度归纳与 Kleene 递归定理化解。

## 可信度与备注
本篇为 OpenAI 批量预印本，暂无 Lean 形式化证明，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。它是结果族 250 的"高阶有限性篇"：基石篇（有限代数包络证原猜想）向它提供有限编译器、二进角落构造与 Steinberg 核湮灭定理，第三篇万有群又复用本文的判据；三篇链条环环相扣，任何一环有误都会波及全局。同调部分的均匀填充论证技术性较强，此处从略，详见论文第 2 节。

{% endraw %}
