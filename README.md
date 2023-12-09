- 👋 Hi, I’m @b11042024
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
#include<bits/stdc++.h>
#include<conio.h>
#include <windows.h>
void color(short x)
{
 if(x>=0 && x<=15)
  SetConsoleTextAttribute(GetStdHandle(STD_OUTPUT_HANDLE), x);
 else
  SetConsoleTextAttribute(GetStdHandle(STD_OUTPUT_HANDLE), 7);
}
using namespace std;
int qp[4][4]={0};
long long int gread=0;
int pd()
{
 int i,j;
 for(i=0;i<4;i++)
 {
 for(j=0;j<4;j++)
 {
 if(qp[i][j]==0)
 {
 return 0;
 }
 if(i==0&&j==0)
 {
 if(qp[i][j]==qp[i+1][j]||qp[i][j]==qp[i][j+1])
 {
  return 0;
 }
 }
 else if(i==0&&j==3)
 {
 if(qp[i][j]==qp[i+1][j]||qp[i][j]==qp[i][j-1])
 {
  return 0;
 }
 }
 else if(i==0)
 {
 if(qp[i][j]==qp[i+1][j]||qp[i][j]==qp[i][j+1]||qp[i][j]==qp[i][j-1])
 {
  return 0;
 }
 }
 else if(i==3&&j==0)
 {
 if(qp[i][j]==qp[i][j+1]||qp[i][j]==qp[i-1][j])
 {
  return 0;
 }
 }
 else if(j==0)
 {
 if(qp[i][j]==qp[i+1][j]||qp[i][j]==qp[i-1][j]||qp[i][j]==qp[i][j+1])
 {
  return 0;
 }
 }
 else if(i==3&&j==3)
 {
 if(qp[i][j]==qp[i-1][j]||qp[i][j]==qp[i][j-1])
 {
  return 0;
 }
 }
 else if(i==3)
 {
 if(qp[i][j]==qp[i-1][j]||qp[i][j]==qp[i][j-1]||qp[i][j]==qp[i][j+1])
 {
  return 0;
 }
 }
 else if(j==3)
 {
 if(qp[i][j]==qp[i-1][j]||qp[i][j]==qp[i][j-1]||qp[i][j]==qp[i+1][j])
 {
  return 0;
 }
 }
 }
 }
 return 1;
}
int sjs()
{
 int num = rand() % 100 + 1;
 if(num<=5)
 {
 return 4;
 }
 else
 {
 return 2;
 }
}
int sc()
{
 for(;;)
 {
 int n=rand()%4;
 int m=rand()%4;
 if(qp[n][m]==0)
 {
 qp[n][m]=sjs();
 return 0;
 }
 
 }
}
void dy(int n)
{
 if(n==0)
 {
 cout<<"  ";
 }
 else if(n==2)
 {
 color(7);
 cout<<" "<<n<<" ";
 color(7);
 }
 else if(n==4)
 {
 color(14);
 cout<<" "<<n<<" ";
 color(7);
 }
 else if(n==8)
 {
 color(6);
 cout<<" "<<n<<" ";
 color(7);
 }
 else if(n==16)
 {
 color(12);
 cout<<" "<<n<<" ";
 color(7);
 }
 else if(n==32)
 {
 color(4);
 cout<<" "<<n<<" ";
 color(7);
 }
 else if(n==64)
 {
 color(13);
 cout<<" "<<n<<" ";
 color(7);
 }
 else if(n==128)
 {
 color(5);
 cout<<" "<<n<<" ";
 color(7);
 }
 else if(n==256)
 {
 color(9);
 cout<<" "<<n<<" ";
 color(7);
 }
 else if(n==512)
 {
 color(3);
 cout<<" "<<n<<" ";
 color(7);
 }
 else if(n==1024)
 {
 color(11);
 cout<<n<<" ";
 color(7);
 }
 else if(n==2048)
 {
 color(10);
 cout<<n<<" ";
 color(7);
 }
 else if(n==4096)
 {
 color(2);
 cout<<n<<" ";
 color(7);
 }
 else
 {
 color(15);
 cout<<n;
 color(7);
 }
}
int main()
{
 srand(time(NULL));
 int i,j;
 cout<<"Game start!(利用w a s d開始控制)"<<endl;
 sc();
 sc();
 cout<<"-------------------------"<<endl; 
 cout<<"|";
 dy(qp[0][0]);
 cout<<"|";
 dy(qp[0][1]);
 cout<<"|";
 dy(qp[0][2]);
 cout<<"|";
 dy(qp[0][3]);
 cout<<"|"<<endl;
 cout<<"-------------------------"<<endl; 
 cout<<"|";
 dy(qp[1][0]);
 cout<<"|";
 dy(qp[1][1]);
 cout<<"|";
 dy(qp[1][2]);
 cout<<"|";
 dy(qp[1][3]);
 cout<<"|"<<endl;
 cout<<"-------------------------"<<endl; 
 cout<<"|";
 dy(qp[2][0]);
 cout<<"|";
 dy(qp[2][1]);
 cout<<"|";
 dy(qp[2][2]);
 cout<<"|";
 dy(qp[2][3]);
 cout<<"|"<<endl;
 cout<<"-------------------------"<<endl; 
 cout<<"|";
 dy(qp[3][0]);
 cout<<"|";
 dy(qp[3][1]);
 cout<<"|";
 dy(qp[3][2]);
 cout<<"|";
 dy(qp[3][3]);
 cout<<"|"<<endl;
 cout<<"-------------------------"<<endl;
 
 for(;;)
 {
 char n;
 n=getch();
 if(n=='w')
 {
 int g=0;
 for(i=0;i<4;i++)
 {
 for(j=1;j<4;j++)
 {
  if(qp[j][i]!=0)
  {
  int k=j;
  while(qp[k-1][i]==0&&k!=0)
  {
  k--;
  }
  qp[k][i]=qp[j][i];
  if(k!=j)
  {
  qp[j][i]=0;
  g=1;
  }
  }
 }
 if(qp[0][i]==qp[1][i]&&qp[0][i]!=0)
 {
  qp[0][i]=qp[0][i]*2;
  gread+=qp[0][i];
  qp[1][i]=qp[2][i];
  qp[2][i]=qp[3][i];
  qp[3][i]=0;
  g=1;
 }
 if(qp[1][i]==qp[2][i]&&qp[1][i]!=0)
 {
  qp[1][i]=qp[1][i]*2;
  gread+=qp[1][i];
  qp[2][i]=qp[3][i];
  qp[3][i]=0;
  g=1;
 }
 if(qp[2][i]==qp[3][i]&&qp[2][i]!=0)
 {
  qp[2][i]=qp[2][i]*2;
  gread+=qp[2][i];
  qp[3][i]=0;
  g=1;
 }
 }
 if(g==0)
 {
 cout<<"換個方向試試~"<<endl;
 continue;
 }
 else
 {
 system("cls");
 }
 }
 else if(n=='d')
 {
 int g=0;
 for(i=0;i<4;i++)
 {
 for(j=2;j>=0;j--)
 {
  if(qp[i][j]!=0)
  {
  int k=j;
  while(qp[i][k+1]==0&&k!=3)
  {
  k++;
  }
  qp[i][k]=qp[i][j];
  if(k!=j)
  {
  qp[i][j]=0;
  g=1;
  }
  }
 }
 if(qp[i][3]==qp[i][2]&&qp[i][3]!=0)
 {
  qp[i][3]=qp[i][3]*2;
  gread+=qp[i][3];
  qp[i][2]=qp[i][1];
  qp[i][1]=qp[i][0];
  qp[i][0]=0;
  g=1;
 }
 if(qp[i][2]==qp[i][1]&&qp[i][2]!=0)
 {
  qp[i][2]=qp[i][2]*2;
  gread+=qp[i][2];
  qp[i][1]=qp[i][0];
  qp[i][0]=0;
  g=1;
 }
 if(qp[i][1]==qp[i][0]&&qp[i][1]!=0)
 {
  qp[i][1]=qp[i][1]*2;
  gread+=qp[i][1];
  qp[i][0]=0;
  g=1;
 }
 }
 if(g==0)
 {
 cout<<"換個方向試試~"<<endl;
 continue;
 }
 else
 {
 system("cls");
 }
 }
 else if(n=='s')
 {
 int g=0;
 for(i=0;i<4;i++)
 {
 for(j=3;j>=0;j--)
 {
  if(qp[j][i]!=0)
  {
  int k=j;
  while(qp[k+1][i]==0&&k!=3)
  {
  k++;
  }
  qp[k][i]=qp[j][i];
  if(k!=j)
  {
  qp[j][i]=0;
  g=1;
  }
  }
 }
 if(qp[3][i]==qp[2][i]&&qp[3][i]!=0)
 {
  qp[3][i]=qp[3][i]*2;
  gread+=qp[3][i];
  qp[2][i]=qp[1][i];
  qp[1][i]=qp[0][i];
  qp[0][i]=0;
  g=1;
 }
 if(qp[2][i]==qp[1][i]&&qp[2][i]!=0)
 {
  qp[2][i]=qp[2][i]*2;
  gread+=qp[2][i];
  qp[1][i]=qp[0][i];
  qp[0][i]=0;
  g=1;
 }
 if(qp[1][i]==qp[0][i]&&qp[1][i]!=0)
 {
  qp[1][i]=qp[1][i]*2;
  gread+=qp[1][i];
  qp[0][i]=0;
  g=1;
 }
 }
 if(g==0)
 {
 cout<<"換個方向試試~"<<endl;
 continue;
 }
 else
 {
 system("cls");
 }
 }
 else if(n=='a')
 {
 int g=0;
 for(i=0;i<4;i++)
 {
 for(j=1;j<4;j++)
 {
  if(qp[i][j]!=0)
  {
  int k=j;
  while(qp[i][k-1]==0&&k!=0)
  {
  k--;
  }
  qp[i][k]=qp[i][j];
  if(k!=j)
  {
  qp[i][j]=0;
  g=1;
  }
  }
 }
 if(qp[i][0]==qp[i][1]&&qp[i][0]!=0)
 {
  qp[i][0]=qp[i][0]*2;
  gread+=qp[i][0];
  qp[i][1]=qp[i][2];
  qp[i][2]=qp[i][3];
  qp[i][3]=0;
  g=1;
 }
 if(qp[i][1]==qp[i][2]&&qp[i][1]!=0)
 {
  qp[i][1]=qp[i][1]*2;
  gread+=qp[i][1];
  qp[i][2]=qp[i][3];
  qp[i][3]=0;
  g=1;
 }
 if(qp[i][2]==qp[i][3]&&qp[i][2]!=0)
 {
  qp[i][2]=qp[i][2]*2;
  gread+=qp[i][2];
  qp[i][3]=0;
  g=1;
 }
 }
 if(g==0)
 {
 cout<<"換個方向試試~"<<endl;
 continue;
 }
 else
 {
 system("cls");
 }
 }
 else
 {
 cout<<"請輸入w、a、s、d"<<endl; 
 continue;
 }
 sc();
 cout<<"分數:"<<gread<<endl;
 cout<<"-------------------------"<<endl; 
 cout<<"|";
 dy(qp[0][0]);
 cout<<"|";
 dy(qp[0][1]);
 cout<<"|";
 dy(qp[0][2]);
 cout<<"|";
 dy(qp[0][3]);
 cout<<"|"<<endl;
 cout<<"-------------------------"<<endl; 
 cout<<"|";
 dy(qp[1][0]);
 cout<<"|";
 dy(qp[1][1]);
 cout<<"|";
 dy(qp[1][2]);
 cout<<"|";
 dy(qp[1][3]);
 cout<<"|"<<endl;
 cout<<"-------------------------"<<endl; 
 cout<<"|";
 dy(qp[2][0]);
 cout<<"|";
 dy(qp[2][1]);
 cout<<"|";
 dy(qp[2][2]);
 cout<<"|";
 dy(qp[2][3]);
 cout<<"|"<<endl;
 cout<<"-------------------------"<<endl; 
 cout<<"|";
 dy(qp[3][0]);
 cout<<"|";
 dy(qp[3][1]);
 cout<<"|";
 dy(qp[3][2]);
 cout<<"|";
 dy(qp[3][3]);
 cout<<"|"<<endl;
 cout<<"-------------------------"<<endl;
 if(pd()==1)
 {
 break;
 }
 }
 cout<<"Game over~"<<endl;
 cout<<"請輸入“quit”並回車退出遊戲"<<endl;
 for(;;)
 {
 char s[10000];
 cin>>s;
 if(strcmp(s,"quit")==0)
 {
 break;
 }
 }
 return 0;
}
