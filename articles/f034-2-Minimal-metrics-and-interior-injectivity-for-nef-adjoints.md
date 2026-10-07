---
layout: default
title: "Minimal metrics and interior injectivity for nef adjoints"
family: "034"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Minimal metrics and interior injectivity for nef adjoints

> 结果族 034：Log abundance for compact Kähler spaces under logarithmic Iitaka subadditivity　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
对射影复 klt pair 上 nef 的 \(\mathbb{Q}\)-Cartier 伴随线丛，证明其在任意射影log消解上的极小半正度量处处 Lelong 数为零，回应了 Gongyo–Matsumura 的公开问题；并据此建立普通上同调的 \(H^1\) 内部单射定理，直接导出四维 klt 丰性（带非零欧拉示性数假设）。

## 问题背景
nef 线丛可以有一列曲率趋于半正的光滑度量，其极限度量可能带奇性；问题是：伴随丛 \(K_H+\Theta\) 的典范与边界项能否阻止最奇异半正度量出现对数极点？奇性的度量用 Lelong 数度量——Lelong 数为零意味着局部可积性 \(e^{-t\phi}\) 对一切 \(t>0\) 成立，即乘子理想（multiplier ideal）平凡。Demailly–Peternell–Schneider 在大且 nef 情形构造了极小奇异度量并证明零 Lelong 数；但 nef 本身不够——Koike 给出椭圆曲线上直纹面的例子，极小度量沿除子有正 Lelong 数。Gongyo–Matsumura 在研究单射定理与丰性时明确提出（Question 5.6）：如何在 nef 的 log 典范丛上构造零 Lelong 半正度量？本文在射影 klt 情形给出肯定回答，不需要大性或非消失假设。

## 主要结果
定理一（Theorem 1.1，伴随度量定理）：设 \((H,\Theta)\) 是正规连通射影复 klt pair，\(\Theta\) 有效有理，\(D_H=K_H+\Theta\) 是 nef 的 \(\mathbb{Q}\)-Cartier 除子（不要求 \(K_H\)、\(\Theta\) 分别 \(\mathbb{Q}\)-Cartier）。则对每个射影 log 消解 \(\pi:V\to H\)，有理线丛 \(N=\pi^*D_H\) 上存在极小奇性（minimal singularities）半正度量，且每个这样的度量在 \(V\) 的每点 Lelong 数为零；等价地 \(\mathcal{I}(t\phi)=\mathcal{O}_V\) 对一切 \(t>0\)。
定理二（Theorem 1.2，内部单射定理）：设 \(V\) 光滑射影，\(L\) 整除子，\(0\le C_0\le C_2\) 有效有理且合并支撑为单正规交叉（simple normal crossing）；若 \(L-C_0\) 与 \(L-C_2\) 都带零 Lelong 数的半正度量，则对 \(0<\lambda<1\)、\(C_1=(1-\lambda)C_0+\lambda C_2\)，自然包含诱导单射 \(H^1(V,K_V+L-\lfloor C_1\rfloor)\hookrightarrow H^1(V,K_V+L-\lfloor C_0\rfloor)\)；取 \(E=\lfloor C_1\rfloor-\lfloor C_0\rfloor\)，得限制映射 \(H^0(V,K_V+L_0)\to H^0(E,(K_V+L_0)|_E)\) 的满射性。推论（Corollary 5.1）：射影复 klt 四维簇 \((X,\Delta)\)、nef 有理伴随 \(D\) 且 \(\chi(X,\mathcal{O}_X)\ne0\) 时 \(D\) 半充盈。

## 证明思路
度量定理的核心是"归一化极值截面 + 局部化 \(\bar\partial\) 方程"的矛盾论证。先固定一个从底上充足丛拉回的扭转 \(A=\pi^*A_H\)（\(A_H=(n+1)H_0\)）：由 klt 的 Kawamata–Viehweg 消灭与 Castelnuovo–Mumford 正则性，对使 \(mD_H\) Cartier 的每个 \(m\)，\(mN+A\) 均整体生成——扭转固定不随 \(m\) 增长，是后续一致性的关键。反设极小权 \(\phi\) 在某点 \(p\) 有正 Lelong 数。对每个 \(m\) 用伴随密度 \(Q_m(s)=\int_V|s|^{2/m}e^{-a/m-b}\) 归一化截面（\(a\) 为 \(A\) 的光滑权，\(b\) 为边界 \(B\) 的除子权；klt 系数 \(<1\) 保证 \(e^{-b}\) 可积，负例外系数也不破坏），在 \(Q_m=1\) 的紧集上取在 \(p\) 点赋值最大的极值截面 \(s_m\)。除以 \(m\) 后扭转消失，这些截面有半正的极限权，极小性把该极限控制在 \(\phi\) 之下，于是两者之差的一个固定子水平集上的伴随质量随 \(m\) 趋于零。此时在仿射开集上解局部化 \(\bar\partial\) 方程（完整 Kähler \(L^2\) 理论），得到全纯竞争截面，其加权范数被上述小质量控制，且局部化常数与 \(m\)、开集无关；一个一致的 Hölder 估计使竞争截面的归一化严格小于极值——矛盾。两个技术要点：弱极限固定在加权 Hilbert 空间中取；跨负例外系数的延拓在正规底 \(H\) 上的真实 Cartier 丛中完成后拉回。

单射定理独立于度量定理：正则化两端点度量（曲率损失任意小、固定指数下一致可积），用"端点权之和的对数"使线丛包含成为压缩映射；在交叉除子之外取完整 Kähler 度量做局部 \(L^2\) 解，其全纯差穿越除子延拓并定义普通 Čech 类；在固定有限覆盖上用开映射定理对类为零的形式给出一致原语界，Bochner 比较使调和代表的像变小，而一切近似代表嵌入同一固定 Hilbert 空间，弱收敛保持原上同调类——从加权估计回到凝聚层上同调的单射。

四维应用则把两件已发表准则接到同一度量上：零 Lelong 半正度量满足 Lazić–Peternell 的"广代数奇性"条件（取零除子和），其 Corollary D（需 \(\chi\ne0\)）给出首个截面；再由 Gongyo–Matsumura 的 Corollary 5.3，零 Lelong 度量加 \(\kappa\ge 0\) 给出半充盈。此路线对数值维数无限制，改进了 Liu–Xu 仅处理 \(\nu\le 1\) 的结果。

## 可信度与备注
本篇为族 034 的解析引擎：主结果暂无 Lean 形式化证明。它向姊妹篇《Fourfold nonvanishing…》提供带号代表一般型（signed representative）排除步骤所需的两个解析输入，也与全维数主篇《Log abundance in characteristic zero》的排除与 jet 论证互补。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
