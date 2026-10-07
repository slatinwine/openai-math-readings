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

## 一句话结论
在把姊妹篇的四个解析与筛法陈述列为显式假设后，论文证明：任意固定有限个互异正素数 \(q_1,\dots,q_k\) 可同时充当 \(\gg x/(\log x)^2\) 个素数 \(p\in(x,2x)\) 的原根，是 Artin 单基猜想的无条件路线向联立版本的条件性推广。

## 问题背景
单基情形即 Artin 原根猜想（1927 年由 Hasse 记录）：固定整数是无穷多个素数的原根；Hooley 于 1967 年在广义黎曼假设下证明了渐近式。联立版本问：有限个基数 \(q_1,\dots,q_k\) 何时同时是同一个 \(p\) 的原根（simultaneous primitive roots）？Matthews 1976 年在 GRH 下得到密度结果；Anwar 与 Pappalardi 于 2017 年在 Schinzel 假设 H 下给出无穷性判据。无条件方面只有"有限选择"型结果：Gupta–Murty 与 Heath-Brown 证明任取三个不同正素数至少有一个是无穷多个素数的原根，但无法指认是哪一个，更谈不上同时。本文证明一个条件性定理：假设姊妹篇《Primitive roots for every admissible integer base》中的四个陈述——一致 Hecke 零自由断言、标记 Type II 估计、分块筛（block sieve）与粗糙数密度（rough-number density）——则联立下界成立；这四个输入的证明在姊妹篇及其引用手稿中，明确不在本文范围之内。

## 主要结果
主定理：设 \(k\ge1\)，\(q_1,\dots,q_k\) 为互不相同的正素数。在上述四个输入假设下，存在常数 \(c_{\mathbf q}>0\) 与 \(x_{\mathbf q}\)，使对每个实数 \(x\ge x_{\mathbf q}\)，区间 \((x,2x)\) 内至少有 \(c_{\mathbf q}x/(\log x)^2\) 个素数 \(p\) 满足 \(p\nmid q_1\cdots q_k\) 且 \(\ord_p(q_i)=p-1\) 对所有 \(i\) 同时成立。两个支柱命题是：素数库命题——设 \(M\ge1\) 为奇 squarefree 整数，\(a\) 为满足 \(\gcd(a(a-1),M)=1\) 的剩余类，则可找到 \(\gg c_{M,a}x/L^2\) 个素数 \(p\equiv a\pmod M\) 形如 \(p=4rQ+1\)，其中 \(Q>x^{0.9}\) 为素数、\(r\) 的素因子全落在 \((\exp(L^{0.1}),\exp(L^{0.3}))\)；一致障碍界命题——对每个固定素数 \(q\) 与区间中的素数 \(\ell\)，同时满足 \(p\equiv1\pmod\ell\) 与 \(q^{(p-1)/\ell}\equiv1\pmod p\) 的素数个数 \(\ll_q x/(\ell(\ell-1)L)+x^{1-10^{-6}}\)。

## 证明思路
整体是"先建库、再逐基排除、最后清点"的三段式。先建库：取 \(M\) 为诸奇基 \(q_i\) 之积（若基全为 \(2\) 则 \(M=1\)），对每个奇 \(q_i\) 选定模 \(q_i\) 的一个二次非剩余，中国剩余定理拼出剩余类 \(a\bmod M\)。库中素数 \(p=4rQ+1\) 且 \(r,Q\) 皆奇，故 \(p\equiv5\pmod 8\)；由二次互反律与 \(2\) 的补充定律，\(q_i>2\) 时 \((q_i/p)=(a/q_i)=-1\)，\(q_i=2\) 时 \((2/p)=-1\)——一个同余类就把所有基数同时变成二次非剩余，这是联立版本的关键一招。再排除：对固定基 \(q=q_i\)，Euler 判据迫使阶指数 \(\iota_p(q)=(p-1)/\ord_p(q)\) 为奇数；若 \(\iota_p(q)>1\)，取其奇素因子 \(\lambda\)，因 \(\iota_p(q)\mid4rQ\)，必有 \(\lambda=Q\) 或 \(\lambda\mid r\)。\(\lambda=Q\) 时 \(j=(p-1)/Q<2x^{0.1}\) 而 \(p\mid q^j-1\)，诸 \(q^j-1\) 之积的对数仅 \(\ll_q x^{0.2}\)，损失 \(O_q(x^{0.2}/L)=o(x/L^2)\)；\(\lambda\mid r\) 时两个同余式经 Frobenius 判据恰等价于 \(p\) 在 Kummer 域 \(K_{\lambda,q}=\Q(\mu_\lambda,q^{1/\lambda})\) 中完全分裂，逐个套用一致障碍界再对 \(\lambda\) 求和，\(\sum1/(\ell(\ell-1))\) 的尾部给出 \(O_q(xL^{-1}e^{-L^{0.1}})\)，\(x^{1-\eta}\) 项乘以至多 \(\exp(L^{0.3})\) 个 \(\ell\) 仍是 \(o(x/L^2)\)。最后清点：基数有限，各基例外集之并仍为 \(o(x/L^2)\)，故库中至少 \(c_{M,a}x/(2L^2)\) 个素数对所有基同时指数为 \(1\)。一致障碍界的证法与姊妹篇同构：将 \(\zeta_K\) 经 Abel 塔分解为 \(F_\ell=\Q(\mu_{12\ell})\) 上 Hecke \(L\)-函数之积，由输入 1 把零自由性下降到 \(K\)；再用误差仅线性依赖 \(\log D+n\) 的光滑素理想显式公式（Mellin 反演加围道移动，零点计数用 Hasanalizade–Shen–Wong 的一致公式），每个完全分裂素数贡献 \(n=\ell(\ell-1)\) 个范数理想，除以次数即得界。素数库的构造则扩展姊妹篇的标记方法：标记权 \(\mathcal W(h)=2^{K-\sum_i\omega_i(h)}\prod_i\omega_i(h)/V_i\) 施加在 \(K\) 个素数区间 \(\mathcal P_i\) 上，强制每组都贡献素因子，剩下的 \(4Q\) 部分由权函数选取；同余条件 \(d\equiv a\pmod M\) 经 Dirichlet 特征展开进入标记 Type II 估计（其系数判据允许乘固定特征），进度内的分布由 Bombieri–Vinogradov 定理供给；分块筛与 Buchstab 型粗糙数密度 \(D_\gamma(w)\) 合账：初始筛余量系数 \(e^{-\gamma_E}/b\)，减去最小素因子分箱成本 \(D_b(1)-1\) 后对小的固定 \(b\) 仍剩正常数，接近 \(\sqrt x\) 的平衡半素数另用单独的筛控制。

## 可信度与备注
本文是显式的条件性结果：四个输入的证明位于姊妹篇及其引用的手稿，本文不复现；主结果亦暂无 Lean 形式化证明，请以社区核验为准，且 OpenAI 官方声明"未经形式化的结果可能有问题"。与姊妹篇是单向依赖关系：族内单基结果的解析与筛法部分一旦成立，联立版本即随之成立，故这批手稿的核验焦点应集中在姊妹篇的 Hecke 零自由定理与标记 Type II 估计上。

{% endraw %}
