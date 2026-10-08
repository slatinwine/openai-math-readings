---
layout: default
title: "A Nearly Quartic Separation Between Randomized and Quantum Query Complexity"
family: "284"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Nearly Quartic Separation Between Randomized and Quantum Query Complexity

> 结果族 284：The optimal quartic separation between randomized and quantum queries　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

量子计算机查资料能少翻很多页，问题是"最坏能省多少次"。已知对任何任务，随机算法所需的查询次数不超过量子算法的四次方，有人猜三次方就够。本文造出一族"规规矩矩"的函数（对每个输入都要答对），其随机查询数几乎顶到四次方——四次方这个指数被证明最优，三次方猜想被推翻。

**关键词卡片**

- 查询复杂度 R(f) 与 Q(f)（query complexity）：最坏情形下随机／量子算法最少要读多少输入位
- 全函数（total function）：所有输入上都要给出答案，不许只挑部分输入
- 四次普适上界（quartic bound）：一切全函数满足 `@@M@@\mathbb{R}(f)=O(\mathbb{Q}(f)^4)@@`
- Forrelation：量子几次查询可解、经典却极难的一族函数，分离的引擎
- 锦标赛引理（tournament lemma）：把"打擂台淘汰赛"精确量子化

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <line x1="60" y1="240" x2="530" y2="240" stroke="#000" stroke-width="1.5"/>
  <line x1="60" y1="240" x2="60" y2="40" stroke="#000" stroke-width="1.5"/>
  <text x="514" y="262" font-size="13" fill="#000">Q</text>
  <text x="34" y="52" font-size="13" fill="#000">R</text>
  <text x="88" y="35" font-size="12" fill="#000">（对数尺度）</text>
  <line x1="80" y1="230" x2="480" y2="60" stroke="#000" stroke-width="1.8"/>
  <text x="475" y="52" font-size="13" fill="#000" text-anchor="end">R ≈ Q^4：最优上界</text>
  <line x1="80" y1="212" x2="480" y2="142" stroke="#999" stroke-width="1.5" stroke-dasharray="7,5"/>
  <text x="335" y="192" font-size="13" fill="#999">R = Q^3：被推翻的猜想</text>
  <circle cx="150" cy="207" r="5" fill="#c00"/>
  <circle cx="230" cy="173" r="5" fill="#c00"/>
  <circle cx="310" cy="139" r="5" fill="#c00"/>
  <circle cx="390" cy="105" r="5" fill="#c00"/>
  <text x="158" y="231" font-size="13" fill="#c00">本文的例子</text>
</svg>

</div>

公式卡（数字版定理）：`@@M@@\mathbb{Q}(F_{k,m})\le C_k\sqrt m\,(\log m)^{b_k}@@`，而 `@@M@@\mathbb{R}(F_{k,m})\ge c_k\,m^{2-1/k}/(\log m)^2@@`；两者之比约为 `@@M@@m^{3/2-1/k}@@`，取 `@@M@@k@@` 足够大，便任意接近四次幂。

**为什么值得关心**

它终结了随机与量子查询复杂度之间"指数究竟几次"的最后悬念：答案是 4，不是 3。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

构造出一族全布尔函数 `@@M@@F_{k,m}@@`：量子算法只需 `@@M@@\sqrt m\,(\log m)^{O_k(1)}@@` 次查询，而任何随机算法都需约 `@@M@@m^{2-1/k}/(\log m)^2@@` 次，两者之比可任意逼近四次幂。这证明已知的四次普适上界指数最优，并推翻了此前猜想的三次关系。

## 问题背景

查询复杂度 (query complexity) 统计算法读取输入比特的次数：`@@M@@\mathbb{R}(f)@@` 与 `@@M@@\mathbb{Q}(f)@@` 分别是随机与量子算法在最坏输入上错误至多 `@@M@@1/3@@` 时所需的最少查询数，两次查询之间的计算不受限制。Grover 搜索对 OR 函数给出最优的二次加速；对只须在部分输入上正确的部分函数 (partial function)，量子甚至有指数加速，但 Beals 等人 2001 年证明对全函数 (total function) 有 `@@M@@\D(f)=O(\mathbb{Q}(f)^6)@@`，指数加速不复可能。2021 年 Aaronson、Ben-David、Kothari、Rao、Tal 借黄皓的敏感度定理 (sensitivity theorem) 把上界压缩到 `@@M@@\D(f)=O(\mathbb{Q}(f)^4)@@`，并猜想随机复杂度满足更强的三次关系 `@@M@@\mathbb{R}(f)=O(\mathbb{Q}(f)^3)@@`。构造方面，借助作弊表 (cheat sheet) 与指针技术，已知的随机–量子分离从 `@@M@@5/2@@` 次幂逐步推进到 `@@M@@3-o(1)@@`。三次与四次之间孰是孰非，成为该领域最后悬而未决的指数问题，本文给出终局答案。

## 主要结果

