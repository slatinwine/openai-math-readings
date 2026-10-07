---
layout: default
title: "Integral Donovan Finiteness over Witt Vectors"
family: "203"
discipline: "Algebra"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Integral Donovan Finiteness over Witt Vectors

> 结果族 203：Donovan's conjecture over fields and complete mixed-characteristic DVRs　·　学科：Algebra　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明了整系数版的 Donovan 有限性：固定素数 \(p\) 与亏群阶上界 \(M\) 后，所有有限群的块在 Witt 向量环 \(W(\overline{\mathbb F}_p)\) 上只代表有限多个 \(\mathcal O\)-线性 Morita 等价类；同一有限性对每个特征零、剩域代数闭的完备离散赋值环（discrete valuation ring，含分歧环）也成立。亏群不必交换，且包括 \(p=2\)。

## 问题背景

记 \(k=\overline{\mathbb F}_p\)、\(\mathcal O=W(k)\)。整系数的 Donovan 问题比剩域上的版本更强：它约束的是整模范畴，连格（lattice）结构一起管住。Eaton–Eisele–Livesey 的 2020 年判据——有界亏群、有界 Cartan 元总和、有界整 Morita–Frobenius 数（Morita–Frobenius number，即最小 Frobenius 幂次回到 Morita 类）三者推出整 Morita 有限性——此前只对交换 \(2\)-群实现了完整结论，四元数亏群则要到 2026 年 8 月的预印本。转到 \(\mathcal O\) 上有两大新困难：其一，系数 Frobenius 的不动点坐标落在无限的 \(W(\mathbb F_q)\) 中，域情形赖以收尾的有限域点计数彻底失效；其二，标量障碍可能含主单位（principal unit，\(1+\rad\)），而主单位在 \(p\)-群上的上同调不必消失。Eisele–Livesey 还构造了 Morita–Frobenius 数无界增长的族，说明有理数据必须显式保留。

## 主要结果

主定理：对每个素数 \(p\) 与正整数 \(M\)，当 \(G\) 取遍有限群、\(b\) 取遍 \(\mathcal O G\) 中亏群阶至多 \(M\) 的块幂等元时，块代数 \(\mathcal O Gb\) 只有有限多个 \(\mathcal O\)-线性 Morita 等价类。推论一：固定任意特征零、剩域 \(\ell\) 代数闭（特征 \(p\)）的完备离散赋值环 \(\mathcal R\)（允许分歧，不要求分式域分裂），同样的有界亏群有限性在 \(\mathcal R\) 上成立。推论二：存在有限个整基序（basic order）\(R_1',\dots,R_v'\)，使每个亏群阶 \(\le M\) 的 \(k\)-块的基代数都同构于某个 \(k\otimes_{\mathcal O}R_i'\)——即整列表反过来重新给出域上的有限性。

## 证明思路

证明与姊妹篇（域上 Donovan 猜想）配合，分三大支柱。第一是**精确比较**。姊妹篇构造的几何比较算子只在模 \(p\) 后精确等变；本文逐行追踪其整系数构造，证明所有标量误差其实都是素于 \(p\) 的特征值之比，落在 Teichmüller 子群 \(\mathcal T=[k^\times]\subseteq\mathcal O^\times\) 中：关键的重叠公式 \(D_{\mathrm{ad}(\ell)}=\lambda_m(\ell)^{-1}E_\ell\) 里的扭转特征 \(\lambda_m\) 是 \(p'\) 阶线性特征，中心元素的歧差同样归结为 \(p'\) 次单位根。而有限 \(p\)-群满足 \(H^i(S,\mathcal T)=0\)（\(|S|\) 次幂映射是 \(\mathcal T\) 的自同构），于是标量 2-上闭链必为上边缘，重新标度算子后得到 \(\mathcal O\) 上**精确**等变、Frobenius 周期有界的整 Morita 双模。误差必须压进 \(\mathcal T\)——任意 \(\mathcal O^\times\) 值误差中的主单位部分无法消去。第二是**基础有限性**。先用实际自同构与乘法因子拼出一个真实有限群 \(\Gamma_S\)，使纯 Sylow 限制恰是有界亏群的实际群块；Marcus 型归纳引理把比较双模扩张成交叉序（crossed order）间的 Morita 等价，给出有界 Morita–Frobenius 数；结合姊妹篇的一致 Cartan 界套用 EEL 判据，得这些总限制序只有有限多个整 Morita 类。但 Morita 列表不区分分次分量，需要新的刚性理论：一个整轨道引理（轨道导数满射的整点只有有限多个轨道，靠特殊纤维维数计数、Hensel 切片与孤立点论证）加上 Hochschild 刚性 \(\mathrm{HH}^1_{\mathcal O}(A)=0\)，推出固定总序的 \(H\)-分次只有有限多类——切向量计算只用群里的消去律、不做平均，故 \(p\mid|H|\) 也成立（固定总序不可省：\(\mathcal O[t]/(t^p-a)\) 型交叉序有无限多类）。由此得到保留群标签与恒等标记的 based 有限列表。第三是**核移除**。对无界正规 \(p'\)-核 \(K\)，主单位上同调因 \(|K|\) 可逆而消失，剩下的扭群代数分裂为矩阵代数之积 \(E\cong\prod_j M_{n_j}(\mathcal O)\)（\(p\nmid n_j\)）；矩阵角把无界分次群换成有界商 \(Q_j\)。剥离矩阵会引入新标量误差：取行列式为 1 的实现矩阵（\(p\nmid n\) 保证 \(n\) 次根存在），新误差满足 \(\gamma^n=1\) 而落入 \(\mathcal T\)，再次被 \(\mathcal T\)-上同调消失清除，故 Sylow 限制仍落在受控的 based 列表中；最后在有界商上，因子系统构成 \(H^2(Q_j,Z_R^\times)\)-挠子，Sylow 限制的核有限（主单位部分经限制–余限制单射，\(\mathcal T\) 部分整体有限），有限纤维给出有限列表。组装时经 An–Eaton 整归约与对偶恢复把任意块变为有限基序上交叉序的块和，三假设齐备即得定理；固定完备赋值环的推论则经 Cohen 环嵌入、块幂等元的唯一 Hensel 提升（\(p=2\) 亦适用）与 Morita 等价的纯量扩张完成。

## 可信度与备注

本文是 OpenAI 2026 年 9 月 25 日的预印本，主结果尚无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。它与同族姊妹篇互相咬合：本文直接调用姊妹篇的一致 Cartan 界与保留实际乘法因子的整比较构造，并把后者"模 \(p\) 后精确"的等变性加强为 \(\mathcal O\) 上精确；反过来，本文的有限整基序列表也重新给出域上基代数的有限列表。两篇合起来完整覆盖了结果族 203 声称的域上与整系数 Donovan 有限性。

{% endraw %}
