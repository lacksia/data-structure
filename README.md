# 1. list
## 리스트 종류
sigly linked list

doubly linked list

circular linked list

## 설명
데이터가 들어올 때마가 메모리를 각각 할당하는 형식 떄문에 메모리 할당 효율이 높음

## 예제 코드
#include <stdio.h>

#include <stdlib.h>

typedef struct list {

 int d;
 
 struct list* p;
 
} LIST;

LIST* root = NULL;

LIST* last = NULL;

void AddList(int a){

 LIST* r = (LIST*)malloc(sizeof(LIST));
 
 r->d = a;
 
 r->p = NULL;
 
 if(root==NULL) root = r;
 
 else           last->p = r;
 
 last = r;
 
}

int main(void){

 AddList(35);
 
 AddList(40);
 
 AddList(45);
 
 while(root){
 
  printf("%d\n", root->d);
  
  root = root->p;
  
 }
 
}

# 2. tree
## 트리 종류
ternary tree

binary tree

perfect binary tree

full binary tree

complete binary tree

binary search tree

## 설명
리스트와 마찬가지로 node 가 있지만 리스트와 다르게 계층을 가지고 각각이 부모 자식의 관계를 가지고 있다.
## 예제 코드
#include <stdio.h>

#include <stdlib.h>

typedef struct Tree {

struct Tree *l, *r;
    
int d;
    
} T;

void print(T* p){

   printf("%d\n", p->d);
   
   if(p->l) print(p->l);
   
   if(p->r) print(p->r);  
   
}

T* mem(){

 T* p=(T*)malloc(sizeof(T));
 
 p->l=p->r=NULL;
 
 return(p);
 
}

int main(void){

   T *r, *r1, *r2, *l1;
    
   l1= (T*)mem(); l1->d=3; 
    
   r2= (T*)mem(); r2->d=8; 
   
   r1= (T*)mem(); r1->d=7; r1->r=r2;
   
   r= (T*)mem(); r->d=5; r->l=l1;  r->r=r1;
   
   print(r);
    
}

# 3. graph
## 설명
트리와 다르게 연결 방향,유무,갯수가 자유롭고 계층과 부모 자식 관계의 구분이 없다.

# 4. 소감
솔직히 처음 들었을 때는 정말 이해하기가 어려웠지만 교수님이 보여주신 유튜브와 수업을 참고하고 충희 같은 친구들에게 조언을 구해 이해하려 노력하고

후에 알게 된 것을 다른 친구들에게도 설명해 주면서 더 잘 이해할 수 있게 되었습니다.

