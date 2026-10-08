---
layout: default
title: "Generalized Star Height at Most Three"
family: "134"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Generalized Star Height at Most Three

> 结果族 134：Generalized star height at most three　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

还是"星号套娃几层够用"的问题，这次的答案更狠：3 层。诀窍像切香肠：把一个长词切成首尾相接的小段，并规定任何一段都不许是另一段的开头，于是无论词多长，切法都唯一。靠着这本"唯一切分账"，论文把所有正则语言的星号嵌套深度压到 3 层封顶。

**关键词卡片**

- 广义星高（generalized star height）：允许取补的正则表达式里，星号最深嵌套的层数。
- 前缀码（prefix code）：任何片段都不是另一片段开头的编码方式，保证切分唯一。
- 片段（episode）：切出的短词段，各自携带一小笔"状态账目更新"。
- 有限幺半群（finite monoid）：自动机记忆的代数化身，元素只有有限个。
- 移位表（shift table）：让切口在周期段中滑动而乘积保持不变的对照表。

**看个具体例子**

把 `@@M@@ababbaab\cdots@@` 切成 `@@M@@ab\,|\,abba\,|\,ab\cdots@@`：只要每段都不是别的段的开头，整词就只会切出这一种片段序列；每段查一次账、更新一次状态，词的归属便定了。定理：任何正则语言 `@@M@@L@@` 都满足 `@@M@@h_\Sigma(L)\le 3@@`，补在同一个 `@@M@@\Sigma^*@@` 中取。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="28" text-anchor="middle" font-size="15" fill="#333">长词切成片段：切法唯一，每段记一笔账</text><text x="40" y="86" font-size="14" fill="#555">词 w =</text><rect x="95" y="58" width="90" height="44" rx="6" fill="#eef7ee" stroke="#383" stroke-width="2"/><text x="140" y="86" text-anchor="middle" font-size="15" fill="#263">a b</text><rect x="215" y="58" width="150" height="44" rx="6" fill="#fff7e8" stroke="#a73" stroke-width="2"/><text x="290" y="86" text-anchor="middle" font-size="15" fill="#642">a b b a</text><rect x="395" y="58" width="120" height="44" rx="6" fill="#fdeeee" stroke="#933" stroke-width="2"/><text x="455" y="86" text-anchor="middle" font-size="15" fill="#622">a b …</text><line x1="200" y1="50" x2="200" y2="110" stroke="#999" stroke-width="2" stroke-dasharray="5,4"/><line x1="380" y1="50" x2="380" y2="110" stroke="#999" stroke-width="2" stroke-dasharray="5,4"/><text x="140" y="132" text-anchor="middle" font-size="13" fill="#383">片段 1</text><text x="290" y="132" text-anchor="middle" font-size="13" fill="#a73">片段 2</text><text x="455" y="132" text-anchor="middle" font-size="13" fill="#933">片段 3</text><text x="40" y="176" font-size="14" fill="#333">每段自带一次"账目更新"（状态如何变化），</text><text x="40" y="204" font-size="14" fill="#333">且任何片段都不是另一片段的开头，</text><text x="40" y="232" font-size="14" fill="#333">所以无论词多长，切分方式都唯一。</text><text x="40" y="262" font-size="14" fill="#345">靠这一点，任何正则语言的星号嵌套 ≤ 3 层。</text></svg>

</div>

**为什么值得关心**

在此系列之前，人们甚至找不到一个广义星高大于 1 的具体语言，更没有绝对上界；本系列三个独立证明（界 13、4、3）互相印证，本篇的 3 是当前最强纪录。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文证明：任何正则语言都可用嵌套星号至多 3 层、允许取补的广义正则表达式在原字母表上写出。这是广义星高问题一致有界性当前已知的最强上界，用"词片段前缀码 + 任意函数移位表 + 全模板解码器"仅两次分裂即达成。

## 问题背景

广义星高问题（generalized star-height problem）问：允许并、连接、星号与取补后，表达所有正则语言需要多深的星号嵌套。星高零即星自由语言，由 Schützenberger 定理（1965）用非周期有限幺半群刻画。普通星高有 Dejean–Schützenberger（1966）的无界下界，但加入补后失效。星高一的正面结果散见于有限交换群（Henneman）、二类幂零群（Pin–Straubing–Thérien 1992）、固定因子计数模 `@@M@@n@@` 的语言（Bourne–Ruškuc 2016；Bourne 2017 推广到任意固定因子）等受限族，均不含任意正则语言。Straubing（2002）把"是否存在绝对上界"与"高度一是否总够"列为两个不同问题；直到近年综述仍没有已知广义星高大于一的语言。本族三篇论文分别给出 13、4、3 的绝对上界，本文给出最强的一个。

