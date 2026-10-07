---
layout: default
title: "Counterexamples to weak chromatic splitting: sphere kernels and descent exponents"
family: "318"
discipline: "Topology"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Counterexamples to weak chromatic splitting: sphere kernels and descent exponents

> 结果族 318：Chromatic splitting: filtrations and counterexamples　·　学科：Topology　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明：对导出 \(p\)-完备球面 \(X\)，典范弱色分裂映射 \(i_{n,X}:L_{n-1}X\to L_{n-1}L_{K(n)}X\) 在高度 \(n=p\)（\(p\geq5\)）与 \(n=p+1\)（\(p\geq7\)）处均无同伦收缩；经典球面 \(\beta\)-元素的幂 \(\beta_1^{(p-1)^2}\) 给出核中具体的非零类。有限输入下的弱色分裂猜想（weak chromatic splitting）被推翻。

## 问题背景

Hopkins 的色分裂猜想（Hovey 记录的 Conjecture 4.2）除预言色重叠的显式分解外，还预言典范映射 \(L_{n-1}X\to L_{n-1}L_{K(n)}X\) 有同伦收缩（retraction，即左逆）。弱式只保留后半条：当 \(X\) 是有限谱的导出 \(p\)-完备化时，\(K(n)\)-局部化单位经 \(L_{n-1}\) 局部化后有收缩。此前的经验是"强公式屡屡失败、弱式总能幸存"：\(n=p=2\) 处 Beaudry 推翻了指定和式公式，Beaudry–Goerss–Henn 补入 Moore 项后弱收缩依然成立，且弱式在高度二以下对所有素数成立；Minami 报告过 Devinatz 对允许完备 \(BP\) 的类似猜想的反例，但那不是有限输入。长 \(\beta\)-幂的非零性早有 Lee–Ravenel 一类结果（如 \(p\geq7\) 时 \(\beta_1^{p^2-p-1}\neq0\)），Ravenel 也算过第一 \(\beta\)-元素的检测；此前缺的是同时做到两件事：在指定低高度局部化下检测出该类，又让它在高高度单位下消失。本文补上了这一步。

## 主要结果

记 \(S=S^0_{(p)}\)，\(X=S_p^\wedge=\operatorname{holim}_j S/p^j\)，\(L_r\) 为 Johnson–Wilson \(E(r)\)-局部化，\(i_{n,X}=L_{n-1}(\eta_X^{(n)})\) 为典范弱分裂映射。令 \(d_p=2p(p-1)-2\)、\(k_p=(p-1)^2\)、\(z_p=\beta_1^{k_p}\)，其中 \(\beta_1\) 是经典第一 \(\beta\)-元素（beta element）。定理一：对每个素数 \(p\geq5\)，\(z_p\) 在 \(\pi_{d_pk_p}L_{p-1}X\) 中的像非零且被 \(\pi(i_{p,X})\) 杀死，故 \(i_{p,X}\) 无同伦收缩。定理二：对每个 \(p\geq7\)，同一个 \(z_p\) 在 \(\pi_{d_pk_p}L_pX\) 中的像非零且被 \(\pi(i_{p+1,X})\) 杀死。特例 \(p=5\)：\(\beta_1^{16}\) 在 \(\pi_{608}L_4X\) 中非零并落在核里。另有一条独立路线：令 \(H=C_p\rtimes C_{(p-1)^2}\) 作用于高度 \(p-1\) 的 Morava \(E\)-理论，可证下降指数（descent exponent）不等式 \(\expn_H(E_{p-1})\gt p^2+2\geq\expn_H(T(B_p))\)（\(\expn_H(V)\) 是使 \(J_H^{\wedge b}\wedge V\to V\) 为零的最小 \(b\)，\(T(V)=L_{K(p-1)}(E_{p-1}\wedge V)\)，\(B_p=L_{K(p)}S\)）；收缩会把 \(E_{p-1}\) 变成 \(T(B_p)\) 的 \(H\)-等变收缩，与指数不相容。

