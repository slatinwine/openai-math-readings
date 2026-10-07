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

本文证明：对导出 `@@M@@p@@`-完备球面 `@@M@@X@@`，典范弱色分裂映射 `@@M@@i_{n,X}:L_{n-1}X\to L_{n-1}L_{K(n)}X@@` 在高度 `@@M@@n=p@@`（`@@M@@p\geq5@@`）与 `@@M@@n=p+1@@`（`@@M@@p\geq7@@`）处均无同伦收缩；经典球面 `@@M@@\beta@@`-元素的幂 `@@M@@\beta_1^{(p-1)^2}@@` 给出核中具体的非零类。有限输入下的弱色分裂猜想（weak chromatic splitting）被推翻。

## 问题背景

Hopkins 的色分裂猜想（Hovey 记录的 Conjecture 4.2）除预言色重叠的显式分解外，还预言典范映射 `@@M@@L_{n-1}X\to L_{n-1}L_{K(n)}X@@` 有同伦收缩（retraction，即左逆）。弱式只保留后半条：当 `@@M@@X@@` 是有限谱的导出 `@@M@@p@@`-完备化时，`@@M@@K(n)@@`-局部化单位经 `@@M@@L_{n-1}@@` 局部化后有收缩。此前的经验是"强公式屡屡失败、弱式总能幸存"：`@@M@@n=p=2@@` 处 Beaudry 推翻了指定和式公式，Beaudry–Goerss–Henn 补入 Moore 项后弱收缩依然成立，且弱式在高度二以下对所有素数成立；Minami 报告过 Devinatz 对允许完备 `@@M@@BP@@` 的类似猜想的反例，但那不是有限输入。长 `@@M@@\beta@@`-幂的非零性早有 Lee–Ravenel 一类结果（如 `@@M@@p\geq7@@` 时 `@@M@@\beta_1^{p^2-p-1}\neq0@@`），Ravenel 也算过第一 `@@M@@\beta@@`-元素的检测；此前缺的是同时做到两件事：在指定低高度局部化下检测出该类，又让它在高高度单位下消失。本文补上了这一步。

## 主要结果

记 `@@M@@S=S^0_{(p)}@@`，`@@M@@X=S_p^\wedge=\operatorname{holim}_j S/p^j@@`，`@@M@@L_r@@` 为 Johnson–Wilson `@@M@@E(r)@@`-局部化，`@@M@@i_{n,X}=L_{n-1}(\eta_X^{(n)})@@` 为典范弱分裂映射。令 `@@M@@d_p=2p(p-1)-2@@`、`@@M@@k_p=(p-1)^2@@`、`@@M@@z_p=\beta_1^{k_p}@@`，其中 `@@M@@\beta_1@@` 是经典第一 `@@M@@\beta@@`-元素（beta element）。定理一：对每个素数 `@@M@@p\geq5@@`，`@@M@@z_p@@` 在 `@@M@@\pi_{d_pk_p}L_{p-1}X@@` 中的像非零且被 `@@M@@\pi(i_{p,X})@@` 杀死，故 `@@M@@i_{p,X}@@` 无同伦收缩。定理二：对每个 `@@M@@p\geq7@@`，同一个 `@@M@@z_p@@` 在 `@@M@@\pi_{d_pk_p}L_pX@@` 中的像非零且被 `@@M@@\pi(i_{p+1,X})@@` 杀死。特例 `@@M@@p=5@@`：`@@M@@\beta_1^{16}@@` 在 `@@M@@\pi_{608}L_4X@@` 中非零并落在核里。另有一条独立路线：令 `@@M@@H=C_p\rtimes C_{(p-1)^2}@@` 作用于高度 `@@M@@p-1@@` 的 Morava `@@M@@E@@`-理论，可证下降指数（descent exponent）不等式 `@@M@@\expn_H(E_{p-1})\gt p^2+2\geq\expn_H(T(B_p))@@`（`@@M@@\expn_H(V)@@` 是使 `@@M@@J_H^{\wedge b}\wedge V\to V@@` 为零的最小 `@@M@@b@@`，`@@M@@T(V)=L_{K(p-1)}(E_{p-1}\wedge V)@@`，`@@M@@B_p=L_{K(p)}S@@`）；收缩会把 `@@M@@E_{p-1}@@` 变成 `@@M@@T(B_p)@@` 的 `@@M@@H@@`-等变收缩，与指数不相容。

## 证明思路

核定理的纲领是"下方检测、上方消灭、自然性拼装"。