## 主要结果

定理 1.1：对每个有限字母表 `@@M@@\Sigma@@` 与每个正则语言 `@@M@@L\subseteq\Sigma^*@@`，有 `@@M@@h_\Sigma(L)\le3@@`，其中补在同一个自由幺半群 `@@M@@\Sigma^*@@` 中取。有限参数与表达式长度可依赖于语言，但嵌套层数被绝对控制；论文不给表达式规模或运行时间的界。核心技术是把有限幺半群计算表达为一组词片段（前缀码）上的仿射更新，配合对任意函数都成立的移位表（shift table）与覆盖全部候选切分的"全模板"（whole-stencil）解码器，使整条递归只需要两次分裂。

## 证明思路

先归约到有限幺半群态射 `@@M@@T:\Sigma^*\to M@@`，让 `@@M@@M@@` 忠实右作用于 `@@M@@V=\mathbf F_2^M@@`（基向量 `@@M@@e_m@@` 满足 `@@M@@e_md=e_{md}@@`）。把词切成片段（episodes）构成前缀码 `@@M@@E@@`，切分唯一；每段携带一个仿射更新。分裂恒等式把"段序列的图语言"化为高度 `@@M@@\max\{2,H+1\}@@` 的表达式，条件是前缀/后缀测试对独立成功配对可靠、对非跳过段可用；仿射恢复用 `@@M@@g_w(v)-g_w(0)@@` 提取线性部分，齐次提升 `@@M@@(v,c)\mapsto(vL+c\gamma,c)@@` 把仿射映射变成线性映射，都不加星号。第一步（外层分裂）处理大多数片段：标签（tags）记录状态、区间乘积与指标，时钟限制前后缀能共同实现的标签对——要么一致，要么恰有一对不等，后者由按段定义的仿射平移吸收；一致时若有标记边界，用移位表让乘积元组中一个坐标对传递的输出无关（前缀查早期乘积、后缀查后期乘积、有限证书检查跨界乘积的每个可能值），若某标记缺失，则用有限幺半群中幂的终归周期性让切口穿过全部时钟剩余类而前缀乘积不变。关键的移位表引理对任意函数 `@@M@@f:A^l\to\operatorname{End}_{\rm lin}(S)@@` 成立：存在只依赖 `@@M@@|A|,|S|@@` 的 `@@M@@l@@`，使每个 `@@M@@f@@` 都有校正 `@@M@@\beta_f@@`，让每组输入与元组各有一条常值坐标线——其证明是把 `@@M@@\beta@@` 视为独立随机向量、用 Erdős–Lovász 相依图方法避免所有坏事件。第二步（内层分裂）处理时钟与标记条件失效的例外片段集 `@@M@@D@@`：在片段早期放置含 `@@M@@\mu@@` 份副本的模板（stencil），后缀把每个候选起点 `@@M@@\tau_{p'}=k+L-p'@@` 的异常谓词当作"见证"来唯一解码真起点——大、小两级末端搜索的配合保证真见证在唯一性判定前不被误删，而对全模板中假起点的计数（末端不稳至多 4 对、每个固定锚点时钟部分至多 `@@M@@c_{\rm cl}\log(2m)@@` 对、每锚点每标签内部标记失败至多 3 对）得出总数小于 `@@M@@\mu@@`，故每种元数据都有可用副本；随后后缀用一个对每个假设前缀乘积 `@@M@@m'\in M@@`（含不可行值）都有定义的总表 `@@M@@\psi_e@@` 完成传输，其线性部分恰是原更新的齐次提升。高度计数：内层分裂从空跳过类出发得 2，布尔恢复后作为外层分裂的跳过类得 3。编译阶段每个成分至多一段无界周期延续，落入模板 `@@M@@ac^ib@@`、数据终归周期，故高度至多一；尾部 `@@M@@F=\neg(E\Sigma^*)@@` 高度一，最终语言为 `@@M@@\bigcup_{df\in S}A_dF_f@@`。

## 可信度与备注

本文验证状态为未形式化：主结果尚无 Lean 证明，请以社区核验为准。同族姊妹篇（界 13 的预测—历史方法、界 4 的多尺度输运方法）与本篇共享分裂恒等式、仿射恢复与标记—周期性原理，三者各自完整、互不引用对方数值定理，构成同一结论的多重独立验证。依照 OpenAI 官方声明，未经形式化的结果可能有问题，本文构造规模巨大且技术繁复，正式采信前宜等待同行评议。

{% endraw %}
