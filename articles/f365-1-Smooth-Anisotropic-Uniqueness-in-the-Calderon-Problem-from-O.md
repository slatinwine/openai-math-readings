---
layout: default
title: "Smooth anisotropic uniqueness in the Calderón problem from one boundary patch"
family: "365"
discipline: "Partial differential equations"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Smooth anisotropic uniqueness in the Calderón problem from one boundary patch

> 结果族 365：Joint metric and connection recovery from one boundary patch　·　学科：Partial differential equations　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
解决了光滑各向异性 Calderón 问题的"同补丁"唯一性：\(n\ge3\) 时，仅在一个任意边界开补丁上同时做输入与观测的零频率能量测量，光滑黎曼度量就被确定至只差一个在该补丁上恒等的微分同胚；固定欧氏区域上的标量电导率则被完全唯一确定。

## 问题背景
Calderón 1980 年提出逆电导率问题：边界的电流—电压响应能否确定内部系数？几何（各向异性）版本把未知量换成黎曼度量，保持边界的微分同胚成为不可避免的歧义。Sylvester–Uhlmann 用复几何光学解证明光滑标量全边界唯一性；Lee–Uhlmann、Lassas–Uhlmann 的几何恢复限于实解析范畴；KSU 等部分数据结果要求输入与观测分居由凸包几何决定的两个不同区域。对任意光滑度量、且输入与观测限制在同一任意补丁的情形，光滑唯一性长期悬而未决——本文给出肯定回答，且不需要背景度量、解析性或叶化假设。

## 主要结果
设 \(M\) 为紧连通光滑 \(n\) 维流形（\(n\ge 3\)，带边界），\(\Gamma\subset\partial M\) 非空真相对开。对 \(f\) 支于 \(\Gamma\)，令 \(u_f^g\) 为 \(-\Delta_gu=0\)、边值为 \(f\) 的解；局部能量 DN 映射（Dirichlet-to-Neumann map）定义为
\(\langle\Lambda_{g,\Gamma}f,h\rangle=\int_M\langle du_f^g,du_h^g\rangle_g\,dV_g\)。
**定理**：若 \(\Lambda_{g_1,\Gamma}=\Lambda_{g_2,\Gamma}\)，则存在光滑微分同胚 \(\Phi:M\to M\) 使 \(\Phi|_\Gamma=\Id\) 且 \(g_2=\Phi^*g_1\)；反向的不变性平凡成立，故这是全部歧义。推论一：全边界数据下可取 \(\Phi\) 逐点固定整个边界。推论二（标量推论，scalar corollary）：欧氏区域 \(\Omega\) 上两个严格正的 \(\gamma_1,\gamma_2\in C^\infty(\overline\Omega)\)，若对每个 \(f\in C_c^\infty(\Gamma)\) 有 \(\gamma_1\partial_\nu u_f^{\gamma_1}=\gamma_2\partial_\nu u_f^{\gamma_2}\) 于 \(\Gamma\)，则 \(\gamma_1=\gamma_2\) 于 \(\overline\Omega\)——不假设不可及边界上的电导率值。

## 证明思路
先由能量型相等恢复边界射流：能量型是密度取值的算子，主符号 \(\sqrt{\det h}\,\rho\) 先定出边界度量与密度；对 DN 算子的光滑符号分解做 Lee–Uhlmann 型递归，每一层新出现的法向射流经极化论证必为零，归纳得两组度量在 \(\Gamma\) 上全部泰勒射流相等。再借射流相等在补丁内侧粘出公共外帽区域 \(E\)，能量极小化的变分比较证明两组格林核（Green kernel）在 \(E\) 上逐点相等；\(E\) 中源产生的调和函数的取值分离内点、其二阶芽（jet）恰好张成方程允许的超平面（点分布对偶加唯一延拓），由此获得调和坐标（harmonic coordinates）与有限的成对调和函数族。核心是局部度量延拓定理：若两图表中度量、格林核与该函数族在一张光滑超曲面一侧相等，则相等可穿过超曲面。其证明分三步：先在乘积空间延拓"混合格林核"（两变量分别满足两个度量的方程）；它在以 \(y\) 为中心的小球面上的通量定义转移泛函 \(T_y\)，精确再现常数与坐标：\(T_y1=1\)、\(T_yx^i=y^i\)。暂时假设规范化后的逆度量差连同有限阶导数小于球半径 \(r\) 的 \(\varepsilon\) 倍；在此条件下构造转移表示密度并在固定中心集上一致 \(L^2\) 有界——这要比较球面调和的升次与降次算子得到带权强制性估计（张量断层成像框架），且移动几何带来的二阶项不能当低阶误差丢弃，需第二次比较纳入控制。常数与坐标的再现恰好消去调和函数的仿射泰勒多项式，余项 \(O(r^2)\) 给出成对差 \(V\) 的 \(\|V/r^2\|_{L^2}\) 界；有限阶插值把所需导数提升到 \(Cr^{3/2}\)，张成的调和黑塞矩阵进而把度量差本身也压到 \(Cr^{3/2}\)——严格优于临时假设。参数顺序精心编排：固定几何与调和族、正则指数、\(\varepsilon\)、阈值，然后一次空间伸缩固定，再让收缩参数 \(\delta\downarrow0\)；连通性论证使收缩贯通 \((0,1]\)，半径趋于零迫使规范化逆度量相等，两度量仅差共形因子；把共形拉普拉斯公式作用于全部公共调和坐标且 \(n\ge3\)（\(n-2\ne0\)），逼出该因子为常数、在已知侧为零。最后源取值使匹配单值且内点不能逃向边界，极大匹配区无内部边界并光滑延拓过边界，支于补丁的边界数据逼出 \(\Phi|_\Gamma=\Id\)。标量推论经换算 \(g=\gamma^{2/(n-2)}e\) 化为几何定理（此时 \(\sqrt{\det g}\,g^{ab}=\gamma\delta^{ab}\)），再用"固定边界补丁的共形自微分同胚必为恒等"的刘维尔型刚性引理（沿多边形路径的 ODE 唯一性）消去坐标歧义。

## 可信度与备注
本文主结果暂无形式化证明。它与同族的联络篇共用边界射流、外帽与格林核机制，并为后者提供乘积延拓、球面几何与角向估计的标量原型；与有界可测非唯一性篇形成对照——光滑范畴一个补丁即够，可测范畴三维全边界仍可不唯一。据 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。

{% endraw %}
