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

## 一句话结论

证明了 Foulkes 猜想在 \(a=6\) 成立：对一切 \(b\ge6\) 与有限维复向量空间 \(V\)，存在 \(\GL(V)\)-等变单射 \(\Sym^6(\Sym^b V)\hookrightarrow\Sym^b(\Sym^6 V)\)，即 \(h_b[h_6]-h_6[h_b]\) Schur-正；已知范围由 \(a\le5\) 推进到 \(a=6\)。

## 问题背景

Foulkes 在 1950 年研究协变量（concomitants）时提出猜想：当 \(1\le a\le b\) 时，应有 \(\GL(V)\)-等变嵌入 \(\Sym^a(\Sym^b V)\hookrightarrow\Sym^b(\Sym^a V)\)。在复数域上由完全可约性（complete reducibility），这等价于 plethysm 复合 \(h_a[h_b]\) 与 \(h_b[h_a]\) 之差是 Schur-正的（Schur-positive）。二元形式情形由经典 Hermite 互反律（Hermite reciprocity）给出同构，高维只能期待重数不等式。已知情形：\(a=1\) 平凡，\(a=2\) 属于 Thrall（1942），\(a=3\) 属于 Dent–Siemons（2000），\(a=4,5\) 分别靠 Müller–Neunhöffer 在 \((4,4)\) 与 Cheung–Ikenmeyer–Mkrtchyan 在 \((5,6)\) 的计算机计算配合 McKay 传播定理得到。但人们惯用的典范 Foulkes–Howe 映射在 \((5,5)\)、\((6,6)\) 处有非零核，这条老路到 \(a=6\) 断掉；Evseev–Paget–Wildon 的特征消缩递推只核实到两参数之和 \(\le 19\)，对应第六情形的 \(b\le 13\)。Brion 虽然证明了对固定 \(a\) 猜想最终成立，却未给出与维数无关的显式界，因此 \(a=6\) 的完全证明此前悬而未决。

## 主要结果

主定理：对每个整数 \(b\ge 6\) 与每个有限维复向量空间 \(V\)，存在 \(\GL(V)\)-等变单射 \(\Sym^6(\Sym^b V)\hookrightarrow\Sym^b(\Sym^6 V)\)；等价地，对每个 \(b\ge 6\)，\(h_b[h_6]-h_6[h_b]\) 的全部 Schur 系数非负。定理对 \(\dim V\) 无任何限制。对角情形 \(b=6\) 两边是同一表示，全部难点在 \(b>6\)。证明在结构上分两段：\(b\ge 30\) 的比较由姊妹篇的二次稳定化定理一次性覆盖，\(6\le b\le 29\) 则化为有限的重数比较；论文还保留了一条不依赖姊妹篇的独立路线，覆盖 \(b\ge 150\) 加上验证到 \(b=149\) 的有限计算。

## 证明思路

整体是"大范围靠代数、中范围靠组合、小范围靠计算机"的三层结构。先由姊妹篇的二次稳定化定理：典范乘法映射 \(\mu_{6,b,V}:\Sym^b(\Sym^6 V)\to\Sym^6(\Sym^b V)\) 在 \(b\ge 30\) 时满射，配合完全可约性即得该范围的嵌入；余下只需处理 \(6\le b\le 29\)。由 Cauchy 分解，源 \(\Sym^6(\Sym^b V)\) 的 Schur 支撑长度至多六，故只需在 \(V=\mathbb C^6\) 上比较六部划分 \(\lambda\vdash 6b\) 处的源重数 \(F(\lambda)\) 与目标重数 \(Q(\lambda)\)；矩形平移引理给出 \(Q(d+6e_i)\ge Q(d)\) 与 \(F(d+6e_6)=F(d)\)，从而可按"剩余类加网格"归约。上界侧，循环公式把 \(h_6[h_b]\) 写成 \(720\) 个置换因式积的平均，带符号条带规则（signed strip rule，plethystic Murnaghan–Nakayama 规则的特例）说明每个因式积的系数只能是 \(0,\pm1\) 且中间划分受包含关系约束；丢弃符号与部分约束后，得到对每个间隙坐标单调的上界函数 \(U(d)\ge F(d)\)。下界侧，最高权多项式乘法把已知的正重数传播到更大的权，而"幂证书"（power certificate）利用基的首项单项式互异，把重数放大归结为点和集（sumset）的 Matolcsi–Ruzsa 型下界 \(|kD|\ge f(C,h,k)\)。另有一个不走重数的图表证书（chart certificate）：取非零向量 \(v\) 并在 \(z(v)\) 处局部化，多元对称不变量的因子长度论证说明，只要 \(\lambda_2+\cdots+\lambda_6\le b\)，目标 \(R_b\) 的整个权空间都落在乘法像 \(A_b\) 里，从而 \(Q\ge F\)。证书程序对 \(6\le b\le 25\) 先测 \(Q\ge U\)，失败的划分（共 \(145435\) 个）再由 Newton 恒等式递推精确计算 \(F\)，无一为负；对 \(26\le b\le 149\) 把间隙向量分解为 \(d=r+6m\)（\(7776\) 个剩余类乘一个六百万点的网格），用共享的幂表与按剩余类精确的种子数组做传输测试，最终只剩尾带 \(\lambda_3+\cdots+\lambda_6\le 27\)。带内的差 \(Q-F\) 由七个与 \(b\) 无关的 Laurent 级数分子 \(G_j(q,y)\) 的系数和给出，第二个程序逐一检查了 \(57065668\) 个系数，无一为负。论文还保留了一条独立路线：图表（chart）证书配合极化（polarization）引理给出 \(b\ge a(a-1)^2=150\) 时的典范满射，连同验证到 \(b=149\) 的有限计算，不依赖姊妹篇同样完成证明。

## 可信度与备注

本篇暂无形式化证明。主路线的 \(b\ge 30\) 部分由已 Lean 形式化的姊妹篇（二次稳定化定理）支撑；\(6\le b\le 29\) 部分是传统数学论证加两个有限计算机验证，程序源代码完整印在附录（C++17、128 位整数，第二个程序用任意精度整数收尾），并附参考输出与复现脚本。按 OpenAI 官方声明，未经形式化的结果可能有问题，本文宜以社区核验为准。

{% endraw %}
