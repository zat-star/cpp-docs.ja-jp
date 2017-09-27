---
title: "new 演算子 (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 69fee812-1c28-4882-8fda-d1ad17860004
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a7386d45f5188e7217ebfd4c235c0763bfd70044
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="new-operator-c"></a>new 演算子 (C++)
オブジェクトまたはオブジェクトの配列にメモリを割り当てます*型名*フリー ストアから、オブジェクトを適切に型指定されたゼロ以外のポインターを返します。  
  
> [!NOTE]
>  Microsoft C++ Component Extensions では、`new` キーワードによる vtable スロット エントリの追加がサポートされています。 詳細については、次を参照してください[new (新しいスロット vtable の)。](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
## <a name="syntax"></a>構文  
  
```  
[::] new [placement] new-type-name [new-initializer]  
[::] new [placement] ( type-name ) [new-initializer]  
```  
  
## <a name="remarks"></a>コメント  
 失敗した場合は、**新しい**は 0 を返しますまたは、例外がスローされます。 を参照してください[新しい演算子と delete 演算子](../cpp/new-and-delete-operators.md)詳細についてはします。 この既定の動作を変更するには、カスタム例外処理ルーチンを記述して呼び出すこと、 [_set_new_handler](../c-runtime-library/reference/set-new-handler.md)ランタイム ライブラリ関数の引数として関数名を使用します。  
  
 マネージ ヒープにオブジェクトを作成する方法については、次を参照してください。 [gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)です。  
  
 ときに**新しい**が C++ クラス オブジェクトのメモリを割り当てるために使用に、メモリが割り当てられた後、オブジェクトのコンス トラクターは呼び出されます。  
  
 使用して、[削除](../cpp/delete-operator-cpp.md)で割り当てられたメモリの割り当てを解除する演算子、**新しい**演算子。  
  
 次の例では、サイズ `dim` × 10 の文字の 2 次元配列を割り当てた後、解放します。 多次元配列を割り当てるときに、最初の次元を除くすべての次元は、正の値に評価される定数式であることが必要です。配列の一番左の次元は、正の値に評価される任意の値でかまいません。 使用して、配列を割り当てるときに、**新しい**演算子、最初の次元を 0 にすることができます:、**新しい**演算子は一意のポインターを返します。  
  
```  
char (*pchar)[10] = new char[dim][10];  
delete [] pchar;  
```  
  
 *型名*含めることはできません**const**、 `volatile`、クラス宣言、または列挙体の宣言。 したがって、次の式は無効です。  
  
```  
volatile char *vch = new volatile char[20];  
```  
  
 **新しい**オブジェクトではないために、演算子が参照型を割り当てられません。  
  
 **新しい**演算子は、関数の割り当てを使用できませんが、関数へのポインターを割り当てるために使用できます。 次の例では、整数を返す関数への 7 個のポインターの配列を割り当てた後、解放します。  
  
```  
int (**p) () = new (int (*[7]) ());  
delete *p;  
```  
  
 演算子を使用する場合**新しい**、余分な引数、およびコンパイル無し、 [/GX](../build/reference/gx-enable-exception-handling.md)、 [/EHa](../build/reference/eh-exception-handling-model.md)、または[/EHs](../build/reference/eh-exception-handling-model.md)オプション、コンパイラでは、演算子を呼び出すコードを生成する**削除**場合は、コンス トラクターが例外をスローします。  
  
 次に示しますの文法要素**新しい**:  
  
 *配置*  
 オーバー ロードする場合は、追加の引数を渡す方法を提供**新しい**です。  
  
 *型名*  
 割り当てる型を指定します。組み込みまたはユーザー定義の型を指定できます。 型の指定が複雑な場合には、かっこで囲むことでバインディング順を強制的に適用できます。  
  
 *initializer*  
 初期化されたオブジェクトの値を指定します。 初期化子は配列には指定できません。 **新しい**演算子は、クラスに既定のコンス トラクターがある場合にのみ、オブジェクトの配列は作成します。  
  
## <a name="example"></a>例  
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
  
## <a name="example"></a>例  
 配置の新しいフォームを使用する場合、**新しい**演算子、コンパイラ、割り当てのサイズ以外の引数を持つフォームは、仮引数付きをサポートしていません、**削除**演算子場合、コンス トラクターでは、例外をスローします。 例:  
  
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
  
## <a name="initializing-object-allocated-with-new"></a>new で割り当てたオブジェクトの初期化  
 省略可能な*初期化子*フィールドの文法に含まれて、**新しい**演算子。 これにより、新しいオブジェクトをユーザー定義コンストラクターで初期化できます。 初期化の実行方法の詳細については、次を参照してください。[初期化子](../cpp/initializers.md)です。 次の例で初期化式を使用する方法を示しています、**新しい**演算子。  
  
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
  
 この例では、オブジェクトで`CheckingAcct`を使用して割り当てが、**新しい**演算子がない既定の初期化が指定されています。 したがって、`Acct()` クラスの既定のコンストラクターが呼び出されます。 その後、オブジェクト `SavingsAcct` は、同じように割り当てられます。ただし、明示的に 34.98 に初期化されます。 34.98 は型ため**二重**初期化を処理する型の引数を受け取るコンス トラクターが呼び出されます。 最後に、`HowMuch` 非クラス型は 43.0 に初期化されます。  
  
 オブジェクトはクラス型では、そのクラスにコンス トラクター (上記の例では) のように、オブジェクト初期化できますが、**新しい**演算子の上記の条件のいずれかが満たされる場合にのみ。  
  
-   初期化子内に指定された引数は、コンストラクターの引数と一致します。  
  
-   クラスには、既定のコンストラクター (引数を指定せずに呼び出すことができるコンストラクター) があります。  
  
 要素ごとの明示的な初期化を完了できませんを使用して配列を割り当てる場合、**新しい**演算子以外の既定コンス トラクターのみ存在する場合が呼び出されます。 参照してください[既定の引数](../cpp/default-arguments.md)詳細についてはします。  
  
 メモリの割り当てに失敗すると (`operator new` が値 0 を返す)、初期化は行われません。 これによって、存在しないデータを初期化しようとすることを防止できます。  
  
 関数呼び出しの場合と同様に、初期化された式が評価される順序は定義されていません。 さらに、メモリの割り当てが実行される前に、これらの式が完全に評価されるものとして信頼しないでください。 メモリ割り当てに失敗した場合、**新しい**演算子は 0 を返します、初期化子の一部の式が完全に評価されない場合があります。  
  
## <a name="lifetime-of-objects-allocated-with-new"></a>new で割り当てたオブジェクトの有効期間  
 によって割り当てられたオブジェクト、**新しい**演算子は定義されているスコープが終了したときに破棄されません。 **新しい**演算子が割り当てたオブジェクトへのポインターを返します、プログラムは、それらのオブジェクトにアクセスするのに適切なスコープを持つポインターを定義する必要があります。 例:  
  
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
  
## <a name="how-new-works"></a>new の機能  
 *割り当て式*: を含む式、**新しい**演算子-3 つの処理します。  
  
-   割り当てられるオブジェクトのストレージを探し、予約します。 この段階が完了すると、適切なサイズのストレージが割り当てられます。ただし、まだオブジェクトではありません。  
  
-   オブジェクトを初期化します。 初期化が完了すると、割り当てられたストレージをオブジェクトにするための十分な情報が得られます。  
  
-   派生したポインター型のオブジェクトへのポインターを返します*新しい型名*または*型名*です。 プログラムでは、このポインターを使用して新しく割り当てられたオブジェクトにアクセスします。  
  
 **新しい**演算子関数を呼び出す`operator new`です。 任意の型の配列およびれていないオブジェクトの**クラス**、 `struct`、または**共用体**の種類、グローバル関数では、 **:: 演算子の new**、記憶域を割り当てるために呼び出されます。 クラス型オブジェクトは、クラスごとに異なる `operator new` 静的メンバー関数を定義できます。  
  
 コンパイラが検出した場合、**新しい**型のオブジェクトを割り当てるオペレーター`type`への呼び出しを発行`type` **:: 演算子 new (sizeof (** `type` **))**またはユーザー定義されなかった場合`operator new`が定義されている**:: 演算子 new (sizeof (** `type` **))**です。 したがって、**新しい**演算子は、オブジェクトの正しいメモリの量を割り当てることができます。  
  
> [!NOTE]
>  引数に`operator new`の種類は**size_t**です。 この型は、DIRECT.H、MALLOC.H、MEMORY.H、SEARCH.H、STDDEF.H、STDIO.H、STDLIB.H、STRING.H、および TIME.H で定義されます。  
  
 文法のオプションで指定できる性*配置*(の文法を参照してください[new 演算子](../cpp/new-operator-cpp.md))。 *配置*パラメーターは、ユーザー定義の実装に対してのみ使用することができます`operator new`; に渡される追加の情報は、その`operator new`です。 式は、*配置*などフィールド`T *TObject = new ( 0x0040 ) T;`に変換されます`T *TObject = T::operator new( sizeof( T ), 0x0040 );`クラス T を持つメンバー演算子は、新しい、それ以外の場合に`T *TObject = ::operator new( sizeof( T ), 0x0040 );`です。  
  
 本来の目的、*配置*フィールドは、ユーザーが指定したアドレスに割り当てられるハードウェアに依存するオブジェクトを許可するがします。  
  
> [!NOTE]
>  前の例では、1 つだけの引数が、*配置*フィールドに余分な引数の数を渡すことができますに制限はありません`operator new`こうするとします。  
  
 `operator new` がクラス型に対して定義されている場合でも、次の形式でグローバル演算子を使用できます。  
  
```  
T *TObject =::new TObject;  
```  
  
 スコープ解決演算子 (`::`)、グローバルの使用を強制**新しい**演算子。  
  
## <a name="see-also"></a>関連項目  
 [単項演算子を含む式](../cpp/expressions-with-unary-operators.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [新しい演算子と delete 演算子](../cpp/new-and-delete-operators.md)
