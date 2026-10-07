---
layout: default
title: "Subpolynomial query complexity for well-conditioned log-concave sampling"
family: "139"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Subpolynomial query complexity for well-conditioned log-concave sampling

> 结果族 139：Subpolynomial query complexity for log-concave sampling　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 一句话结论

对 Hessian 介于 \(I\) 与 \(2I\)、极小值点已知的对数凹位势，本文证明任意固定 \(\varepsilon>0\) 下只需 \(C_\varepsilon d^\varepsilon\) 次精确一阶查询即可把 Gibbs 分布采样到总变差 \(1/10\)，并配 \(\Omega(\log d)\) 下界，确定该预言机模型的最优维度幂指数为零。

## 问题背景

对数凹采样（log-concave sampling）问：要从 Gibbs 分布 \(\pi_V(dx)\propto e^{-V(x)}dx\) 取样，需要查询多少次位势信息？主流做法是对 Langevin 动力学作离散化，但离散化误差随维度增长。即便位势一致强凸且光滑（\(I_d\preceq\nabla^2V\preceq2I_d\)，条件数与精度都固定），此前最好的保证也是 \(\widetilde O(d^{1/3})\) 次查询（Altschuler 的移位复合分析、Chen 等的路径空间拒绝采样），以及期望意义下的 \(\widetilde O(d^{1/6})\) 与 \(\widetilde O(d^{1/5})\)（Picard 平滑与高斯云方法）。于是问题变得尖锐：维度的正幂究竟是本质代价，还是特定算法的痕迹？本文在精确一阶预言机（exact first-order oracle）模型中彻底回答了这一问题：查询返回 \((V(x),\nabla V(x))\)，允许自适应与随机性，查询之间的计算不受任何限制，且查询预算须在每次执行中一致成立——在此模型下，正幂并非本质，最优指数为零。

## 主要结果

记 \(Q(d)\) 为满足如下要求的最坏查询数：对类 \(\mathcal V_d\) 中每个 \(C^2\) 位势 \(V\)（\(V(0)=0\)、\(\nabla V(0)=0\)、\(I_d\preceq\nabla^2V\preceq2I_d\)，即极小值点已知）都输出与 \(\pi_V\) 总变差（total variation）距离至多 \(1/10\) 的样本。主定理（Theorem 1.1）断言：对每个固定 \(\varepsilon>0\) 存在常数 \(C_\varepsilon\)，使 \(Q(d)\le C_\varepsilon d^\varepsilon\) 对一切 \(d\ge2\) 成立；同时存在绝对常数 \(c>0\) 使 \(Q(d)\ge c\log d\)，且该下界即使只限于高斯位势 \(V(x)=x^TAx/2\)（\(I\preceq A\preceq2I\)）也对任意随机化自适应算法成立。两者合并，最优维度指数 \(\gamma_*=\limsup_{d\to\infty}\log Q(d)/\log d\) 恰为零。须注意：上界并非 polylog 级，常数与逼近阶依赖 \(\varepsilon\)；论文只计查询数，不对查询之间的实数计算施加任何复杂性或比特精度约束。

## 证明思路

上界先化归为一个"近二次"原语（Theorem 2.1）：对 \(X\sim\pi_V\) 施加小高斯扰动后取条件律，得到 \(\nu_{x,r}(dz)\propto e^{-|z|^2/2-F(x+rz)}dz\)，其中 \(\Lip(\nabla F)\le\delta=d^{-e}\) 极小，而求一次 \(\nabla F\) 恰好消耗一次原梯度查询；原语用 \(\polylog(d)\delta^{-t}\) 次查询输出"目标样本加一份独立高斯"。其内部有两个理想构件：一是高斯输运 \(Y_\rho=\rho Z+\sqrt{1-\rho^2}N\)（概率流／随机插值观点），其速度场又是一个条件梯度均值，问题呈自相似结构；二是平稳配流（skew 矩阵动力学）把条件均值表示成路径积分加初始动量，精确等于 \(u+sG\)。高阶导数用全分裂（all-split）张量范数逐阶控制（基于 Appell 多项式与高阶 Poincaré 不等式），每升一阶只损失 polylog 因子，\(\sqrt d\) 只在最终向量输出时付一次。真正的难点是嵌套条件均值的中心本身随机：编译器一节为每个例程建立逐点平移恒等式——中心平移 \(\Delta\) 可由种子平移 \(v\otimes\Delta/r\) 精确补偿，所有物理查询保持不变；再对种子做确定性协方差缩减，把中心处的高斯噪声原样吸收，使"噪声中心上的调用"恰为"固定中心的正确分布"（引理 7.1）。标签对 \((b,p)\) 与两种深度（表达式依赖深度、例程调用高度）保证递归有限且查询上限在每次执行中成立。最后回到原目标：先跑收缩的近端链（每步 \(W_2\) 收缩 \(1/(1+h)\)，共 \(O(h^{-1}\log d)\) 步）逼近加噪目标；再做 \(O(\log d)\) 层方差减半的条件下降（恒等式 \(Z=Y/2+Z_{\rm new}/\sqrt2\)），把条件律化为近似高斯；以模式（mode）为中心的高斯加 \(O(\log d)\) 次不动点迭代收尾；有限个小维度用拒绝采样兜底。总查询为 \(\polylog(d)\delta^{-(1+t)}=d^{e(1+t)+o(1)}\)，取 \(2e<\varepsilon\)、\(t<1\) 即得 \(d^\varepsilon\)。下界只看高斯：先以延迟揭示的 Haar 旋转把任意算法输出压入块 Krylov（block-Krylov）张成；再取谱 \(\lambda_k=(3+\cos\theta_k)/2\) 与余弦统计量 \(\cos(n\theta_k)\)（\(n=2q+1\) 超过多项式次数的两倍），用离散余弦正交性证明该二次型在整个随机张成上一致地小；而目标高斯下同一统计量的均值为 \((d/\sqrt2)(-\varrho)^n\)（\(\varrho=3-\sqrt8\) 的几何级数恒等式），当 \(q\le c\log d\) 时远超阈值，Chebyshev 不等式分离两个联合实验，故查询太少必失败。

## 可信度与备注

主结果（Theorem 1.1 的上、下界）已有 Lean 形式化证明（族内文档 lean/docs/139.md）；按 OpenAI 官方声明，未经形式化的结果可能有问题，正文其余构造性细节（张量估计、编译器例程等）仍以社区核验为准。上、下界在同一文中互相补足：上界说明 \(d^\varepsilon\) 可达，下界说明连 \(\log d\) 都不可省，合并才得到"指数为零"的完整刻画。本文面向预言机复杂度而非实际运行时间，常数随 \(\varepsilon\) 趋小而恶化，引用时须留意这一适用范围。

{% endraw %}
