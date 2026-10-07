---
layout: default
title: "Log abundance in characteristic zero"
family: "034"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Log abundance in characteristic zero

> 结果族 034：Log abundance for compact Kähler spaces under logarithmic Iitaka subadditivity　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
在特征零的任意维数上证明了有理边界的对数丰性（log abundance）猜想：射影 log canonical pair 上 nef 的 \(\mathbb{Q}\)-Cartier 伴随除子必半充盈；在 \(\mathbb{C}\) 上还证明了任意维数光滑射影簇的典范非消失，补齐了极小模型纲领两大支柱之一的最后一块。

## 问题背景
丰性猜想（abundance conjecture）与极小模型存在性并列，是高维双有理几何（birational geometry）的另一半支柱。它断言：当 log canonical pair \((X,B)\) 的伴随除子 \(K_X+B\) nef（在每条曲线上度数非负）时，数值正性应来自截面——某个正倍数 \(m(K_X+B)\) 被整体截面生成，从而定义到射影空间的态射，把数字变成几何。三维情形由 Miyaoka、Kawamata 于 1988–1992 年解决，对数与半 log canonical 版本由 Keel–Matsuki–McKernan 与 Fujino 完成；高维的瓶颈是非消失（nonvanishing）：光滑簇上伪有效（pseudo-effective）的典范除子是否有非零多典范截面，此前只在低维或附加假设下已知。BCHM（2010）解决了 klt pair 的极小模型存在性，丰性却仍缺失；Liu–Xu（2025）也只覆盖数值维数至一的情形。

## 主要结果
主定理（文中 Theorem 1.1）：设 \((X,B)\) 是特征零代数闭域上的正规射影 log canonical pair，\(B\) 为有效有理除子，\(K_X+B\) 为 \(\mathbb{Q}\)-Cartier。若 \(K_X+B\) nef，则它半充盈（semiample）：存在 \(m>0\) 使 \(m(K_X+B)\) 由整体截面生成。证明过程中还在 \(\mathbb{C}\) 上建立了任意维数的光滑典范非消失（canonical nonvanishing）：\(K_X\) 伪有效蕴含 \(\kappa(X,K_X)\ge 0\)，即 \(H^0(X,mK_X)\ne 0\) 对某 \(m\) 成立。推论包括：实边界 lc pair 的好极小模型（good log minimal model）存在性；\(\kappa=0\) 时数值平凡推出 \(\mathbb{Q}\)-线性平凡；有理 lc pair 典范环的有限生成；半 log canonical 丰性；以及典范非消失与有理曲线、余切张量、基本群间的分类联系。

## 证明思路
证明在 \(\mathbb{C}\) 上按维数归纳，归纳命题强于主定理：带实边界的射影 lc pair 若伴随除子伪有效则有好极小模型。链条为 \(\mathrm{GLM}_{\le n-1}\Rightarrow \mathrm{NV}_n\Rightarrow \mathrm{GLM}_{\le n}\Rightarrow \mathrm{SA}_n\)：先用低维好模型证 \(n\) 维光滑非消失，再用它制造 \(n\) 维好模型，最后经比较引理得到 nef 伴随除子的半充盈。

两步共用一台发动机——"带号代表判据"：在既约边界 \(D\) 的 \(\mathbb{Q}\)-factorial dlt pair 上，若 \(L=K_X+D\) nef、\(L-cD\) 伪有效、\(L\sim_{\mathbb{Q}}\sum a_iD_i\)（系数可正可负）且 \(L|_D\) 在整个既约概形上半充盈，则 \(\kappa(L)=\nu(L)\)。证明是几何性的：先由 \(L|_D\) 的截面得态射，在正系数分支像的一般点作根覆盖（root construction）分离正、负系数部分；再用滤过 Hodge 模（filtered Hodge modules，Saito 理论）把像上参数连同横向参数穿过全部无穷小邻域提升；固定底参数、变化横向参数，把一条边界纤维形变为避开整个边界的射影子簇，得到支配族且 \(L\) 在其上数值平凡；这些"零族"约束 nef reduction 的维数，垂直下降把 \(L\) 等同于底上大除子的拉回。此法承 Miyaoka 三维证明的精神，但须在可约边界上构造相容的形式提升，\(L|_D\) 的半充盈由 Fujino–Gongyo 正规化粘合定理提供。

光滑非消失用反证法：对假想反例，先由对数 Iitaka 次可加性（配套姊妹篇的唯一新输入）经 Albanese 映射排除正非正则度；再用正电流与代数网、以及 Lelong 数的升链条件排除两类被低维子簇覆盖的方式。关键一步是 \(X\times X\) 上的"双槽 jet"构造：取两个拉回之和的射影丛，若 jet 分离失败，移动基分量给出两因子间的对应，经 Hanamura 双有理群定理使某固定覆盖双有理等价于阿贝尔簇，回到已排除情形。最后的数值矛盾由 Frobenius 对比完成：把固定数据模大素数约化，在 Frobenius 扭曲模型的乘积上考察赋值映射，用 Sun 的 Frobenius 滤过与 Langer 不稳定性估计在对角线上得到两个不相容的秩界。

好模型步骤中 \(\kappa\ge 1\) 由低维好模型处理；\(\kappa=0\) 时经 Hashizume 约化与 Birkar 有理多面体定理化为有理 dlt 情形，带号判据给出数值维数也为零，迫使有效代表为零即 \(L\sim_{\mathbb{Q}}0\)。收尾取 crepant dlt 模型，用负性引理比较除子，截面经投影公式下降；最后经有限生成子域铺开与嵌入 \(\mathbb{C}\)，把整体生成性忠实平坦地转移到任意特征零代数闭域。

## 可信度与备注
本篇出自 OpenAI 数学证明项目，主结果暂无 Lean 形式化证明。论证依赖配套的"对数 Iitaka 次可加性"一文作为唯一外部新输入（仅用于排除正非正则度）；姊妹篇《Minimal metrics…》与《Fourfold nonvanishing…》分别从解析度量与四维特例侧支撑同一非消失路线。按 OpenAI 官方声明，未经形式化的结果可能有问题，全文请以社区核验为准。

{% endraw %}
