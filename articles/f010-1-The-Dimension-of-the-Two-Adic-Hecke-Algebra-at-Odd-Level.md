---
layout: default
title: "The Dimension of the Two-Adic Hecke Algebra at Odd Level"
family: "010"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Dimension of the Two-Adic Hecke Algebra at Odd Level

> 结果族 010：Unrestricted pro-modularity at the prime two　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明：对每个奇数 `@@M@@N@@`，水平 `@@M@@\Gamma_1(N)@@` 的完整 2-adic Hecke 代数（Hecke algebra）的谱的每个不可约分支（irreducible component）的 Krull 维数（Krull dimension）都恰好是 4。这证明了 Emerton 维数猜想在 `@@M@@p=2@@` 的情形，且不设剩余表示不可约等任何附加条件。

## 问题背景

不同权的模形式（modular forms）之间丰富的同余关系，把它们的 Hecke 特征值编织成单一的 p-adic 代数。Hida 的普通族、Coleman–Mazur 的本征曲线（eigencurve）与 Gouvêa–Mazur 的无穷蕨（infinite fern）都表明：这个代数的谱比任何单条特征形式族都大得多，许多族可以穿过同一个经典点。Emerton 在 2011 年对这种"完整"Hecke 代数——不局限于某一个剩余变形问题——提出维数猜想（Conjecture 2.9），并用无穷蕨证得下界：每个不可约分支维数至少为 4；补齐上界则是一个变形论难题。困难集中在 `@@M@@p=2@@`：整系数伪表示（pseudorepresentation）的标准技巧需要除以 2，而已有的伴随 Selmer 群（adjoint Selmer group）消没定理（Kisin、Allen）又都带剩余不可约性假设，无法覆盖标量或可约的剩余分支。Newton–Thorne 2023 年不带剩余限制的消没定理成为突破口。

## 主要结果

固定奇数 `@@M@@N@@`。设 `@@M@@M_i(N)@@` 为权 `@@M@@i@@`、水平 `@@M@@\Gamma_1(N)@@` 的模形式全体（含 Eisenstein 级数），`@@M@@T_\ell@@` 为 Hecke 算子，`@@M@@S_\ell@@` 在权 `@@M@@i@@` 上按 `@@M@@\ell^{i-2}\langle\ell\rangle@@` 作用（`@@M@@\langle\ell\rangle@@` 为菱形算子）。令 `@@M@@T_{\le k}^{(2)}(N)@@` 为 `@@M@@\bigoplus_{i=1}^k M_i(N)@@` 上由诸 `@@M@@T_\ell@@` 与 `@@M@@\ell S_\ell@@`（`@@M@@\ell\nmid 2N@@`）生成的 `@@M@@\Z@@`-代数，取 2-adic 逆向极限 `@@M@@A=T_2(N)=\varprojlim_k\Z_2\otimes T_{\le k}^{(2)}(N)@@`。主定理断言：`@@M@@\Spec T_2(N)@@` 的每个不可约分支的维数恰为 4。关键在于该代数保留了所有的权、所有 Eisenstein 特征值体系与所有剩余特征值体系——定理不要求剩余伽罗瓦表示不可约、非标量或在 2 处特殊，可约与标量分支同样被覆盖，这正是"including all residual components"的含义。

## 证明思路

整体是下界与上界的夹逼。先搭代数骨架：每个有限层 `@@M@@A_k@@` 经经典特征值嵌入有限个特征值环之积，故 `@@M@@A@@` 紧、约化、经典点 Zariski 稠密。为证 Noether 性，作者以 Chenevier 的行列式律（determinant law）替代需要除以 2 的伪表示技巧：由 Chebotarev 密度与闭像论证，构造 `@@M@@A@@` 上迹为 `@@M@@T_\ell@@`、行列式为 `@@M@@\ell S_\ell@@` 的整系数二维行列式；再由 Jochnowitz 定理（固定素到 2 水平的剩余体系只有有限多个）把 `@@M@@A@@` 分解为有限个局部因子，并经 Chenevier 的普遍行列式变形环证明每个因子是完备 Noether 局部环。Emerton 的下界（每分支维数 `@@M@@\ge4@@`）直接引为输入。

