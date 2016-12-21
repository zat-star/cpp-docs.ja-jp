---
title: "エイリアスと typedef (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "typedef"
dev_langs: 
  - "C++"
ms.assetid: af1c24d2-4bfd-408a-acfc-482e264232f5
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# エイリアスと typedef (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*エイリアスの宣言*を使用して、以前に宣言した型のシノニムとして使用する名前を宣言できます   \(このメカニズムは非公式には*型エイリアス*とも呼ばれます\)。  また、このメカニズムを使用して*エイリアス テンプレート*を作成できます。このテンプレートはカスタム アロケーターに特に便利にな場合があります。  
  
## 構文  
  
```  
  
using identifier = type;  
```  
  
## 解説  
 `identifier`  
 エイリアスの名前。  
  
 `type`  
 エイリアスを作成する型識別子。  
  
 エイリアスでは新しい型は定義されず、既存の型名の意味を変更することはできません。  
  
 エイリアスの最もシンプルな形式は C\+\+03 の `typedef` のメカニズムと同等です。  
  
```cpp  
  
// C++11  
using counter = long;  
  
// C++03 equivalent:  
// typedef long counter;  
  
```  
  
 いずれの形式でも "カウンター" 型の変数を作成できます。  次のような `std::ios_base::fmtflags` の型エイリアスが便利な場合があります。  
  
```cpp  
  
// C++11  
using fmtfl = std::ios_base::fmtflags;  
// C++03 equivalent:  
// typedef std::ios_base::fmtflags fmtfl;  
  
fmtfl fl_orig = std::cout.flags();  
fmtfl fl_hex = (fl_orig & ~std::cout.basefield) | std::cout.showbase | std::cout.hex;  
// ...  
std::cout.flags(fl_hex);  
  
```  
  
 エイリアスは関数ポインターでも機能しますが、typedef の同等のものよりはるかに読みやすくなります。  
  
```cpp  
  
// C++11  
using func = void(*)(int);  
  
// C++03 equivalent:  
// typedef void (*func)(int);  
  
// func can be assigned to a function pointer value  
void actual_function(int arg) { /* some code */ }  
func fptr = &actual_function;  
  
```  
  
 `typedef` メカニズムでは、テンプレートでは機能しないという制限があります。  しかし、C\+\+11 での型エイリアスの構文ではエイリアス テンプレートを作成できます。  
  
```cpp  
template<typename T> using ptr = T*;   
  
// the name 'ptr<T>' is now an alias for pointer to T  
ptr<int> ptr_int;  
  
```  
  
## 使用例  
 次の例に、エイリアス テンプレートをカスタム アロケーター \(この場合は整数ベクター型\) で使用する方法を示します。  `int` を任意の型に置き換えて、便利なエイリアスを作成することで、主要な機能コード内の複雑なパラメーター リストを隠ぺいできます。  コード全体でカスタム アロケーターを使用することで読みやすくして、入力ミスによるバグが発生するリスクを減らすことができます。  
  
```cpp  
  
#include <stdlib.h>  
#include <new>  
  
template <typename T> struct MyAlloc {  
    typedef T value_type;  
  
    MyAlloc() { }  
    template <typename U> MyAlloc(const MyAlloc<U>&) { }  
  
    bool operator==(const MyAlloc&) const { return true; }  
    bool operator!=(const MyAlloc&) const { return false; }  
  
    T * allocate(const size_t n) const {  
        if (n == 0) {  
            return nullptr;  
        }  
  
        if (n > static_cast<size_t>(-1) / sizeof(T)) {  
            throw std::bad_array_new_length();  
        }  
  
        void * const pv = malloc(n * sizeof(T));  
  
        if (!pv) {  
            throw std::bad_alloc();  
        }  
  
        return static_cast<T *>(pv);  
    }  
  
    void deallocate(T * const p, size_t) const {  
        free(p);  
    }  
};  
  
#include <vector>  
using MyIntVector = std::vector<int, MyAlloc<int>>;  
  
#include <iostream>  
  
int main ()   
{  
    MyIntVector foov = { 1701, 1764, 1664 };  
  
    for (auto a: foov) std::cout << a << " ";  
    std::cout << "\n";  
  
    return 0;  
}  
```  
  
