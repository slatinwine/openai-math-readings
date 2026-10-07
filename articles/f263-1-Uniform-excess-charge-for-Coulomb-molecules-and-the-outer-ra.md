---
layout: default
title: "Uniform excess charge for Coulomb molecules and the outer radius of neutral atoms"
family: "263"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Uniform excess charge for Coulomb molecules and the outer radius of neutral atoms

> 结果族 263：The ionization and generalized ionization conjectures　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明：\(M\) 个固定原子核、总核电荷 \(Z\) 的分子最多严格束缚 \(Z+CM\) 个电子（\(C\) 为普适常数），且中性原子的首电离能与"半电子外半径"都被正常数上下夹住。这是完整库仑模型下电离猜想的首次完整解答，也是本族另两篇的证明地基。

## 问题背景

一个分子到底能"抓住"多少电子？这是库仑体系基态理论的基本问题。对非相对论库仑哈密顿量（Coulomb Hamiltonian）\(H_n\)，若第 \(n\) 个电子数区间的基态能量满足 \(E_n<E_{n-1}\)，就称体系"严格束缚"（binds strictly）\(n\) 个电子。Simon 在 2000 年的公开问题集中问：单原子的最大严格束缚电子数与核电荷之差是否有界？分子版猜想 \(N_c\le Z+CM\) 收录于 Lewin 2025 年的综述。此前 Lieb（1984，无需费米统计）给出线性界，Lieb–Sigal–Simon–Thirring 证明渐近中性 \(N_c(Z)/Z\to1\)，Nam 与 Hundertmark–Pattakos–Schulz 又相继给出 \(N_c<1.22Z+3Z^{1/3}\)、\(1.1185Z+4Z^{1/3}\) 的定量估计，但都无法给出均匀的超出界。近似模型中的相应定理已由 Benguria–Lieb（TFvW 理论）与 Solovej（Hartree–Fock 理论）建立；完整模型的真正障碍在于基态可以带有任意多体关联。

## 主要结果

定理一（均匀超出电荷，uniform excess charge）：存在普适常数 \(C\)，对任意 \(M\ge1\) 个位置互异、电荷 \(z_j\ge1\) 的原子核（\(Z=\sum z_j\)）与任意 \(n\ge1\)，\(E_n<E_{n-1}\) 蕴含 \(n\le Z+CM\)；且当 \(n>Z+CM\) 时必有 \(E_n=E_{n-1}\)。单核情形给出 \(n\le Z+C\)，对一切实数 \(Z\ge1\) 成立。定理二（外半径）：对整数电荷 \(Z\ge1\) 的中性原子与任意基态 \(\Psi_Z\)，定义 \(R(\Psi_Z)=\inf\{r:\int_{|x|>r}\rho_{\Psi_Z}\,dx\le\frac12\}\)，则 \(c\le R(\Psi_Z)\le C\)。推论：首电离能（first ionization energy）\(I_1(Z)=E_Z(Z-1)-E_Z(Z)\) 满足 \(c\le I_1(Z)\le C\)。所有常数与核数、核电荷、核位置无关，也不要求基态唯一或球对称。

## 证明思路

核心困难是固定电子数阻碍局部比较：一个小球中的电子可多可少，挖空后的"条件核"不极小化任何固定粒子数的问题。作者改为相对全体区间的下确界 \(E=\inf_n E_n\) 工作，全程让能量偏移 \(\delta\) 可见，使局部估计在施加观测、删除粒子、更换概率律之后仍然可用。

分子部分分三步。先做空间切割：记录每个被移走的电子（含位置与自旋），剩余条件核保持反对称；用相干态（coherent states）上比较与诺伊曼（Neumann）特征值下比较——两者动能系数一致——造出局部托马斯–费米（Thomas–Fermi）极小化子 \(\rho=k(W_+)^{3/2}\) 及其屏蔽场（screened field）。再引入含噪观测：给电子位置加独立误差并遗忘标签，概率为 \(p\) 的观测事件只耗费 \(C\ell^{-2}\log^5(e/p)\) 的能量、不含粒子数因子；用两种后验分布的条件期望恒等式比较各自的场。最后在倍增尺度 \(r_j=2^jr_0\) 上逐层向外传播一个满足非线性次解不等式的正场：每步取错开常数平移的旧场与观测场的局部最大值，使逆比较恰在取到最大值的分支补出源项，再条件平均遗忘一层数据，反应项的凸性保证不等式存活；误差不要求"空间处处良好"的事件，只累计期望积分，总量 \(o(M)\)。终局用球面平均把正场转化为 \(0<Z-N+\text{外部质量}+\text{误差}\)，而外部电子数 \(\le CMr_*^{-3}\)，取 \(r_*=(B_0M/K_{\rm exc})^{1/3}\)、\(B_0\) 充分大，便与"超额 \(K_{\rm exc}/M\to\infty\)"矛盾。

原子部分改用"到核距离"作几何尺度，传播产生内部电子亏量：先用它证 \(E_{Z-1}\le E+C\)（删去外部电子）；再在半径 \(S\) 的环上对插入中心取平均，向单电离态插入一个包宽 \(b=S^{3/5}\) 的远置轨道包，平均插入场至少 \(1/(2S)\) 而代价 \(o(S^{-1})\)，得正能隙 \(E_{Z-1}-E_Z\ge1/(4S)\)；最后用壳层加权换测度（权重在已揭示数据中可测，换律不破坏条件场）得尾部估计 \(\int_{|x|>R}\rho\le C/R\)。亏量给半径下界、尾部给上界，有限个小 \(Z\) 用紧性单独处理，即完成夹逼。

## 可信度与备注

本文是结果族 263 的"地基篇"：它发展的局域化、屏蔽与条件态估计，正是姊妹篇（广义电离能与广义外半径）显式引用的输入，族内三篇互相咬合。半径与电离能的普适双侧界与 Solovej 在 Hartree–Fock 理论中的先例结构一致，是交叉印证。按任务标注本文暂无形式化证明；依 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
