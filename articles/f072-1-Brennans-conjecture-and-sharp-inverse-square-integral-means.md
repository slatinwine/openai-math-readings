---
layout: default
title: "Brennan's conjecture and sharp inverse-square integral means"
family: "072"
discipline: "Real and complex analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Brennan's conjecture and sharp inverse-square integral means

> 结果族 072：Brennan's conjecture and the integral-means spectrum　·　学科：Real and complex analysis　·　验证状态：主结果已 Lean 形式化

## 一句话结论

证明了 Brennan 1978 年猜想：单连通平面域到单位圆盘的任何共形双射 \(\varphi\) 都使 \(|\varphi'|^s\) 面积可积（\(4/3<s<4\)），并确定 schlicht 类的精确逆平方积分均值指数 \(B_{\mathcal S}(-2)=1\)。

## 问题背景

设 \(\mathbb D\) 为单位圆盘，\(dA\) 为平面 Lebesgue 测度。Brennan 于 1978 年提出：若单连通平面域 \(W\) 到 \(\mathbb D\) 有共形双射 \(\varphi\)，则 \(\int_W|\varphi'(z)|^s\,dA<\infty\) 对一切 \(4/3<s<4\) 成立，且对边界不做任何正则性假设、不要求 \(W\) 有界。该积分衡量共形映射在任意边界附近"压缩面积"的剧烈程度，是单叶函数论（univalent function theory）的核心问题，域形式与积分均值形式的整理见 Bertilsson 1999 年论文。经共形换元，问题等价于对一切单叶盘映射 \(f\) 证明 \(\int_{\mathbb D}|f'|^t\,dA<\infty\)（\(-2<t<2/3\)）：正幂方向用经典增长估计可处理，困难集中在负幂，即导数"非常小"的情形。经典畸变定理（distortion theorem）给出 \(|f'(z)|^{-1}\le C(1-|z|)^{-1}\)，平方后只得径向增长指数 \(2\)，而目标指数是 \(1\)；缺失的正是"极小导数在圆周上出现的频率"这一信息。这一缺口使完整区间悬置四十余年。

## 主要结果

定理分三层。第一层是一致径向估计：对每个 \(\varepsilon>0\) 存在 \(C_\varepsilon<\infty\)，使所有标准化单叶函数（schlicht 类）\(f\in\mathcal S\)（\(f(0)=0\)、\(f'(0)=1\)）满足 \(M_{-2}[f'](r)\le C_\varepsilon(1-r)^{-1-\varepsilon}\)（\(1/2\le r<1\)），其中 \(M_t[f'](r)\) 是 \(|f'|^t\) 的圆周平均。由此得精确谱值 \(B_{\mathcal S}(-2)=1\)，且对一切 \(t\le-2\) 有 \(B_{\mathcal S}(t)=|t|-1\)（保留任意小的正损失）。第二层即 Brennan 猜想本身：凡球面边界至少两点的单连通域 \(W\) 上的共形双射 \(\varphi:W\to\mathbb D\)，都有 \(\int_W|\varphi'|^s\,dA<\infty\)（\(4/3<s<4\)），等价于 \(\int_{\mathbb D}|f'|^t\,dA<\infty\)（\(-2<t<2/3\)）。第三层是端点锐利性：Koebe 函数 \(z/(1-z)^2\) 及其逆映射在 \(s=4\) 与 \(s=4/3\) 两端均使积分发散，开区间无法再扩大。推论还给出 Gol'dshtein–Ukhlov 意义上的齐次 Sobolev 空间拉回有界性。

## 证明思路

证明是围绕一个正算子的反证法。先把盘映射搬至上半平面紧模型：\(\mathcal K\) 由满足 \(F(i)=0\)、\(F'(i)=1\) 的单叶 \(F:\mathbb H\to\mathbb C\) 组成，由 Montel 定理与 Hurwitz 定理知其紧致。对换基点的仿射重归一化 \(T_z\) 定义加权算子 \(A_z\Phi(F)=|Q_F(z)|^2\Phi(T_zF)\)（\(Q_F=1/F'\)），取两个子尺度点的平均得 \(L\)，其 \(n\) 次幂恰是高度 \(2^{-n}\) 的二进网格采样。关键归约是：若范数增长率 \(\rho=\lim\|L^n\|^{1/n}\le2\)，则逐格比较加上四次旋转覆盖整个圆周，把 \(M_{-2}[f'](r)\) 控制在 \(C\|L^n\|\) 之内，一致估计随之成立。于是假设 \(\rho>2\)，记 \(\beta=\log_2\rho>1\)。先用预解式的极大值点造出 \(L\) 的特征概率测度，再对水平平移与对数尺度取平均，得到 \(\mathcal K\) 上满足精确协变律 \(\mathbb E[|Q_F(x+iy)|^2\Phi(T_zF)]=y^{-\beta}\mathbb E\Phi(F)\) 的概率 \(P\)；对常数测试求导，得对数导数 \(q_F=-iyF''/F'\) 在基点的矩 \(\mathbb Ea_F(i)=-\beta/2\)、\(\mathbb E|q_F(i)|^2=\beta(\beta+1)/4\)。再引入辅助光滑映射 \(G_F=F-\frac{iy}{k}F'\)（\(k=(\beta+3)/4\)），其规范化符号 Jacobi \(J_F\) 满足代数恒等式 \(k^2J_F=k(k-1)+(2k-1)a_F+|q_F|^2\)，代入矩得 \(\mathbb EJ_F(i)>0\)，这是"正号"。几何侧给出相反符号：位势 \(V_\xi^F=y^k/|F-\xi|\) 的临界点恰为 \(G_F(z)=\xi\) 的解，\(J_F>0\) 者为鞍点、\(J_F<0\) 者为极大点；逃逸节保证对几乎一切目标正超水平集紧，每个正水平之上只有有限个临界点；对超水平集的 Jordan 边界用 Hopf 切向旋转论证与 Stokes 定理计数梯度指标，得"极大点个数不少于鞍点"。把两类临界点各按 \(V\) 值降序排名并同秩配对，每个鞍点分到一个 \(V\) 值不降的极大点，且该配对 Borel 可测、仿射协变——这两条是与律 \(P\) 积分的前提。最后输运：经 \(G_F\) 换变量，源上的加权积分化为目标侧权重 \((V/k)^4\) 之和，配对只增该权重，故在扩张矩形上正部积分不超过负部积分；取期望后协变律把空间密度变成 \(dx\,dy/y\)，令矩形扩张使两侧盒子因子之比趋于 \(1\)，得 \(\mathbb EJ_F(i)\le0\)，与严格正值矛盾，故 \(\rho\le2\)。收尾用 Hölder 不等式得全部 \(-2<t<0\) 的面积可积性；正幂 \(0<t<2/3\) 用换元后的加权面积估计；Koebe 函数在两端点的扇形内直接算出发散。

## 可信度与备注

主结果已 Lean 形式化：族内配套的 Brennan.lean、BrennanSharp.lean 覆盖可积区间、\(B_{\mathcal S}(-2)=1\) 与 Koebe 端点发散。姊妹篇《A strict inverse-first-power bound for univalent functions》用同一框架（紧模型、二进采样、鞍点—极大点配对）证得 \(B_b(-1)<1/4\)，两文方法论互为印证。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本篇核心结论已形式化，读者仍应以社区核验与 Lean 仓库为最终依据。

{% endraw %}