再在每个分支上寻找好的经典点：权 `@@M@@i\ge3@@` 的 Eisenstein 体系在好素数 `@@M@@\ell@@` 处取值 `@@M@@\psi(\ell)+\phi(\ell)\ell^{i-1}@@` 与 `@@M@@\psi(\ell)\phi(\ell)\ell^{i-1}@@`。对固定的 Dirichlet 特征对与权的奇偶类，利用奇素数分解 `@@M@@\ell=s_\ell 5^{b_\ell}@@`（`@@M@@s_\ell=\pm1@@`，`@@M@@b_\ell\in\Z_2@@`）把 `@@M@@\ell^{i-1}@@` 插值为 `@@M@@s_\ell^{i-1}(1+X)^{b_\ell}@@`，它在 `@@M@@X=5^{i-1}-1@@` 处取值正确；紧图论证配合 Strassmann 定理证明插值延拓为连续映射 `@@M@@\Phi:A\to\OO[[X]]@@`，其像介于 `@@M@@\Z_2[[X]]@@` 与 `@@M@@\OO[[X]]@@` 之间，维数为 2。于是 Eisenstein 轨迹维数至多 2、有界权轨迹至多 1，都填不满维数至少 4 的分支；由经典点稠密性，每个分支上存在权 `@@M@@\ge3@@` 的经典尖点，且不落在其他分支上。

最后在该尖点处压缩切空间：把代数切向量写成连续导子 `@@M@@D@@`，经 `@@M@@\lambda+\eps D@@` 得到一阶行列式变形，由 Chenevier 的绝对不可约提升定理得到 `@@M@@r_D:G\to\GL_2(E[\eps])@@`；写 `@@M@@r_D=(1+\eps c)r@@`，则 `@@M@@c@@` 为上闭链，比较迹便把 `@@M@@D@@` 嵌入 `@@M@@H^1(G,\ad r)@@`，特征零（可除以 2）保证单射，故 `@@M@@\dim A_\frakx\le\dim_E H^1(G,\ad r)@@`，其中 `@@M@@\ad r@@` 是含标量的完整伴随表示（维数 4，恰为行列式允许变化时所需）。右侧由两件事实控制：Newton–Thorne 定理给出整体 Bloch–Kato 有限 Selmer 群 `@@M@@H^1_f(\Q,\ad r)=0@@`（奇水平保证 CM 型的 CM 域不含于 `@@M@@\Q(\zeta_{2^\infty})@@`）；局部上 `@@M@@v\ne2@@` 处商群为零，仅 `@@M@@v=2@@` 处由 Euler 示性数公式与 Bloch–Kato 维数公式得商维数 3，故 `@@M@@H^1(G,\ad r)\le3@@`。收尾用完备局部环的维数公式：`@@M@@\dim A/P\le\dim A_\frakx+1\le4@@`（经典商在 `@@M@@\Z_2@@` 上有限、维数 1），与下界合并得每个分支恰为 4 维。

## 可信度与备注

本文暂无形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。论文的深层外部输入——Deligne/Deligne–Serre 的伽罗瓦表示附着、Emerton 下界、Chenevier 行列式理论、Newton–Thorne 的 Selmer 消没——都在使用处注明了出处与假设；两段自足的新论证（Eisenstein 插值的紧图构造、特征零切空间估计）均不依赖剩余不可约性。在本结果族中，姊妹篇把每个 2-adic 伽罗瓦表示实现到某个完备 Hecke 代数（无限制 pro-modularity），并据此推出 `@@M@@p=2@@` 的 Fontaine–Mazur 型模性；本文给出这些 Hecke 代数谱的每个分支的精确维数，与姊妹篇互相支撑。

{% endraw %}
