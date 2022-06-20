# Task 3

1、实现求乘法逆元的函数，给定a和m，求a模m的乘法逆元，无解时请给出无解提示，并且只返回正整数。

2、实现模指数运算的函数，给定x、y和m，求x的y次方模m。

```cpp
//求乘法逆元
#include<iostream>
using namespace std;

int egcd(int a,int b,int r0, int r1,int s0,int s1,int arr[]){
	if(b==0){
		arr[0]=r0;
		arr[1]=s0;
		return a;
	}
	else{	
		egcd(b,a%b,r1,r0-a/b*r1,s1,s0-a/b*s1,arr);
	}
}

bool judge_mod_reverse(int a,int m,int array[]){ 
	int d = egcd(a,m,1,0,0,1,array);
	if(d == 1){
		while( array[0] <= 0){
			array[0]+=m;
		}
		return 1;
	}
	else{
		return 0;
	}
}

int main(){
	int inverse[2];
	if( judge_mod_reverse(73,131,inverse) ){
		cout<<inverse[0];
	}
	else{
		cout<<"nil";
	}
	
}

//mod指数运算
#include<iostream>
using namespace std;

int rec_mod_exp(int x,int y,int m){
	if( y == 0){
		return 1;
	}
	int z = rec_mod_exp(x,y/2,m);
	if((y & 1) == 0){
		return z*z%m;
	}
	else{
		return x*z*z%m;
	}
}

int main(){
	cout<<rec_mod_exp(2,11,9);
}

```

3、设p = 23和a = 3，使用费尔马小定理计算a^{2019} mod p?

解：

设所求值为 y ， y ∈ N

23是素数

∵ 2019 = 22*91+17

由费马小定理有：a^{2019} mod p = a^{17} mod p

∴ 3^17 ≡ y (mod 23) , 

得: y = 16

4、使用欧拉定理计算2^{100000} mod 55。

ϕ(55) = ϕ(5) * ϕ(11) = 40

100000 = 40 * 2500

易得所求值为 1

5、手动计算7^{1000}的最后两个数位等于什么？

7=7
7*7 = 49
49*7 = 343
43 * 7 = 301

01 * 7 = 07
07*7 = 49

...

又 1000 mod 4 = 0
易得最后两个数位是
01