---
layout: default
title: "Entanglement with zero distillable secret key in local dimension ten"
family: "272"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Entanglement with zero distillable secret key in local dimension ten

> 结果族 272：Entanglement without distillable secret key　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

在 `@@M@@\mathbb C^{10}\otimes\mathbb C^{10}@@` 上显式构造出一个纠缠态：即便双方可联合处理任意多份副本、进行无限双向认证公开通信，窃听者还持有体系纯化态与全部公开记录，其可蒸馏秘密密钥（distillable secret key）`@@M@@K_D@@` 仍严格为零，连一个近似保密比特都拿不到；同一构造还否定了双映射 PPT 复合猜想与 PPT 信道平方猜想。

## 问题背景

秘密密钥蒸馏问的是：相距遥远的两个实验室能否通过对共享量子态 `@@M@@\rho_{AB}@@` 作局部操作与认证公开通信，产出窃听者 Eve 无法预测的相同随机比特，其中 Eve 持有输入的纯化态（purification）并阅读全部公开记录。可分离态（separable state）对这样的 Eve 必为零密钥，于是问题变成：纠缠是否总能为保密所用？这正是 Krüger–Werner 开问题集（2005 年 3 月，联系人为 P. Horodecki）的第 24 问"Secret key from all entangled states"。此前图景错综：PPT 纠缠态无可蒸馏纠缠（即界纠缠，bound entanglement），其中某些却有正的秘密密钥（所谓私有态，private states）。真正的难点在于：要给出否定回答，必须构造一个即使在最强协议模型下——联合处理全部副本、无限双向公开通信、输入为唯一共享私密资源——密钥速率仍为零的纠缠态，且误差下界须是与副本数、通信量、局部内存都无关的一致常数。

## 主要结果

论文证明三个定理。**定理一**：存在显式给出的纠缠密度算符 `@@M@@\rho@@`，作用在 `@@M@@\mathbb C^{10}\otimes\mathbb C^{10}@@` 上，其值域不含任何非零积向量（product vector），且 `@@M@@K_D(\rho)=0@@`。更强的定量形式：对任意 `@@M@@n\geq1@@` 与任意按文中定义完成（completed）的比特输出协议，输出态与任何理想保密比特的距离满足
`@@M@@D\Bigl\lVert\tau-\frac12\sum_{i=0}^1|i,i\rangle\langle i,i|\otimes\sigma_{E'}\Bigr\rVert_1\geq\frac15,@@`
即通常迹距离（trace distance）至少 `@@M@@1/10@@`，常数与一切协议参数无关。**定理二**：存在显式 PPT 映射 `@@M@@\Phi_1,\Phi_2:M_{10}(\mathbb C)\to M_{10}(\mathbb C)@@`（PPT 指映射自身及其与坐标转置的复合均为完全正，completely positive），使复合的 Choi 矩阵 `@@M@@Z=J(\Phi_2\circ\Phi_1)@@` 非零且值域无积向量，故复合不是纠缠破坏（entanglement breaking）的——这否定了 Christandl–Müller-Hermes–Wolf 的无限制双映射 PPT 复合猜想。**定理三**：存在显式保迹 PPT 信道 `@@M@@\Theta:M_{21}(\mathbb C)\to M_{21}(\mathbb C)@@`，其平方 `@@M@@\Theta\circ\Theta@@` 不是纠缠破坏的（同一信道放在两个位置），回答了 2012 年 BIRS 工作坊报告的问题 G，即 Christandl 的 PPT 平方猜想。三者的连接点是 `@@M@@\rho=Z/\operatorname{tr}Z@@`。

## 证明思路

证明分两条主线：对一大类态的一致操作性障碍，与让构造的态真正纠缠的十维几何。

