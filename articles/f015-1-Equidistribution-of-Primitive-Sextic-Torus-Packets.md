---
layout: default
title: "Equidistribution of Primitive Sextic Torus Packets"
family: "015"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Equidistribution of Primitive Sextic Torus Packets

> 结果族 015：Torus-packet equidistribution in prime, quartic, and sextic degrees　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

素数次的轨道束想变均匀，几乎是水到渠成；复合次数（比如六次）却暗藏陷阱：轨道可能"偷懒"，缩进大厅的某个角落原地打转，拒绝铺满全厅。这篇论文证明：对本原六次全实域的极大序理想类束，所有偷懒模式都不可能存活——墨水终究染遍全局。

**关键词卡片**

- 本原六次域 (primitive sextic field)：没有中间域的六次全实域
- 测度刚性 (measure rigidity)：EKL 分类定理——带正熵的遍历测度必是某类整齐的"齐性"测度
- 分块退化 (blocking)：六个坐标缩进 3+3 或 2+2+2 小块的两种危险极限
- 熵 (entropy)：测度"混合快慢"的度量；正熵意味着足够活跃
- 调节子 (regulator)：单位群"大小"的指标；论文精确算出每条轨道体积为 `@@M@@(s/2)R_K@@`

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 300">
  <text x="280" y="24" font-size="15" text-anchor="middle" fill="#333">危险的偷懒：六个坐标缩进小方块</text>
  <rect x="40" y="50" width="90" height="90" fill="#fbe0e0"/>
  <rect x="130" y="140" width="90" height="90" fill="#fbe0e0"/>
  <rect x="40" y="50" width="180" height="180" fill="none" stroke="#666" stroke-width="1.5"/>
  <line x1="70" y1="50" x2="70" y2="230" stroke="#aaa" stroke-width="1"/>
  <line x1="100" y1="50" x2="100" y2="230" stroke="#aaa" stroke-width="1"/>
  <line x1="130" y1="50" x2="130" y2="230" stroke="#aaa" stroke-width="1"/>
  <line x1="160" y1="50" x2="160" y2="230" stroke="#aaa" stroke-width="1"/>
  <line x1="190" y1="50" x2="190" y2="230" stroke="#aaa" stroke-width="1"/>
  <line x1="40" y1="80" x2="220" y2="80" stroke="#aaa" stroke-width="1"/>
  <line x1="40" y1="110" x2="220" y2="110" stroke="#aaa" stroke-width="1"/>
  <line x1="40" y1="140" x2="220" y2="140" stroke="#aaa" stroke-width="1"/>
  <line x1="40" y1="170" x2="220" y2="170" stroke="#aaa" stroke-width="1"/>
  <line x1="40" y1="200" x2="220" y2="200" stroke="#aaa" stroke-width="1"/>
  <text x="130" y="252" font-size="13" text-anchor="middle" fill="#333">3+3 分块</text>
  <rect x="340" y="50" width="60" height="60" fill="#dde8f7"/>
  <rect x="400" y="110" width="60" height="60" fill="#dde8f7"/>
  <rect x="460" y="170" width="60" height="60" fill="#dde8f7"/>
  <rect x="340" y="50" width="180" height="180" fill="none" stroke="#666" stroke-width="1.5"/>
  <line x1="370" y1="50" x2="370" y2="230" stroke="#aaa" stroke-width="1"/>
  <line x1="400" y1="50" x2="400" y2="230" stroke="#aaa" stroke-width="1"/>
  <line x1="430" y1="50" x2="430" y2="230" stroke="#aaa" stroke-width="1"/>
  <line x1="460" y1="50" x2="460" y2="230" stroke="#aaa" stroke-width="1"/>
  <line x1="490" y1="50" x2="490" y2="230" stroke="#aaa" stroke-width="1"/>
  <line x1="340" y1="80" x2="520" y2="80" stroke="#aaa" stroke-width="1"/>
  <line x1="340" y1="110" x2="520" y2="110" stroke="#aaa" stroke-width="1"/>
  <line x1="340" y1="140" x2="520" y2="140" stroke="#aaa" stroke-width="1"/>
  <line x1="340" y1="170" x2="520" y2="170" stroke="#aaa" stroke-width="1"/>
  <line x1="340" y1="200" x2="520" y2="200" stroke="#aaa" stroke-width="1"/>
  <text x="430" y="252" font-size="13" text-anchor="middle" fill="#333">2+2+2 分块</text>
  <text x="280" y="280" font-size="13" text-anchor="middle" fill="#333">本文证明：偷懒分量不可能存活，极限只能是均匀</text>
