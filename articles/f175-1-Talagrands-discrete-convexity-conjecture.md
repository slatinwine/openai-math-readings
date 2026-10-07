---
layout: default
title: "Talagrand's discrete-convexity conjecture"
family: "175"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Talagrand's discrete-convexity conjecture

> 结果族 175：Talagrand's expectation thresholds, discrete convexity, and graph decompositions　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 一句话结论

证明了 Talagrand 离散凸性猜想（2010 年猜想 7.1／2021 年研究问题 13.3.2）：存在普适常数 \(k=2^{75}\)，任何高概率集合族中"不能被 \(k\) 个成员之并覆盖"的例外集族，在原密度处有小成本覆盖。

## 问题背景

Talagrand 的高斯凸性问题问：紧平衡集的有限次高斯测度之和能否一致地包含一个测度至少 \(1/2\) 的凸集？离散版本以"并"代替"和"：在 Bernoulli 乘积测度 \(\mu_p\) 下很可能出现的集合族 \(\mathcal D\)，固定次数的成员之并应当覆盖"几乎所有"集合，而例外族应是 \(p\)-small 的，即有成本 \(\leq1/2\) 的包含覆盖（cover）。Talagrand 于 2010 年正式提出该猜想，并指出它与正选择子过程的联系。相关进展包括：Hua–Song–Tudose 解决了高斯问题并给出带密度损失 \(p^C\) 的离散推论；Li 证明了分数版本；Park 结合舍入得到带 \(\log\log\) 损失的积分结论；Ascoli–He–Park–Talagrand 则给出离散凸性的阈值重述并证明了若干图包含情形。完全消除密度损失是悬而未决的目标。

## 主要结果

定理 1.1：取 \(k=2^{75}\)。对每个 \(N\geq1\)、每个 \(p\in(0,1)\)、每个族 \(\mathcal D\subseteq2^{[N]}\)（无需单调性），只要 \(\mu_p(\mathcal D)\geq1-1/k\)，例外族 \(E_k(\mathcal D)\)——即不能含于 \(\mathcal D\) 中 \(k\) 个成员之并的集合——就是 \(p\)-small 的：存在 \(\mathcal G\) 使每个例外集合包含某 \(I\in\mathcal G\) 且 \(c_p(\mathcal G)=\sum_I p^{|I|}\leq1/2\)。常数绝对有效，覆盖密度不降。论文还由此恢复 Park–Pham 的正选择子结论，并联合姊妹篇的常数因子舍入定理给出"两个并、常数密度损失"的推论。

## 证明思路

证明分三步。第一步是初等覆盖引理：对 \(r\)-均匀超图族 \(\mathcal H\)，若 \(|\mathcal H|\rho^r\leq2^{h+1}\)，则包含至少 \(2^{12h}\) 条边的集合有成本 \(\leq3\cdot2^{-h}\) 的覆盖。构造分三层：加权度大的小集合直接充当生成元；对剩下的"正则"边独立采样有序对（概率 \(\pi=2^{-8h}\)）并取其并；若某长元组的所有点对都未被采到，就把全并加入残余生成元——其概率 \((1-\pi)^{m^2}\) 随 \(m\) 的平方指数衰减，恰好支付长元组的成本。

第二步构造权重并覆盖 \(E_{32}(\mathcal F)\)。定义 \(b(U)\) 为指示函数的交替和——它正是偏置 Fourier 系数（biased Fourier coefficient）的常数倍——并令 \(w(U)=b(U)^2\)。Parseval 恒等式给全局界 \(\sum_U q^{|U|}w(U)\leq\mu_q(\mathcal F)\leq1\)。对每个例外集 \(S\)，构造 32 行数组的符号乘积测度：对 \(S\) 内的列从 Bernoulli 质量中减去一个奇偶（parity）修正项，使全零列质量为零且跨行可分解；因 \(S\) 不能被 32 个族成员覆盖，乘积在支集上逐点为零，展开得恒等式 \(0=\sum_{U\subseteq S}(-1)^{|U|}b(U)^{32}\)，从而 \(\sum_{\emptyset\neq U\subseteq S}w(U)^{16}\geq2^{-32}\)。两行版本的符号核正是 Li 的构造；此处推广到 32 行以获得十六次幂，再与覆盖引理结合才得到固定的密度损失。权重大的集合直接入覆盖；其余按尺寸与权重分箱，逐箱套第一步引理——每个例外集都含"太多"中等权重的子集，必被某箱的覆盖击中。这给出密度 \(q/2^{70}\)。

第三步用精确耦合（coupling）回到原密度：构造 \(L=2^{70}\) 个边际同为 \(\mu_p\) 但相依的行，使其并恰具 \(\mu_q\) 律（\(q=Lp\)；当 \(Lp\geq1\) 时并恒为全集，例外族为空）。令 \(\mathcal F\) 为 \(L\) 个 \(\mathcal D\) 成员之并的族，联合界给 \(\mu_q(\mathcal F)\geq31/32\)，而 \(E_{32}(\mathcal F)=E_{32L}(\mathcal D)\)，第二步即得 \(p\)-small。这一精确耦合允许族 \(\mathcal D\) 完全任意，是把覆盖成本拉回原密度 \(p\) 的关键。

## 可信度与备注

本文主结果已由 Lean 形式化证明，且是图分解姊妹篇明确引用的必要输入（该篇尚未形式化）。作者注明其符号核方法承自 Li 的两行核与 Friedgut 等的偏置 Fourier 分析。按 OpenAI 官方声明，未经形式化的下游应用仍应以社区核验为准。

{% endraw %}