主定理断言最优指数 `@@M@@\alpha_{\mathrm{tot}}=4@@`：一方面所有全函数满足 `@@M@@\mathbb{R}(f)=O((1+\mathbb{Q}(f))^4)@@`（已知结果，附录给出自足证明）；另一方面，对每个固定整数 `@@M@@k\ge2@@`，存在全函数 `@@M@@F_{k,m}@@`（`@@M@@m@@` 取充分大的 4 的幂）使

`@@M@@D\mathbb{Q}(F_{k,m})\le C_k\sqrt m\,(\log m)^{b_k},\qquad \mathbb{R}(F_{k,m})\ge c_k\,\frac{m^{2-1/k}}{(\log m)^2}.@@`

二者之比为 `@@M@@m^{3/2-1/k}@@` 除以多项式对数因子，令 `@@M@@k@@` 增大便任意接近四次幂。于是任何 `@@M@@\alpha<4@@` 的普适关系 `@@M@@\mathbb{R}(f)=O((1+\mathbb{Q}(f))^\alpha)@@` 都被否定，文献中猜想的三次界随之证伪。

## 证明思路

构造是"带外向指针 (outward pointer) 的编址证书"。输入分 `@@M@@m@@` 列，每列含 `@@M@@m@@` 位串 `@@M@@X_i@@`、`@@M@@r=O(\log m)@@` 个无承诺的 `@@M@@k@@` 重 Forrelation 实例，以及按这 `@@M@@r@@` 个实例的答案（即真实地址）索引的证书单元 `@@M@@B_{i,s}@@`，内存放指向其余各列的指针与电路求值记录 (transcript)。列 `@@M@@i@@` 获胜，指 `@@M@@X_i=1^m@@`、真实地址单元的记录正确、且其指针在其余各列中都指到一个 0。`@@M@@F_{k,m}=1@@` 当且仅当存在获胜列；获胜者至多一个，且所有条件皆是输入位的能行谓词，故无任何承诺。Forrelation 量子 `@@M@@O_k(1)@@` 次查询可解，经典需 `@@M@@\Omega_k(m^{1-1/k}/(\log m)^2)@@` 次（Bansal–Sinha 定理，唯一外部下界），此差距即分离引擎。

先证量子上界，核心是"概率比较锦标赛 (tournament)"引理。非获胜列的地址实例可违反承诺，两列比较的胜负概率任意，固定图上的算法不再适用。引理条件仅是：比较电路相干可逆、胜负概率互补 `@@M@@a_{ij}+a_{ji}=1@@`，且某个 `@@M@@i_*@@` 以概率 `@@M@@\ge1-\epsilon@@` 击败所有对手；结论为 `@@M@@O(c\sqrt m\,T^2\log T)@@` 次查询可得含 `@@M@@i_*@@` 的短列表。证明把"按乘法权重选 pivot、权重再乘 `@@M@@a_{ip}@@`"的理想过程精确量子化：叠加态与已有 pivot 逐一相干比较，成功分支的条件分布恰为权重分布，振幅放大 (amplitude amplification) 不改变它；互补性使总权重期望每步减半，保证 `@@M@@i_*@@` 入选。外向指针恰提供支配性：获胜者的全 1 串令对手无处指零，自己却指认每个对手的零，故对手承诺被破坏也无妨。最后将候选的获胜条件拆成 `@@M@@K@@` 个精确局部测试，Grover 搜索找失败者即完成验证。

再证随机下界，耦合两个输入：哑输入每列独立藏一个零、单元空白，函数值为 0；均匀选列 `@@M@@I@@`，抹去其零并填好其实地址单元，指针恰指向各列隐藏的零，得值为 1 的种植输入 (planted input)。区分二者须找到被抹的零，或碰到新填的单元。前者因零位在适应式查询下保持条件均匀，概率至多 `@@M@@4G/m^2@@`；后者或该列是"重列"——对其 Forrelation 串查询超过 `@@M@@L@@` 次，概率至多 `@@M@@G/(mL)@@`——或须在 `@@M@@L@@` 次查询内猜中 `@@M@@r@@` 维地址向量。对最后情形，逐实例封顶的适应直接积 (direct product) 论证被写成超鞅：以各分量剩余最优猜中率之积为位势，期望在适应查询下不增，故猜中概率 `@@M@@\le(2/3)^r@@`，取并集后仍可忽略。三项合计小于 `@@M@@1/3@@`，故 `@@M@@\mathbb{R}(F_{k,m})>\lfloor mL/100\rfloor@@`（`@@M@@L=\lfloor m^{1-1/k}/(\log m)^2\rfloor@@`）。取 `@@M@@k@@` 使 `@@M@@2-1/k>\alpha/2@@`，比值随 `@@M@@m@@` 发散，排除一切 `@@M@@\alpha<4@@`。

## 可信度与备注

本文暂无形式化证明，按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。除 Bansal–Sinha 的 Forrelation 随机下界作为黑盒引用外，构造、锦标赛引理、耦合下界与附录中的四次上界重证均给出完整证明；本结果族 284 即以此篇为支柱，其"候选者比较"视角与近期证书复杂度 (certificate complexity) 分离工作一脉相承，而上界侧依赖的敏感度定理已是广为接受的结果。

{% endraw %}
