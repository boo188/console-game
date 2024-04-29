/*
<hangman game>
*/

#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <string.h>

int hangman();
void score(int);

int main(void)
{
  printf("Game Start!\n\n");
  hangman();

}

int hangman()
{
  int select;
  int num = 25;
  //num : 내가 저장할 단어의 개수
  char words[25][10] = {
    {"dog"},
    {"cat"}, 
    {"tiger"}, 
    {"monkey"}, 
    {"rabit"}, 
    {"duck"},
    {"turtle"},
    {"cow"},
    {"chicken"},
    {"lion"},
    {"snake"},
    {"horse"},
    {"mouse"},
    {"giraffe"},
    {"penguin"},
    {"whale"},
    {"deer"},
    {"sheep"},
    {"poat"},
    {"wolf"},
    {"fox"},
    {"elephant"},
    {"bear"},
    {"camel"},
    {"dolphin"}
  };
  srand(time(NULL));
  //rand()함수를 사용하기 위해 초기화해줌.
  select = rand() % num;
  //select는 0부터 24사이에서 무작위로 저장됨.
  char problem[10] = {0,};
  //rand()함수로 정해진 단어를 problem에 저장.
  char answer[10] = {0,};
  //콘솔 창에 출력할 문자 배열.
  //언더바를 출력하고 나중에 사용자가 정답을 맞추면 알파벳으로 저장.
  char char_answer;
  //사용자가 입력한 문자열을 입력받을 변수.

  int len_answer;
  //rand()함수에 의해 정해진 단어의 문자 길이를 저장하는 변수.
  int count = 0;
  //사용자가 정답을 맞추는 것을 실패한 횟수를 세리기 위함.

  len_answer = strlen(words[select]);
  //내가 저장한 words들 사이에서 rand()함수에 의해 정해진 단어의 문자 길이를 strlen()함수를 이용하여 저장.
  strcpy(problem, words[select]);
  //strcpy(a, b)란 a에 b를 복사해 붙여넣음.
  //정해진 단어를 problem 변수에 복사 붙여넣음.


  //문자의 길이만큼 '_'를 공백을 기준으로 반복.
  for (int i = 0; i < len_answer; i++)
  {
    answer[i] = '_';
    //answer[i]배열에 문자의 길이만큼 언더바 저장.
    printf(" %c", answer[i]);
    //공백 + '_' 출력 (문자열의 길이만큼)
  }
  printf("\n");

  while (1)
  {
    printf("Please Enter An Alphabet. : ");
    scanf("%c", &char_answer);
    //사용자로부터 알파벳을 입력받음.
    getchar();
    int right = 0;
    //맞으면 1로 저장
    for (int i = 0; i < len_answer; i++)
    {
      //정해진 단어와 사용자가 입력한 값이 같으면 
      if (problem[i] == char_answer)
      {
        answer[i] = problem[i];
        //언더바로 저장되어있던 answer배열에 정해진 단어를 저장.
        right = 1;
      }
    }
    //같지 않으면
    if (right == 0)
    {

      count++;
      //횟수 1 증가.
      printf("wrong!\n");
      
      score(count);
      //틀린 횟수만큼 행맨 그리는 함수 부르기.
    }

    //answer배열 출력.
    for (int i = 0; i < len_answer; i++)
    {
      printf(" %c", answer[i]);
    }
    printf("\n");

    //answer와 problem이 완전히 같지 않거나 틀린 횟수가 6이 아니면 밑에 두 if문은 실행되지 않고 계속 반복
    if (strcmp(answer, problem) == 0)
    {
      //strcmp(a, b)함수란 a와 b의 문자열이 같으면 0을 반환 a가 b보다 크면 1을 반환, a가 b보다 작으면 -1d을 반환.
      printf("!!!!! you win !!!!!\n");
      break;
    }
    if (count == 6)
    {
      printf("You lost. Try again.\n");
      printf("The answer is \"%s\"", problem);
      break;
    }

  }
  return 0;
}

void score(int count)//틀린 횟수만큼 행맨 그리는 함수
{
  if (count == 0)
  {
    printf(" |--|\n");
    printf("    |\n");
    printf("    |\n");
    printf("    |\n");
    printf(" ___|\n");
  }

  else if (count == 1)
  {
    printf(" |--|\n");
    printf(" O  |\n");
    printf("    |\n");
    printf("    |\n");
    printf(" ___|\n");
  }
  else if (count == 2)
  {
    printf(" |--|\n");
    printf(" O  |\n");
    printf(" |  |\n");
    printf("    |\n");
    printf("    |\n");
  }
  else if (count == 3)
  {
    printf(" |--|\n");
    printf(" O  |\n");
    printf("/|  |\n");
    printf("    |\n");
    printf(" ___|\n");
  }
  else if (count == 4)
  {
    printf(" |--|\n");
    printf(" O  |\n");
    printf("/|\\ |\n");
    printf("    |\n");
    printf(" ___|\n");
  }
  else if (count == 5)
  {
    printf(" |--|\n");
    printf(" O  |\n");
    printf("/|\\ |\n");
    printf("/   |\n");
    printf(" ___|\n");
  }
  else if (count == 6)
  {
    printf(" |--|\n");
    printf(" O  |\n");
    printf("/|\\ |\n");
    printf("/ \\ |\n");
    printf(" ___|\n");
  }
}
