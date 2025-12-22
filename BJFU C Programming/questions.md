1. 1，2，3，4可以组成多少个不含重复数字的三位数
#include<stdio.h>
int main()
{
    int number=0;
    for(int i=1;i<5;i++)
    {
        for(int j=1;j<5;j++)
        {
            for(int k=1;k<5;k++)
            if(i!=j&&j!=k&&i!=k)
            {
                printf("%d%d%d ",i,j,k);
                number++;
            }
        }
    }
    printf("可以组成%d个三位数",number);
    return 0;
}
2.一个数字加上156 100为完全平方数
#include<stdio.h>
#include<math.h>
int main()
{
    for(int number=0;number<1000;number++)
    {
        int x=sqrt(number+100);
        int y=sqrt(number+156);
        if(x*x==number+100&&y*y==number+156)
        {
            printf("%d",number);
            break;
        }
    }
    return 0;
}
3.三个数从小到大
#include<stdio.h>
void exchange(int*p1,int*p2)
{
    int temp;
    temp=*p1;*p1=*p2;*p2=temp;

}
int main()
{
    int x,y,z;
    scanf("%d %d %d",&x,&y,&z);
    if(x>y)
    {
        exchange(&x,&y);
    }
    if(x>z)
    {
        exchange(&x,&z);
    }//先要确定第一位
    if(y>z)
    {
        exchange(&y,&z);
    }
    printf("%d %d %d",x,y,z);
    return 0;
}
4.输出九九乘法表
#include<stdio.h>
int main()
{
    int l,r;
    for(l=1;l<10;l++)
    {
        for(r=1;r<=l;r++)
        {
            printf("%d*%d=%d ",r,l,l*r);
        }
        printf("\n");
    }
    return 0;
}
5.兔子问题（fib数列）
#include<stdio.h>
int Fib(int n)
{
    if(n>0)
    {
        return Fib(n-1)+Fib(n-2);
    }
    if(n=0)
    return 1;
}
int main()
{
    for(int i=1;i<13;i++)
    {
        printf("%d",Fib(i));
    }
}
6.输出质数
#include<stdio.h>
#include<math.h>
int main()
{
    int flag=1;
    for(int number=101;number<=200;number++)
    {
        flag=1;
        for(int i=2;i<=sqrt(number);i++)
        {
            if((number%i)==0)
            {
                flag=0;
                break;
            }

        }
        if(flag)
        {
            printf("%d ",number);
        }
    }
    return 0;
}
7.水仙花数
#include<stdio.h>
int main()
{
    int a,b,c;
    for(int i=100;i<1000;i++)
    {
        a=i/100;
        b=(i/10)%10;
        c=i%10;
        if(a*a*a+b*b*b+c*c*c==i)
        {
            printf("%d ",i);
        }
    }
    return 0;
}
8.将整数分解质因数
#include<stdio.h>
int main()
{
    int input;
    printf("请输入一个一百以内的整数：");
    scanf("%d",&input);
    printf("%d=",input);
    for(int i=2;i<=input;i++)
    {
        while(input!=i)
        {
            if(input%i==0)
            {
                printf("%d*",i);
                input/=i;
            }
            else
            break;
        }

    }
    printf("%d",input);
    return 0;
}
9.分项统计
#include<stdio.h>
int main()
{
    int letters=0,space=0,digit=0,others=0;
    char x;
    while((x=getchar())!='\n')
    {
        if((x>='a'&&x<='z')||(x>='A'&&x<='Z'))
        {
            letters++;
        }
        else if(x==' ')
        {
            space++;
        }
        else if(x>='0'&&x<='9')
        {
            digit++;
        }
        else
        {
            others++;
        }
    }
    printf("%d %d %d %d",letters,space,digit,others);
}
10.控制数字相加
#include<stdio.h>
int main()
{
    int a,number,sum=0;
    printf("请输入要相加的数字以及相加的次数：");
    scanf("%d %d",&a,&number);
    for(int i=0;i<number;i++)
    {
        sum+=a;
        a=a*10+a;
    }
    printf("%d",sum);
    return 0;
}
11.完数(一个数字可以表示为其质因数之和)
#include<stdio.h>
int main()
{
    int x,check=1;
    printf("请输入一个数字：");
    scanf("%d",&x);
    for(int i=2;i<=x;i++)
    {
        while(x!=i)
        {
            if(x%i==0)
            {
            x/=i;
            check+=i;
            }
            else
            break;
        }
        
    }
    if(x==check)
    {
        printf("该数字是完数");
    }
    else
    printf("该数字不是完数");
    return 0;
}
12.小球反弹
#include<stdio.h>
int main()
{
    double sum=0;
    double height=10;
    for(int i=0;i<10;i++)
    {
        sum+=height;
        height/=2;
    }
    printf("总上升高度是：%.5f",sum);
    printf("第十次上升高度为：%.5f",height);
    return 0;
}
13.猴子吃桃子
#include<stdio.h>
int main()
{
    int r=1;
    for(int i=0;i<9;i++)
    {
        r=(r+1)*2;
    }
    printf("%d",r);
    return 0;
}
14.乒乓球比赛(注意边界)
#include<stdio.h>
int main()
{
    char i,j,k;
    for(i='x';i<='z';i++)
    {
        if(i!='x')
        {
            for( k='x';k<='z';k++)
            {
                if(k!='x'&&k!='z')
                {
                    for(j='x';j<='z';j++)
                    {
                        if(i!=j&&j!=k&&i!=k)
                        {
                        printf("a的对手是%c，b的对手是%c，c的对手是%c",i,j,k);
                        }
                    }
                }
            }
            
        }
    }
    return 0;
}
15.数列问题
#include<stdio.h>
int main()
{
    int up1=1,up2=2,down1=1,down2=1;
    int t1,t2;
    double sum=0.0;
    for(int i=0;i<20;i++)
    {
        sum+=(double)up2/down2;
        t1=up2;
        up2+=up1;
        up1=t1;
        t2=down2;
        down2+=down1;
        down1=t2;

    }
    printf("%.2f",sum);
    return 0;
}
16.累加

