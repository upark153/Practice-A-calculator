# Practice-A-calculator
This is a programming exercise to create a calculator in c language.
- - -
﻿
1.

100개의 포켓볼을 오박사에게 지급 받았습니다.


2.

피카츄 파이리 꼬북이 메타몽 들이 각각 들어있다고 하는데,


3.

지우는 이 포켓볼을 다 까보기로 했다.


4.

포켓볼을 깔 때마다

피카츄 파이리 꼬북이 메타몽 중에

하나가 랜덤으로 선택되어 나오게 코드를 짜고


5.

포켓볼 100개를 다 깠을 때

피카츄 파이리 꼬북이 메타몽이 각각 몇개씩 나왔는지 표시하시오


6.

메타몽은 집계 이후

피카츄 파이리 꼬부기 메타몽 중 랜덤으로

변신되므로


7.

최종집계를 표현하게 구현하시오


연속뽑기

한번씩 뽑기 둘다???



문제를 보고 든 생각.

1. 포켓볼 100개를 받아야 한다.

2. 포켓볼 안에 피카츄 파이리 꼬북이 메타몽이 들어있다.

3. 포켓볼을 깐다(100번을 반복해야 겠지?, 그리고 랜덤으로 나온다)

4. 포켓볼 다 깐 후 결과 = 피카츄 : ?개 , 파이리 : ?개, 꼬북이 : ?개, 메타몽 : ?개

5. 집계 이후 메타몽은 피카츄 파이리 꼬부기 메타몽 중 랜덤 변신 하여 최종 집계

= 피카츄 ?개, 파이리 ?개, 꼬부기 ?개, 메타몽 : ?개

