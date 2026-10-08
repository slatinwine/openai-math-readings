---
layout: default
title: "Simultaneous primitive roots: a conditional lower bound for prime bases"
family: "029"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Simultaneous primitive roots: a conditional lower bound for prime bases

> 结果族 029：Primitive roots for every admissible integer base　·　学科：数论（Number theory）　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

上一篇说：随便指一个整数（比如 2），就有无穷多张素数"钟面"请它当发令员。这一篇再进一步：随便指一组整数（比如 2 和 3，甚至 2、3、5、7），存在无穷多张钟面让这组人同时当发令员。注意这是条件性结果：只要姊妹篇的四个技术声明成立，结论就成立。

**关键词卡片**

- 联立原根（simultaneous primitive roots）：多个基数在同一个素数 p 下同时都是原根。
- 条件结果（conditional result）：依赖显式列出假设的定理——此处假设姊妹篇的四个解析与筛法输入。
- 二次非剩余（quadratic nonresidue）：在模 p 意义下不是任何数的平方；证明用中国剩余定理一次让所有基数变成非剩余。
- Kummer 扩域（Kummer extension）：添加 q 的 λ 次根得到的数域，用于识别并排除"坏素数"。

**看个具体例子**

最小样本 p = 5：2 的幂走出 1→2→4→3→1，3 的幂走出 1→3→4→2→1，两条路线都跑遍全部四个非零刻度，所以 2 和 3 同时是模 5 的原根。主定理说这样的素数有无穷多：在四个假设下，区间 (x, 2x) 内至少有 c·x/(ln x)² 个素数让指定的一组素数基数同时当原根。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><line x1="30" y1="28" x2="72" y2="28" stroke="#333" stroke-width="3"/><text x="78" y="33" font-size="13" fill="#333">2 的幂（顺时针）</text><line x1="30" y1="50" x2="72" y2="50" stroke="#c0392b" stroke-width="2.5" stroke-dasharray="6 4"/><text x="78" y="55" font-size="13" fill="#c0392b">3 的幂（逆时针）</text><line x1="289" y1="53" x2="360" y2="124" stroke="#333" stroke-width="3"/><polygon points="367,131 357.5,126.5 362.5,121.5" fill="#333"/><line x1="367" y1="149" x2="296" y2="220" stroke="#333" stroke-width="3"/><polygon points="289,227 298.5,222.5 293.5,217.5" fill="#333"/><line x1="271" y1="227" x2="200" y2="156" stroke="#333" stroke-width="3"/><polygon points="193,149 202.5,153.5 197.5,158.5" fill="#333"/><line x1="193" y1="131" x2="264" y2="60" stroke="#333" stroke-width="3"/><polygon points="271,53 266.5,62.5 261.5,57.5" fill="#333"/><line x1="276" y1="93" x2="241" y2="128" stroke="#c0392b" stroke-width="2.5" stroke-dasharray="6 4"/><polygon points="232,136 240,132 236,126" fill="#c0392b"/><line x1="232" y1="144" x2="266" y2="178" stroke="#c0392b" stroke-width="2.5" stroke-dasharray="6 4"/><polygon points="272,184 267,179 263,175" fill="#c0392b"/><line x1="284" y1="188" x2="318" y2="154" stroke="#c0392b" stroke-width="2.5" stroke-dasharray="6 4"/><polygon points="324,148 319,157 315,153" fill="#c0392b"/><line x1="328" y1="136" x2="294" y2="102" stroke="#c0392b" stroke-width="2.5" stroke-dasharray="6 4"/><polygon points="288,96 297,101 293,105" fill="#c0392b"/><circle cx="280" cy="68" r="13" fill="#fff" stroke="#333" stroke-width="2"/><text x="280" y="73" font-size="14" text-anchor="middle" fill="#333">1</text><circle cx="352" cy="140" r="13" fill="#fff" stroke="#333" stroke-width="2"/><text x="352" y="145" font-size="14" text-anchor="middle" fill="#333">2</text><circle cx="280" cy="212" r="13" fill="#fff" stroke="#333" stroke-width="2"/><text x="280" y="217" font-size="14" text-anchor="middle" fill="#333">4</text><circle cx="208" cy="140" r="13" fill="#fff" stroke="#333" stroke-width="2"/><text x="208" y="145" font-size="14" text-anchor="middle" fill="#333">3</text><text x="280" y="262" font-size="14" text-anchor="middle" fill="#333">两条环都走遍 1、2、3、4 → 2 与 3 同为模 5 的原根</text></svg>

