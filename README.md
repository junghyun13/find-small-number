# find-small-number
# c program
# Take the numbers from A and B one by one, multiply the two numbers and add them up. What is the smallest value? A와B에 담긴 수를 하나씩 뽑아서 두수를 곱한값을 누적해서 더하는데 이때 가장 작은 값은 얼마인가?
#include <stdio.h>
#include <stdbool.h>
#include <stdlib.h>
// A_len은 배열 A의 길이입니다.
// B_len은 배열 B의 길이입니다.
int compare(const int *a, const int*b){
    return *a>*b?1:-1;
}
int solution(int A[], size_t A_len, int B[], size_t B_len) {
    int answer = 0;
    qsort(A, A_len,sizeof(int),compare); //정렬할 배열,요소의 개수,요소의 크기,비교함수를 넣어줌
    qsort(B, B_len,sizeof(int),compare);
    for (int i=0; i < A_len; i++){
        // printf("%d %d\n", A[i],B[B_len-1-i]);
        answer += A[i]*B[B_len-1-i];
    }
    return answer;
}
#python
def solution(A,B):
    answer = 0
    A.sort()
    B.sort()
    for i in range(len(A)):
        answer += A[i]*B[len(B)-1-i]

    return answer
#intput-->A=[1,4,2],B=[5,4,4]
#result-->29 (1*5+2*4+4*4)
