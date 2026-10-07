---
layout: default
title: "Localization costs and information growth for exact Gaussian observations"
family: "140"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Localization costs and information growth for exact Gaussian observations

> 结果族 140：Memory–sample lower bounds for noiseless Gaussian regression　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文对"均匀立方体经球坐标映射"的先验证明：`@@M@@t@@` 个 `@@M@@\Theta(d)@@` 行精确高斯观测块、每条消息至多 `@@M@@\exp(Ad^2)@@` 个取值时，只携带 `@@M@@O_A(dt)@@` nats 信息，且在额外披露恢复几何铺开性的二进格子后界仍成立。

## 问题背景

对无噪高斯回归逐块迭代信息界时，会撞上一个循环困难：块估计要求当前后验满足"几何铺开条件"（不向低维邻域集中），而消息本身恰恰破坏这一条件；要恢复它就得向分析披露包含信号的二进格子（dyadic cell），而披露本身要花信息——定位的代价能否被其收益抵偿？这就是本文主题"定位代价"（localization costs）。文献脉络上，Steinhardt–Duchi 与 Raz 建立了带噪与离散的内存–样本权衡，Dagan–Kur–Shamir 证明了一致线性方程组的二次空间下界；最接近的方法学前身是 Sharan–Sidford–Valiant（SSV）第七节的投影矩展开与逐次正交化。但精确标签情形必须重证多行密度估计，并首次系统清算每次定位的信息账单。

## 主要结果

主定理（重复定位）说：令 `@@M@@n=d-1@@`，`@@M@@Z@@` 在边长 `@@M@@1/\sqrt n@@` 的方体上均匀分布，`@@M@@S=\phi(Z)=(Z,\sqrt{1-\|Z\|^2})@@` 落在球面上；把观测分成 `@@M@@k=\lfloor n/16\rfloor@@` 行一块，每条消息 `@@M@@W_i@@` 至多 `@@M@@N\le\exp(Ad^2)@@` 个值（`@@M@@A@@` 固定）。则可以披露一列包含 `@@M@@Z@@` 的嵌套二进格子 `@@M@@Q_0\supset Q_1\supset\cdots\supset Q_t@@`，使得增广记录 `@@M@@\Pi_t=(W_1,Q_1,\ldots,W_t,Q_t)@@` 满足互信息 `@@M@@I(Z;\Pi_t)\le Cdt@@`，且期望格子深度 `@@M@@\E J_t\le Ct@@`。原始消息历史是 `@@M@@\Pi_t@@` 的函数，故自动继承同一界。学习者推论：状态数 `@@M@@M=o(d^2)@@` 的学习者若对每个信号都以 `@@M@@\ge2/3@@` 概率成功，则 `@@M@@T\ge c\,d\log(1/\epsilon)@@`。论文还给出八条定位路线（极大得分、有限熵、有界密度分裂、似然截断、网格加细、侧投影、分离元组、前驱张成）与两种信息修正工具（核势 `@@M@@\Phi@@` 与格子修正），覆盖立方体先验与球面均匀先验两类应用。

## 证明思路

铺开条件要求：支在格子 `@@M@@Q@@` 上的后验对每个相对深度 `@@M@@j@@` 的后代格子质量 `@@M@@\le B2^{-nj/2}@@`。第一步证明加权投影估计：铺开条件经二进覆盖给出管道型估计 `@@M@@\mu\{\mathrm{dist}(a(z),V)\le\delta\}\le BC^d\delta^{n/2-q}@@`；把任意 `@@M@@L^2@@` 权重塞进后验，对平滑标签密度的 `@@M@@m@@` 次矩展开引入 `@@M@@m@@` 个独立点，高斯行作用在差矩阵 `@@M@@\mathsf D@@` 上时每行是协方差为 `@@M@@\mathsf D^{\mathsf T}\mathsf D@@` 的高斯向量，其密度峰值反比于单纯体积 `@@M@@V_*@@`，平滑参数 `@@M@@\eta@@` 的幂次恰好相消；再用尾部积分逐点控制 `@@M@@\int D_i^{-k}@@`，取对偶即得对权重一致的 `@@M@@L^m@@` 密度界。第二步把密度换成信息：消息概率 `@@M@@p_w(z)@@` 的 `@@M@@L^2@@` 范数由对偶与 H\"older 用参考概率 `@@M@@b_w@@`（标签换成均匀参考）控制，再经 Jensen 与 log-sum 不等式得单块界 `@@M@@I\le Cd+\log B+(2/m+e^{-ck})\log N@@`。第三步是定位记账：消息之后铺开性可能失效，于是披露"最深的重格子"（后验质量 `@@M@@\ge2^{-nj/2}@@` 的最深祖先）；深度 `@@M@@j@@` 处重格子至多 `@@M@@2^{nj/2}@@` 个，指明一个只花约 `@@M@@nj/2@@` 比特，而"信号落入深度 `@@M@@j@@` 格子"本身认证 `@@M@@nj@@` 比特信息，这一半的指数差就是支付披露与下一轮 `@@M@@\log B@@` 的盈余。关键细节是记账须按"选中"该格子的概率而非落入概率归一化。第四步闭合迭代：链式法则给上界 `@@M@@I\le Cdt+(\tfrac n2+2)\log2\,\E J_t@@`，而相对熵恒等式 `@@M@@\KL(\lambda\|\mu_0)=nJ_t\log2+\cdots@@` 给下界 `@@M@@I\ge n\log2\,\E J_t@@`，两相比较逼出 `@@M@@\E J_t\le Ct@@`，代回即得 `@@M@@I\le Cdt@@`。流式应用：固定一切随机性化为确定性学习者，块消息记状态（含块内停止偏移），`@@M@@N\le(k+3)2^M+1@@` 满足字母表条件；成功帽体积 `@@M@@\le(5\epsilon)^n@@`，由数据处理不等式精确估计需 `@@M@@\Omega(n\log(1/\epsilon))@@` 信息，故块数 `@@M@@t\ge c\log(1/\epsilon)@@`；最后用保留全部数据的端点论证消除取整，得 `@@M@@T\ge c\,d\log(1/\epsilon)@@`。

## 可信度与备注

据任务文件，本文暂无 Lean 形式化证明，可信度依赖社区核验，读者宜谨慎对待细节常数。其最终结论与两篇已形式化的姊妹篇《Memory and precision…》《Posterior replicas…》一致，且其"前驱张成"路线直接引用后者的等标签测度定理（Theorem 3.3），另有一条混合投影矩取自同伴论文。按 OpenAI 官方声明："未经形式化的结果可能有问题"。

{% endraw %}