先建立操作性障碍。论文定义"表示类"`@@M@@\mathscr C@@`：`@@M@@\omega=(\mathcal L\otimes\mathcal M)(\chi\chi^*)@@`，两个映射及其与输入转置的复合都完全正。核心是"四效应不等式"：对任意四个正矩阵（不加归一化），先在表示空间把拉回 `@@M@@A_i@@` 同余化为可交换，再用完全正性得一个方向的块估计、用双因子同时转置的完全正性得反向估计，最后按特征值大小分裂输入向量并作三角不等式，得"等比特分支间的相干"被"比特不一致概率"控制。再做转录分析：在公开记录的一个公共测度下，四个比特分支密度可分解为局域积 `@@M@@X_i(t)\otimes Y_j(t)@@`——证明时把协议跑在辅助积探针上：给定完整公开记录时两条局域采样带条件独立，信息完全（informationally complete）测试把独立性转成公共积因子，再经滤波转移到真实输入。最后合拢：设 `@@M@@e@@` 为双方比特不相同的总概率，`@@M@@\mathfrak f@@` 为 Eve 两个等比特条件态的根保真度（root fidelity）对转录的积分。正确性给 `@@M@@e\leq\eta/2@@`；保密性经 Fuchs–van de Graaf 下界给 `@@M@@\mathfrak f\geq(1-\eta)/2@@`；四效应不等式加 Cauchy–Schwarz 给 `@@M@@\mathfrak f\leq\sqrt{e(1-e)}+e@@`。若 `@@M@@\eta<1/5@@`，末式右端小于 `@@M@@2/5@@` 而前一式左端大于 `@@M@@2/5@@`，矛盾。常数不依赖副本数与协议；取长密钥首比特是迹范数收缩，正速率全被排除。

再让态纠缠。Choi 转移恒等式 `@@M@@J(G\circ F)=(F^\sharp\otimes G)(\Omega_b\Omega_b^*)@@` 把 PPT 对的复合变成 `@@M@@\mathscr C@@` 中的态 `@@M@@\rho=Z/\operatorname{tr}Z@@`；而可分正矩阵的值域必含非零积向量，故只需让 `@@M@@\operatorname{ran}Z@@` 无积向量。做法：取 PPT 映射 `@@M@@L:M_4(\mathbb C)\to M_4(\mathbb C)@@` 与 20 个射影方向，使 `@@M@@L(xx^*)@@` 在其上奇异，且任何非零齐次二次多项式至多在其 9 个方向上为零。用十维对称平方记录 `@@M@@x@@` 的二次单项式（Veronese 型映射 `@@M@@\widehat x@@`），用六维外平方把秩损失转成核向量 `@@M@@\widehat x\otimes\widehat x@@`（借助与费米子对偶同源的互补对算子 `@@M@@K@@`）。若 `@@M@@\operatorname{ran}Z@@` 含积向量 `@@M@@u\otimes v@@`，则 `@@M@@u,v@@` 给出两个非零二次型，其零点集须覆盖全部 20 个方向，但 `@@M@@9+9<20@@`，矛盾。`@@M@@L@@` 显式来自一个实整数 `@@M@@6\times4@@` 矩阵束；论文在三个素数上做精确约化，证明相关的二十次代数是域且正规闭包的伽罗瓦群（Galois group）为 `@@M@@S_{20}@@`，借此把一个非零二次求值行列式传递到所有十点子集，附录给出完整算术证书。

最后做保迹信道：把两个映射重标定、在两坐标块间交替切换、把缺失的迹送入吸收旗标（Filippov 保迹扩张）；`@@M@@\Theta\circ\Theta@@` 的 Choi 矩阵有一局部角落恰为 `@@M@@Z@@` 的正常数倍，局部压缩保持可分性，故平方非纠缠破坏。

## 可信度与备注

本篇主结果暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。构造附带精确算术证书（三个素数上的精确约化与 `@@M@@S_{20}@@` 伽罗瓦群论证，附录含补充有限核查），且论文明言不主张 10 与 21 是最小维数。该结果族本批仅此一篇，但论文内部两大部件互为支撑：十维几何构造提供落在 `@@M@@\mathscr C@@` 类中的显式纠缠实例，操作性障碍定理赋予它对全部许可协议的一致零密钥结论；引言还将其与 Pauwels–Gisin–Renner 2026 年的经典源零密钥速率结果并置，显示量子与经典两条线的呼应。

{% endraw %}
