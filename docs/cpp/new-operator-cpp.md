---
title: "new 演算子 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "new キーワード [C++]"
ms.assetid: 69fee812-1c28-4882-8fda-d1ad17860004
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# new 演算子 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

フリー ストアから *type\-name* のオブジェクトまたはオブジェクトの配列にメモリを割り当て、オブジェクトへの適切に型指定されたゼロ以外のポインターを返します。  
  
> [!NOTE]
>  Microsoft C\+\+ Component Extensions では、`new` キーワードによる vtable スロット エントリの追加がサポートされています。  詳細については、「[new \(new slot in vtable\)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)」を参照してください。  
  
## 構文  
  
```  
[::] new [placement] new-type-name [new-initializer]  
[::] new [placement] ( type-name ) [new-initializer]  
```  
  
## 解説  
 この処理に失敗した場合、**new** はゼロを返すか、例外をスローします。詳細については、「[new 演算子と delete 演算子](../cpp/new-and-delete-operators.md)」を参照してください。  カスタム例外処理ルーチンを作成し、[\_set\_new\_handler](../Topic/_set_new_handler.md) ランタイム ライブラリ関数を呼び出して、その引数として関数名を渡すことにで、この既定の動作を変更できます。  
  
 マネージ ヒープにオブジェクトを作成する方法については、「[gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)」を参照してください。  
  
 **new** を使用してメモリを C\+\+ クラス オブジェクトに割り当てると、メモリの割り当て後に、そのオブジェクトのコンストラクターが呼び出されます。  
  
 [new](../cpp/delete-operator-cpp.md) 演算子を使用して割り当てたメモリを解放するには、**delete** 演算子を使用します。  
  
 次の例では、サイズ `dim` × 10 の文字の 2 次元配列を割り当てた後、解放します。  多次元配列を割り当てるときに、最初の次元を除くすべての次元は、正の値に評価される定数式であることが必要です。配列の一番左の次元は、正の値に評価される任意の値でかまいません。  **new** 演算子を使用して配列を割り当てるとき、最初の次元はゼロでかまいません。**new** 演算子は一意のポインターを返します。  
  
```  
char (*pchar)[10] = new char[dim][10];  
delete [] pchar;  
```  
  
 *type\-name* に **const**、`volatile`、クラス宣言、または列挙体宣言を含めることはできません。  したがって、次の式は無効です。  
  
```  
volatile char *vch = new volatile char[20];  
```  
  
 **new** 演算子は参照型を割り当てません。それらがオブジェクトでないためです。  
  
 **new** 演算子は、関数の割り当てには使用できませんが、関数へのポインターの割り当てには使用できます。  次の例では、整数を返す関数への 7 個のポインターの配列を割り当てた後、解放します。  
  
```  
int (**p) () = new (int (*[7]) ());  
delete *p;  
```  
  
 余分な引数を付けずに **new** 演算子を使用し、[\/GX](../Topic/-GX%20\(Enable%20Exception%20Handling\).md)、[\/EHa](../build/reference/eh-exception-handling-model.md)、または [\/EHs](../build/reference/eh-exception-handling-model.md) オプションを指定してコンパイルする場合、コンストラクターが例外をスローしたときに **delete** 演算子を呼び出すコードが、コンパイラによって生成されます。  
  
 次の一覧では、**new** の文法要素について説明します。  
  
 *placement*  
 **new** をオーバーロードする場合、追加の引数を渡す方法を指定します。  
  
 *type\-name*  
 割り当てる型を指定します。組み込みまたはユーザー定義の型を指定できます。  型の指定が複雑な場合には、かっこで囲むことでバインディング順を強制的に適用できます。  
  
 *initializer*  
 初期化されたオブジェクトの値を指定します。  初期化子は配列には指定できません。  **new** 演算子は、クラスに既定のコンストラクターがある場合のみ、オブジェクトの配列を生成します。  
  
## 使用例  
 次のコード例では、文字配列と `CName` クラスのオブジェクトを割り当てた後、解放します。  
  
```  
// expre_new_Operator.cpp  
// compile with: /EHsc  
#include <string.h>  
  
class CName {  
public:  
   enum {  
      sizeOfBuffer = 256  
   };  
  
   char m_szFirst[sizeOfBuffer];  
   char m_szLast[sizeOfBuffer];  
  
public:  
   void SetName(char* pszFirst, char* pszLast) {  
     strcpy_s(m_szFirst, sizeOfBuffer, pszFirst);  
     strcpy_s(m_szLast, sizeOfBuffer, pszLast);  
   }  
  
};  
  
int main() {  
   // Allocate memory for the array  
   char* pCharArray = new char[CName::sizeOfBuffer];  
   strcpy_s(pCharArray, CName::sizeOfBuffer, "Array of characters");  
  
   // Deallocate memory for the array  
   delete [] pCharArray;             
   pCharArray = NULL;  
  
   // Allocate memory for the object  
   CName* pName = new CName;  
   pName->SetName("Firstname", "Lastname");  
  
   // Deallocate memory for the object  
   delete pName;  
   pName = NULL;  
}  
```  
  
