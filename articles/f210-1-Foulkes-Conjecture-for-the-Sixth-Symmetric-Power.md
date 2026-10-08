---
layout: default
title: "Foulkes' conjecture for the sixth symmetric power"
family: "210"
discipline: "Algebra"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Foulkes' conjecture for the sixth symmetric power

> 结果族 210：Foulkes' conjecture for sixth powers and quadratic stabilization　·　学科：Algebra　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

两种装箱法：左边是 6 个大箱子、每箱装 `@@M@@b@@` 件商品（可重复、不分顺序）；右边是 `@@M@@b@@` 个小箱子、每箱装 6 件。总件数都是 `@@M@@6b@@`，但两边"能装出哪些花样"的清单不同。Foulkes 猜想说右边清单更丰富，足以把左边每种花样一对一嵌进去。本文证明：箱数取 6 时，这件事对一切 `@@M@@b\ge6@@` 都成立。

**关键词卡片**

- 对称幂（symmetric power）：`@@M@@\Sym^b V@@`＝从 `@@M@@V@@` 里无序挑 `@@M@@b@@` 份、允许重复的所有组合撑成的空间。
- 等变单射（equivariant injection）：与对称群 `@@M@@\GL(V)@@` 的作用兼容的一一嵌入，"花样对照表"不破坏对称性。
- Schur 正性（Schur positivity）：把表示拆成基本积木（Schur 函数）后系数全非负，等价于嵌入存在。
- plethysm：对称函数的复合 `@@M@@h_a[h_b]@@`，"箱中套箱"结构的精确代数化身。
- Foulkes–Howe 映射：一条天然的乘法翻译通道，老证明都想走它，但它到 `@@M@@a=6@@` 时有洞，本文只能绕路。

**看个具体例子**

