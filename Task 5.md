# Task 5

1.群 G 的非空子集 H 是 G 的子群，当且仅当 H != ∅，且对任意 a, b ∈ H，$a*b^{-1} ∈ H$。

证:

当群 G 的非空子集 H 是 G 的 子群 时，

有H != ∅。

对任意 a, b ∈ H，存在 $a^{-1},b^{-1} ∈ H$

由封闭性可知 $a*b^{-1} ∈ H$

必要性得证

当 H != ∅，且对任意 a, b ∈ H，$ab^{-1} ∈ H$时

设e为G的单位元

任取a ∈ H，有$aa^{-1}=e∈H$

又∵H是G的非空子集

∴对任意 a ∈ H 都有 a∈G 且 a·e = e·a = a

所以H中存在单位元e

∴对于任意b∈H 有 $eb^{-1}=b^{-1} ∈ H$

所以H中任意元素均存在逆元

∴对任意$a, b ∈ H,$ 有 $ab=a（b^{-1}）^{-1} ∈H$

所以H满足封闭性

∀a,b,c ∈ H, 有 a, b, c ∈ G

∴(a · b) · c = a · (b · c)；

所以H有结合律

充分性得证

2、设G是阿贝尔群，m是任意整数，记$G^m = \{ g^m: g\in G \}$。请证明$G^m$是G的一个子群。

当m==0时，G^m={e} 显然是 G 的一个子群

当m为正整数时，

∵G是群

任取g∈G

由封闭性可知

gg∈G

ggg∈G

…

$∴g^m∈G$

所以$G^m$是G的一个非空子集

$∀g^m,k^{m} ∈ G^m$

有$g^m,(k^{-1})^{m} ∈G$

又∵G是阿贝尔群

$∴ g^m*(k^{-1})^m = (gk^{-1})^m$

由封闭性可知$gk^{-1} ∈ G$

$∴(gk^{-1})^m ∈ G^m$

所以由命题6.8得$G^m$是G的一个子群

当m是负整数时，对$(g^{-1})^{– m}$的证明类似

故得证

3、如果群G没有非平凡子群，则群G是循环群。

证：

设 a ∈ G 且 a ≠ e

则 $H = \{ a^k : k ∈ Z\} ≤ G$

又因为G中没有非平凡子群

∴ H = G

∴G是循环群

4、证明循环群G中任意元素的阶都整除群G的阶。

当G是有限群时,

令G中生成元为g

|G|为G的阶

则|G|为g的阶

即 $g^{|G|} = e$

显然G中生成元的阶都整除G的阶

任取G中非生成元的元素 a

令 $g^{|G|+x } = a$

x为符合等式的最小正整数

由良序原理得 x 必定存在

∵|G|是群G元素总数

∴g^1…g^|G|遍历了一遍群

∴ 0 ≤ x <|G|

令 k为a的阶

有$a^k = (g^{|G|+x })^k = g^{ |G|k + xk} = e = g^{|G|}$

$∴ |G| + x = |G|k^{-1}$

∵|G|+ x 是正整数

∴k整除|G|

∴G中所有非生成元的阶都整除G的阶

所以有限循环群G中任意元素的阶都整除群G的阶

//用拉格朗日证———————

4、群G中任意元素的阶都整除群G的阶。

证：

由拉格朗日定理

群 G 被划分为 [G : H] 个不同的左陪集，每一个左陪集有 |H| 个元素。因此 |G| = [G : H]|H|.

等价地，子群 H 的阶必然整除群 G 的阶。

任取群元a

生成群 < a > ,显然元素a的阶就是该群的阶

又∵ < a > ≤ G

所以群G中任意元素的阶都整除群G的阶。

//——————————-

5.编程:

编程完成以下工作：给定一个素数 p，找出 $Z_p^*$ 的最小生成元。对于素数 1 < p <
10000，哪一个素数 p 使得 $Z^∗_p$的最小生成元最大？

```cpp
#include <iostream>
#include <cmath>
using namespace std;

//模指数运算 
int power_mod(int a, int exp, int n){
    int temp = 1;
    while(exp){
        if (exp % 2 == 1){
            temp = (temp*a) % n;
        }
        a = (a*a) % n;
        exp /= 2;
    }
    return temp;
}

//判断是否素数 
bool is_prime(int n){
	if(n==1){
		return 0;
	}
	for(int i=2;i*i<=n;i++){
		if( n%i == 0 ){
			return 0;
		}
	}
	return 1;
}

//素因子数量 
int prime_factor_amount(int p,int factor[]){
	
	int len=0;
	for(int i=2 ; 2*i<=p ; i++){
		if( p % i == 0 && is_prime(i) == 1 ){
			factor[len]=i;
			len++;
		}
	}
	return len;
}

//找最小生成元 
int prime_root(int p){
	int factor[p-1];
	int len=prime_factor_amount(p-1,factor);
	int i,flag;
	for(i=2;i<p;i++){
		
		flag=1;
		for(int j=0;j<len;j++){
			if(power_mod(i,(p-1)/factor[j],p)==1){
				flag=0;
				break;
			}
		}
		if(flag==1 && power_mod(i,p-1,p)==1){
			return i;
		}
	}
	
	return -1; 
	//nil
}

int main(){
/*	int p;
	cin>>p;
	int sum = prime_root(p);
	cout<<sum;
*/
	int milion_p[1300];
	int sum=3,i;
	milion_p[0]=2,milion_p[1]=3,milion_p[2]=5;
	for(i=7;i<=9997;i=i+2){
		if(is_prime(i)){
			milion_p[sum]=i;
			sum++;				
		}
	}
	int max_generator=-1;
	int max_p=0;
	for(i=0;i<sum;i++){
		int temp=prime_root(milion_p[i]);
	
		if( temp > max_generator ){
			max_generator = temp;
			max_p = milion_p[i];
		}
	}
	cout<<max_p;
	
	return 0;
}
```

编程完成以下工作。选取素数 q，使得 p = 2 ∗ q + 1 也是素数。随机选取 $h ∈ Z^∗_p$，使得 g = $h^2$ 且 g ≠ 1。显然，<g> 是循环群。

(a). 写一个 Python（或者 Sage）程序生成群 <g>。
(b). 群 <g> 的阶是多少，为什么？
(c). 群 <g> 中有多少个生成元？能说明理由吗？

```python
def generate(root,p):
    group=set()
    g=root*root
    for i in range(1,p-1):
        group.add(pow(g,i,p))
        
    return group

if __name__=="__main__":

    a=generate(6,11)
    b=generate(2,11)
    print(a)
    print(b)
```

以下是错误答案

（b）

$Z_p^*$ 的群成员有2q个

令e为$Z_p^*$ 的单位元

由群G中任意元素的阶都整除群G的阶可得

$h^{2q}$=e=$g^q$

∴对任意 g ∈ < g > 都有 $g∈Z_p^*$ 且 g·e = e·g = g

∴e也是< g >的单位元

易得q为g在群< g >上的阶

即群< g >的阶为q

(c)

由推论7.1可知

群 G = < g >是阶为 q 的循环群，则群 G 中恰有 ϕ(q) 个生成元。

ϕ(q)=q-1