## 证明思路

核定理的纲领是"下方检测、上方消灭、自然性拼装"。

先做约化：完备化映射 \(c:S\to X\) 的纤维是 \(F(S[1/p],S)\)，乘 \(p\) 在其上可逆，故 \(c\) 对每个 \(K(a)\) 都是等价；于是只要某个 \(K(t)\)-局部谱的单位在 \(z\in\pi_qS\) 上取值非零、而 \(K(n)\)-局部单位把 \(z\) 杀死，两个自然性方块便把 \(z\) 的像送进 \(\pi_qL_{n-1}X\) 且被 \(i_{n,X}\) 杀死。若有收缩则该群上有左逆，立即矛盾。

下方检测：取 \(h=p-1\) 与有限子群 \(G\)（纯稳定子部分为 \(C_p\rtimes C_{h^2}\)），令 \(Y=E_h^{hG}\) 为普通同伦不动点谱（homotopy fixed point spectrum）。Devinatz–Hopkins 把其不动点谱序列等同于局部 Adams 谱序列；Hopkins–Miller 计算（经 Heard 记录）给出正滤过部分为 \(\mathbb F_p[\alpha,\beta,\Delta^{\pm1}]/(\alpha^2)\)，且单位把球面 \(\beta_1\) 送到滤过二处的 \(c\beta\)，\(E_\infty\) 中 \(\beta^{h^2}\neq0\)。作者补证一条普通滤过乘积引理（谱序列乘法就是实际同伦滤过的伴随分次乘法），从而 \(\eta_*(\beta_1^{h^2})\) 非零；\(Y\) 是 \(K(h)\)-局部的，非零性便传到 \(L_{p-1}X\) 及一切 \(L_rX\)（\(r\geq p-1\)）。

上方消灭：在 \(K(a)\)-局部范畴令 \(I_a=\fib(B_a\to E_a)\)，实际 Adams 滤过 \(F^s\pi_*B_a\) 恰是 \(I_a^{\otimes_a s}\) 的像，且滤过可乘。连续上同调在 \(s\gt a^2+1\) 处消失——高度 \(p\) 用纯稳定子维数加半线性 Witt 迹一收缩处理 \(p\)-挠 Galois 商，高度 \(p+1\) 的扩群无 \(p\)-挠、直接用维数——强收敛给出零尾巴 \(F^{a^2+2}\pi_*B_a=0\)。正稳定球面茎是挠群而 \((E_a)_*\) 无挠且集中在偶度，故 \(\beta_1\) 的像落在 \(F^2\)，其 \(k_p\) 次幂落在 \(F^{2k_p}\)；而 \(2k_p-(p^2+1)=p^2-4p+1\gt0\)（\(p\geq5\)）、\(2k_p-((p+1)^2+1)=p(p-6)\gt0\)（\(p\geq7\)），幂被零尾巴吞没。

独立的指数证明绕开核类：下界只需某个类在普通同伦不动点谱序列的一个指定有限页存活，无需永驻循环或球面代表元；上界由 Devinatz–Hopkins 幂零性定理先给出有限指数，数值上链界使相关映射在一切有限测试后为零，再用 Brown–Comenetz 论证使映射本身为零，最后用连贯迹（coherent trace）把有限层结构搬运到高度 \(p-1\)。两条路各自封死高度 \(p\) 处的收缩。

## 可信度与备注

主结果暂无形式化证明；高度 \(p\) 的不可收缩有核类与下降指数两个互相独立的论证，互为印证。同族 318 的姊妹篇显示图景分层：\(n\geq1\)、\(p\gt n+1\) 时重叠仍有由局部球面片段组成的 \(2^n\) 步滤过；本文推翻有限输入的弱收缩；\(p=3\) 高度三的姊妹篇则证明连更弱表述的有限拼装也失败。三个层次的问题互不蕴含。OpenAI 官方声明：未经形式化的结果可能有问题。

{% endraw %}