## 出力  
  **1701 1764 1664**   
## Typedefs  
 `typedef` 宣言は、スコープ内で、宣言の *type\-declaration* 部分で指定された型のシノニムになる名前を導入します。  
  
 typedef 宣言を使用して、既に言語で定義されている型や、宣言した型に対して、より短い、またはわかりやすい名前を作成できます。  Typedef 名を使用して、変更可能な実装の詳細をカプセル化できます。  
  
 **class**、`struct`、**union**、および `enum` の宣言とは異なり、`typedef` の宣言は新しい型を導入しません。既存の型に対して新しい名前を導入します。  
  
 `typedef` を使用して宣言された名前は他の識別子と同じ名前空間を使用します \(ステートメント ラベルを除く\)。  したがって、クラス型の宣言以外では、以前に宣言された名前と同じ識別子を使用できません。  次に例を示します。  
  
```  
// typedef_names1.cpp  
// C2377 expected  
typedef unsigned long UL;   // Declare a typedef name, UL.  
int UL;                     // C2377: redefined.  
```  
  
 他の識別子に関連する名前隠蔽規則も、`typedef` を使用して宣言する名前の可視性を制御します。  したがって、次の例は C\+\+ で有効です。  
  
```  
// typedef_names2.cpp  
typedef unsigned long UL;   // Declare a typedef name, UL  
int main()  
{  
   unsigned int UL;   // Redeclaration hides typedef name  
}  
  
// typedef UL back in scope  
```  
  
-   [typedef 名の再宣言](../misc/redeclaration-of-typedef-names.md)  
  
-   [クラス型がある typedef の使用](../misc/use-of-typedef-with-class-types.md)  
  
-   [typedef 名の名前空間](../misc/name-space-of-typedef-names.md)  
  
```  
// typedef_specifier1.cpp  
typedef char FlagType;  
  
int main()  
{  
}  
  
void myproc( int )  
{  
    int FlagType;  
}  
```  
  
 Typedef と同じ名前でローカル スコープの識別子を宣言するとき、あるいは同じスコープまたは内部スコープで構造体または共用体のメンバーを宣言するときは、型指定子を指定する必要があります。  例:  
  
```  
typedef char FlagType;  
const FlagType x;  
```  
  
 識別子、構造体メンバー、または共用体メンバーに対して `FlagType` 名を再利用するには、次のように型を指定する必要があります。  
  
```  
const int FlagType;  // Type specifier required  
```  
  
 次のような記述だけでは不十分です。  
  
```  
const FlagType;      // Incomplete specification  
```  
  
 `FlagType` は再宣言された識別子ではなく、型の一部であると見なされるためです。  この宣言は、次のような正しくない宣言であると見なされます。  
  
```  
int;  // Illegal declaration   
```  
  
 ポインター、関数、配列型を含め、あらゆる型を typedef で宣言できます。  構造体型または共用体型を定義する前に、構造体型または共用体型へのポインターの typedef 名を宣言できます。ただし、定義が宣言と同じ可視性である必要があります。  
  
### 使用例  
 `typedef` 宣言の使用方法の 1 つは、宣言をより同型でコンパクトにすることです。  例:  
  
```  
typedef char CHAR;          // Character type.  
typedef CHAR * PSTR;        // Pointer to a string (char *).  
PSTR strchr( PSTR source, CHAR target );  
typedef unsigned long ulong;  
ulong ul;     // Equivalent to "unsigned long ul;"  
```  
  
 `typedef` を使用して同じ宣言の中に基本型と派生型を指定するには、宣言子をコンマで区切ります。  例:  
  
```  
typedef char CHAR, *PSTR;  
```  
  
 次の例は、値を返さず、2 つの int 引数を受け取る関数に対する型 `DRAWF` を用意します。  
  