## 使用例  
 仮引数付きの new 演算子、つまり割り当てサイズ以外の引数を伴う形式の **new** 演算子を使用する場合、コンストラクターが例外をスローしたときの仮引数付きの **delete** 演算子は、コンパイラによってサポートされていません。  例:  
  
```  
// expre_new_Operator2.cpp  
// C2660 expected  
class A {  
public:  
   A(int) { throw "Fail!"; }  
};  
void F(void) {  
   try {  
      // heap memory pointed to by pa1 will be deallocated  
      // by calling ::operator delete(void*).  
      A* pa1 = new A(10);  
   } catch (...) {  
   }  
   try {  
      // This will call ::operator new(size_t, char*, int).  
      // When A::A(int) does a throw, we should call  
      // ::operator delete(void*, char*, int) to deallocate  
      // the memory pointed to by pa2.  Since  
      // ::operator delete(void*, char*, int) has not been implemented,  
      // memory will be leaked when the deallocation cannot occur.  
  
      A* pa2 = new(__FILE__, __LINE__) A(20);  
   } catch (...) {  
   }  
}  
  
int main() {  
   A a;  
}  
```  
  
## new で割り当てたオブジェクトの初期化  
 オプションの *initializer* フィールドは、**new** 演算子の文法に含まれます。  これにより、新しいオブジェクトをユーザー定義コンストラクターで初期化できます。  初期化の実行方法の詳細については、「[初期化](../cpp/initializers.md)」を参照してください。  次の例では、**new** 演算子で初期化式を使用する方法を説明します。  
  
```  
// expre_Initializing_Objects_Allocated_with_new.cpp  
class Acct  
{  
public:  
    // Define default constructor and a constructor that accepts  
    //  an initial balance.  
    Acct() { balance = 0.0; }  
    Acct( double init_balance ) { balance = init_balance; }  
private:  
    double balance;  
};  
  
int main()  
{  
    Acct *CheckingAcct = new Acct;  
    Acct *SavingsAcct = new Acct ( 34.98 );  
    double *HowMuch = new double ( 43.0 );  
    // ...  
}  
```  
  
 この例では、オブジェクト `CheckingAcct` は **new** 演算子を使用して割り当てられますが、既定の初期化は指定されません。  したがって、`Acct()` クラスの既定のコンストラクターが呼び出されます。  その後、オブジェクト `SavingsAcct` は、同じように割り当てられます。ただし、明示的に 34.98 に初期化されます。  34.98 は **double** 型であるため、初期化を処理するために、その型の引数を受け取るコンストラクターが呼び出されます。  最後に、`HowMuch` 非クラス型は 43.0 に初期化されます。  
  
 オブジェクトがクラス型で、\(前の例のように\) そのクラスにコンストラクターがある場合、次の条件の 1 つが満たされる場合にのみオブジェクトを **new** 演算子で初期化できます。  
  
-   初期化子内に指定された引数は、コンストラクターの引数と一致します。  
  