取 `@@M@@V=\mathbb{C}^6@@`、`@@M@@b=7@@`：猜想断言 `@@M@@\Sym^6(\Sym^7 V)@@` 的每种花样都能在 `@@M@@\Sym^7(\Sym^6 V)@@` 里找到对应。`@@M@@b=6@@` 时两边是同一表示、毫无难度，全部难关都在 `@@M@@b>6@@`；本文对每个 `@@M@@b@@` 逐一攻下。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="110" y="46" font-size="14" text-anchor="middle" fill="#333">Sym⁶(SymᵇV)：6 个大盒</text>
  <rect x="25" y="75" width="52" height="52" fill="#eef" stroke="#3355aa" stroke-width="2"/>
  <circle cx="39" cy="89" r="3.5" fill="#3355aa"/><circle cx="52" cy="89" r="3.5" fill="#3355aa"/><circle cx="65" cy="89" r="3.5" fill="#3355aa"/><circle cx="39" cy="102" r="3.5" fill="#3355aa"/><circle cx="52" cy="102" r="3.5" fill="#3355aa"/><circle cx="65" cy="102" r="3.5" fill="#3355aa"/><circle cx="52" cy="115" r="3.5" fill="#3355aa"/>
  <rect x="85" y="75" width="52" height="52" fill="#eef" stroke="#3355aa" stroke-width="2"/>
  <circle cx="99" cy="89" r="3.5" fill="#3355aa"/><circle cx="112" cy="89" r="3.5" fill="#3355aa"/><circle cx="125" cy="89" r="3.5" fill="#3355aa"/><circle cx="99" cy="102" r="3.5" fill="#3355aa"/><circle cx="112" cy="102" r="3.5" fill="#3355aa"/><circle cx="125" cy="102" r="3.5" fill="#3355aa"/><circle cx="112" cy="115" r="3.5" fill="#3355aa"/>
  <rect x="145" y="75" width="52" height="52" fill="#eef" stroke="#3355aa" stroke-width="2"/>
  <circle cx="159" cy="89" r="3.5" fill="#3355aa"/><circle cx="172" cy="89" r="3.5" fill="#3355aa"/><circle cx="185" cy="89" r="3.5" fill="#3355aa"/><circle cx="159" cy="102" r="3.5" fill="#3355aa"/><circle cx="172" cy="102" r="3.5" fill="#3355aa"/><circle cx="185" cy="102" r="3.5" fill="#3355aa"/><circle cx="172" cy="115" r="3.5" fill="#3355aa"/>
  <rect x="25" y="145" width="52" height="52" fill="#eef" stroke="#3355aa" stroke-width="2"/>
  <circle cx="39" cy="159" r="3.5" fill="#3355aa"/><circle cx="52" cy="159" r="3.5" fill="#3355aa"/><circle cx="65" cy="159" r="3.5" fill="#3355aa"/><circle cx="39" cy="172" r="3.5" fill="#3355aa"/><circle cx="52" cy="172" r="3.5" fill="#3355aa"/><circle cx="65" cy="172" r="3.5" fill="#3355aa"/><circle cx="52" cy="185" r="3.5" fill="#3355aa"/>
  <rect x="85" y="145" width="52" height="52" fill="#eef" stroke="#3355aa" stroke-width="2"/>
  <circle cx="99" cy="159" r="3.5" fill="#3355aa"/><circle cx="112" cy="159" r="3.5" fill="#3355aa"/><circle cx="125" cy="159" r="3.5" fill="#3355aa"/><circle cx="99" cy="172" r="3.5" fill="#3355aa"/><circle cx="112" cy="172" r="3.5" fill="#3355aa"/><circle cx="125" cy="172" r="3.5" fill="#3355aa"/><circle cx="112" cy="185" r="3.5" fill="#3355aa"/>
  <rect x="145" y="145" width="52" height="52" fill="#eef" stroke="#3355aa" stroke-width="2"/>
  <circle cx="159" cy="159" r="3.5" fill="#3355aa"/><circle cx="172" cy="159" r="3.5" fill="#3355aa"/><circle cx="185" cy="159" r="3.5" fill="#3355aa"/><circle cx="159" cy="172" r="3.5" fill="#3355aa"/><circle cx="172" cy="172" r="3.5" fill="#3355aa"/><circle cx="185" cy="172" r="3.5" fill="#3355aa"/><circle cx="172" cy="185" r="3.5" fill="#3355aa"/>
  <text x="110" y="225" font-size="13" text-anchor="middle" fill="#333">每盒 b 件（可重复、不分顺序）</text>
  <line x1="225" y1="115" x2="340" y2="115" stroke="#c0392b" stroke-width="2.5"/>
  <polygon points="340,108 356,115 340,122" fill="#c0392b"/>
  <text x="288" y="98" font-size="13" text-anchor="middle" fill="#c0392b">GL(V)-等变单射</text>
  <text x="288" y="140" font-size="13" text-anchor="middle" fill="#c0392b">对一切 b ≥ 6</text>
  <text x="436" y="46" font-size="14" text-anchor="middle" fill="#333">Symᵇ(Sym⁶V)：b 个小盒</text>
  <rect x="375" y="75" width="26" height="26" fill="#efe" stroke="#2e8b57" stroke-width="2"/>
  <circle cx="382" cy="83" r="2" fill="#2e8b57"/><circle cx="388" cy="83" r="2" fill="#2e8b57"/><circle cx="394" cy="83" r="2" fill="#2e8b57"/><circle cx="382" cy="93" r="2" fill="#2e8b57"/><circle cx="388" cy="93" r="2" fill="#2e8b57"/><circle cx="394" cy="93" r="2" fill="#2e8b57"/>
  <rect x="409" y="75" width="26" height="26" fill="#efe" stroke="#2e8b57" stroke-width="2"/>
  <circle cx="416" cy="83" r="2" fill="#2e8b57"/><circle cx="422" cy="83" r="2" fill="#2e8b57"/><circle cx="428" cy="83" r="2" fill="#2e8b57"/><circle cx="416" cy="93" r="2" fill="#2e8b57"/><circle cx="422" cy="93" r="2" fill="#2e8b57"/><circle cx="428" cy="93" r="2" fill="#2e8b57"/>
  <rect x="443" y="75" width="26" height="26" fill="#efe" stroke="#2e8b57" stroke-width="2"/>
  <circle cx="450" cy="83" r="2" fill="#2e8b57"/><circle cx="456" cy="83" r="2" fill="#2e8b57"/><circle cx="462" cy="83" r="2" fill="#2e8b57"/><circle cx="450" cy="93" r="2" fill="#2e8b57"/><circle cx="456" cy="93" r="2" fill="#2e8b57"/><circle cx="462" cy="93" r="2" fill="#2e8b57"/>
  <rect x="477" y="75" width="26" height="26" fill="#efe" stroke="#2e8b57" stroke-width="2"/>
  <circle cx="484" cy="83" r="2" fill="#2e8b57"/><circle cx="490" cy="83" r="2" fill="#2e8b57"/><circle cx="496" cy="83" r="2" fill="#2e8b57"/><circle cx="484" cy="93" r="2" fill="#2e8b57"/><circle cx="490" cy="93" r="2" fill="#2e8b57"/><circle cx="496" cy="93" r="2" fill="#2e8b57"/>
  <rect x="375" y="111" width="26" height="26" fill="#efe" stroke="#2e8b57" stroke-width="2"/>
  <circle cx="382" cy="119" r="2" fill="#2e8b57"/><circle cx="388" cy="119" r="2" fill="#2e8b57"/><circle cx="394" cy="119" r="2" fill="#2e8b57"/><circle cx="382" cy="129" r="2" fill="#2e8b57"/><circle cx="388" cy="129" r="2" fill="#2e8b57"/><circle cx="394" cy="129" r="2" fill="#2e8b57"/>
  <rect x="409" y="111" width="26" height="26" fill="#efe" stroke="#2e8b57" stroke-width="2"/>
  <circle cx="416" cy="119" r="2" fill="#2e8b57"/><circle cx="422" cy="119" r="2" fill="#2e8b57"/><circle cx="428" cy="119" r="2" fill="#2e8b57"/><circle cx="416" cy="129" r="2" fill="#2e8b57"/><circle cx="422" cy="129" r="2" fill="#2e8b57"/><circle cx="428" cy="129" r="2" fill="#2e8b57"/>
  <rect x="443" y="111" width="26" height="26" fill="#efe" stroke="#2e8b57" stroke-width="2"/>
  <circle cx="450" cy="119" r="2" fill="#2e8b57"/><circle cx="456" cy="119" r="2" fill="#2e8b57"/><circle cx="462" cy="119" r="2" fill="#2e8b57"/><circle cx="450" cy="129" r="2" fill="#2e8b57"/><circle cx="456" cy="129" r="2" fill="#2e8b57"/><circle cx="462" cy="129" r="2" fill="#2e8b57"/>
  <rect x="477" y="111" width="26" height="26" fill="#efe" stroke="#2e8b57" stroke-width="2"/>
  <circle cx="484" cy="119" r="2" fill="#2e8b57"/><circle cx="490" cy="119" r="2" fill="#2e8b57"/><circle cx="496" cy="119" r="2" fill="#2e8b57"/><circle cx="484" cy="129" r="2" fill="#2e8b57"/><circle cx="490" cy="129" r="2" fill="#2e8b57"/><circle cx="496" cy="129" r="2" fill="#2e8b57"/>
  <text x="523" y="108" font-size="20" fill="#2e8b57">⋯</text>
  <text x="436" y="165" font-size="13" text-anchor="middle" fill="#333">每盒恰好 6 件，共 b ≥ 6 盒</text>