#include<stdio.h>
int main()
{
    int sum1=0,sum2=1;
    for(int i=1;i<21;i++)
    {
        sum2*=i;
        sum1+=sum2;
        
    }
    printf("%d",sum1);
    return 0;
}
17.递归阶乘
#include<stdio.h>
int Ac(int n)
{
    if(n>0)
    return n*Ac(n-1);
    if(n==0)
    return 1;
}
int main()
{
    int result=Ac(5);
    printf("%d",result);
    return 0;
}
18.递归年龄
int age(int n)
{
    if(n==1)//注意n==1一定要写在n>0判断的前面，否则永远无法执行
    return 10;
    if(n>0)
    return 2+age(n-1);
}
int main()
{
    printf("%d",age(5));
    return 0;
}
19.求几位数，逆序打印
#include<stdio.h>
int main()
{
    int input,number=0;
    printf("请输入一个数字：");
    scanf("%d",&input);
    while(input/10!=0)
    {
        printf("%d ",input%10);
        number++;
        input/=10;
    }
    printf("%d",input);
    printf("\n");
    printf("这是一个%d位数",number+1);
    return 0;
}
20.五位数判断是否是回文数
#include<stdio.h>
int main()
{
    printf("请输入一个五位数:");
    int input;
    scanf("%d",&input);
    if((input%10==input/10000)&&((input/1000)%10==(input/10)%10))
    printf("该数字是回文数");
    else
    printf("该数字不是回文数");
    return 0;
}
//拓展：任意输入一个数字判断是否是回文数
#include<stdio.h>
int main()
{
    int input,check,new;
    scanf("%d",&input);
    check=input;
    while(input>0)
    {
        new=10*new+input%10;
        input/=10;
    }
    if(check==new)
    {
        printf("该数字是回文数");
    }
    else
    {
    printf("该数字不是回文数");
    }
}
21.递归反写字符串
#include<stdio.h>
void rprint(char *p)
{
    if(*p=='\0')
    {
        return;
    }
    rprint(p+1);
    printf("%c",*p);
    
}
int main()
{
    char str[6];
    scanf("%5s",str);
    rprint(str);
    return 0;
}
#include<stdio.h>
#include<string.h>
int main()
{
    char arr[100];
    scanf("%s",arr);
    int len=strlen(arr);
    for(int i=len-1;i>=0;i--)
    {
        printf("%c",arr[i]);
        
    }
    return 0;
}
22.判断是星期几(monday，tuesday，wednesday，thursday，friday，saturday，sunday)
#include<stdio.h>
int main()
{
    printf("请输入首字母(小写)：");
    char letter=getchar();
        switch(letter)
        {
            case 'm':
            printf("monday");break;
            case 'w':
            printf("wednesday");break;
            case 'f':
            printf("friday");break;
            case 't':
            printf("请输入第二个字母");
            getchar();
            if(getchar()=='h')
            {
                printf("thursday");
            }
            else
            {
                printf("tuesday");
            }
            break;
            case 's':
            printf("请输入第二个字母");
            getchar();
            if(getchar()=='a')
            {
                printf("saturday");
            }
            else
            {
                printf("sunday");
            }
            break;
        }
    return 0;
}
23.100以内的质数
#include<stdio.h>
#include<math.h>
int main()
{
    int flag=1;
    printf("2 3 ");
    for(int i=4;i<=100;i++)
    {
        flag=1;
        for(int j=2;j<=sqrt(i);j++)
        {
            if(i%j==0)
            {
                flag=0;
                break;
            }
        }
        if(flag)
        {
            printf("%d ",i);
        }
    }
    return 0;
}
24.数组逆序输出+柔性数组
#include<stdio.h>
struct S
{
    int n;
    int arr[];
};
int main()
{
    struct S*p=(struct S*)malloc(sizeof(struct S)+100*sizeof(int));
    printf("请输入你要存入的数字个数：");
    int x;
    scanf("%d",&x);
    for(int i=0;i<x;i++)
    {
       scanf("%d",&p->arr[i]); 
    }
    for(int j=x-1;j>=0;j--)
    {
        printf("%d ",p->arr[j]);
    }
    free(p);
    p=NULL;
    return 0;
}

