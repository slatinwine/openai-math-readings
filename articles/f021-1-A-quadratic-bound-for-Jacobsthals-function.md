---
layout: default
title: "A quadratic bound for Jacobsthal's function"
family: "021"
discipline: "Number theory"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A quadratic bound for Jacobsthal's function

> 结果族 021：A quadratic bound for Jacobsthal's function　·　学科：Number theory　·　验证状态：主结果已 Lean 形式化

## 一句话结论

对任何至多有 \(k\) 个不同素因子的 \(n\)，长度 \(\ll k^2/(\log\log(3k))^2\) 的任意连续整数区间必含与 \(n\) 互素的数。这肯定了 Jacobsthal 的二次上界问题，并在 Iwaniec 的 \(k^2\log^2 k\) 之上首次去掉全部对数损失。

## 问题背景

Jacobsthal 函数 \(j(n)\) 是使"任意 \(m\) 个连续整数中必有与 \(n\) 互素者"的最小 \(m\)；令 \(h(k)=\sup_{\omega(n)\le k}j(n)\)，其中 \(\omega(n)\) 记不同素因子个数。Jacobsthal 自 1960 年起研究它，Erdős 于 1962 年记录了他的问题：是否 \(h(k)\ll k^2\)？由中国剩余定理（Chinese remainder theorem），\(h(k)-1\) 恰是能用至多 \(k\) 个素数的整除类覆盖的最长区间长度，因此这是有限覆盖问题，与筛法（sieve theory）及素数间隙紧密相关。Brun 筛先给出多项式上界，Vaughan（1977）证明 \(j(n)\ll\omega(n)^2\log^4(2\omega(n))\)，Iwaniec（1978）用移位筛改进为 \(h(k)\ll k^2\log^2 k\)——此后近半个世纪无人去掉这两个对数，障碍在于一维筛的模数被限制在区间长度的平方根附近，正落在临界参数 2 上。此外 Hajdu 与 Saradha 发现 \(j(P_{24})=234<236=h(24)\)（\(P_k\) 为前 \(k\) 个素数之积），说明素数积并非总是最坏情形，故必须对任意素数集、任意平移一致地证明。

## 主要结果

主定理：存在绝对常数 \(C>0\)，使对一切 \(k\ge1\) 有
\[h(k)\le C\,\frac{k^2}{(\log\log(3k))^2}.\]
该界对素因子大小与区间位置（含负起点、含零）完全一致。核心是定量幸存者估计：取 \(L=\log z\)，\(Y=\lfloor z^2/L^2\rfloor\)，\(w=L/(\log L)^2\)，\(B=L/\log w\)，\(V_0=\prod_{p\le w}(1-1/p)\)，则当 \(z\) 充分大时，无论怎样为每个素数 \(p\le z\) 指定禁止剩余类 \(a_p\bmod p\)，\([1,Y]\) 中避开全部禁止类的整数至少有 \(cYV_0/B^2\) 个；由 Mertens 定理这 \(\sim e^{-\gamma}cY\log w/L^2\)。禁止类是任意指定的，不假设随机。随后取截断 \(z=A_0\,k\log k/\log\log k\)，此时 \(Y\asymp k^2/(\log\log k)^2\)；再用一个上界筛逐个删除大于 \(z\) 的剩余素因子（至多 \(k\) 个，每个至多删去 \(O(1+X/\log X)\) 个幸存者，\(X=Y/z\)），取 \(A_0\) 充大便仍剩正数，故区间内有与 \(n\) 互素的整数。有限个小 \(k\) 用容斥平凡界 \((k+1)2^k+1\) 吸收进常数 \(C\)。

## 证明思路

证明分"参考计算"与"真实比较"两大块。先建递减素数树：把被覆盖整数按最小违规素数分类，迭代得到由 \((w,z]\) 内严格递减素数组成的节点 \(d\)，其计数满足精确恒等式 \(S_d(b)=N_d-\sum_p S_{dp}(x(p))\)，其中 \(x(p)=\log p/\log w\)。奇偶交替给出 Bonferroni 型符号：偶数层展开是下界。再在奇数层施加准入规则 \(r-x\ge\max(2x,x+2)\)（\(r\) 为间隙参数），保证保留的等差数列长度 \(\ge w^{1/100}\)，可被一个绝对一致的上界筛控制。

