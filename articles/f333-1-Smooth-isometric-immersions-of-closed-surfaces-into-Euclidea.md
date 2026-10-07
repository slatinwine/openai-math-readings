---
layout: default
title: "Smooth isometric immersions of closed surfaces into Euclidean four-space"
family: "333"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Smooth isometric immersions of closed surfaces into Euclidean four-space

> 结果族 333：Smooth isometric immersions of surfaces into ℝ⁴　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文证明：任何闭（紧致、无边）光滑黎曼曲面——包括不可定向曲面、高斯曲率任意的度量——都存在 \(C^\infty\) 等距浸入（isometric immersion）到 \(\mathbb{R}^4\)。这把 Gromov 的闭曲面 \(\mathbb{R}^5\) 定理压低一维，解决了四维等距浸入问题的闭曲面情形。

## 问题背景

给定黎曼曲面 \((M,g)\)，等距浸入是保持内积的光滑映射 \(F:M\to\mathbb{R}^4\)，即 \(\langle dF(v),dF(w)\rangle=g(v,w)\)。解析理论早已完备：Janet–Cartan 定理（1926–27）把实解析曲面局部实现于 \(\mathbb{R}^3\)；但光滑情形连局部结论都不成立——本文引用的姊妹篇构造了 \((-1,1)^2\) 上的光滑度量，原点附近不容许到 \(\mathbb{R}^3\) 的光滑等距浸入。Nash 1956 年的嵌入定理对曲面需要 17 维，Gromov 把闭曲面做到 \(\mathbb{R}^5\)；四维问题由 Gromov 记录并归于 Chern（约 1950 年）。平面区域上的四维结果（Poznyak 1973 等）要求圆盘型区域，无法搬到闭曲面。困难在于：余维只剩 2 时法向自由度极小，而闭曲面（尤其不可定向）上的修正必须全局兼容。

## 主要结果

主定理（Theorem 1.1）：每个闭光滑黎曼曲面 \((M,g)\) 都容许 \(C^\infty\) 等距浸入到 \((\mathbb{R}^4,\delta_4)\)。不假设 \(M\) 可定向或连通，对高斯曲率与拓扑无限制；结论是浸入（immersion）而非嵌入，允许自相交。证明的核心是"本原添加"（primitive addition）命题：在保持边界几何条件的前提下，把度量为 \(\gamma(F)\) 的浸入改成 \(\gamma(F)+a^2\,dx^2\)，其中 \(a^2dx^2\) 是支在坐标圆盘内的正秩一张量。

## 证明思路

先做全局准备。由 Whitney 浸入定理经磨光与球极逆投影得 \(S^3\) 中的浸入，缩小成小球面 \(F^0\)，使亏值 \(h=g-\gamma^0\) 正定，负径向 \(n^0\) 则是全局单位法向——不可定向曲面因此也能处理：只传播这一个"优选法向"（preferred normal），无需整体法标架。再用三组夹角 \(0,\pi/3,2\pi/3\) 的余向量把 \(h\) 分解为有限个秩一张量 \(a_j^2\,dx_j^2\)，支在圆盘 \(D_j\) 内；相位取凸函数 \(x_r=\ell_r\cdot u+\tfrac12 L|u|^2\)，对"刚要加入它之前"的度量有正横向 Hessian（transverse Hessian）。关键在次序：先固定修改族的 \(C^2\) 界，再用 Sard 定理选圆盘半径与相位线性部分，使边界两两横截、无三重点；再在交叉点把 \(S^3\) 内的第二基本形式（second fundamental form）清零，Gauss 方程随即给出 \(Q_{il}>0\)。

再做单步添加：在垂直于 \(F_y\)、\(F_{yy}\) 的平面内构造周期速度环（velocity loop），平均位移为零、首阶度量恰好加上 \(a^2dx^2\)；对 \(F_{yy}\) 正交消去首个横向误差，转弯处取大横向导数防法向退化。

然后是两个解析装置。小增量定理：在横向第二基本形式 \(B_{yy}\neq0\) 的"好相位"方向，对共轭线性化方程逐模求解至有限精度，选自由法向振幅使二次均值为预定张量（有限次代数替换），再消去振荡二次模，位移在 \(C^2\) 中仅 \(O(\delta\tau)\)。精确修正定理：Nash–Moser 式迭代，但每步只磨光数据、把增量加到未磨光的映射上；恒等式 \(\delta'^2(H'-h_*)=\delta^2(H-H_s)-E-\mathcal{C}(G-G_s,U)\) 使高阶导数只线性进入新亏值，无需线性化度量映射的全局逆。按块推进精度阶、有限步后升阶，最终在所有 \(C^m\) 中收敛到度量恰为 \(h_*\) 的光滑浸入；全局添加有限次，每次内部是这个无穷磨光迭代。

最后，边界条件（\(A_i\neq0\)、与 \(n\) 内积为正、双向 \(Q_{il}>0\)）经大振荡后仍被保持，优选法向经局部调整延拓，对有限列表归纳即得 \((F^K)^*\delta_4=g\)。

## 可信度与备注

本文是 OpenAI 批量产出的手稿之一，主结果暂无 Lean 形式化证明，按官方声明"未经形式化的结果可能有问题"，请以社区核验为准。姊妹篇的局部 \(\mathbb{R}^3\) 障碍说明光滑度量局部未必能进 \(\mathbb{R}^3\)，与本文合起来把闭曲面问题的答案钉在四维。证明沿 Nash–Gromov 振荡修正传统展开，新贡献在于模式方程的有限求解方案与法向几何在余维二中的传播；速度环的实现与几何保持两节技术性较强，此处从略。

{% endraw %}
