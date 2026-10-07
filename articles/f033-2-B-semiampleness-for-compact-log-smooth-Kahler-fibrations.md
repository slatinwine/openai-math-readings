---
layout: default
title: "B-semiampleness for compact log-smooth Kähler fibrations"
family: "033"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | B-semiampleness for compact log-smooth Kähler fibrations

> 结果族 033：Iitaka subadditivity, variation, and logarithmic additivity　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文证明了 b-半丰富性猜想（b-semiampleness conjecture）的紧 Kähler、log 光滑情形：即使底与全空间均非射影、边界含系数 1 的分量，moduli 有理 b-线丛仍可在某个修改模型上被整体全纯截面生成，补上了代数范畴已知结论与解析范畴之间明确遗留的缺口。

## 问题背景

典范丛公式（canonical bundle formula）把纤维化的典范几何拆成判别式（discriminant，度量奇异纤维贡献）与 moduli 部分（度量族的变化）。b-半丰富性猜想预测 moduli 部分的某个倍数在底的双有理模型上定义一个态射，是极小模型纲领中连接正性与丰富性的关键一环。Kawamata 的 Hodge 半正性是其源头；Ambro 建立了 moduli 部分的双有理稳定与一般 klt 情形的正性；Fujino–Gongyo 证明射影 lc-平凡纤维化的 b-nef 性；Bakker–Filipazzi–Mauri–Tsimerman（BFMT）在代数范畴证明了该猜想，但其讨论保留映射的射影性，Kähler（解析）情形在其论文 Remarks 6.31 与 7.5 中被明确指出并未随之解决。难点有三：非射影 Kähler 流形缺少丰富线丛作锚点；边界系数可为 1，使 Hodge 结构从纯变分（pure variation）变为混合变分（mixed variation）；数值半正性不足以产生实际全纯线丛的整体生成。

## 主要结果

设 \(f:Y\to X\) 是紧 Kähler 流形间具连通纤维的满射全纯映射，\(\Delta\) 是有效有理除子，支撑单正规交叉（simple normal crossing）、系数落在 \([0,1]\)，且 \(K_Y+\Delta\sim_{\Q}f^*L\)（\(L\in\Pic(X)_{\Q}\)）。对每个修改 \(\mu:X'\to X\)，用 log 常规阈值（log canonical threshold）\(t_P\) 定义判别式 \(B_{X'}=\sum_P(1-t_P)P\) 与 moduli 部分 \(M_{X'}=\mu^*L-K_{X'}-B_{X'}\)。主定理：moduli 有理 b-线丛 \(\mathbf M=(M_{X'})\) 是 b-半丰富的——存在光滑紧 Kähler 修改 \(S\to X\)，使得 (a) 对每个进一步的修改 \(\nu:S_1\to S\) 都有 \(M_{S_1}=\nu^*M_S\)（在 \(\Pic(S_1)_{\Q}\) 中）；(b) 某个正整数倍 \(mM_S\) 由其整体全纯截面生成。水平系数 1 分量被允许，点底与相对维数零亦然；不假设 \(f\)、\(X\)、\(Y\) 的射影性，也不假设 Campana 轨道 Iitaka 假设。论文特别指出该判别式是阈值型而非轨道底的重数下确界除子，故把多重形式分解产生的 Hodge 线与它等同是证明的主要步骤之一。

## 证明思路

先取边界单正规交叉的紧 Kähler 修改 \(S\)，局部取相对 log 多重体积线的 \(m\) 次根覆盖：其最高 Hodge 特征空间一维，根形式 \(\tau\) 在好开集上只有沿系数 1 分量的对数极点。系数 1 部分天然产生混合变分结构；通过迭代留数（iterated residue），把这条线经由单一纯权等级（pure weight grade）与最深边界层的体积线等同——此步依赖 Fujino–Fujisawa 的混合 Hodge 延拓定理，保证该约化在圆盘上与延拓相容。随后是全文最精细的局部计算：在分辨后的横向圆盘上做幂替换 \(t=u^N\)，用变量替换恒等式（含基雅可比）逐除子追踪阶数，证明根体积的规范化 Hodge 阶恰为 \(\operatorname{ord}_P^{\mathrm{Hodge}}(\tau)=t_P-1\)。由此得到两个关键推论：典范 Hodge 延拓就是实际的 moduli 线；该等同在每个更高光滑模型上拉回，即定理的 (a)。再向最深的边界层伴随，得到 log 典范丛平凡的紧 Kähler klt 纤维；Matsumura–Wang–Wu–Zhang 的定理给出其有限乘积覆盖。逐点的乘积分解不足以推出半丰富性，作者转而构造带截面的标记族（marked family），在有限基变换后实现有限纤维覆盖，并把乘积图嵌入固定的紧 Kähler 环境中参数化；紧 Douady 分量与正常可构造性论证给出紧的正常满射 \(P\to S\)，在稠密开集上承载乘积族（辅助基 \(P\) 不必射影、也不必在 \(S\) 上一般有限）。乘积因子分类处理：射影 log Calabi–Yau 因子借助射影比较基上的代数 b-半丰富性定理；最高形式由权一、权二周期控制的因子，则通过 Hodge 滤波的平坦变换把实极化换成有理极化而不改变积分单值，再用 BFMT 的算术周期紧致化在辅助基上解析地提供半丰富延拓。最后，以留数积分作为延拓范数，体积范数的乘积恒等式与双侧对数增长界把开集上的线丛同构穿过边界延拓（排除隐藏的平坦扭曲）；半丰富性经 Stein 因子分解与有限解析范数从 \(P\) 下降到 \(S\)，得到在每一点整体生成且指数单一的结论。

## 可信度与备注

主结果暂无形式化证明，请以社区核验为准。本篇是结果族 033 的解析分支，与射影 Iitaka 子可加性、反向对数 Kodaira 不等式等姊妹篇共享典范丛公式与 BFMT Hodge 理论框架；值得注意的是本篇明确不使用 Campana 轨道 Iitaka 定理，从而在族内独立供给 b-半丰富性这一输入。按 OpenAI 官方声明，未经形式化的结果可能存在问题，宜以社区核验为准。

{% endraw %}