-   クラスには、既定のコンストラクター \(引数を指定せずに呼び出すことができるコンストラクター\) があります。  
  
 アクセス制御とあいまいさのコントロールは、「`operator new`あいまいさ」と「[特殊なメンバー関数を使用した初期化](http://msdn.microsoft.com/ja-jp/0b399cab-40a7-4e79-9278-05f40139a0e1)」に規定された規則に従って、[とコンストラクターで実行されます。](http://msdn.microsoft.com/ja-jp/82223d73-64cb-4923-b678-78f9568ff3ca)  
  
 **new** 演算子を使用して配列を割り当てる場合は、明示的な要素ごとの初期化は実行できません。既定のコンストラクターがあれば、このコンストラクターのみ呼び出されます。  詳細については、「[既定の引数](../Topic/Default%20Arguments.md)」を参照してください。  
  
 メモリの割り当てに失敗すると \(`operator new` が値 0 を返す\)、初期化は行われません。  これによって、存在しないデータを初期化しようとすることを防止できます。  
  
 関数呼び出しの場合と同様に、初期化された式が評価される順序は定義されていません。  さらに、メモリの割り当てが実行される前に、これらの式が完全に評価されるものとして信頼しないでください。  メモリの割り当てに失敗し、**new** 演算子がゼロを返すと、初期化子の一部の式は完全に評価されない場合があります。  
  
## new で割り当てたオブジェクトの有効期間  
 **new** 演算子によって割り当てられたオブジェクトは、それが定義されているスコープが終了しても破棄されません。  **new** 演算子は割り当てたオブジェクトへのポインターを返すため、プログラムでこのオブジェクトにアクセスするには、適切なスコープのポインターを定義する必要があります。  例:  
  
```  
// expre_Lifetime_of_Objects_Allocated_with_new.cpp  
// C2541 expected  
int main()  
{  
    // Use new operator to allocate an array of 20 characters.  
    char *AnArray = new char[20];  
  
    for( int i = 0; i < 20; ++i )  
    {  
        // On the first iteration of the loop, allocate  
        //  another array of 20 characters.  
        if( i == 0 )  
        {  
            char *AnotherArray = new char[20];  
        }  
    }  
  
    delete [] AnotherArray; // Error: pointer out of scope.  
    delete [] AnArray;      // OK: pointer still in scope.  
}  
```  
  
 この例では、ポインター `AnotherArray` がスコープ外になると、オブジェクトを削除できなくなります。  
  
## new の機能  
 *allocation\-expression* \(**new** 演算子を含む式\) は次の 3 つの処理を行います。  
  
-   割り当てられるオブジェクトのストレージを探し、予約します。  この段階が完了すると、適切なサイズのストレージが割り当てられます。ただし、まだオブジェクトではありません。  
  
-   オブジェクトを初期化します。  初期化が完了すると、割り当てられたストレージをオブジェクトにするための十分な情報が得られます。  
  
-   *new\-type\-name* または *type\-name* から派生したポインター型のオブジェクトへのポインターを返します。  プログラムでは、このポインターを使用して新しく割り当てられたオブジェクトにアクセスします。  
  
 **new** 演算子は `operator new` 関数を呼び出します。  任意の型の配列の場合、または **class** 型、`struct` 型、**union** 型ではないオブジェクトの場合、**::operator new** グローバル関数を呼び出してストレージを割り当てます。  クラス型オブジェクトは、クラスごとに異なる `operator new` 静的メンバー関数を定義できます。  
  
 コンパイラは、`type` 型のオブジェクトを割り当てる **new** 演算子を検出すると、`type`**::operator new\( sizeof\(** `type` **\) \)** の呼び出しを発行します。または、ユーザー定義の `operator new` が定義されていない場合は、**::operator new\( sizeof\(** `type` **\) \)** を呼び出します。  したがって、**new** 演算子は、オブジェクトに適したサイズのメモリを割り当てることができます。  
  
> [!NOTE]
>  `operator new` の引数は  **size\_t** 型です。  この型は、DIRECT.H、MALLOC.H、MEMORY.H、SEARCH.H、STDDEF.H、STDIO.H、STDLIB.H、STRING.H、および TIME.H で定義されます。  
  
 必要であれば *placement* も指定できます \([new 演算子](../cpp/new-operator-cpp.md)の文法を参照してください\)。  *placement* パラメーターは `operator new` のユーザー定義の実装にのみ使用できます。これは、追加情報が `operator new` に渡されることを許可します。   *のように `T *TObject = new ( 0x0040 ) T;`placement* フィールドが指定された式は、クラス T がメンバー演算子 new を持つ場合は `T *TObject = T::operator new( sizeof( T ), 0x0040 );` に変換されます。その以外の場合は `T *TObject = ::operator new( sizeof( T ), 0x0040 );` に変換されます。  
  
 *placement* フィールドの本来の目的は、ハードウェアに依存するオブジェクトをユーザー指定のアドレスに割り当てられるようにすることです。  
  
> [!NOTE]
>  前の例では *placement* フィールドに引数を 1 つだけ指定しましたが、この方法で `operator new` に渡すことができる引数の数に制限はありません。  
  
 `operator new` がクラス型に対して定義されている場合でも、次の形式でグローバル演算子を使用できます。  
  
```  
T *TObject =::new TObject;  
```  
  
 スコープ解決演算子 \(`::`\) を使用する場合は、グローバルの **new** 演算子を使用する必要があります。  
  
## 参照  
 [単項演算子を含む式](../Topic/Expressions%20with%20Unary%20Operators.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [operator new 関数](../misc/operator-new-function.md)