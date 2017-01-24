---
title: "new および delete 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "delete_cpp"
  - "new_cpp"
  - "new"
  - "delete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "delete キーワード [C++], 構文"
  - "new キーワード [C++], オブジェクトの動的な割り当て"
  - "nothrownew.obj"
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
caps.latest.revision: 16
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# new および delete 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ では、[new](../cpp/new-operator-cpp.md) 演算子と [delete](../cpp/delete-operator-cpp.md) 演算子を使用して、オブジェクトの動的割り当てと割り当て解除をサポートしています。  これらの演算子は、フリー ストアと呼ばれるプールからオブジェクトのメモリを割り当てます。  `new` 演算子は特殊な関数 [operator new](../misc/operator-new-function.md) を呼び出し、`delete` 演算子は特殊な関数 [operator delete](../Topic/operator%20delete%20Function.md) を呼び出します。  
  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] .NET 2002 では、標準 C\+\+ ライブラリの `new` 関数は、メモリ割り当てに失敗した場合に std::bad\_alloc 例外をスローするという、C\+\+ 標準で指定されている動作をサポートします。  
  
 C ランタイム ライブラリの `new` 関数も、メモリ割り当てに失敗した場合に std::bad\_alloc 例外をスローします。  
  
 引き続き C ランタイム ライブラリの `new` のスローしないバージョンが必要な場合は、プログラムを nothrownew.obj とリンクします。  ただし、nothrownew.obj とリンクすると、標準 C\+\+ ライブラリの `new` は機能しなくなります。  
  
 C ランタイム ライブラリと標準 C\+\+ ライブラリを構成するライブラリ ファイルの一覧については、「[CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)」を参照してください。  
  
## 新しい演算子  
 次のようなステートメントがプログラムで検出された場合は、関数 `operator new` の呼び出しに変換されます。  
  
```  
char *pch = new char[BUFFER_SIZE];  
```  
  
 要求がゼロ バイトのストレージに対するものである場合、**operator new** は別のオブジェクトへのポインターを返します \(つまり、**operator new** を繰り返し呼び出すと、複数の異なるポインターが返されます\)。  割り当て要求のメモリが不足している場合、**operator new** は **NULL** を返すか、例外をスローします \(詳細については、「[new 演算子と delete 演算子](../cpp/new-and-delete-operators.md)」を参照\)。  
  
 メモリを解放し割り当てを再試行するルーチンを記述できます。詳細については、「[\_set\_new\_handler](../Topic/_set_new_handler.md)」を参照してください。  復旧方法の詳細については、「[メモリ不足状態の処理](../Topic/Handling%20Insufficient%20Memory%20Conditions.md)」を参照してください。  
  
 `operator new` 関数の 2 つのスコープの説明を次の表に示します。  
  
### operator new 関数のスコープ  
  
|演算子|スコープ|  
|---------|----------|  
|**::operator new**|グローバル|  
|*class\-name* **::operator new**|クラス|  
  
 **operator new** の最初の引数は、**size\_t** 型 \(STDDEF.H で定義した型\) で、戻り値の型は常に **void \*** である必要があります。  
  
 グローバルな **operator new** 関数は、**new** 演算子が、組み込み型のオブジェクト、ユーザー定義の **operator new** 関数を含まないクラス型のオブジェクト、および任意の型の配列の割り当てに使用されるときに呼び出されます。  **operator new** が定義されたクラス型のオブジェクトを割り当てるために **new** 演算子が使用されると、そのクラスの **operator new** が呼び出されます。  
  
 クラスに定義された **operator new** 関数は、そのクラス型のオブジェクトのグローバルな **operator new** 関数を隠す静的メンバー関数です \(したがって仮想関数にはできません\)。  **new** を使用してメモリを割り当て、指定した値に設定する場合を考えます。  
  
```  
// spec1_the_operator_new_function1.cpp  
#include <malloc.h>  
#include <memory.h>  
  
class Blanks  
{  
public:  
    Blanks(){}  
    void *operator new( size_t stAllocateBlock, char chInit );  
};  
void *Blanks::operator new( size_t stAllocateBlock, char chInit )  
{  
    void *pvTemp = malloc( stAllocateBlock );  
    if( pvTemp != 0 )  
        memset( pvTemp, chInit, stAllocateBlock );  
    return pvTemp;  
}  
// For discrete objects of type Blanks, the global operator new function  
// is hidden. Therefore, the following code allocates an object of type  
// Blanks and initializes it to 0xa5  
int main()  
{  
   Blanks *a5 = new(0xa5) Blanks;  
   return a5 != 0;  
}  
```  
  
 **new** のかっこ内で指定された引数は、`Blanks::operator new` 引数として `chInit` に渡されます。  ただし、グローバルな **operator new** 関数は隠されているため、次のようなコードではエラーが生成されます。  
  
```  
Blanks *SomeBlanks = new Blanks;  
```  
  
 Visual C\+\+ 5.0 以前では、**new** 演算子を使用して割り当てられる非クラス型とすべての配列 \(**class** 型であるかどうかに関係なく\) は、常に **operator new** グローバル関数を使用していました。  
  
 Visual C\+\+ 5.0 から、コンパイラはクラス宣言でのメンバー配列の **new** および **delete** 演算子をサポートします。  例:  
  