</div>

**为什么值得关心**

此前无条件只能保证"任取三个素数基数至少一个成立"；本文（在假设下）给出指认式的联立版本，证明"先建素数库、再逐基排除"这条路线可以推广。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
在把姊妹篇的四个解析与筛法陈述列为显式假设后，论文证明：任意固定有限个互异正素数 `@@M@@q_1,\dots,q_k@@` 可同时充当 `@@M@@\gg x/(\log x)^2@@` 个素数 `@@M@@p\in(x,2x)@@` 的原根，是 Artin 单基猜想的无条件路线向联立版本的条件性推广。

## 问题背景
单基情形即 Artin 原根猜想（1927 年由 Hasse 记录）：固定整数是无穷多个素数的原根；Hooley 于 1967 年在广义黎曼假设下证明了渐近式。联立版本问：有限个基数 `@@M@@q_1,\dots,q_k@@` 何时同时是同一个 `@@M@@p@@` 的原根（simultaneous primitive roots）？Matthews 1976 年在 GRH 下得到密度结果；Anwar 与 Pappalardi 于 2017 年在 Schinzel 假设 H 下给出无穷性判据。无条件方面只有"有限选择"型结果：Gupta–Murty 与 Heath-Brown 证明任取三个不同正素数至少有一个是无穷多个素数的原根，但无法指认是哪一个，更谈不上同时。本文证明一个条件性定理：假设姊妹篇《Primitive roots for every admissible integer base》中的四个陈述——一致 Hecke 零自由断言、标记 Type II 估计、分块筛（block sieve）与粗糙数密度（rough-number density）——则联立下界成立；这四个输入的证明在姊妹篇及其引用手稿中，明确不在本文范围之内。

## 主要结果
主定理：设 `@@M@@k\ge1@@`，`@@M@@q_1,\dots,q_k@@` 为互不相同的正素数。在上述四个输入假设下，存在常数 `@@M@@c_{\mathbf q}>0@@` 与 `@@M@@x_{\mathbf q}@@`，使对每个实数 `@@M@@x\ge x_{\mathbf q}@@`，区间 `@@M@@(x,2x)@@` 内至少有 `@@M@@c_{\mathbf q}x/(\log x)^2@@` 个素数 `@@M@@p@@` 满足 `@@M@@p\nmid q_1\cdots q_k@@` 且 `@@M@@\ord_p(q_i)=p-1@@` 对所有 `@@M@@i@@` 同时成立。两个支柱命题是：素数库命题——设 `@@M@@M\ge1@@` 为奇 squarefree 整数，`@@M@@a@@` 为满足 `@@M@@\gcd(a(a-1),M)=1@@` 的剩余类，则可找到 `@@M@@\gg c_{M,a}x/L^2@@` 个素数 `@@M@@p\equiv a\pmod M@@` 形如 `@@M@@p=4rQ+1@@`，其中 `@@M@@Q>x^{0.9}@@` 为素数、`@@M@@r@@` 的素因子全落在 `@@M@@(\exp(L^{0.1}),\exp(L^{0.3}))@@`；一致障碍界命题——对每个固定素数 `@@M@@q@@` 与区间中的素数 `@@M@@\ell@@`，同时满足 `@@M@@p\equiv1\pmod\ell@@` 与 `@@M@@q^{(p-1)/\ell}\equiv1\pmod p@@` 的素数个数 `@@M@@\ll_q x/(\ell(\ell-1)L)+x^{1-10^{-6}}@@`。