先做约化：完备化映射 `@@M@@c:S\to X@@` 的纤维是 `@@M@@F(S[1/p],S)@@`，乘 `@@M@@p@@` 在其上可逆，故 `@@M@@c@@` 对每个 `@@M@@K(a)@@` 都是等价；于是只要某个 `@@M@@K(t)@@`-局部谱的单位在 `@@M@@z\in\pi_qS@@` 上取值非零、而 `@@M@@K(n)@@`-局部单位把 `@@M@@z@@` 杀死，两个自然性方块便把 `@@M@@z@@` 的像送进 `@@M@@\pi_qL_{n-1}X@@` 且被 `@@M@@i_{n,X}@@` 杀死。若有收缩则该群上有左逆，立即矛盾。

下方检测：取 `@@M@@h=p-1@@` 与有限子群 `@@M@@G@@`（纯稳定子部分为 `@@M@@C_p\rtimes C_{h^2}@@`），令 `@@M@@Y=E_h^{hG}@@` 为普通同伦不动点谱（homotopy fixed point spectrum）。Devinatz–Hopkins 把其不动点谱序列等同于局部 Adams 谱序列；Hopkins–Miller 计算（经 Heard 记录）给出正滤过部分为 `@@M@@\mathbb F_p[\alpha,\beta,\Delta^{\pm1}]/(\alpha^2)@@`，且单位把球面 `@@M@@\beta_1@@` 送到滤过二处的 `@@M@@c\beta@@`，`@@M@@E_\infty@@` 中 `@@M@@\beta^{h^2}\neq0@@`。作者补证一条普通滤过乘积引理（谱序列乘法就是实际同伦滤过的伴随分次乘法），从而 `@@M@@\eta_*(\beta_1^{h^2})@@` 非零；`@@M@@Y@@` 是 `@@M@@K(h)@@`-局部的，非零性便传到 `@@M@@L_{p-1}X@@` 及一切 `@@M@@L_rX@@`（`@@M@@r\geq p-1@@`）。

上方消灭：在 `@@M@@K(a)@@`-局部范畴令 `@@M@@I_a=\fib(B_a\to E_a)@@`，实际 Adams 滤过 `@@M@@F^s\pi_*B_a@@` 恰是 `@@M@@I_a^{\otimes_a s}@@` 的像，且滤过可乘。连续上同调在 `@@M@@s\gt a^2+1@@` 处消失——高度 `@@M@@p@@` 用纯稳定子维数加半线性 Witt 迹一收缩处理 `@@M@@p@@`-挠 Galois 商，高度 `@@M@@p+1@@` 的扩群无 `@@M@@p@@`-挠、直接用维数——强收敛给出零尾巴 `@@M@@F^{a^2+2}\pi_*B_a=0@@`。正稳定球面茎是挠群而 `@@M@@(E_a)_*@@` 无挠且集中在偶度，故 `@@M@@\beta_1@@` 的像落在 `@@M@@F^2@@`，其 `@@M@@k_p@@` 次幂落在 `@@M@@F^{2k_p}@@`；而 `@@M@@2k_p-(p^2+1)=p^2-4p+1\gt0@@`（`@@M@@p\geq5@@`）、`@@M@@2k_p-((p+1)^2+1)=p(p-6)\gt0@@`（`@@M@@p\geq7@@`），幂被零尾巴吞没。

独立的指数证明绕开核类：下界只需某个类在普通同伦不动点谱序列的一个指定有限页存活，无需永驻循环或球面代表元；上界由 Devinatz–Hopkins 幂零性定理先给出有限指数，数值上链界使相关映射在一切有限测试后为零，再用 Brown–Comenetz 论证使映射本身为零，最后用连贯迹（coherent trace）把有限层结构搬运到高度 `@@M@@p-1@@`。两条路各自封死高度 `@@M@@p@@` 处的收缩。

## 可信度与备注

主结果暂无形式化证明；高度 `@@M@@p@@` 的不可收缩有核类与下降指数两个互相独立的论证，互为印证。同族 318 的姊妹篇显示图景分层：`@@M@@n\geq1@@`、`@@M@@p\gt n+1@@` 时重叠仍有由局部球面片段组成的 `@@M@@2^n@@` 步滤过；本文推翻有限输入的弱收缩；`@@M@@p=3@@` 高度三的姊妹篇则证明连更弱表述的有限拼装也失败。三个层次的问题互不蕴含。OpenAI 官方声明：未经形式化的结果可能有问题。

{% endraw %}