25.从小到大的数组插入
#include<stdio.h>
#include<stdlib.h>
struct S
{
    int n;
    int arr[];
};
int main()
{
    struct S*p=(struct S*)malloc(sizeof(struct S)+100*sizeof(int));
    printf("请输入你要存入的数字个数：");
    int x;
    scanf("%d",&x);
    printf("请按照从小到大的顺序输入数组中\n");
    for(int i=0;i<x;i++)
    {
       scanf("%d",&p->arr[i]); 
    }
    printf("请输入你要插入的数字：");
    int insert,flag;
    scanf("%d",&insert);
    for(int j=0;j<x;j++)
    {
        if(insert>p->arr[j])
        flag=j+1;
        break;
    }
    for(int k=x;k>flag;k--)
    {
        p->arr[k]=p->arr[k-1];
    }
    p->arr[flag]=insert;
    for(int i=0;i<=x;i++)
    {
        printf("%d ",p->arr[i]);
    }
    free(p);
    p=NULL;
    return 0;
}//插入排序一定是从后往前！！！！
26.
//c语言中所有的排序
//1.选择排序
#include<stdio.h>
int main()
{
    int flag,temp;
    int arr[10]={2,3,1,6,4,5,8,7,10,9};
    for(int i=0;i<10;i++)
    {
        flag=i;
        for(int j=i+1;j<10;j++)
        {
            if(arr[j]<arr[flag])
            {
            flag=j;
            }
        }
        if(flag!=i)
        {
            temp=arr[i];
            arr[i]=arr[flag];
            arr[flag]=temp;
        }
    }
    for(int i=0;i<10;i++)
    {
        printf("%d ",arr[i]);
    }
    return 0;
}
//2.冒泡排序
#include<stdio.h>
int main()
{
    int arr[10]={2,3,1,6,4,5,8,7,10,9};
    int temp;
    for(int i=0;i<9;i++)
    {
        for(int j=0;j<9-i;j++)//每次是确定最大的那一个
        {
            if(arr[j+1]<arr[j])
            {
                temp=arr[j+1];
                arr[j+1]=arr[j];
                arr[j]=temp;
            }
        }
    }
    for(int i=0;i<10;i++)
    {
        printf("%d ",arr[i]);
    }
    return 0;
}
//3.插入排序（大概就是先“同化”，再将原本的key重新赋值到其应在的位置）
#include<stdio.h>
int main()
{
    int arr[10]={2,3,1,6,4,5,8,7,10,9};
    int key,j;
    for(int i=1;i<10;i++)
    {
        key=arr[i];
        j=i-1;
        while(j>=0&&arr[j]>key)
        {
            arr[j+1]=arr[j];
            j--;
        }
        arr[j+1]=key;
    }
    for(int i=0;i<10;i++)
    {
        printf("%d ",arr[i]);
    }
    return 0;
}
#include<stdio.h>
int main()
{
    int arr[4]={8,2,7,1};
    int key,j;
    for(int i=1;i<4;i++)
    {
        key=arr[i];
        j=i-1;
        while(j>=0&&arr[j]>key)
        {
            arr[j+1]=arr[j];
            j--;
        }
        arr[j+1]=key;

    }
    for(int i=0;i<4;i++)
    {
        printf("%d ",arr[i]);
    }
    return 0;
}
27.打印杨辉三角
#include<stdio.h>
int main()
{
    int a[10][10];
    printf("\n");
    for(int i=0;i<10;i++)
    {
        a[i][0]=1;
        a[i][i]=1;
    }
    for(int j=2;j<10;j++)
    {
        for(int k=1;k<j;k++)
        {
            a[j][k]=a[j-1][k-1]+a[j-1][k];
        }
    }
    for(int i=0;i<10;i++)
    {
        for(int j=0;j<=i;j++)
        {
            printf("%d ",a[i][j]);
        }
        printf("\n");
    }
    return 0;
}
28.指针将三个数从大到小输出
#include<stdio.h>
void swap(int *p1,int *p2)
{
    int temp;
    temp=*p1;
    *p1=*p2;
    *p2=temp;
}
int main()
{
    printf("请输入三个整数:");
    int a,b,c;
    scanf("%d %d %d",&a,&b,&c);
    if(a<b)
    {
        swap(&a,&b);
    }
    if(a<c)
    {
        swap(&a,&c);
    }
    if(b<c)
    {
        swap(&b,&c);
    }
    printf("%d %d %d",a,b,c);
    return 0;  
}
29.第一个为最大，最后一个为最小
#include<stdio.h>
void swap(int *p1,int *p2)
{
    int temp;
    temp=*p1;
    *p1=*p2;
    *p2=temp;
}
int main()
{
    int arr[10]={3,2,1,4,6,5,7,9,10,8};
    int max=0,min=0;
    for(int i=1;i<10;i++)
    {
        if(arr[i]>arr[max])
        {
            max=i;
        }
        if(arr[i]<arr[min])
        {
            min=i;
        }
    }
    swap(&arr[0],&arr[max]);
    swap(&arr[9],&arr[min]);
    for(int i=0;i<10;i++)
    {
        printf("%d ",arr[i]);
    }
    return 0;
}
30.
//n个整数，前面m个数字放在末尾
//方法一
#include<stdio.h>
#include<stdlib.h>
struct S
{
    int n;
    int arr[];
};
int main()
{
    struct S*p=(struct S*)malloc(sizeof(struct S)+100*sizeof(int));
    int n,m;
    printf("请问你要存入数组的个数为:");
    scanf("%d",&n);
    for(int i=0;i<n;i++)
    {
        scanf("%d",&p->arr[i]);
    }
    printf("\n");
    printf("请问你要调换前多少个数：");
    scanf("%d",&m);
    int temp[m];
    for(int i=0;i<m;i++)//先将前面的m个元素存入temp中
    {
        temp[i]=p->arr[i];
    }
    for(int i=m;i<n;i++)//再将后面的元素向前移动
    {
        p->arr[i-m]=p->arr[i];
    }
    for(int i=0;i<m;i++)//补齐最后的元素
    {
        p->arr[n-m+i]=temp[i];
    }
    for(int i=0;i<n;i++)
    {
        printf("%d ",p->arr[i]);
    }
    free(p);
    p=NULL;
    return 0;
}
//方法二
#include<stdio.h>
#include<stdlib.h>
struct S
{
    int n;
    int arr[];
};
int main()
{
    struct S*p=(struct S*)malloc(sizeof(struct S)+100*sizeof(int));
    int n,m,temp;
    printf("请问你要存入数组的个数为:");
    scanf("%d",&n);
    for(int i=0;i<n;i++)
    {
        scanf("%d",&p->arr[i]);
    }
    printf("\n");
    printf("请问你要调换前多少个数：");
    scanf("%d",&m);
    for(int i=0;i<m;i++)
    {
        temp=p->arr[0];
        for(int j=0;j<n-1;j++)
        {
            p->arr[j]=p->arr[j+1];
        }
        p->arr[n-1]=temp;
    }
    for(int i=0;i<n;i++)
    {
        printf("%d ",p->arr[i]);
    }
    free(p);
    p=NULL;
    return 0;
}
31.键盘输入一个字符串，编写代码获取字符串的长度并输出，要求使用字符指针实现
#include<stdio.h>
int main()
{
    char arr[100];
    gets(arr);
    char *p=arr;
    int number=0;
    while(*p!='\0')
    {
        p++;
        number++;
    }
    printf("%d",number);
    return 0;
}
32.
键盘输入一个长度为len（1 <= len < 30）的字符串，再输入一个正整数 m（1 <= m <= len），将此字符串中从第 m 个字符开始的剩余全部字符复制成为另一个字符串，并将这个新字符串输出。要求用指针处理字符串。
#include<stdio.h>
#include<string.h>
int main()
{
    char str[30]={0};
    scanf("%s",str);
    int m;
    scanf("%d",&m);
    int sz=strlen(str);
    for(int i=m;i<=sz;i++)
    {
        printf("%c",str[i-1]);
    }
    return 0;
}
33.牛牛学习了指针相关的知识，想实现一个 int cal(int *array,int n) 的函数求出长度为 n 的数组的和。
#include<stdio.h>
#include<stdlib.h>
int cal(int *array,int n)
{
    int sum=0;
    for(int i=0;i<n;i++)
    {
        sum+=array[i];
    }
    return sum;
}
int main()
{
    int n;
    scanf("%d",&n);
    int *p=(int *)malloc(n*sizeof(int));
    for(int i=0;i<n;i++)
    {
        scanf("%d",&p[i]);
    }
    int sum=cal(p,n);
    printf("%d",sum);
    free(p);
    p=NULL;
    return 0;
}
34.牛牛试图给一个长度为 n 整数数组排序，即实现一个 void sort(int *array,int n) 
#include<stdio.h>
#include<stdlib.h>
void bubble_sort(int *array,int n)
{
    int temp;
    for(int i=0;i<n-1;i++)
    {
        for(int j=0;j<n-1-i;j++)
        {
            if(array[j]>array[j+1])
            {
                temp=array[j];
                array[j]=array[j+1];
                array[j+1]=temp;
            }
        }
    }
}
int main()
{
    int n;
    scanf("%d",&n);
    int *p=(int *)malloc(n*sizeof(int));
    for(int i=0;i<n;i++)
    {
        scanf("%d",&p[i]);
    }
    bubble_sort(p,n);
    for(int i=0;i<n;i++)
    {
        printf("%d ",*(p+i));
    }
    return 0;
}
//模拟考试现在开始
以下题目是北京林业大学2021-2022学年度第一学期程序设计期末考试试卷
//1.请输入十个-20-20的数字，假设输入的数字都符合要求，输入数字n对小于n的数字进行从小到大的排序，对大于n的数字也进行从小到大的排序
#include<stdio.h>
void bubble_sort(int temp1[],int number)
{
    int temp;
    for(int i=0;i<number-1;i++)
    {
        for(int j=0;j<number-1-i;j++)
        {
            if(temp1[j]>temp1[j+1])
            {
                temp=temp1[j];
                temp1[j]=temp1[j+1];
                temp1[j+1]=temp;
            }
        }
    }
}
int main()
{
    printf("请输入十个在-20到20之间的数字");
    int arr[10];
    for(int i=0;i<10;i++)
    {
        scanf("%d",&arr[i]);
    }
    printf("请输入目标值n:");
    int n;
    scanf("%d",&n);
    int number1=0,number2=0;
    int temp1[10],temp2[10];
    for(int i=0;i<10;i++)
    {
        if(arr[i]<n)
        {
            temp1[number1]=arr[i];
            number1++;
        }
        else
        {
            temp2[number2]=arr[i];
            number2++;
        }
      
    }
    bubble_sort(temp1,number1);
    bubble_sort(temp2,number2);
    for(int i=0;i<number1;i++)
    {
        printf("%d ",temp1[i]);
    }
    printf("\n");
    for(int i=0;i<number2;i++)
    {
        printf("%d ",temp2[i]);
    }
    return 0;
}
//2.输入十组学生的学号，姓名，平时成绩，期末成绩，最终成绩由0.4*平时成绩+0.6*期末成绩组成，请计算出最终成绩最高的学生，并且输出其个人信息
#include<stdio.h>
struct S
{
    char id[10];
    char name[10];
    int score1;
    int score2; 
};
int main()
{
    struct S score_list[10];
    for(int i=0;i<10;i++)
    {
        scanf("%s %s %d %d",score_list[i].id,score_list[i].name,&score_list[i].score1,&score_list[i].score2);
    }
    for(int i=0;i<9;i++)
    {
        struct S temp;
        for(int j=0;j<9-i;j++)
        {
            if(0.4*score_list[j].score1+0.6*score_list[j].score2<0.4*score_list[j+1].score1+0.6*score_list[j+1].score2)
            {
                temp=score_list[j];
                score_list[j]=score_list[j+1];
                score_list[j+1]=temp;
            }
        }
    }
    printf("%s %s %d %d",score_list[0].id,score_list[0].name,score_list[0].score1,score_list[0].score2);
    return 0;
}
//3.输入两个句子，将其中的单词单独作为一行存储
提示：注意判断的先后顺序！！！
笔者在这里出现了一些逻辑上的问题
#include<stdio.h>
int main()
{
    char sentence1[23] = "English is a language";
    char sentence2[22] = "C is also a language";
    for(int i = 0; i < 23; i++)
    {
        if(sentence1[i] == '\0')
        {
            break;
        }
        printf("%c", sentence1[i]);
        if(sentence1[i] == ' ')
        {
            printf("\n");
        }
    }
    printf("\n");
    for(int i = 0; i < 22; i++)
    {
        if(sentence2[i] == '\0')
        {
            break;
        }
        printf("%c", sentence2[i]);
        if(sentence2[i] == ' ')
        {
            printf("\n");
        }
    }
    return 0;
}
//4.同上题，is a the是关键字，遇到时直接跳过，并继续输出下一个单词
#include<stdio.h>
int main()
{
    char sentence1[23] = "English is a language";
    char sentence2[22] = "C is also a language";
    for(int i = 0; i < 23; i++)
    {
        if(sentence1[i] == '\0')
        {
            break;
        }
        if(sentence1[i] =='a'&&(sentence1[i+1]==' '||sentence1[i+1]=='\0'))
        {
            i+=1;
        }
        if(sentence1[i] =='i'&&sentence1[i+1] =='s'&&(sentence1[i+2]==' '||sentence1[i+2]=='\0'))
        {
            i+=2;
        }
        if(sentence1[i] == ' ')
        {
            printf("\n");
            continue;
        }
        printf("%c", sentence1[i]);
    }
    printf("\n");
    for(int i = 0; i < 22; i++)
    {
        if(sentence2[i] == '\0')
        {
            break;
        }
        if(sentence2[i] =='a'&&(sentence2[i+1]==' '||sentence2[i+1]=='\0'))
        {
            i+=1;
        }
        if(sentence2[i] =='i'&&sentence2[i+1] =='s'&&(sentence2[i+2]==' '||sentence2[i+2]=='\0'))
        {
            i+=2;
        }
        if(sentence2[i] == ' ')
        {
            printf("\n");
            continue;
        }
        printf("%c", sentence2[i]);
    }
    return 0;
}

