[![Work in Repl.it](https://classroom.github.com/assets/work-in-replit-14baed9a392b3a25080506f3b7b6d57f295ec2978f6f33ec97e36a161684cbe9.svg)](https://classroom.github.com/online_ide?assignment_repo_id=4032144&assignment_repo_type=AssignmentRepo)
# 1. Си хэл сэргээх

`myinclude.h` файл дотор зарлагдсан функцүүдийг `functions.c` файл дотор хэрэгжүүл.  
Энэхүү ажилд гарч буй олонлог нь элементийн давхардалгүй хүснэгт болно. Хүснэгтийн хэмжээ ядаж 100 байх ёстой.  

  * Хүснэгтээс хамгийн их бүхэл тоог буцаах функц
    ```C
    int max(int A[], int n);
    ```
    `n`: `A` хүснэгтэд хадгалагдсан тоонуудын тоо.  
  * Хүснэгтээс хамгийн бага бүхэл тоог буцаах функц
    ```C
    int min(int A[], int n);
    ```
    `n`: `A` хүснэгтэд хадгалагдсан тоонуудын тоо.  
  * `A` хүснэгтэд байгаа тоонуудыг `B` хүснэгтэд хуулах функц.
    ```C
    void copy(int A[], int n, int B[]);
    ```
   `n`: `A` хүснэгтэд хадгалагдсан тоонуудын тоо.  
   `B` хүснэгт `A` хүснэгтээс хэмжээгээрээ том гэж үзнэ. Уг функц утга буцаахгүй
   
  * `find` функц нь `n` ширхэг бүхэл тоо агуулсан `A` хүснэгтээс `x` утгыг хайж, хамгийн эхэнд олдсон индексийг буцаана. Олдохгүй бол `-1` утгыг буцаана.
    ```C
    int find(int A[], int n, int x);
    ```
    Жишээ нь: `{5, 2, 8, 7, 1}` хүснэгтээс `x = 2` утгыг хайвал `1` гэж буцаана.
   
  * `make_set` функц нь A хүснэгтэд байгаа тоонуудын олонлогийг B хүснэгтэд хадгалаад, B хүснэгтэд хадгалсан олонлогийнхоо хэмжээг буцаана.  
    Жишээ нь:
    ```C
    int make_set(int A[], int n, int B[]);
    // ...
    int B[6];
    int A[] = {1, 5, 1, 2, 3, 2};
    int m = make_set(A, 6, B);  // Энд B нь {1, 5, 2, 3}, m = 4 болно.
    ```
  `B` хүснэгтэд хадгалагдах дараалал огтхон ч хамаагүй. `A` хүснэгтэд байгаа тоо дахин давтагдахгүйгээр, ямар нэгэн дарааллаар `B` хүснэгтэд хадгалагдсан бол зөвд тооцогдоно.
  
  * `union_set` функц нь `A`-д хадгалагдсан хүснэгтийг олонлог гэж үзээд `B` хүснэгтэд байрлах тоонуудыг `A`-д нэмж хадгалах ба `A` хүснэгтийн шинэ хэмжээг буцаана. `B` хүснэгт олонлог байх албагүй (Тоонууд давхардсан байж болно). Харин шинэ `A` бол олонлог байх ёстой.  `n, m` нь харилцан `A, B` хүснэгтийн хэмжээнүүд. `A` хүснэгтийг хангалттай том гэж үзнэ.
    ```C
    int union_set(int A[], int n, int B[], int m);
    ```
    Жишээ нь: `A = {1, 5, 7}, B = {7, 5, 3, 7}` бол `A = {1, 5, 7, 3}` болох ба `4`-ыг буцаана.
    
  * `intersection_set` функц нь `A, B` хоёр олонлогийн огтлолцол буюу хоёуланд нь байгаа элементүүдийг `C` хүснэгтэд хадгална. `C` хүснэгтэд хадгалсан элементүүдийн тоог буцаана. `C` хүснэгтийг хангалттай том гэж үзнэ. `C` хүснэгт нь олонлог байх ёстой ба элементүүдийн хадгалагдсан дараалал чухал биш.
    ```C
    int intersection_set(int A[], int n, int B[], int m, int C[]);
    ```
    Жишээ нь: `A = {1, 5, 7}, B = {7, 5, 3}` бол `C = {7, 5}` болох ба `2`-ыг буцаана.