﻿
- - -
```
#include <stdio.h> // main 함수 사용하기 위해
#include <stdlib.h> // srand, rand 함수 사용하기 위해
#include <time.h> // time 함수 사용하기 위해

int main(void)
{
     int start = 0; // 1을 누르면 포켓볼 100개 까기 시작, 0을 누르면 포켓볼 안깔거야 를 만들기 위해서
     int poketmon, poketball; // poketmon 은 피카츄 파이리 꼬북이 메타몽 랜덤 개봉하기 위한 변수
                                     // poketball 은 100개까지 반복적으로 개봉하기 위한 변수
     int pica = 0;         // 피카츄 숫자 세기 위해서
     int pail = 0;         //  파이리 숫자 세기 위해서
     int kkobo = 0;     // 꼬북이 숫자 세기 위해서
     int meta = 0;      // 메타몽 숫자 세기 위해서
     int metago = 0;   // 메타몽 변신 숫자 세기 위해서

     srand(time(0));    // 항상 결과를 다른 값을 주기 위해서 선언. 매번 결과값이 똑같다면 진정한 랜덤함수라고 할 수 없기에
     printf("오박사로부터 포켓볼 100개를 받았습니다 \n");
     printf("1을 누르면 포켓볼 100개 개봉, 0을 누르면 개봉 안할꺼야 \n");
     scanf("%d", &start);
     if(start==1)  // 1을 누른다면 아래 값 출력
     {
            for(poketball=0; poketball<100; poketball++) // 포켓볼이 0이고, 100까지 반복, 1씩 증가
            {
              printf("++포켓볼 던져써 ! 누구야 넌++\n"); 
              poketmon = rand() %4 // 0(피카츄), 1(파이리), 2(꼬북이) 3(메타몽) 랜덤 
              if(poketmon==0)
              {
                 printf("피카츄\n");
                 pica++;
              }
             else if(poketmon==1)
             {
                printf("파이리\n");
                pail++;
             }
            else if(poketmon==2)
            {
               printf("꼬북이\n");
               kkobo++;
            }
           else
            {
               printf("메타몽\n");
               meta++;
            }
          }
          printf("친구들아 몇명이야?\n"); // 반복문을 닫고 마지막 결과 값 출력
          printf("피카츄:%d 파이리: %d 꼬북이: %d 메타몽: %d\n", pica, pail, kkobo, meta);
   }     
  else if(start==0) // 0을 누르면 아래 값 출력
  {
    printf("개봉 안할거라능\n");
  }
 printf("메타몽이 변신 하려면 1, 안하려면 0 : \n");
 scnaf("%d", &start);
 if(start==1)
 {
        for(poketball=0; poketball<meta; poketball++)   // 메타몽이 변신하므로 메타몽 값보다 작을때까지 반복
        {
              printf("++메타몽 변신!!++\n");
              poketmon = rand() %4;   // 메타몽이 피카츄,파이리,꼬북이,메타몽 으로 변신
              if(poketmon==0)
              {
                     printf("피카츄\n");
                     pica++;
              }
              else if(poketmon==1)
             {
                    printf("파이리\n");
                    pail++;
             }
             else if(poketmon==2)
             {
                   printf("꼬북이\n");
                   kkobo;
             }
             else
             {
                  printf("메타몽\n");
                  metago++;      // 메타몽 변신 값이 커진다.
             }
        }
        printf("메타몽 변신 완료! 최종 몇명이야?\n");
        printf("피카츄:%d, 파이리:%d 꼬북이:%d 메타몽:%d\n", pica, pail, kkobo, metago);
 }
 else if(start==0)
 {
    printf("변신 안할꺼라능\n");
 }
 return 0;
}
```
- - -
﻿1.연속뽑기
- - -
```
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main(void)
{
    int pica=0;
    int pail=0;
    int kkobo=0;
    int poketball, poketmon;

    printf("오박사로부터 포켓볼 100개를 받았습니다.\n");
    printf("지우는 모두 다 까볼꺼에요\n");

    srand(time(0));

    for(poketball=0; poketball<100; poketball++)
    {
        poketmon=rand()%3; // 피카츄,파이리,꼬북이, 0,1,2
        if(poketmon==0)
        {
            printf("피카츄!\n");
            pica++;
        }
        if(poketmon==1)
        {
            printf("파이리!\n");
            pail++;
        }
        if(poketmon==2)
        {
            printf("꼬북이!\n");
            kkobo++;
        }
    }
    printf("피카츄:%d 파이리:%d 꼬북이:%d\n", pica, pail, kkobo);
}
```
- - -
﻿2.단일 뽑기
- - -
```
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main(void)
{
    int pica=0;
    int pail=0;
    int kkobo=0;
    int poketball, poketmon;
    int ppobgi;

    printf("오박사로부터 포켓볼 100개를 받았습니다.\n");
    printf("지우는 모두 다 까볼꺼에요\n");

    srand(time(0));

    for(poketball=0; poketball<100; poketball++)
    {
        printf("1을 누르면 포켓볼 뽑기 시작!,0을 누르면 종료 : ");
        scanf("%d", &ppobgi);
        if(ppobgi==1)
            {
                poketmon=rand()%3;
                if(poketmon==0)
                {
                    printf("피카츄!\n");
                    pica++;
                }
                else if(poketmon==1)
                {
                    printf("파이리!\n");
                    pail++;
                }
                else
                {
                    printf("꼬북이!\n");
                    kkobo++;
                }
            }
        else if(ppobgi==0)
            break;
    }
    printf("피카츄:%d 파이리:%d 꼬북이:%d\n", pica, pail, kkobo);
    return 0;
}
```
- - -
가위바위보 다시 연속 뽑기
- - -
```
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main(void)
{
    int team;
    int game;
    int jteam_win=0; 
    int steam_win=0;
    int yj, uy;
    double cnt=0;
    double jrate, srate=0;
    srand(time(0));
    team=rand()%2;

    if(team==0)
    {
        printf("재일팀 : 연재, 성일팀 : 의용\n");
    }
    else
    {
        printf("재일팀 : 의용, 성일팀 : 연재\n");
    }
    printf("팀 나누기 완료되었습니다.\n");
    printf("1을 누르면 연속가위바위보 시작, 0을 누르면 종료 : \n");
    scanf("%d",&game);
    if(game==1)
    {
        while(jteam_win!=10 && steam_win!=10)
        {
            cnt=cnt+1;
            printf("가위바위보 시작! %.f 번째 판!\n",cnt);
            yj=rand()%3;
            uy=rand()%3;

            while(yj==uy)
            {
                printf("비겼으므로 재경기합니다\n");
                yj=rand()%3;
                uy=rand()%3;
            }

            if(yj>uy)
            {
                if(yj==2&&uy==0) // 연재:보, 의용:가위 , 의용승리
                {
                    printf("!! 성일 승리\n");
                    steam_win=steam_win+1;
                }
                else // yj=2, uy=1 > 연재:보, 의용:바위 연재승리
                     // yj=1, uy=0 > 연재:바위 의용:가위 연재승리
                {
                    printf("!! 재일 승리\n");
                    jteam_win=jteam_win+1;
                }
                jrate=jteam_win/cnt*100;
                srate=steam_win/cnt*100;
                if(steam_win==0)
                {
                    srate=0;
                }
                printf("재일 %d회 성일 %d회\n", jteam_win, steam_win);
                printf("승률 재일:%.3f %% 성일:%.3f %%\n", jrate, srate);
            }

            else // yj<uy 일 경우
            {
                if(yj==0 && uy==2) // 연재:가위, 의용:보 연재승리
                {
                    printf("!! 재일 승리\n");
                    jteam_win=jteam_win+1;
                }
                else // yj=1, uy=2 > 연재 :바위, 의용:보 의용 승리
                     // yj=0, uy=1 > 연재 :가위, 의용:바위 의용 승리
                {
                    printf("!! 성일 승리\n");
                    steam_win=steam_win+1;
                }
                jrate=jteam_win/cnt*100;
                srate=steam_win/cnt*100;
                if(jteam_win==0)
                {
                    jrate=0;
                }
                printf("재일 %d회 성일 %d회 \n", jteam_win, steam_win);
                printf("승률 재일:%.3f %% 성일:%.3f %%\n", jrate, srate);
            }
        }
    }    
    else(game==0);
        printf("게임을 종료합니다\n");
    return 0;
}
```
- - -
계산기 만들기
- - -
```
#include <stdio.h>

int add(int a, int b)  // 덧셈을 위한 선언
{
    int result;          // 결과 값 변수 선언
    result = a + b;   // 결과 값 = 더하기
    return result;     // 결과 값 반환한다. 이유는? 메모리에 값이 들어가고(result값), 다시 result값을 계산하려면 초기화 느낌  ?
}
int minus(int a, int b) // 뺄셈을 위한 선언
{
    int result;
    result = a - b;
    return result;
}
int multiple(int a, int b) // 곱셈을 위한 선언
{
    int result;
    result = a * b;
    return result;
}
int division(int a, int b) // 나눗셈을 위한 선언
{
    int result; 
    result = a / b;
    return result;
}

int main(void)
{
     int a, b; // 뒤에 연산을 하기 위한 변수 다시 선언!
     int c; // 반복문을 하기 위한 변수 선언 !, 1=덧셈, 2=뺄셈, 3=곱셈, 4=나눗셈 5= 종료
            // 왜냐하면 한번 계산을 끝냈을 때 다시 계속 계산 해야 하므로(계산기는 계속 계산한다)
     while(c!=5) // 5입력 하면 반복문 종료!
      {
         printf("두개의 수 입력(두개의 수 사이 공백): ");
         scanf("%d %d", &a, &b);
         printf("1입력=덧셈, 2입력=뺄셈, 3입력=곱셈, 4입력=나눗셈, 5입력=종료 : ");
         scanf("%d", &c);
         if(c==1) // 덧셈이겟죠?
         {
           printf("%d \n", add(a,b)); // 출력한다, 위에 덧셈 식을 
         }
        else if(c==2) // 뺄셈이겠죠?
         {
           printf("%d \n", minus(a,b)); // 출력한다, 위에 뺄셈 식을
         }
        else if(c==3) // 곱셈이겠죠?
         {
           printf("%d \n", multiple(a,b)); // 출력한다, 위에 곱셈 식을
         }
        else if(c==4) // 나눗셈이겠죠?
         {
          printf("%d \n", division(a,b)); // 출력한다, 위에 나눗셈 식을
         }
      }
      return 0;
}
```
```
#include <stdio.h>

int add(int a, int b)
{
    int result;
    result = a+b;
    return result;
}
int minus(int a, int b)
{
    int result;
    result = a-b;
    return result;
}
int multiple(int a, int b)
{
    int result;
    result = a*b;
    return result;
}
int division(int a, int b)
{
    int result;
    result = a/b;
    return result;
}

int main(void)
{
    int a,b;
    int c;

    while(c!=5)
    {
        printf("두 수 입력 : ");
        scanf("%d %d", &a, &b);
        printf("더하기=1, 뺼셈=2, 곱셈=3, 나눗셈=4, 종료=5 : ");
        scanf("%d", &c);

        switch(c)
        {
            case 1: printf("덧셈 결과:%d\n", add(a,b)); break;
            case 2: printf("뺄셈 결과:%d\n", minus(a,b)); break;
            case 3: printf("곱셈 결과:%d\n", multiple(a,b)); break;
            case 4: printf("나눗셈 결과:%d\n", division(a,b)); break;
            case 5: printf("종료\n");
        }
    }
    return 0;
}
```
         
