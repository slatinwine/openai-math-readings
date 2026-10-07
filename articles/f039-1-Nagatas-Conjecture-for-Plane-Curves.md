---
layout: default
title: "Nagata's Conjecture for Plane Curves"
family: "039"
discipline: "Algebraic and complex geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Nagata's Conjecture for Plane Curves

> 结果族 039：Nagata's conjecture and maximal Seshadri constants　·　学科：Algebraic and complex geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论
证明了 \(r\ge 10\) 个非常一般复点上，任何带任意重数 \(m_i\) 的非零有效平面曲线必满足 \(\sum_i m_i\lt d\sqrt r\)，以严格、非齐次的形式完全确立 Nagata 猜想，并给出爆炸曲面上多点 Seshadri 常数的精确值 \(1/\sqrt r\)。

## 问题背景
过多点作平面曲线是经典插值问题：给定点的位置与所需消失阶，曲线次数 \(d\) 最小能有多小？Nagata 在研究希尔伯特第十四问题（Hilbert's fourteenth problem）时于 1959 年提出该猜想，并证明了点数为平方数（至少 16）的情形。维数计数给出临界尺度：\(d\) 次型有 \(\binom{d+2}{2}\) 个系数，\(r\) 个点上阶 \(\ge m\) 至多施加 \(r\binom{m+1}{2}\) 个线性条件，首项恰在 \(d=m\sqrt r\) 处平衡。条件计数只能保证该尺度之上曲线存在；要证明之下不存在，必须对所有 \(m\) 一致地控制条件之间的线性相关，这正是难点。此外 \(r=9\) 时非零三次曲线总存在，严格不等式不可能从 9 开始。此前最好结果如 Roé 的 \(d\gt m(\sqrt{r-1}-\pi/8)\)（\(r\ge 10\)）与十点情形的 \(d/m\ge 117/37\)，均未触及 \(\sqrt r\) 本身。

## 主要结果
主定理：对每个整数 \(r\ge 10\)，存在配置空间 \(U_r\) 中可数个真 Zariski 闭子集之并 \(E_r\)（余集非空），使得对 \(E_r\) 之外的任意点组 \((p_1,\ldots,p_r)\)：若非零有效平面曲线（effective plane curve，即某个 \(d\ge 1\) 次齐次形式的零除子，允许可约与非约化）满足 \(\mathrm{mult}_{p_i}C\ge m_i\)，则必有 \(d\sqrt r\gt\sum_{i=1}^r m_i\)。重数向量完全任意（非齐次形式），且同一点组对所有次数与重数向量一致成立。推论：结论经 \(\mathbb Q\) 上定义的关联轨迹延伸到任意不可数、特征为零的代数闭域；在 \(r\) 点爆炸（blow-up）曲面上，除子类 \(\sqrt r\,H-\sum_i E_i\) 严格 nef 且自交为零，故多点 Seshadri 常数（multipoint Seshadri constant）\(\varepsilon(\mathcal O(1);p_1,\ldots,p_r)=1/\sqrt r\)。

## 证明思路
先做归约：若某非常一般点组出现违约曲线，则由关联轨迹的闭性与有理定义性，相应线性系统在每个点组都有非零解（普适系统 \(\mathsf U_r(d,m)\)）；再用 Nagata 的循环乘积技巧——对重数向量取 \(r\) 次循环置换、各取一条曲线相乘——得到等重数系统，次数 \(d=rd_0\)、公共重数 \(m=\sum_i m_i\)，且 \(d/m\le\sqrt r\)，还可取任意公倍数放大。于是只需排除一切 \(d/m\le\sqrt r\) 的普适系统。

再把曲线化为法丛上的多项式：让点沿切向逼近一条 \(k\) 次光滑曲线 \(B\)，重标度法向坐标后取极限，得到法丛全空间 \(\mathrm{Tot}(M)\) 上的多项式 \(F(w)=\sum_j f_j w^j\)，系数 \(f_j\in H^0(B,L^{d-kj})\)，在任意指定的法向位移处仍消失到阶 \(\ge m\)。平方情形 \(r=k^2\) 由此直接排除：选取使 \(A=M(-P)\) 非挠的点组（正 genus 曲线上挠线丛仅可数个，故可选）以及落在赋值像之外的位移，最高次项的度数计数与 \(w^{m-1}\) 系数比较均导出矛盾。

非平方情形改用三次曲线：九个点取零法向位移，迫使前 \(m+1\) 个系数落入同一度数 \(h=3(d-3m)\) 的截面空间 \(H^0(B,T\otimes A^{m-j})\)；先用类似计数证明 \(d\gt 3m\)。剩余 \(q=r-9\) 个点沿水平线碰撞，\(b\) 次纤维求导后基座阶至少 \(q(m-b)\)，故某个有限维 jet 映射 \(J_\tau\) 必有非平凡核。随后让三次曲线退化为 \(X_\tau=\mathbb C^*/\tau^{\mathbb Z}\)，乘性 theta 函数（multiplicative theta function）的剩余类 Laurent 基给出显式坐标，其归一化表达式在对数坐标 \((x,y)\) 下趋于 \(e^{Kx+jy}\)（\(K\) 为 Laurent 指数、\(j\) 为纤维次数），混合导数给出极限矩阵 \((K^\ell j^b)\)，其中 \(0\le b\lt m\)、\(0\le\ell\lt q(m-b)\)，列由指数对 \((j,K)\) 标号。

最后用插值排除核：单纯的总数计数不够，关键在按固定 \(K\) 的水平行分组——只要每行点数 \(\le m\)，且点数 \(\ge t\) 的行数 \(\le q(m-t+1)\)，单项式张成的空间 \(\mathrm{span}\{K^\ell J^b\}\) 便能插值指数集上的任意函数，矩阵满列秩。指数对恰含于一个多边形 \(\mathcal D_\lambda\)，其水平切片宽度轮廓恰好提供这两条界；由于 \(d/m\) 有理而 \(\sqrt r\) 无理，严格间隙 \(d/m\lt\sqrt r\) 允许取收缩参数 \(\lambda\lt 1\)，并取 \((d,m)\) 的公倍数吸收取整端点误差。满秩对充分小的正 \(\tau\) 保持，与每个固定曲线上 \(J_\tau\) 有核矛盾，定理得证。

## 可信度与备注
本文主结果已由 Lean 形式化证明。它是结果族 039 的基石：曲面姊妹篇明确把 \(r\ge 10\) 的严格阈值与严格非齐次不等式引用为本文的独立精细化，高维篇则沿用同一套机制；本文得到的 \(\varepsilon=1/\sqrt r\) 正是族概述中极大 Seshadri 常数断言的平面原型。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文已形式化，可信度较高。

{% endraw %}
