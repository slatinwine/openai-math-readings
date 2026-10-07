---
layout: default
title: "The Critical Spin Field of the Planar XY Model"
family: "216"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Critical Spin Field of the Planar XY Model

> 结果族 216：Critical and near-critical XY scaling and BKT universality　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明临界 XY 模型（边界角度钉零的方盒）的归一化自旋场收敛到刚度 \(K_*=2/\pi\) 的零 Dirichlet 高斯自由场的全方差虚指数 \(V_*\)，且一切混合矩收敛——BKT 理论的临界高斯描述首次在自旋场（而非高度场）层面获得严格证实。

## 问题背景

二维 XY 模型的无质量相被期望由高斯场描述，但自旋是角度的指数函数而非角度本身，高度场的高斯极限并不能直接给出自旋场的极限；在临界点还可能残留一个随尺度变化的标量因子，挡在微观自旋与连续归一化之间。此前严格结果集中于关联界与对偶高度：McBryan–Spencer 上界、Fröhlich–Spencer 低温代数下界、van Engelenburg–Lis 的二分法、Lammers 的自旋–高度关联长度等式、Newman–Wu 的角度梯度高斯极限；姊妹篇在充分低温处理过指数自旋场。临界点处的自旋场极限此前并不存在。

## 主要结果

在质量定义的临界逆温度 \(b_c\)、边界角度全为零的方盒 \(D_n\) 上，定义归一化自旋场 \(S_n=\frac1{n^2}\sum_{x}a_n^{-1}\exp\{\frac{G_n(x,x)-G_n(0,0)}{2K_*}\}e^{i\theta_x}\delta_x\)，\(K_*=\frac2\pi\)，其中 \(a_n=\E^0_n\cos\theta_0\) 是真实中心磁化，\(G_n\) 是未标度的格点 Green 函数。定理：\(S_n\) 沿全序列依律收敛于 \(V_*=\lim_{\epsilon\downarrow0}\exp\{\frac{i\Phi_{D,\epsilon}}{\sqrt{K_*}}+\frac{\E\Phi_{D,\epsilon}^2}{2K_*}\}\)，即零 Dirichlet 高斯自由场（Gaussian free field）\(\Phi_D\) 的全方差虚指数，属虚高斯乘性混沌（imaginary Gaussian multiplicative chaos）理论的对象；收敛在 \(H^{-3}_{\rm loc}((-1,1)^2)\) 中成立，一切混合矩（含非中性矩）与联合律同时收敛。目标场的期望为 \(\int f\)，非对角矩核为 \(\exp\{G_D(z,w)/K_*\}\)，奇性指数恰为 \(1/4\)。归一化只用了 \(a_n\) 与 Green 因子，不假设任何幂律、对数修正或幅度存在；\(K_*=\frac{a(b_c)}{4\pi^2}=\frac2\pi\) 与重整化群预言的重整化刚度一致。

## 证明思路

先建立"磁性扇区"（magnetic sector）语言：Fourier 展开把自旋乘积变成高度配分函数比，每个自旋插入规定绕其位置整绕数的对偶高度。高度极限处理不了一个格距宽的孔（puncture），于是第一步让所有孔保持正宏观半径，证明扇区代价的变分公式（variational formula）：扇区比收敛于 \(\exp\{-\mathcal M(U)/(2a)\}\)，其中 \(\mathcal M(U)=\inf_{g\in H^1(U)}\int_U|dv_0+dg|^2\) 只依赖周期。上界用由流函数构造的无散检验场加分块切割，把倾斜因子化为各方块中心 Laplace 变换之积；下界施加盒平均二次罚项、用分离钉估计比较切块、切缝后套用单值高度极限再还原。

第二步回到微观孔。在每个插入外环绕一列近似圆环，界面上的粘合核是"条件于分离带内全部高度差、恢复被删键"的配分因子；除以其中心零数据值后介于 0 与 1。关键在于不把误差按尺度数目相乘，而是在均值零函数上做收缩论证：任意固定的微观核，无论初始粘合因子多差（只要为正），最终产生的末带密度相对自由环律不超过两倍。再把所有环列接到带正半径孔的外部区域——那里归已证的变分公式管辖；微观部分的贡献对每个单位插入与定义 \(a_n\) 的那个单插入完全相同，取对数相减后精确相消，剩下的是 Green 函数交互，在分离构型上一致收敛。

最后从分离关联走向场律：一个可积的两点界控制碰撞，配合 Lee–Yang 绝对矩不等式 \(\|W\|_{L^p}\le C\sqrt p\,v^{1/2}\) 与自旋矩的非负性，把碰撞区域从每个混合矩中剔除；再由矩确定性与局部 Sobolev 紧性得到 \(H^{-3}_{\rm loc}\) 中的依律收敛。

## 可信度与备注

本文是族内"条件三角"的一角：输入姊妹篇的临界高度系数 \(a(b_c)=8\pi\) 与高度、钉扎极限定理及有限比较引理；同时它只把 \(a_n\) 当作归一化常数使用，不断言其渐近——那正是批内第二篇的定理，二者互相咬合，第二篇给出 \(a_n\asymp n^{-1/8}(\log n)^{1/16}\) 后，本文的归一化便有了明确量级；第一篇再把它平方成两点关联的对数修正。全部结果未形式化；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
