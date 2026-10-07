---
layout: default
title: "Power-law violations of Yau's nodal upper bound"
family: "350"
discipline: "Differential geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Power-law violations of Yau's nodal upper bound

> 结果族 350：Yau's nodal bounds: surfaces and higher dimensions　·　学科：Differential geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论
论文在 \(S^4\times S^1\) 上构造出一个光滑黎曼度量及固定 \(\epsilon_0>0\)，使精确特征函数序列的节点四维体积增长快于 \(\lambda^{1/2+\epsilon_0}\)——不仅推翻 Yau 节点上界猜想的光滑版本，连"允许任意小幂损失"的放宽上界也一并否定。

## 问题背景
Yau 1982 年的节点集猜想预测光滑闭流形上 \(\mathcal H^{n-1}(Z(u))\) 被 \(\sqrt\lambda\) 双侧控制。解析情形由 Donnelly–Fefferman 证明；光滑情形 Logunov 证得锐下界与维度相关的多项式上界，Hezari 在 Gevrey 类与指定拟解析类中得到更强的上界，但都不覆盖任意光滑度量。此前的一个自然问题是：光滑上界也许只是失去某个任意小的幂？本文给出否定回答：存在固定度量，其节点测度除以 \(\lambda^{1/2+\epsilon}\)（对某个固定 \(\epsilon_0>0\) 内的 \(\epsilon\)）仍发散。族内姊妹篇已在三、四维给出 \(\mathcal H/\sqrt\lambda\to\infty\) 的定性反例但未宣称幂律超出，本文把违反升级为固定指数级。

## 主要结果
主定理：存在 \(S^4\times S^1\) 上的光滑黎曼度量 \(g\)、固定常数 \(\epsilon_0>0\)，以及实光滑特征函数 \(u_j\)（\(-\Delta_g u_j=\lambda_j u_j\)，\(\lambda_j\to\infty\)）使得
\[\frac{\mathcal H_g^4(Z(u_j))}{\lambda_j^{1/2+\epsilon_0}}\longrightarrow\infty.\]
推论：与任意固定闭流形做乘积，同样的幂律违反在一切 \(n>5\) 维成立。论文对三、四维不作断言（那是姊妹篇的定性结论）。

## 证明思路
证明先在四维球面 \(B=S^4\) 上操作"正对"（positive pair）：可独立变化的正定对称逆度量张量 \(A\) 与密度 \(\rho\)，定义加权算子 \(Lf=\rho^{-1}\operatorname{div}_\mu(A\,df)\)；化为普通度量留到最后。核心是"量化单步构造"命题：在圆对 \((g_0^{-1},1)\) 的固定 \(C^1\) 邻域内，每一步都能以任意小的有限范数改动，产出一个以 \(k^2\) 为简单特征值、且带尺寸 \(\ge ck^{1+\gamma}\) 符号证书的精确特征函数，其中指数 \(\gamma>0\) 对所有阶段统一。

第一步做包络的幂律放大。在固定坐标区域内以固定尺度比对对数轮廓反复"波纹化"（corrugation）：每一代中为下一代准备好的子立方体贡献的新梯度积分超过整个旧父立方体的总量，形成每代固定倍数的乘法增益；取 \(\log k\) 的固定小倍数代后，得到光滑包络 \(h=h_k\) 满足 \(\int_V\sqrt{1+|\nabla h|^2}\,dx\ge ck^\gamma\)，同时各阶导数仅按代数的指数增长、被 \(k\) 的可控幂笼罩。

第二步造波包并做高斯叠加。在 \(e^{kh}\) 之下求解复程函与输运方程的有限 Taylor 截断（波包，packets），其相位 Hessian 构造在零实斜率处依然有效；它们与球面显式特征函数 \(u_*=\operatorname{Re}(x_1+ix_2)^N\)（\(k^2=N(N+3)\)）经光滑截断粘接。对约 \(k^{40}\) 个中心的波包取独立实高斯组合：以趋于 1 的概率，一阶 jet（函数值与梯度）处处有 \(k^{-500}W\) 型多项式下界（指数 500 不依赖有限阶数选择），且存在"符号证书"（sign certificate，一族两两处于短圆柱两端、严格反号的三维平行圆盘）尺寸 \(\ge ck^{1+\gamma}\)——这靠波包的非零虚对数梯度提供条件方差，再由加权填充不等式 \(\sum R_x^3\ge ck^{1+\gamma}\)（\(R_x=(kQ_x)^{-1}\) 为局部波长半径）汇总而成。

第三步做精确系数修正。显式公式 \(\delta A=Fu\,I\)、\(\delta\rho=k^{-2}(Fu-\operatorname{div}_\mu(FI\,du))\)（\(F=-\mathfrak r/\mathcal D\)，\(\mathcal D=u^2+I(du,du)\)）恒等地抵消残差，修正的 \(C^R\) 范数 \(\le Ck^{-M+2129+1088R}\)，取 \(M\) 充大便趋于零；jet 下界保证在函数指数小的地方也能修正。随后在受保护的圆形补丁上用满足 \(E\,du=0\) 的张量微扰把特征值变简单而 \(u\) 纹丝不动。

第四步收敛到单个度量，要害是"常数可以让步、指数不让步"：\(\gamma\)、坐标图与背景邻域全阶段统一，仅常数与频率门槛可退化。各阶段增量按 \(2^{-j}\) 预算求和，收敛到光滑正对 \(\mathcal P_\infty\)；每阶段的持续性邻域在下一阶段之前固定，极限落在所有邻域内，故极限算子拥有保留全部证书盘的特征函数 \(v_i\)，其特征值落于互斥区间 \((k_i^2/2,\,2k_i^2)\) 且趋于无穷。最后用圆周扭曲积（warped product）\(g=G_\infty+q^2\,d\varphi^2\) 在 \(S^4\times S^1\) 上把加权算子实现为普通 Laplace–Beltrami 算子。每条证书圆柱内的纵向线段必含零点，Lipschitz 投影论证给出 \(\mathcal H_g^4(Z(u_i))\ge c\,i\,k_i^{1+\gamma/2}\)；取 \(\epsilon_0=\gamma/4\) 并用 \(\lambda_i<2k_i^2\)，比值 \(\ge c'\,i\to\infty\)。

## 可信度与备注
本篇主结果已 Lean 形式化。它与族内另两篇构成完整图景：曲面篇证明二维上界恒成立，三、四维篇给出 \(\sqrt\lambda\) 归一化下的定性发散，本文则证明在五维及以上连任意小的幂损失都无法挽救。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇主结果已有形式化证明，细节可信度较高。

{% endraw %}