</svg>

</div>

六次时对角群的维数是 5。若某个极限测度偷懒，分类定理迫使它住在非平凡对角元的不动点集里——恰好只剩图示两种分块。论文的"全活性"论证显示：任何分块都会让某些方向彻底休眠，而算术给出的管道估计强制高混合速度，两者矛盾；于是唯一幸存的极限是 Haar 均匀测度，且尖端无质量流失。

**为什么值得关心**

六次是首个不带任何附加条件（无需伽罗瓦群或分裂假设）被攻克的复合次数；"算术分离驱动熵下界"的路线在此经受住最严苛的测试。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了全实本原六次数域（无真中间域）极大序的完整理想类 torus packet，按对角轨道体积加权后，随域判别式 `@@M@@|\Disc(K)|\to\infty@@` 在幺模格空间中均衡分布于 Haar 概率测度且无质量逃逸，把 Duke 型定理推进到不带任何辅助条件的复合次数六。

## 问题背景

全实数域的理想经各实嵌入变成格，单位群使对角群轨道紧化，理想类把这些紧轨道拼成有限的 packet（包）。实二次域时 packet 投影为模曲面上的闭测地线：Linnik 的遍历方法给出均衡分布但需附加分裂条件，Duke（1988）以解析方法对基本判别式去掉条件，ELMV（2012）再给出覆盖任意非平方判别式的动力学证明。次数升高后对角轨道维数大于一，Einsiedler–Katok–Lindenstrauss（2006）的测度分类定理说：正熵的 `@@M@@A@@`-遍历概率必是某齐性代数轨道上的不变测度。素数次时它直接就是 Haar 测度；复合次数（如六次）却存在真分块子群，其闭轨道同样能承载有限不变测度，识别并排除这些多余的极限分量正是复合次数的主要障碍。此前 Khayutin（2019）要求 Galois 群在嵌入上双传递，Wieser–Yang（2026）处理带二次子域的四次 packet 还需固定分裂位，六次本原域一直悬而未决。

## 主要结果

主定理：设 `@@M@@K_i@@` 为全实六次本原域（primitive，即不存在中间域 `@@M@@\mathbb{Q}\subsetneq F\subsetneq K_i@@`），`@@M@@|\Disc(K_i)|\to\infty@@`，并任意选取嵌入排序 `@@M@@\sigma_i@@`，则体积加权的 packet 概率测度满足
`@@M@@D\int_{X_6} f\,\dd\mu_{K_i,\sigma_i}\longrightarrow\int_{X_6} f\,\dd m_6\qquad(f\in C_c(X_6)),@@`
极限是幺模格空间 `@@M@@X_6=\SL_6(\mathbb{Z})\backslash\SL_6(\mathbb{R})@@` 上的 Haar 概率测度 `@@M@@m_6@@`；且无质量逃逸（no escape of mass）：对每个 `@@M@@\epsilon>0@@` 存在紧集 `@@M@@C@@` 使 `@@M@@\mu_{K_i,\sigma_i}(C)\ge 1-\epsilon@@` 对一切充分大的 `@@M@@i@@` 成立。packet 的构造是：理想 `@@M@@I@@` 经六个实嵌入成格，归一化协体积为 1 得 `@@M@@\Lambda_{I,\sigma}@@`；每个普通理想类取一代表，再乘遍全部 `@@M@@2^6@@` 个坐标符号对角阵 `@@M@@w@@`，得到紧轨道 `@@M@@\Lambda_{I,\sigma}wA_6@@`，按各轨道的 `@@M@@A@@`-体积加权求平均。乘遍所有符号使 packet 不依赖理想类代表的选取。论文还精确算出每条轨道体积为 `@@M@@(s/2)R_K@@`（`@@M@@R_K@@` 为调节子）、轨道数 `@@M@@h_K2^6/s@@`、总权重为 `@@M@@Q\kappa@@`（`@@M@@Q=D^{1/2}@@`，`@@M@@\kappa@@` 为 `@@M@@\zeta_K@@` 在 `@@M@@s=1@@` 的留数）。