## 证明思路
整体是"先建库、再逐基排除、最后清点"的三段式。先建库：取 `@@M@@M@@` 为诸奇基 `@@M@@q_i@@` 之积（若基全为 `@@M@@2@@` 则 `@@M@@M=1@@`），对每个奇 `@@M@@q_i@@` 选定模 `@@M@@q_i@@` 的一个二次非剩余，中国剩余定理拼出剩余类 `@@M@@a\bmod M@@`。库中素数 `@@M@@p=4rQ+1@@` 且 `@@M@@r,Q@@` 皆奇，故 `@@M@@p\equiv5\pmod 8@@`；由二次互反律与 `@@M@@2@@` 的补充定律，`@@M@@q_i>2@@` 时 `@@M@@(q_i/p)=(a/q_i)=-1@@`，`@@M@@q_i=2@@` 时 `@@M@@(2/p)=-1@@`——一个同余类就把所有基数同时变成二次非剩余，这是联立版本的关键一招。再排除：对固定基 `@@M@@q=q_i@@`，Euler 判据迫使阶指数 `@@M@@\iota_p(q)=(p-1)/\ord_p(q)@@` 为奇数；若 `@@M@@\iota_p(q)>1@@`，取其奇素因子 `@@M@@\lambda@@`，因 `@@M@@\iota_p(q)\mid4rQ@@`，必有 `@@M@@\lambda=Q@@` 或 `@@M@@\lambda\mid r@@`。`@@M@@\lambda=Q@@` 时 `@@M@@j=(p-1)/Q<2x^{0.1}@@` 而 `@@M@@p\mid q^j-1@@`，诸 `@@M@@q^j-1@@` 之积的对数仅 `@@M@@\ll_q x^{0.2}@@`，损失 `@@M@@O_q(x^{0.2}/L)=o(x/L^2)@@`；`@@M@@\lambda\mid r@@` 时两个同余式经 Frobenius 判据恰等价于 `@@M@@p@@` 在 Kummer 域 `@@M@@K_{\lambda,q}=\mathbb{Q}(\mu_\lambda,q^{1/\lambda})@@` 中完全分裂，逐个套用一致障碍界再对 `@@M@@\lambda@@` 求和，`@@M@@\sum1/(\ell(\ell-1))@@` 的尾部给出 `@@M@@O_q(xL^{-1}e^{-L^{0.1}})@@`，`@@M@@x^{1-\eta}@@` 项乘以至多 `@@M@@\exp(L^{0.3})@@` 个 `@@M@@\ell@@` 仍是 `@@M@@o(x/L^2)@@`。最后清点：基数有限，各基例外集之并仍为 `@@M@@o(x/L^2)@@`，故库中至少 `@@M@@c_{M,a}x/(2L^2)@@` 个素数对所有基同时指数为 `@@M@@1@@`。一致障碍界的证法与姊妹篇同构：将 `@@M@@\zeta_K@@` 经 Abel 塔分解为 `@@M@@F_\ell=\mathbb{Q}(\mu_{12\ell})@@` 上 Hecke `@@M@@L@@`-函数之积，由输入 1 把零自由性下降到 `@@M@@K@@`；再用误差仅线性依赖 `@@M@@\log D+n@@` 的光滑素理想显式公式（Mellin 反演加围道移动，零点计数用 Hasanalizade–Shen–Wong 的一致公式），每个完全分裂素数贡献 `@@M@@n=\ell(\ell-1)@@` 个范数理想，除以次数即得界。素数库的构造则扩展姊妹篇的标记方法：标记权 `@@M@@\mathcal W(h)=2^{K-\sum_i\omega_i(h)}\prod_i\omega_i(h)/V_i@@` 施加在 `@@M@@K@@` 个素数区间 `@@M@@\mathcal P_i@@` 上，强制每组都贡献素因子，剩下的 `@@M@@4Q@@` 部分由权函数选取；同余条件 `@@M@@d\equiv a\pmod M@@` 经 Dirichlet 特征展开进入标记 Type II 估计（其系数判据允许乘固定特征），进度内的分布由 Bombieri–Vinogradov 定理供给；分块筛与 Buchstab 型粗糙数密度 `@@M@@D_\gamma(w)@@` 合账：初始筛余量系数 `@@M@@e^{-\gamma_E}/b@@`，减去最小素因子分箱成本 `@@M@@D_b(1)-1@@` 后对小的固定 `@@M@@b@@` 仍剩正常数，接近 `@@M@@\sqrt x@@` 的平衡半素数另用单独的筛控制。

## 可信度与备注
本文是显式的条件性结果：四个输入的证明位于姊妹篇及其引用的手稿，本文不复现；主结果亦暂无 Lean 形式化证明，请以社区核验为准，且 OpenAI 官方声明"未经形式化的结果可能有问题"。与姊妹篇是单向依赖关系：族内单基结果的解析与筛法部分一旦成立，联立版本即随之成立，故这批手稿的核验焦点应集中在姊妹篇的 Hecke 零自由定理与标记 Type II 估计上。

{% endraw %}