```  
typedef void DRAWF( int, int );  
```  
  
 上記の `typedef` ステートメントの後で、次の宣言  
  
```  
DRAWF box;   
```  
  
 は次の宣言と同等です。  
  
```  
void box( int, int );  
```  
  
 `typedef` は、多くの場合、ユーザー定義型を宣言し、名前を付けるために、次のように `struct` と組み合わせて使用されます。  
  
```  
// typedef_specifier2.cpp  
#include <stdio.h>  
  
typedef struct mystructtag  
{  
    int   i;  
    double f;  
} mystruct;  
  
int main()  
{  
    mystruct ms;  
    ms.i = 10;  
    ms.f = 0.99;  
    printf_s("%d   %f\n", ms.i, ms.f);  
}  
```  
  
  **10   0.990000**   
### typedef の再宣言  
 `typedef` 宣言を使用すると、同じ名前を再宣言して同じ型を参照することができます。  例:  
  
```  
// FILE1.H  
typedef char CHAR;  
  
// FILE2.H  
typedef char CHAR;  
  
// PROG.CPP  
#include "file1.h"  
#include "file2.h"   // OK  
```  
  
 プログラム PROG.CPP は 2 つのヘッダー ファイルを含み、両方のヘッダー ファイルに名前 `typedef` の `CHAR` 宣言が含まれています。  両方の宣言が同じ型を参照する限り、このような再宣言は許容されます。  
  
 以前に異なる型として宣言された名前を `typedef` で再定義することはできません。  したがって、FILE2.H が次の内容である場合、  
  
```  
// FILE2.H  
typedef int CHAR;     // Error  
```  
  
 コンパイラは、名前 `CHAR` を再宣言して異なる型を参照しようとするため、エラーが発生します。  このことは、次のような構造もに及びます。  
  
```  
typedef char CHAR;  
typedef CHAR CHAR;      // OK: redeclared as same type  
  
typedef union REGS      // OK: name REGS redeclared  
{                       //  by typedef name with the  
    struct wordregs x;  //  same meaning.  
    struct byteregs h;  
} REGS;  
```  
  
### typedef:  C\+\+ と C  
 クラス型を持つ `typedef` 指定子の使用がサポートされているのは、主に、`typedef` 宣言内で名前のない構造体を宣言する ANSI C に対応するためです。  たとえば、多くの C プログラマは次のように記述します。  
  
```  
// typedef_with_class_types1.cpp  
// compile with: /c  
typedef struct {   // Declare an unnamed structure and give it the  
                   // typedef name POINT.  
   unsigned x;  
   unsigned y;  
} POINT;  
```  
  
 このような宣言の利点は、次のような宣言を使用できることです。  
  
```  
POINT ptOrigin;  
```  
  
 次のように記述する必要がありません。  
  
```  
struct point_t ptOrigin;  
```  
  
 C\+\+ では、`typedef` 名と実際の型 \(**class**、`struct`、**union**、および `enum` のキーワードで宣言\) との違いがより明確です。  `typedef` ステートメント内で無名の構造体を宣言する C 言語の記述法も使用できますが、C 言語に見られる表記の利点は得られません。  
  
```  
// typedef_with_class_types2.cpp  
// compile with: /c /W1  
typedef struct {  
   int POINT();  
   unsigned x;  
   unsigned y;  
} POINT;  
```  
  
 前の例では、名前のないクラス `POINT` 構文を使用して、`typedef` という名前のクラスを宣言しています。  `POINT` はクラス名として扱われますが、この方法で導入された名前には次の制限が適用されます。  
  
-   **class**、`struct`、または **union** プレフィックスの後には名前 \(シノニム\) を記述できません。  
  
-   名前は、クラス宣言内のコンストラクター名またはデストラクター名として使用できません。  
  
 つまり、この構文には、継承、構築、または破棄のための機能はありません。  
  
## 参照  
 [using キーワード](../misc/using-keyword.md)