</svg>

</div>

**为什么值得关心**

把 1950 年猜想的已知范围从 `@@M@@a\le5@@` 推进到 `@@M@@a=6@@`；旧路线（Foulkes–Howe 映射）到这一站已断裂，本文用"大范围代数＋中范围组合＋小范围计算机"三层结构另辟蹊径，其中大范围部分由已 Lean 形式化的姊妹篇支撑。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了 Foulkes 猜想在 `@@M@@a=6@@` 成立：对一切 `@@M@@b\ge6@@` 与有限维复向量空间 `@@M@@V@@`，存在 `@@M@@\GL(V)@@`-等变单射 `@@M@@\Sym^6(\Sym^b V)\hookrightarrow\Sym^b(\Sym^6 V)@@`，即 `@@M@@h_b[h_6]-h_6[h_b]@@` Schur-正；已知范围由 `@@M@@a\le5@@` 推进到 `@@M@@a=6@@`。

## 问题背景

Foulkes 在 1950 年研究协变量（concomitants）时提出猜想：当 `@@M@@1\le a\le b@@` 时，应有 `@@M@@\GL(V)@@`-等变嵌入 `@@M@@\Sym^a(\Sym^b V)\hookrightarrow\Sym^b(\Sym^a V)@@`。在复数域上由完全可约性（complete reducibility），这等价于 plethysm 复合 `@@M@@h_a[h_b]@@` 与 `@@M@@h_b[h_a]@@` 之差是 Schur-正的（Schur-positive）。二元形式情形由经典 Hermite 互反律（Hermite reciprocity）给出同构，高维只能期待重数不等式。已知情形：`@@M@@a=1@@` 平凡，`@@M@@a=2@@` 属于 Thrall（1942），`@@M@@a=3@@` 属于 Dent–Siemons（2000），`@@M@@a=4,5@@` 分别靠 Müller–Neunhöffer 在 `@@M@@(4,4)@@` 与 Cheung–Ikenmeyer–Mkrtchyan 在 `@@M@@(5,6)@@` 的计算机计算配合 McKay 传播定理得到。但人们惯用的典范 Foulkes–Howe 映射在 `@@M@@(5,5)@@`、`@@M@@(6,6)@@` 处有非零核，这条老路到 `@@M@@a=6@@` 断掉；Evseev–Paget–Wildon 的特征消缩递推只核实到两参数之和 `@@M@@\le 19@@`，对应第六情形的 `@@M@@b\le 13@@`。Brion 虽然证明了对固定 `@@M@@a@@` 猜想最终成立，却未给出与维数无关的显式界，因此 `@@M@@a=6@@` 的完全证明此前悬而未决。

## 主要结果

