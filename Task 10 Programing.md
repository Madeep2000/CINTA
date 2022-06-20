# task 10: Programing

递归在后面

```cpp
#include<iostream>
using namespace std;

int legendre(int q,int p){
	int temp,mod4,mod8;
	int flag = 1;
	
	while(1){
		q %= p;
		mod4 = p % 4;
		mod8 = p % 8;
		if(q == 2){
			return ( mod8 == 1 || mod8 == 7) ? flag*1 : flag*(-1);
		}
		else if(q == 1){
			return 1*flag;
		}
		else if(q == -1){
			return (mod4 == 1) ? flag*1 : flag*(-1);
		}
	
		else if(q % 2 == 0){
			int count = 0;
			while(q % 2 == 0){
				q /= 2;
				count++;
			}
			if(mod8 == 3 || mod8 == 5){
				if(count % 2 != 0){
					flag = (-1)*flag;
				}
			} //分解的2不是偶数个 且 （2/p）为-1时
			
		}
		
		else{
			if(mod4 == 3 && q % 4 == 3){
				flag = flag*(-1);
			}
			temp = p;
			p = q;
			q = temp;
		}
	
	}
			
	
}

int main(){
	int a,b;
	int d;
	while(1){
		cin>>a>>b;
		d = legendre(a,b);
		cout<<d<<endl;		
	}
	return 0;
}

/*递归
int legendre(int q,int p){
	
	if(q>p){
		q = q%p;
	}
	
	int mod4 = p % 4;
	int mod8 = p % 8;
	
	if(q == 2){
		return ( mod8 == 1 || mod8 == 7) ? 1 : -1;
	}
	else if(q == 1){
		return 1;
	}
	else if(q == -1){
		return (mod4 == 1) ? 1 : -1;
	}
	
	else if(q % 2 == 0){
		return legendre(2,p)*legendre(q/2,p);	
	}
	
	else{
		if( mod4 == 1 || q % 4 == 1){
			return legendre(p,q);
		}
		else{
			return legendre(p,q)*(-1);	
		}		
	}
	
}
*/
```

测试：

19 13 

-1

131 19

1

499 131

-1

277 491

1

181 7

-1