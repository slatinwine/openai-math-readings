---
layout: default
title: "A nonspectrahedral hyperbolicity cone"
family: "095"
discipline: "Convex and metric geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A nonspectrahedral hyperbolicity cone

> 结果族 095：Hyperbolicity cones without semidefinite lifts　·　学科：Convex and metric geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论

构造了 23 个实变量、16 次的显式齐次双曲多项式，其闭双曲锥不能写成任何有限实对称线性矩阵不等式，从而推翻几何版广义 Lax 猜想。

## 问题背景

1958 年 Lax 提出：三变量的双曲多项式是否都有对称行列式表示？Helton–Vinnikov 定理与 Lewis–Parrilo–Ramana 的等价性给出肯定答案，因此三元双曲锥都是谱面（spectrahedron）。高维情形，广义 Lax 猜想断言每个齐次双曲多项式的闭双曲锥（hyperbolicity cone）——Gårding 证明其为凸——都能由有限线性矩阵不等式 \(L(x)\succeq0\) 定义。由于双曲锥在凸优化中扮演超越半定规划的角色，这一表示问题直接关系到"双曲规划能否归约为半定规划"。此前的相关反例停留在多项式层面：某个多项式没有行列式表示，并不能排除同一个锥被另一个多项式或另一支铅笔表示。卡点在于：必须对任意有限矩阵尺寸、任意实系数的铅笔，从锥自身的几何中提炼出刚性矛盾。

## 主要结果

定理 1.1：设 \(Q(y)\) 为由系数一的 Choi–Lam 双二次型（Choi–Lam biquadratic form）\(b(z,y)=z^\top Q(y)z\) 决定的 \(3\times3\) 矩阵，\(\Phi_y\) 为由它诱导的 \(\Sym^4\) 上的线性映射，则
\[p(X,Z,y)=\det\big((\det X)Z-\Phi_y(\operatorname{adj}X)\big),\qquad (X,Z,y)\in\Sym^4\times\Sym^4\times\R^3\]
是 20 次齐次多项式，关于 \(e=(I_4,I_4,0)\) 双曲且 \(p(e)=1\)；其闭双曲锥 \(K=\Lambda_+(p,e)\) 不是谱面：对任意有限 \(N\) 与任意实线性映射 \(L:\Sym^4\times\Sym^4\times\R^3\to\Sym^N\)，都有 \(K\ne\{(X,Z,y):L(X,Z,y)\succeq0\}\)。推论 1.2：商 \(q=p/\det X\) 可延拓为同样 23 个变量的 16 次齐次双曲多项式且锥不变，故得到 16 次反例。作者不声称维数或次数极小；实对称框架也已覆盖 Hermitian 铅笔。

## 证明思路

整条证明链围绕一个标量刚性展开：Choi–Lam 型 \(b\) 非负非零，却具有弱极端性（weak extremality）——任何满足 \(\ell(z,y)^2\le b(z,y)\) 的双线性型 \(\ell\) 必须恒为零。作者先给出短证明：\(b\) 的零点直接消去 \(\ell\) 的非对角系数，再沿使 \(b\) 以四阶速度消失的曲线消去对角系数。

先证多项式性质良好。对秩一矩阵有恒等式 \(u^\top\Phi_y(vv^\top)u=b(v_0u'-u_0v',y)\ge0\)，故 \(\Phi_y\) 是保持半正定的正线性映射（positive linear map）。双曲性用上半平面论证：取 \(t=a+i\eta\)，\((tI_4-X)^{-1}\) 的虚部负定，经 \(\Phi_y\) 的正性传导后目标矩阵虚部正定从而可逆，故 \(p(te-(X,Z,y))\) 无复根。随之算出两个切片：\(X\succ0\) 时属于 \(K\) 当且仅当 \(Z\succeq\Phi_y(X^{-1})\)；\(y=0\) 时当且仅当 \(X\succeq0\) 且 \(Z\succeq0\)。

再压榨假设的铅笔。设 \(K\) 有表示 \(L=L_1(X)+L_2(Z)+L_3(y)\)。先除去公共核并把 \(L(e)\) 归一化为严格正定；\(y=0\) 切片迫使 \(L_1,L_2\) 是正映射，分块后得到单态（unital）正映射 \(D:\Sym^4\to\Sym^a\)、\(E:\Sym^4\to\Sym^c\) 与线性映射 \(B:\R^3\to\R^{a\times c}\)。关键一步是重标度：由 \(\Phi_{sy}=s^2\Phi_y\)，整条点列 \((I_4,s^2Z_0,sy)\) 落在 \(K\) 内；用 \(\diag(I_a,s^{-1}I_c)\) 做同余变换并令 \(s\to0\)，可得 \(G(y)=0\)，且块矩阵 \(\begin{pmatrix}D(X)&B(y)\\B(y)^\top&E(Z)\end{pmatrix}\succeq0\) 与 \(Z\succeq\Phi_y(X^{-1})\) 等价，取 Schur 补即 \(E(Z)\succeq B(y)^\top D(X)^{-1}B(y)\)。

然后取秩一极限。令 \(X_t=vv^\top+t(I-vv^\top)\)、\(Z_t=uu^\top+t(I-uu^\top)\) 趋于秩一投影，把两个等价条件分别化成闭射线的阈值，对齐得 \(\lambda_{\max}(A_t)=\|C_t\|_{\op}^2\)；令 \(t\to\infty\)，\(D(X_t)^{-1/2}\) 收敛到 \(D(I-vv^\top)\) 核上的投影 \(P(v)\)，\(E\) 侧同理得 \(R(u)\)，于是出现精确的范数恒等式
\[b(v_0u'-u_0v',y)=\big\|P(v)B(y)R(u)\big\|_{\op}^2\]
——Choi–Lam 型从锥的几何中原样浮现。

最后一步切向微分。核投影 \(R(u)\) 在秩最大的开集上光滑；在基点 \(u=v\) 处左边为零，强迫 \(P(v)B(y)R(v)=0\)。沿球面路径 \(u_s=(v+sh)/\sqrt{1+s^2\|h\|^2}\) 求导，左边变成 \(b(Jh,y)\)，右边变成 \(\|P(v)B(y)\,dR_v(h)\|_{\op}^2\)，其中 \(J:v^\perp\to\R^3\) 是同构。于是矩阵 \(F(z,y)=P(v)B(y)dR_v(J^{-1}z)\) 的每个元素都是双线性型，且其平方不超过 \(\|F\|_{\op}^2=b(z,y)\)；由弱极端性这些元素全部为零，从而 \(b\) 恒为零，与 \(b(e_1,e_1)=1\) 矛盾。

## 可信度与备注

本文主结果已有 Lean 形式化证明（见结果族 095 的 Lean 文档），是同族三篇中验证最扎实的一环。姊妹稿关系密切：本文只排除原坐标下的铅笔表示；十月初的姊妹篇进一步证明这同一个锥其实拥有 \(100\times100\)、含 307 个辅助变量的精确半定提升，即它是谱面影子而非谱面；而族内另一篇高维构造则说明确有双曲锥连影子都不是。三者合起来把 Lax 猜想的各个层级逐一切断。按 OpenAI 官方声明，未经形式化的结果可能有问题——本文主结果不在其列。

{% endraw %}
