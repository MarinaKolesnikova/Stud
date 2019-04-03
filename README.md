# Stud
#include<iostream>
#include <conio.h>
#include <cstring>
#include<cstdlib>
using namespace std;/////

int check(char s[], int t){
	int i,a=0,b=0,c=0;
	
		for(i=0;i<t;i++){
			if(int(s[i])>=48&&int(s[i])<=57) 
			a=1;
			if(isalpha(s[i])) {
			 b=1;
			if(isupper(s[i])){
			 c=1;
			}}			
}
if (a==1&&b==1&&c==1){
	cout<<"\npassword is ok\n"; return(true);
}
else{
 cout<<"password should cosist of capital letters, numbers and letters "; return(false);}}




class str{
	protected:
char*pw;
int y;
public:
	str() ;
	str(char s[]);
	str(char c);
	str(const str & arr);
	~str(){delete[]pw;}
void	showL(){cout<<y;}
void len(){y=0;}
void	clear();
//	friend void check(char s[]);
	
};
str::str(){
	int i;
	 y=10;
	 pw=new char[y];
	 for(i=0;i<y;i++){
	 	if(i%2==0) pw[i]=rand()%25 + 65;
	 	if(i%3==0) pw[i]=char( rand() %25 +97);
	 	if(i%2!=0&&i%3!=0) pw[i]=char( rand() % 9+48);}
	 cout<<"\nyour password is created:\n";
	 	 for(i=0;i<y;i++)
		  cout<<pw[i];
}
str::str(char s[]){
	int i;
	y=strlen(s);
	pw=new char[y];
	for ( i = 0; i<y; i++){
	pw[i]=s[i];
	cout<<pw[i];}
	cout<<'\n';
}
str::str(char c){
	y=1;
	pw=new char[y];
	pw[0]=c;
}
str::str(const str & arr){
	int i;
	y=arr.y;
pw=new char[arr.y];
	for(i=0;i<y;i++){
		pw[i]=arr.pw[i];
	}
}

void str::clear(){
	int i;
	memset(pw,0,y);
	cout<<'\n';
	//	for(i=0;i<y;i++){
//	cout<<pw[i]<<0;}
//	cout<<'\n';
}

class pass: public str{
	public:
	pass():str() {};
	pass(char s[]):str(s){};
	pass(const pass& er);
	~pass(){delete []pw;}
    
};

pass::	pass(const pass& er){
	int i;
	y=er.y;
	pw=new char[er.y];
	for(i=0;i<y;i++)
		pw[i]=er.pw[i];}

 int main(){
 	bool b,a;
 	int k,i=0;
char c;
char *buff=new char[100];
cout<<"Password should consist of 8 capital letters,\n numbers and letters or more \n enter a password:";

while(b!=1){
while(!a){
 while (c!=13){
 c=getch();
	 if(int(c)==8){
		printf("\b ");
	i=i-1;}
	else{
cout<<"*";
 buff[i]=c;i=i+1;}}
 if(i>8)a=1;
 else {cout<<"\nless then 8, one more time\n";
 i=0;
c=0;}}
b=check(buff,i);
if(b==0){
i=0;c=0;a=0;}}

 char *ch=new char[i]; 
for(k=0;k<i;k++){
	ch[k]=buff[k];
cout<<ch[k];}


pass e;
e.clear();

pass pr(ch);

 return(0);}
