# Task 7

4.设 $ϕ : G↦H$ 是一种群同态。证明：如果 $G$ 是循环群，则$ϕ(G)$ 也是循环群;如果$G$是交换群，则$ϕ(G)$也是交换群。

证：

如果$G$是循环群，令$g$为生成元，则对任意 $a ∈ G$ ，满足 $a = g^k$

$∴ϕ(a) = ϕ(g^k)$

由同态可知

$ϕ(g^k) = ϕ(gg...gg) = (ϕ(g))^k = ϕ(a)$

所以$ϕ(G)$ 也是循环群

如果$G$是交换群，则对任意$a,b ∈ G$，满足$ab=ba$

则 $ϕ(ab) = ϕ(ba)$

由同态可知

$ϕ(ab) = ϕ(a)ϕ(b)$

$ϕ(ba) = ϕ(b)ϕ(a)$

$∴ ϕ(a)ϕ(b) = ϕ(b)ϕ(a)$

所以$ϕ(G)$ 也是交换群

5.证明：如果 $H$ 是 群$G$ 上指标为2的子群，则$H$是群$G$的正规子群。

映射$gH↦(gH)^{–1} = Hg^{–1}$定义左陪集和H的右陪集之间的双射，因此左陪集的数量等于右陪集的数量。

$∵[G : H] = 2$

$∴$不同的左陪集个数为2

其中一个为$eH = H$

不同右陪集个数为2

其中一个为 $He = H$

当 $gH = H$ 时 $gH = eH = Hg$

当 $gH ∩ H = ∅$ 时显然 $Hg ∩ H = ∅$

$∵ H$的所有左(右)陪集划分群 $G$

$∴ gH = Hg$

所以 $H$ 是群 $G$ 的正规子群

6.证明：如果群$G$是阿贝尔群，则商群 $G/H$ 也是阿贝尔群。

$∵ G$ 是阿贝尔群 且 $H$ 是 $G$ 的 正规子群

$∴ gH = Hg , 其中 g ∈ G$

$∴任取 a,b ∈ G$

由上可得 $aH*bH = abH = a(bH) = aHb$ 

由封闭性可知 $Hb ⊆ G$

显然 $Hb$ 是 $G$   的正规子群

$∴ aHb = Hba = baH$

∴ $abH = baH$

 所以商群 $G/H$ 也是阿贝尔群。

7.证明：如果群G是循环群，则商群 G/H 也是循环群。

 如果$G$是循环群，令$g$为生成元，则对任意 $a ∈ G$ ，满足 $a = g^k$

∵  $H$ 是 $G$ 的 正规子群

$∴ 任取 a ∈ G 有 aH = Ha$

显然 $HH = H$ 

由上可知 $aH = g^kH =  gg..ggH = gg..ggHH..HH = gHgH...gH = (gH)^k$

所以商群 $G/H$ 也是循环群。