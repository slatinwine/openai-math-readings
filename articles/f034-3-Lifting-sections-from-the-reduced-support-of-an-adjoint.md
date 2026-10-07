---
layout: default
title: "Lifting sections from the reduced support of an adjoint"
family: "034"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Lifting sections from the reduced support of an adjoint

> 结果族 034：Log abundance for compact Kähler spaces under logarithmic Iitaka subadditivity　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了一个"支撑式截面提升"定理：当 dlt 对的伴随除子有某个有效倍数落在系数为 1 的边界支撑内、且其线丛在整个约化支撑上半丰富时，Iitaka 维数必为正；由此把丰富性与非零截面问题分离，证得四维及以下"有非零截面即丰富"。

## 问题背景

对数丰富性猜想（log abundance conjecture）是双有理几何纲领的核心难题：射影 log canonical 对 \((X,\Delta)\) 上 nef 的伴随除子 \(D=K_X+\Delta\) 应当是半丰富（semiample）的，即某个倍数由整体截面生成并定义代数纤维化。三维及以下的情形已由 Kawamata、Keel–Matsuki–McKernan、Fujino 等解决；四维以上卡在两件事：先找到一个非零截面（nonvanishing），再从截面族得到纤维化。Liu–Xu 此前只在数值维数（numerical dimension）\(\nu\leq1\) 的附加限制下证明了"非零截面之后即丰富"。本文把丰富性的障碍完全压缩到"第一个截面从哪里来"这一步，并在四维及以下去掉数值维数限制。

## 主要结果

**定理 A（支撑边界提升，supported boundary lifting）**：设 \((V,C)\) 是特征零代数闭域上的射影 ℚ-因子 dlt 对，\(C\) 为有效有理边界，记 \(A=K_V+C\)。若存在 Cartier 的非零有效除子 \(G\sim qA\)（\(q>0\) 充分可除），使 \(\operatorname{Supp}G\subseteq\operatorname{Supp}\lfloor C\rfloor\)，且 \(\mathcal O_V(G)|_{G_{\mathrm{red}}}\) 在整个约化支撑上是半丰富线丛，则 \(\kappa(V,A)>0\)。

条件里不含任何额外 nef 假设：支撑内的曲线靠半丰富性、支撑外的曲线靠有效性分别保证 \(G\)-度非负；支撑包含还可以是严格的——额外的系数一分支 \(H\) 允许与 \(S\) 及其分层相交。

**定理 B（非零截面之后的丰富性）**：\(\dim X\leq4\) 的射影 log canonical 对，\(\Delta\) 有效有理，\(D=K_X+\Delta\) 为 nef 的 ℚ-Cartier 除子且 \(\kappa(X,D)\geq0\)，则 \(D\) 半丰富；\(\kappa=0\) 时更有 \(D\sim_{\mathbb Q}0\)。结论经第 6 节转移到任意特征零代数闭域。

**定理 C（到光滑非零截面的归约）**：若每个伪有效 \(K_W\) 的光滑射影复簇都有 \(mK_W\) 的非零截面，则任意维数的 nef log canonical 伴随除子半丰富。结合姊妹篇《Fourfold nonvanishing by minimal metrics and moving jets》的四维非零截面结果，直接得到四维及以下的完整对数丰富性。

## 证明思路

证明分两段：先把"提升障碍"压到约化边界上消掉（定理 A），再用归纳把丰富性交给低维与最小模型（定理 B）。

第一段。记 \(S=G_{\mathrm{red}}\)，半丰富性给出态射 \(f:S\to\mathbb P^\ell\)。麻烦在于 \(f\) 本身未必延伸到 \(S\) 的任何邻域，障碍只能用约化边界上的态射来度量。先取 \(\mathcal O_V(G)\) 的非零标架丛：其上线丛有重言平凡化，标架伸缩给出 \(\mathbb G_m\)-作用，函数与形式按权（weight）分解。两次循环覆盖构造加上等变消解，产生既约 Cartier 除子 \(E=(y=0)\) 与一个对数拓扑形式 \(\sigma\)，其留数 \(\Omega\) 的权 \(a=r/q>0\) 为正。从 \(y^k=0\) 提升到 \(y^{k+1}=0\) 时，局部提升之差是 \(y^k\) 的倍数，其系数在 \(E\) 上给出上同调类——这就是障碍。关键观察：两个误差之积在该阶消失，故连接同态满足 Leibniz 律，障碍是一个导子（derivation）\(\delta\)。留数嵌入把它送进 Hodge 模块的滤过直接像（利用 Saito 的严格性与 Kodaira–Saito 消没），从而保留集中在奇异纤维与更小分层上的类。再在边界态射的图（graph）上做局部计算，把 \(\delta\) 与"首符号"写进同一个留数恒等式。先消水平分量：若它非零，用横截有限覆盖与其微分的伴随矩阵可造出从丰富线丛到首符号核的非零映射，被 Kodaira–Saito 消否定理排除；剩下的竖直分量恰是标架伸缩的 Euler 导数，留数恒等式给出权 \(m=a+k>0\) 乘以竖直障碍为零，权非零迫使障碍本身为零。于是任意阶有限提升畅通。最后取覆盖不变量与标架作用的零次分量，把提升的层降回 \(V\) 上：这些层以周期 \(r\) 带正挠度循环出现，用 Serre 消没与 Euler 特征的可加性计数，得 \(h^0(V,\mathcal O_V(NG)/\mathcal O_V)\to\infty\)；两个线性无关截面的比值是非常数有理函数，故 \(\kappa(V,G)>0\)。

第二段（定理 B）分三步。\(\kappa=0\) 时若存在非零有效代表：提高边界系数后取 log 最小模型，nef 性保证代表在新模型上存活（负性引理），低维丰富性与 Fujino–Gongyo 的黏合定理使其在整个楼面上半丰富，于是被定理 A 排除，故 \(D\sim_{\mathbb Q}0\)。\(\kappa>0\) 时取 Iitaka 纤维化，在一般纤维上用有效 log 最小模型与模型比较，配合 Hodge 指标定理证明 \(\pi^*D|_F\equiv0\)，进而 \(\nu=\kappa\)。最后经 crepant dlt 修改验证所有 log canonical 中心上的半丰富性，引用 Fujino–Gongyo 的"nef 且 log 丰富⟹半丰富"。域的转移则是把全部数据下降到一个可嵌入 \(\mathbb C\) 的代数闭子域，再由基变换搬回截面与生成性。

## 可信度与备注

本文主结果暂无 Lean 形式化证明；依 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。全文技术性最强、最需独立核验的环节是图上留数恒等式处对 Saito Hodge 模块严格性与 Kodaira–Saito 消没的使用。本篇与同族姊妹篇互相咬合：它提供"非零截面⟹丰富"的引擎，非零截面本身由《Fourfold nonvanishing by minimal metrics and moving jets》供给，合起来给出族 34 在四维及以下的完整对数丰富性，并为全维数情形提供条件性归约框架。

{% endraw %}