```  
// spec1_the_operator_new_function2.cpp  
class MyClass  
{  
public:  
   void * operator new[] (size_t)  
   {  
      return 0;  
   }  
   void   operator delete[] (void*)  
   {  
   }  
};  
  
int main()   
{  
   MyClass *pMyClass = new MyClass[5];  
   delete [] pMyClass;  
}  
```  
  
### メモリ不足の処理  
 失敗したメモリ割り当てのテストは、次のようなコードを使用して実行できます。  
  
```  
// insufficient_memory_conditions.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
#define BIG_NUMBER 100000000  
int main() {  
   int *pI = new int[BIG_NUMBER];  
   if( pI == 0x0 ) {  
      cout << "Insufficient memory" << endl;  
      return -1;  
   }  
}  
```  
  
 他にも失敗したメモリ割り当て要求を処理する方法はあります。このようなエラーを処理するカスタム リカバリ ルーチンを作成し、[\_set\_new\_handler](../Topic/_set_new_handler.md) ランタイム関数を呼び出して関数を登録する方法です。  
  
## delete 演算子  
 **new** 演算子を使用して動的に割り当てられたメモリは、**delete** 演算子を使用して解放できます。  delete 演算子は **operator delete** 関数を呼び出し、この関数がメモリを解放して使用可能なプールに戻します。  **delete** 演算子を使用すると、クラスのデストラクターも呼び出されます \(存在する場合\)。  
  
 グローバルとクラス スコープの **operator delete** 関数があります。  特定のクラスに対して定義できる **operator delete** 関数は、1 つだけです。定義されている場合、グローバルの **operator delete**関数は隠されます。  グローバルの **operator delete** 関数は、常に任意の型の配列に対して呼び出されます。  
  
 グローバルの **operator delete** 関数は、宣言された場合、解放するオブジェクトへのポインターを含む **void \*** 型の単一の引数を受け取ります。  戻り値の型は `void` です \(**operator delete** は値を返せません\)。  クラス メンバーの **operator delete** 関数には、2 つの形式が存在します。  
  
```  
void operator delete( void * );  
void operator delete( void *, size_t );  
```  
  
 特定のクラスに存在できるのは、上記の 2 つのバリアントのうち 1 つだけです。  最初の形式は、グローバルの `operator delete` の説明と同様に動作します。  2 番目の形式は 2 つの引数を取ります。最初の引数は解放するメモリ ブロックへのポインターで、2 番目は解放するバイト数です。  2 番目の形式は、基底クラスの **operator delete** 関数を派生クラスのオブジェクトの削除に使用するときに、特に便利です。  
  
 **operator delete** 関数は静的です。したがって、仮想関数にすることはできません。  `operator delete` 関数は、「[メンバー アクセス コントロール](../cpp/member-access-control-cpp.md)」で説明されているように、アクセス制御に従います。  
  
 次の例は、メモリの割り当てと解放を記録するように設計された、ユーザー定義の **operator new** 関数と **operator delete** 関数を示しています。  
  
```  
// spec1_the_operator_delete_function1.cpp  
// compile with: /EHsc  
// arguments: 3  
#include <iostream>  
using namespace std;  
  
int fLogMemory = 0;      // Perform logging (0=no; nonzero=yes)?  
int cBlocksAllocated = 0;  // Count of blocks allocated.  
  
// User-defined operator new.  
void *operator new( size_t stAllocateBlock ) {  
   static int fInOpNew = 0;   // Guard flag.  
  
   if ( fLogMemory && !fInOpNew ) {  
      fInOpNew = 1;  
      clog << "Memory block " << ++cBlocksAllocated  
          << " allocated for " << stAllocateBlock  
          << " bytes\n";  
      fInOpNew = 0;  
   }  
   return malloc( stAllocateBlock );  
}  
  
// User-defined operator delete.  
void operator delete( void *pvMem ) {  
   static int fInOpDelete = 0;   // Guard flag.  
   if ( fLogMemory && !fInOpDelete ) {  
      fInOpDelete = 1;  
      clog << "Memory block " << cBlocksAllocated--  
          << " deallocated\n";  
      fInOpDelete = 0;  
   }  
  
   free( pvMem );  
}  
  
int main( int argc, char *argv[] ) {  
   fLogMemory = 1;   // Turn logging on  
   if( argc > 1 )  
      for( int i = 0; i < atoi( argv[1] ); ++i ) {  
         char *pMem = new char[10];  
         delete[] pMem;  
      }  
   fLogMemory = 0;  // Turn logging off.  
   return cBlocksAllocated;  
}  
```  
  
 上記のコードを "メモリ リーク" の検出に使うことができます。メモリ リークとは、フリー ストアに割り当てられ、解放されていないメモリを指します。  この検出を実行するため、グローバルな **new** 演算子と **delete** 演算子がメモリの割り当てと解放をカウントするように再定義されています。  
  
 Visual C\+\+ 5.0 から、コンパイラはクラス宣言でのメンバー配列の **new** および **delete** 演算子をサポートします。  例:  
  
```  
// spec1_the_operator_delete_function2.cpp  
// compile with: /c  
class X  {  
public:  
   void * operator new[] (size_t) {  
      return 0;  
   }  
   void operator delete[] (void*) {}  
};  
  
void f() {  
   X *pX = new X[5];  
   delete [] pX;  
}  
```  
  
## 参照  
 [特殊なメンバー関数](../misc/special-member-functions-cpp.md)