## 证明思路

先做算术估计。向量展开公式把格向量计数化为理想计数：`@@M@@\int_X\widehat f\,\dd\mu=\frac1{Q\kappa}\sum_{l\ge1}d_K(l)V_f(l/Q)@@`；结合 Stark 的有效无零点信息与 Shiu–Pollack 短区间界得理想数一致上界，进而得尖点一致界（保证 tightness）与极限测度的小球估计 `@@M@@\mu(xB(r))\le Cr^6@@`。最关键的管道估计要同时数一个普通向量与一个对偶向量：二者逐坐标乘积 `@@M@@v_jy_j=\sigma_j(z)@@` 落在余微分（codifferent）`@@M@@\mathfrak D_K^{-1}@@` 中，且其部分迹被限制在长 `@@M@@O(e^{-t})@@` 的区间内；本原性保证任何非有理元素生成全域，使对偶迹切片格有直径 `@@M@@O(D^{-1/30})@@` 的基本平行体，这样的 `@@M@@z@@` 只有 `@@M@@O(Qe^{-t})@@` 个，而理想除子数 `@@M@@\exp(C\log D/\log\log D)@@` 在 `@@M@@t\in[\log D/(\log\log D)^{2/3},\ \log D/(\log\log D)^{1/3}]@@` 内被 `@@M@@e^{-t}@@` 压倒，故双侧对角管道的测度不超过 `@@M@@e^{-t/3}@@`。

再做测度分类：小球估计经 ELMV 熵判据给出几乎每个 `@@M@@A@@`-遍历分量的正熵，EKL 定理使这些分量成为齐性测度；而真齐性轨道必含于某个非平凡代数对角阵的不动点集，六次时只剩 `@@M@@3+3@@` 与 `@@M@@2+2+2@@` 两种分块替代。

然后是本文最核心的中间分辨率构造。紧轨道沿根群 `@@M@@U_{jk}@@` 的精确条件测度集中在一点，表达不出管道估计检测到的扩散；于是先在取极限之前按横向小胞条件化，胞腔的对数深度取在增长区间内的一个"平台"上，使条件概率在很宽的深度范围内几乎不变，由此得到既携带算术信息、又有图表间射影一致性与对角等变性、并满足乘积规则 `@@M@@m^{WU}=m^W\times m^U@@` 的极限叶状测度。

接着用熵论证排除惰性：若跨某切割的根群不活跃，长轨道段的名字可用膨胀率至多 `@@M@@\delta@@` 的慢方向网格编码，单位时间熵上界可压到 `@@M@@C_6\delta+o(1)@@`，与管道估计强制的熵下界 `@@M@@\eta/3@@` 矛盾；故任何被 `@@M@@\mu_i@@` 支配的概率沿长段必有正活性，组合论证再升级为极限状态几乎处处全活性。

最后组装：真齐性分量集中于不动点片，其固定对角元必有两不等对角元，相应根的斑块与该片至多交于一点，迫使该根不活跃，与全活性矛盾；故极限只能是 `@@M@@m_6@@`。所有子序列极限相同即得收敛，尖点界保证无质量逃逸。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，请以社区核验为准。它与同族两篇姊妹篇——固定素数次（`@@M@@\ge5@@`、任意局部型）篇与本原四次（任意序）篇——共享同一套 ordinary-vector 算术框架，论文明确沿用其展开与计数方法，三者在素数、四、六三个方向互相印证"算术分离驱动熵下界"的路线；四次篇的立方预解式估计是处理序指标的平行分支。按 OpenAI 官方声明，未经形式化的结果可能存在问题，引用前宜等待专家复核。

{% endraw %}
