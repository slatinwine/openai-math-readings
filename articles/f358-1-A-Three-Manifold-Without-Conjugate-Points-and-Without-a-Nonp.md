---
layout: default
title: "A Three-Manifold Without Conjugate Points and Without a Nonpositively Curved Metric"
family: "358"
discipline: "Differential geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Three-Manifold Without Conjugate Points and Without a Nonpositively Curved Metric

> 结果族 358：A three-manifold without conjugate points or nonpositive curvature　·　学科：Differential geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论

本文构造出一个闭连通可定向的三维光滑流形：它带有无共轭点（without conjugate points）的黎曼度量，却不存在任何截面曲率非正的度量，对 Ivanov–Kapovitch 的三维存在性问题给出否定回答。

## 问题背景

黎曼度量无共轭点，指任何测地线上都没有在两个不同时刻为零的非零雅可比场（Jacobi field）；截面曲率（sectional curvature）非正必然无共轭点。Gulliver 在 1975 年证明对单个度量反方向不成立——修改负曲率度量可造出正曲率区域而仍无共轭点——但其流形本身仍承认负曲率度量。于是存在性问题悬置：带某个无共轭点度量的闭流形，是否也必带某个非正曲率度量？Ivanov–Kapovitch（2014）与 Burns–Matveev 综述明确提出并特别包含三维。二维答案为正（万有覆盖同胚于 \(\mathbb R^2\)，单值化定理给出平坦或双曲度量），故问题从三维开始；图流形（graph manifold）正是他们指出的核心试验场，且专门问及两块穿孔环面乘积的粘合。

## 主要结果

**主定理**（定理 1.1）：存在闭连通可定向光滑三维流形 \(M\)，其上有 \(C^\infty\) 黎曼度量无共轭点，而 \(M\) 不承认任何截面曲率处处 \(\le 0\) 的 \(C^\infty\) 黎曼度量。

构造：取两份 \(N_i=\Sigma\times S^1\)，\(\Sigma\) 为带一条边界分支的亏格一紧曲面；沿边界环面按 \(h_2=h_1+f_1,\ f_2=h_1\) 粘合（\(h_i\) 为曲面边界，\(f_i\) 为圆因子），粘合矩阵行列式 \(-1\) 反转定向，\(M\) 仍可定向，是 Leeb（1995）"两件图流形阻碍"的实例。

阻碍比定理更强：\(\pi_1(M)\) 在任何非空真 \(\operatorname{CAT}(0)\) 空间上都没有真且余紧的等距作用，故 \(M\) 不承载局部 \(\operatorname{CAT}(0)\) 长度度量；又由 Ivanov–Kapovitch 等价定理（存在无焦点点（without focal points）度量当且仅当存在非正曲率度量），\(M\) 也不存在无焦点点度量。

## 证明思路

正反两半完全独立。先看拓扑阻碍。设 \(\Gamma=\pi_1(M)=G_1*_{\Gamma_T}G_2\) 真余紧等距作用于真 \(\operatorname{CAT}(0)\) 空间；先证每个元素半单，再用平坦环面定理（flat torus theorem）：环面群 \(\Gamma_T\cong\mathbb Z^2\) 的最小集含一张不变欧氏平面，\(\Gamma_T\) 作格平移，记平移向量为 \(\mathbf v(\cdot)\)。关键代数事实：每件中 \(h_i=[a_i,b_i]^{\pm1}\) 是换位子且整块 \(G_i\) 与纤维 \(f_i\) 交换，故中心化子在 \(\operatorname{Min}(f_i)\cong Y_i\times\mathbb R\) 上的轴向平移分量是同态、在换位子上为零，经勾股恒等式推出正交条件 \(\langle\mathbf v(h_i),\mathbf v(f_i)\rangle=0\)。令 \(u=\mathbf v(h_1)\)、\(v=\mathbf v(f_1)\)，粘合关系给出 \(\mathbf v(h_2)=u+v\)、\(\mathbf v(f_2)=u\)，代入得 \(0=\langle u+v,u\rangle=|u|^2\)，与 \(u\) 非零矛盾。

再看度量构造。在两块之间插入颈 \([0,1]\times T^2\)，度量为 \(g=dt^2+dx^{\mathsf T}P(t)^{-1}dx\)，其中余度量（cometric，环面度量之逆）\(P\) 是凹的正定矩阵路径（\(-P''\succeq0\)）：小参数 \(\delta\) 控制导数，大小为 \(\delta^2\) 的剪切在周期取 \(B_1=\delta^2B_2\) 后精确实现整数粘合；两端经凸翘曲领圈光滑接到截断双曲尖点核，开颈之外处处非正曲率。

最后证无共轭点，用 Milnor 的指标形式（index form）框架。守恒动量 \(p=Q\dot x\) 与凹函数 \(F=p^{\mathsf T}Pp\) 使坐标第二变分逐项非负，但与内蕴指标形式相差端点项。测地线对颈的访问分为常高、单调穿越、同边界折返三类，前两类用切向规范变换即可处理；折返通道经规范后，正的边界项控制变分场环向端点改变的一个分量，再与坐标能量经柯西–施瓦茨和二次极小化结合，时间裕度 \(4v_0\le\beta\kappa p_1^2L\)（\(\beta<1\)）使估计对入射角、高度、时长一致，单一 \(\delta\) 即可应付所有测地线。全局组装把原始场的指标积分沿可能无穷次访问可数求和，再由非负性排除共轭点的判据（\(H^1\) 磨光与雅可比场零延拓导出矛盾）收尾。

## 可信度与备注

主结果已 Lean 形式化；Lean 文档（lean/docs/358.md）确认形式化覆盖"无共轭点 + 无非正曲率度量"，断言及于所有测地线与雅可比场，但无焦点与 \(\operatorname{CAT}(0)\) 推论不在其中，该部分宜以社区核验为准。本批结果族仅此一篇，无姊妹篇交叉支撑；拓扑一节与 Leeb（1995）等经典框架直接对照。按 OpenAI 官方声明，未经形式化的结果可能存在问题。

{% endraw %}