再算参考树：把真实计数 \(N_d\) 换成理想值 \(\mu_d=(Y/d)V_0\)，得带调和权重 \(1/p\) 的递推；继而把素数和换成积分 \(\int dx/x\) 进入连续模型。经典线性筛函数 \(f,F\)（满足时滞方程 \((sf(s))'=F(s-1)\) 等）给出基准。真正的难点在根处：其比值 \(2-a_\star/B\) 恰落在 \(f\) 取零的临界参数 2 之下，基准贡献为负的 \(-a_\star e^\gamma B^{-2}\)，正余量只能来自截断值 2 处的边界差异。为评估这个 \(B^{-2}\) 尺度的量，作者用 \(f,F\) 的导数定义权 \(\phi\)，把调和转移改造成概率核（一次测度变换），利用过程的再生结构（regeneration）配合关键更新定理（key renewal theorem）求得极限占据测度，再迁移回素数路径。边界异常 \(\delta_i\) 以 \(\exp(-cr\log r)\) 衰减；与全乘积 \(1/2\) 比较并按"首次被遗漏的叶子"展开，得到带号修正积分 \(I\)：前几项可显式积分，尾项被控制，严格有理算术给出 \(I>0.14\)（细算超过 \(0.2229\)），最终 \(B^2P_\mathrm e(r_0,B)/e^\gamma\to-a_\star+2I/M_g>0.02\)，参考余量为正。

第三步做真实—参考比较。长数列上由筛法基本引理（fundamental lemma of sieve theory）保证 \(N_d\) 接近 \(\mu_d\)；大的相对偏差必沿路径末端某条"见证边"显现。把这些路径装入素数箱相互独立的盒子后，反演估计（inverse estimate）表明大量异常边迫使孤立素数与某个固定有理数 \(A/D\) 对齐：\(Da_p\equiv A\pmod p\)。其证明组合了小系数高度的多项式插值、Jarník 凸弧格点界 \(O(D_0^4(1+S^{2/3}))\) 与 Gallagher 大筛（larger sieve）的对偶计数，即"模集中迫使代数结构"的原理。方差估计（奇异级数平均的截断形式）进一步说明只有小模数、小截距的有理数才能解释大量异常端点；随后在这些对齐分支的合适偶节点处"停车"，对对齐素数求平均会得到比参考子树更多的幸存者，而标记更新（marked renewal）论证保证几乎所有异常路径质量都会到达停车点。

最后装配：比较恒等式
\[L_{\mathrm{stop}}-YV_0P_\mathrm e(r_0,B)=\sum_{d\in\mathcal T}(-1)^{\omega(d)}(N_d-\mu_d)+\sum_{d\in\mathcal S}\bigl(S_d(b_d)-\mu_dP_\mathrm e(r_d,b_d)\bigr)\]
把按预算分配的各小量误差加总，得 \(S_1(B)\ge(c_L/2)YV_0/B^2\)，证得幸存者定理，进而按上节方式导出主定理。

## 可信度与备注

论文标注主结果及关键中间定理（幸存者估计）已有 Lean 形式化证明（结果族 021 对应 lean/docs/021.md），属该系列中验证等级较高的工作；文中数值性步骤（如 \(I>0.14\)、\(e^{0.70}<2.014\)）均以严格有理算术核验。依据 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。本结果族以本文为核心，其 Lean 形式化与论文互为印证；而 Ford–Green–Konyagin–Maynard–Tao 的下界 \(j(P_k)\gg k(\log k)^2\log\log\log k/\log\log k\) 表明真实阶可能远低于二次，Vaughan 更猜想 \(j(n)\ll_\eps\omega(n)^{1+\eps}\)，留待后续。

{% endraw %}
