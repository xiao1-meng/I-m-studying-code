# I-m-studying-code
good good study day day up
刚刚在mooc上学到的枚举算法：称硬币：
#include <iostream>
#include <cstring>
using namespace std;
char Left[3][7]; //天平左边硬币
char Right[3][7]; //天平右边硬币
char result[3][7]; //结果
bool IsFake(char c,bool light) ;
//light 为真表示假设假币为轻，否则表示假设假币为重
int main() {
	int t;
	cin >> t;
	while(t--)
	 {
		 for(int i = 0;i < 3; ++i) cin >> Left[i] >> Right[i] >> result[i];
		 for(char c='A'; c<='L';c++) {
	      if( IsFake(c,true) ){
			 cout << c << " is the counterfeit coin and it is light.\n";
			 break;
	 }
	 	else if( IsFake(c,false) ){
	 			cout << c << " is the counterfeit coin and it is heavy.\n";
	 break;
	 }
	 }
	}
	return 0;                                                                   
	} 
	bool IsFake(char c,bool light)
	//light 为真表示假设假币为轻，否则表示假设假币为重
	{
	for(int i = 0;i < 3; ++i) {
	char * pLeft,*pRight; //指向天平两边的字符串
	if(light) {
	pLeft = Left[i];
	pRight = Right[i];
	}
	else {
	pLeft = Right[i];
	pRight = Left[i];
	}
	switch(result[i][0]) {
	case 'u':
	if ( strchr(pRight,c) == NULL)
	return false;
	break;
	case 'e':
	if( strchr(pLeft,c) || strchr(pRight,c))
	return false;
	break;
	case 'd':
	if ( strchr(pLeft,c) == NULL)
	return false;
	break;
	}
	}
  对我来说，难点在于bool函数没有掌握好，并且对代码的前瞻性没有准备，对于跳跃思想和代码的精简，要多花时间才能看懂！	
，难点在于return true;
	}