主定理：对每个整数 `@@M@@b\ge 6@@` 与每个有限维复向量空间 `@@M@@V@@`，存在 `@@M@@\GL(V)@@`-等变单射 `@@M@@\Sym^6(\Sym^b V)\hookrightarrow\Sym^b(\Sym^6 V)@@`；等价地，对每个 `@@M@@b\ge 6@@`，`@@M@@h_b[h_6]-h_6[h_b]@@` 的全部 Schur 系数非负。定理对 `@@M@@\dim V@@` 无任何限制。对角情形 `@@M@@b=6@@` 两边是同一表示，全部难点在 `@@M@@b>6@@`。证明在结构上分两段：`@@M@@b\ge 30@@` 的比较由姊妹篇的二次稳定化定理一次性覆盖，`@@M@@6\le b\le 29@@` 则化为有限的重数比较；论文还保留了一条不依赖姊妹篇的独立路线，覆盖 `@@M@@b\ge 150@@` 加上验证到 `@@M@@b=149@@` 的有限计算。

## 证明思路

整体是"大范围靠代数、中范围靠组合、小范围靠计算机"的三层结构。先由姊妹篇的二次稳定化定理：典范乘法映射 `@@M@@\mu_{6,b,V}:\Sym^b(\Sym^6 V)\to\Sym^6(\Sym^b V)@@` 在 `@@M@@b\ge 30@@` 时满射，配合完全可约性即得该范围的嵌入；余下只需处理 `@@M@@6\le b\le 29@@`。由 Cauchy 分解，源 `@@M@@\Sym^6(\Sym^b V)@@` 的 Schur 支撑长度至多六，故只需在 `@@M@@V=\mathbb C^6@@` 上比较六部划分 `@@M@@\lambda\vdash 6b@@` 处的源重数 `@@M@@F(\lambda)@@` 与目标重数 `@@M@@Q(\lambda)@@`；矩形平移引理给出 `@@M@@Q(d+6e_i)\ge Q(d)@@` 与 `@@M@@F(d+6e_6)=F(d)@@`，从而可按"剩余类加网格"归约。上界侧，循环公式把 `@@M@@h_6[h_b]@@` 写成 `@@M@@720@@` 个置换因式积的平均，带符号条带规则（signed strip rule，plethystic Murnaghan–Nakayama 规则的特例）说明每个因式积的系数只能是 `@@M@@0,\pm1@@` 且中间划分受包含关系约束；丢弃符号与部分约束后，得到对每个间隙坐标单调的上界函数 `@@M@@U(d)\ge F(d)@@`。下界侧，最高权多项式乘法把已知的正重数传播到更大的权，而"幂证书"（power certificate）利用基的首项单项式互异，把重数放大归结为点和集（sumset）的 Matolcsi–Ruzsa 型下界 `@@M@@|kD|\ge f(C,h,k)@@`。另有一个不走重数的图表证书（chart certificate）：取非零向量 `@@M@@v@@` 并在 `@@M@@z(v)@@` 处局部化，多元对称不变量的因子长度论证说明，只要 `@@M@@\lambda_2+\cdots+\lambda_6\le b@@`，目标 `@@M@@R_b@@` 的整个权空间都落在乘法像 `@@M@@A_b@@` 里，从而 `@@M@@Q\ge F@@`。证书程序对 `@@M@@6\le b\le 25@@` 先测 `@@M@@Q\ge U@@`，失败的划分（共 `@@M@@145435@@` 个）再由 Newton 恒等式递推精确计算 `@@M@@F@@`，无一为负；对 `@@M@@26\le b\le 149@@` 把间隙向量分解为 `@@M@@d=r+6m@@`（`@@M@@7776@@` 个剩余类乘一个六百万点的网格），用共享的幂表与按剩余类精确的种子数组做传输测试，最终只剩尾带 `@@M@@\lambda_3+\cdots+\lambda_6\le 27@@`。带内的差 `@@M@@Q-F@@` 由七个与 `@@M@@b@@` 无关的 Laurent 级数分子 `@@M@@G_j(q,y)@@` 的系数和给出，第二个程序逐一检查了 `@@M@@57065668@@` 个系数，无一为负。论文还保留了一条独立路线：图表（chart）证书配合极化（polarization）引理给出 `@@M@@b\ge a(a-1)^2=150@@` 时的典范满射，连同验证到 `@@M@@b=149@@` 的有限计算，不依赖姊妹篇同样完成证明。

## 可信度与备注

本篇暂无形式化证明。主路线的 `@@M@@b\ge 30@@` 部分由已 Lean 形式化的姊妹篇（二次稳定化定理）支撑；`@@M@@6\le b\le 29@@` 部分是传统数学论证加两个有限计算机验证，程序源代码完整印在附录（C++17、128 位整数，第二个程序用任意精度整数收尾），并附参考输出与复现脚本。按 OpenAI 官方声明，未经形式化的结果可能有问题，本文宜以社区核验为准。

{% endraw %}
