---
layout: default
title: "Schnell fiber spaces and good canonical models"
family: "034"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Schnell fiber spaces and good canonical models

> 结果族 034：Log abundance for compact Kähler spaces under logarithmic Iitaka subadditivity　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了 Schnell 的零 Kodaira 纤维空间定理：当 \(m_0K_X-f^*H\) 伪有效且几何一般纤维 \(\kappa(F)=0\) 时 \(\kappa(X)=\dim Y\)；并由 Schnell 的既有归约导出 Campana–Peternell 不等式 \(\kappa(X)\geq\kappa(D)\) 与一般纤维空间等式 \(\kappa(X)=\kappa(F)+\dim Y\)。

## 问题背景

Campana 与 Peternell 在研究余切丛正性时提出比较式 \(NK_X=A+B\)（\(N\) 为正整数、\(A\) 有效、\(B\) 伪有效）并猜想 \(\kappa(X)\geq\kappa(A)\)；取 \(A=0\) 即"伪有效典范除子应有非零多重典范截面"这一非零截面问题。Schnell 在关于奇异度量与非零截面的研究中系统发展了这一问题族：他证明一般情形可归约到纤维 Kodaira 维数为零的纤维空间，并在底的上典范除子伪有效时证得特例。Kim 用典范丛公式（canonical bundle formula）在附加假设下推进，Zou 则独立证得与本文相同的主定理。本文走第三条路：不做丛公式，而是从全空间的好典范模型（good canonical model）出发，用一次混合交岔计数直接得出下界。

## 主要结果

**定理（Schnell 零 Kodaira 纤维空间结论）**：设 \(f\colon X\to Y\) 是光滑连通射影复簇之间具连通纤维的满射，\(F\) 为光滑几何一般纤维且 \(\kappa(F)=0\)。若底上存在丰富 Cartier 除子 \(H\) 与正整数 \(m_0\) 使 \(m_0K_X-f^*H\) 伪有效（pseudo-effective），则 \(\kappa(X)=\dim Y\)。

丰富比较是本质的：若 \(K_F\) 为挠、取乘积 \(F\times\mathbb P^1\to\mathbb P^1\)，则该类在动曲线 \(\{x\}\times\mathbb P^1\) 上度数为负而不伪有效，且全空间 \(\kappa=-\infty\)；反之 \(F\times Y\to Y\)（\(K_Y\) 丰富）满足数值假设，结论成立。

**推论（Campana–Peternell 不等式）**：光滑连通射影复簇上有效 Cartier 除子 \(D\) 与正整数 \(m_0\) 满足 \(m_0K_X-D\) 伪有效，则 \(\kappa(X)\geq\kappa(D)\)。

**推论（一般纤维空间结论）**：去掉 \(\kappa(F)=0\) 假设、同样数值条件下，\(\kappa(X)=\kappa(F)+\dim Y\)，且存在 \(r,\ell_0\) 使每个 \(\ell\geq\ell_0\) 都有 \(H^0(X,\mathcal O_X(\ell rK_X-f^*H))\neq0\)——扣回原丰富拉回后仍然非零。

## 证明思路

上界是"易加法"（easy addition）：取 \(|mK_X|\) 的一个非零截面组，由 \(\omega_X|_{X_\eta}\simeq\omega_{X_\eta/K}\otimes\ell\) 知基因子在截面比中消去，限制到几何一般纤维上得到 \(|mK_F|\) 的非零子系、像维为零，故每个多重典范像的维数不超过 \(\dim Y\)。

下界是全文核心。数值假设加上 \(f^*H\) 伪有效（丰富除子的倍数有有效代表）推出 \(K_X\) 伪有效，于是调用族内姊妹篇的光滑典范好模型定理：存在 \(K_X\)-负双有理收缩到 \(K_V\) 半丰富的 ℚ-因子 klt 簇 \(V\)，且在光滑公共消解 \(X\xleftarrow{p}W\xrightarrow{q}V\) 上有比较式 \(p^*K_X=q^*K_V+E\)，其中 \(E\geq0\) 且 \(q\)-例外。取整体生成的 \(D=rK_V\) 及其态射 \(g\colon V\to Z\)，记 \(k=\dim Z\)；拉回 \(D\) 的截面再乘以有效 Cartier 除子 \(rE\) 的典范截面，得单射 \(H^0(V,D)\hookrightarrow H^0(X,rK_X)\)，且截面比在 \(E\) 支撑之外不变，故 \(\kappa(X)\geq k\)。

假设 \(k<y=\dim Y\) 导出矛盾：构造混合交岔曲线类 \(C=(q^*D)^k(q^*A)^{d-k-1}\)（\(A\) 为 \(V\) 上极丰富），其因子全部来自 \(V\)。三条性质分别验证：其一，\(C\) 与每个伪有效类配对非负——逐次选取避开前面交岔分支的整体生成成员，得有效零闭链，再由线性性与连续性扩张到闭有效锥；其二，\(C\) 消灭例外除子与 \(q^*D\)——Cartier 投影公式给 \(E\cdot C=q_*E\cdot D^kA^{d-k-1}=0\)，而 \(k+1\) 张一般超平面错过 \(k\) 维像使 \((q^*D)^{k+1}=0\)；其三，\(h^*H\cdot C>0\)——在 \(q\) 局部同构且 \(gq\)、\(h=fp\) 微分满秩的一点，利用 \(y>k\) 提供的一个 \(U\) 外余切方向选出 \(d\) 个横截超平面，再对参数空间做小摄动把局部横截点变成全局真交岔中的单重点。于是 \((m_0p^*K_X-h^*H)\cdot C=-h^*H\cdot C<0\)，与拉回保持伪有效矛盾，故 \(k\geq y\)，两边夹得 \(\kappa(X)=\dim Y\)。

最后推广：好模型输入同时给出典范非零截面（\(K_T\) 伪有效⟹\(\kappa(T)\geq0\)）；配合 Schnell 已发表的归约——每次用 Fujita–Mori 型引理把正 \(\kappa\) 纤维换成基维数严格更大的纤维空间，迭代至零纤维情形调用主定理；再用 Fujita–Mori 判据把截面中的大除子经 \(Y\) 上截面乘法换回原来的丰富 \(H\)，得一般结论。

## 可信度与备注

本文主结果暂无 Lean 形式化证明；依 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。几何部分只依赖经典交岔理论与 Good-model 比较式，论证透明；其成立的关键输入"光滑典范好模型定理"来自族 34 的姊妹篇（该文 Corollary 11.2），两篇构成"数值假设⟹截面结论"的完整链条。Zou 已独立证明同一主定理，形成族外交叉印证。

{% endraw %}
