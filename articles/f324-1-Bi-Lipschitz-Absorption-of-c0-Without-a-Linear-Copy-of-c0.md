---
layout: default
title: "Bi-Lipschitz Absorption of c0 Without a Linear Copy of c0"
family: "324"
discipline: "Functional analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Bi-Lipschitz Absorption of c0 Without a Linear Copy of c0

> 结果族 324：Lipschitz equivalent Banach spaces need not be linearly isomorphic　·　学科：Functional analysis　·　验证状态：主结果已 Lean 形式化

## 一句话结论

构造出可分实 Banach 空间 \(Z\)：它不含任何线性拷贝的 \(c_0\)，却与 \(Z\oplus_\infty c_0\) 双 Lipschitz 等价——\(c_0\) 被"非线性吸收"，且同一空间双 Lipschitz 包含一切可分度量空间。

## 问题背景

Banach 空间的非线性几何追问：只控制距离、不尊重加法的映射能保留多少线性结构。Ribe 定理保证一致同胚的空间共享相同的有限维线性结构；Aharoni–Lindenstrauss 给出不可分反例后，可分情形成为焦点。Godefroy–Kalton–Lancien 证明：与 \(c_0\)（或其子空间）整体双 Lipschitz 等价的空间必线性同构于 \(c_0\)（相应子空间）——但这是关于整个空间的论断。另一个问题是：若空间只是含有 \(c_0\) 的双 Lipschitz 像（嵌入而非整体等价），是否必含线性拷贝？Kalton 2008 年综述将其列为问题 2，与可分 Lipschitz 同构问题并列；Hájek–Johanis–Schlumprecht 在 2024 年 1 月的预印本中仍称其看似公开。相关的弱结果包括：Kalton 2004 年构造的可分 Schur 空间与含补 \(c_0\) 的空间一致同胚（非线性连续模）；Sarı 的 coarse-Lipschitz 嵌入允许加性误差。本文则给出全局双侧 Lipschitz 界与到上的映射。

## 主要结果

主定理：存在可分实 Banach 空间 \(Z\)，不含与 \(c_0\) 线性同构的闭子空间，且存在到上的双 Lipschitz 映射

\[F:Z\oplus_\infty c_0\longrightarrow Z,\]

其中 \(\oplus_\infty\) 是取 \(\max\) 的直和范数。由下 Lipschitz 界，\(F\) 自动是双射。两个空间不可能线性同构：直和含 \(c_0\) 的线性等距拷贝，而 \(Z\) 不含。论文还推出三条同空间结论：其一，\(Z\oplus_\infty c_0\) 与 \(Z\) 双 Lipschitz 等价但不线性同构；其二，把 \(F\) 限制在 \(c_0\) 坐标上即得 \(c_0\) 到 \(Z\) 的双 Lipschitz 嵌入，而 \(Z\) 无线性拷贝；其三，由 Aharoni 定理（每个可分度量空间都双 Lipschitz 嵌入 \(c_0\)）与该限制复合，\(Z\) 成为一切可分度量空间的双 Lipschitz 万有靶。

## 证明思路

先做代数归约。吸收判据（absorption criterion）说：设有界线性 \(Q:Z\to U\)、双 Lipschitz 双射 \(g:E\oplus_\infty U\to U\) 与 Lipschitz 映射 \(K\)，满足精确恒等式 \(QK=g-P\)（\(P\) 为向 \(U\) 的投影），则 \(F(b,t)=b+K(t,Qb)\) 是 \(Z\oplus_\infty E\to Z\) 的双 Lipschitz 双射，其逆由 \(g^{-1}\) 显式表出。要点在于恒等式"提升"了修正项 \(g-P\)，完全不要求 \(Q\) 到上或有右逆——这刻意绕开了 Godefroy–Kalton 的推论（可分空间上商映射的 Lipschitz 右逆必自动线性化），否则构造将立即坍缩。于是只剩两项任务：以 \(E=c_0\) 实现这样的 \(g\)，并造出无 \(c_0\) 的 \(Z\)。

再造 \(g\)。取 \(E,U\) 为可数坐标的 \(c_0\)，把 \(U\) 的坐标切成有限块排成行。每块内取向量 \(v\) 与泛函 \(w\)（\(wv=1\)）：来自前一块的标量替换当前块的 \(wx\) 分量，块内其余分量不动——记此冻结位移为 \(S_s\)。若各 \(v,w\) 固定，输出可用显式线性逆恢复输入；但权重实际依赖归一化输入，故需控制权重随输入的变化以获全局双 Lipschitz 界，并在有限行上使用 Brouwer 不动点定理；每行末尾附加一个额外标量，既配平维数，又迫使可能的输出溢出消失；最后由稠密性与闭像论证得到到上，下界常数 \(c_g=1/5-24\eta>0\)。

接着构造 \(Z\) 并实现提升。把 \((S_s-P)s\) 的每个坐标视为单位球上的标量函数：它们只依赖有限多个坐标且支撑局部化。两种局部操作——在小柱上取常值、只保留变化量——配合严格的尺度预算与尺度不增的排序，保证支撑持续局部化。随后以 Arens–Eells 分子（molecule）与 Lipschitz 自由空间（Lipschitz-free space）的框架定义范数：由"选定测试列表的符号和具有共同 Lipschitz 界"给出各半范数，再以趋于 \(1\) 的指数作外层平方和拼成完整范数。外层平方和阻止假想的 \(c_0\) 基经不同测试类逃逸，变化的指数则保证每个基向量被某个标量测试检测到。坐标测试定义 \(Q\)，点分子的径向延拓定义 \(K\)，验证 \(QK=g-P\) 且 \(\mathrm{Lip}(K)\le3\)。

最后排除线性 \(c_0\)。若有嵌入 \(T:c_0\to Z\)，则基向量的有限符号和一致有界，且对每个泛函坐标趋于零（弱零列）。滑峰（gliding hump）选择配合半范数的凸性（Jensen 不等式与随机符号平均）先从单一测试类中提取出能检测子列的测试；再修改这些检测器，使其支撑两两不交，或呈嵌套平台（plateau）且平台值可和地小——两种构型都保证修改后测试的任意有限符号和有共同的 Lipschitz 界。随机符号展开随后迫使被检测向量的符号和范数至少按 \(\sqrt{|H|}\) 增长，与一致有界矛盾，故 \(Z\) 无线性 \(c_0\)。装配节合并吸收判据、映射 \(g\) 与提升 \((Q,K)\)，即得主定理与三条推论。

## 可信度与备注

主定理已通过 Lean 形式化验证。同族姊妹篇用 \(c_0(\ell_2)\)（Hilbert 块值零序列）作障碍给出另一组可分反例，方法与本文独立；本文改为排除普通 \(c_0\)，并额外给出同空间吸收与万有性，两者互补地支撑"双 Lipschitz 等价不决定线性同构类"这一主题。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本文主结果已形式化，中间构造细节仍以论文文本与社区核验为准。

{% endraw %}
