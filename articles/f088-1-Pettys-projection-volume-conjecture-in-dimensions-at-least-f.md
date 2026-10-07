---
layout: default
title: "Petty's projection-volume conjecture in dimensions at least four"
family: "088"
discipline: "Convex and metric geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Petty's projection-volume conjecture in dimensions at least four

> 结果族 088：Sharp projection-body inequalities and a counterexample to simplex maximization　·　学科：Convex and metric geometry（凸几何与度量几何）　·　验证状态：主结果已 Lean 形式化

## 一句话结论

证明 Petty 投影体积猜想在所有 \(n\ge 4\) 维成立：体积固定的凸体中，椭球、且仅有椭球，使其投影体的体积最小。与陈等人此前证得的三维结果合并，这个 1971 年提出的仿射等周型猜想在全部 \(n\ge 3\) 维度获得解决。

## 问题背景

凸体 \(K\subset\R^n\) 的投影体（projection body）\(\Pi K\) 把各方向的"影子"打包成一个新凸体：其支撑函数 \(h_{\Pi K}(u)\) 定义为 \(K\) 向超平面 \(u^\perp\) 正交投影的 \((n-1)\) 维体积。泛函 \(R_n(K)=|\Pi K|/|K|^{n-1}\) 在平移与可逆线性变换下不变，属于仿射等周问题（affine isoperimetric problem）；注意它与经典 Petty 投影不等式不同——后者度量的是 \(\Pi K\) 的极体的体积。Petty 在 1971 年猜想：当 \(n\ge3\) 时 \(R_n\) 恰被椭球最小化，由 \(\Pi B_2^n=\kappa_{n-1}B_2^n\) 可知最小值就是球的值。此前最好的结果都带限制：Saroglou–Zvavitch 与 Ivaki 的定理只在线性换坐标后"接近球"的范围内局部成立；Mielke–Sulz 只处理旋转体；陈-冯-李-席-徐证明了无附加假设的三维情形。难点在于一般凸体既不对称也无边界正则性，且等号条件必须是全局的。

## 主要结果

主定理：对每个 \(n\ge4\) 与每个凸体 \(K\subset\R^n\)，

\[\frac{|\Pi K|}{|K|^{n-1}}\ \ge\ \kappa_{n-1}^{\,n}\,\kappa_n^{\,2-n},\]

等号成立当且仅当 \(K=a+TB_2^n\)，即 \(K\) 是椭球。定理对任意凸体成立，等号断言是全局的、不要求接近椭球。结合陈等人的三维定理，猜想对一切 \(n\ge3\) 成立（三维是外部结果，本文证明并不依赖它）。论文第七节还从主定理推出三组新不等式：Lutwak–Petty 低次投影体不等式——对 \(1\le i\le n-1\)，\(V_{i+1}(\Pi_i K)/V_{i+1}(K)^i\) 达到球的下界，其中 \(2\le i\le n-2\) 是新确立的范围；非负紧支光滑函数的混合行列式梯度积分 \(\mathcal D_n(f_1,\dots,f_n)\) 的最优仿射 \(L^1\) Sobolev 不等式，其对角形式强于 Zhang 的仿射 Sobolev 不等式；以及赋范空间中 Holmes–Thompson 体积的等周不等式，等号当且仅当范数球是椭球且体与之位似。

## 证明思路

证明走"化体为测度"的路线，核心是一个与投影体无关的双线性不等式。

第一步，把凸体换成测度。将 \(K\) 平移并归一化到 \(|K|=\kappa_n\) 后，体积的第一变分产生 \(\R^n\) 上的概率测度 \(\eta_K\)：支撑有界、张成全空间，且对每个对称凸体 \(M\) 满足 \(\int h_M\,d\eta_K\ge(|M|/\kappa_n)^{1/n}\)；同时 \(h_{\Pi K}(y)\) 等于 \(\int|x\cdot y|\,d\eta_K(x)\) 的固定倍数。于是目标下界化归为：任何两个满足该支撑函数条件的测度 \(\eta,\zeta\) 都有 \(\iint|x\cdot y|\,d\eta(x)d\zeta(y)\ge b_n\)（\(b_n=\E|u_1|\)）。

第二步，为测度配备变分最优的范数。在 \(\tau_A(L)=1\) 约束下最小化目标 \(J(g)\)（\(n=4\) 取对数型 \(\E\log g\)，\(n\ge5\) 取线性型 \(\E g\)），存在唯一极小体，其规范函数（gauge）\(g\) 满足变分表示：测度的支撑泛函可用梯度场 \(X_{g^k}=g^{k-1}\nabla g\) 的球面平均表出。该构造属于对偶 Minkowski 问题（dual Minkowski problem）框架，但论文直接自证了表示公式、唯一性，以及随矩阵秩退化所需的连续性——测度可以带原子，极小体也不必光滑。

第三步，两块球面调和估计。符号检验用 \(|a|\ge\operatorname{sgn}(u\cdot v)\,a\) 把配对下方控制为含 cosine 变换（cosine transform）与 Funk 变换（Funk transform）的双线性形式，谱间隙 \(\lambda_2=2n<\lambda_4=4(n+2)\) 把常数部分与 4 次及以上调和部分分开；严格的范数估计则断言对任何范数 \(g\)（不要求光滑）有 \(c_{n,k}\|Q(g^k)\|_2^2\le(\E g^k)^2-(\E g^{k-1})^2\)，除非 \(g\equiv1\)（欧氏情形）否则严格——证明先用范数凸性给出的曲率不等式 \(\Delta_S g+(n-1)g\ge0\) 分部积分，再化为逐点标量不等式，最后用光滑化逼近过渡到一般范数。

第四步，消去二次调和分量。它不是符号检验算子的零特征空间，只能靠选仿射坐标去除：把变分极小化解连续延拓到半正定矩阵锥的边界（此时规范函数退化为半范数），在退化核方向显式计算出一个指向锥内的矩阵场，Brouwer 不动点定理给出 \(\det A=1\) 的正定矩阵 \(A\)，使 \(g_A^k\) 的二次分量为零。只需对一个测度做此规范化，另一个测度用逆步变换 \(A^{-1}\) 处理，配对 \(\iint|x\cdot y|\) 在 \((Ax)\cdot(A^{-1}y)=x\cdot y\) 下不变。

最后合成：对 \(\eta_K\) 与体积归一的投影体的测度应用双线性不等式，得 \(|\Pi K|\ge\kappa_n\kappa_{n-1}^{\,n}\)，解除归一化即为主定理。等号情形被逐步逼紧：先得 \(g\equiv1\)，即支撑条件在某个中心椭球上取等，再由第一变分的等号断言推出 \(K\) 是该椭球的平移相似像。

## 可信度与备注

论文标注主结果已有 Lean 形式化证明。族内姊妹篇《A product counterexample to the simplex maximum for projection-body volume》处理同一泛函的另一端：本文确定极小值侧（椭球唯一最小化），姊妹篇推翻极大值侧的 Brannen 单形猜想，两篇合看才构成 \(R_n\) 极值行为的完整图景。第七节推论引用了 Lutwak 与 Haddad 的条件性蕴含等外部文献，属"主定理＋引用"的组合。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文主结果已形式化，是族内可信度最高的一环。

{% endraw %}
