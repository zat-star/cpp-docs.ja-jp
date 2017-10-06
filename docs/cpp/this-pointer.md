---
title: "このポインター |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- this_cpp
dev_langs:
- C++
helpviewer_keywords:
- nonstatic member functions
- pointers, to class instance
- this pointer
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
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
ms.openlocfilehash: 86ccf50a089b1497bdc166ee9367215dc59b3ca1
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="this-pointer"></a>this ポインター
**この**ポインターは、ポインターの非静的メンバー関数内でのみアクセス可能な**クラス**、 `struct`、または**共用体**型です。 これは、呼び出されるメンバー関数によって処理されるオブジェクトを指します。 静的メンバー関数はありません、**この**ポインター。  
  
## <a name="syntax"></a>構文  
  
```  
  
      this   
this->member-identifier  
```  
  
## <a name="remarks"></a>コメント  
 オブジェクトの**この**ポインターがオブジェクト自体の一部ではないの結果には反映されません、`sizeof`オブジェクトのステートメント。 その代わりに、非静的メンバー関数がオブジェクトに対して呼び出されると、オブジェクトのアドレスが関数の隠し引数としてコンパイラに渡されます。 たとえば、次の関数を呼び出してみましょう。  
  
```  
myDate.setMonth( 3 );  
```  
  
 これは次のように解釈できます。  
  
```  
setMonth( &myDate, 3 );  
```  
  
 オブジェクトのアドレスは、メンバー関数内から使用可能、**この**ポインター。 ほとんどの用途**この**は暗黙的です。 明示的に使用する、不要な場合は法律、**この**クラスのメンバーを参照する場合。 例:  
  
```  
void Date::setMonth( int mn )  
{  
   month = mn;            // These three statements  
   this->month = mn;      // are equivalent  
   (*this).month = mn;  
}  
```  
  
 式 `*this` は、通常、メンバー関数から現在のオブジェクトを返すために使用されます。  
  
```  
return *this;  
```  
  
 **この**ポインターは自己参照を防止にも使用します。  
  
```  
if (&Object != this) {  
// do not execute in cases of self-reference  
```  
  
> [!NOTE]
>  **この**ポインターは変更できないへの代入**この**は許可されていません。 C の以前の実装への割り当てが許可されている**この**です。  
  
 場合によっては、**この**ポインターを直接使用 — たとえば、自己参照型のデータを操作する構造体を現在のオブジェクトのアドレスが必要です。  
  
## <a name="example"></a>例  
  
```  
// this_pointer.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string.h>  
  
using namespace std;  
  
class Buf   
{  
public:  
    Buf( char* szBuffer, size_t sizeOfBuffer );  
    Buf& operator=( const Buf & );  
    void Display() { cout << buffer << endl; }  
  
private:  
    char*   buffer;  
    size_t  sizeOfBuffer;  
};  
  
Buf::Buf( char* szBuffer, size_t sizeOfBuffer )  
{  
    sizeOfBuffer++; // account for a NULL terminator  
  
    buffer = new char[ sizeOfBuffer ];  
    if (buffer)  
    {  
        strcpy_s( buffer, sizeOfBuffer, szBuffer );  
        sizeOfBuffer = sizeOfBuffer;  
    }  
}  
  
Buf& Buf::operator=( const Buf &otherbuf )   
{  
    if( &otherbuf != this )   
    {  
        if (buffer)  
            delete [] buffer;  
  
        sizeOfBuffer =  strlen( otherbuf.buffer ) + 1;   
        buffer = new char[sizeOfBuffer];  
        strcpy_s( buffer, sizeOfBuffer, otherbuf.buffer );  
    }  
    return *this;  
}  
  
int main()  
{  
    Buf myBuf( "my buffer", 10 );  
    Buf yourBuf( "your buffer", 12 );  
  
    // Display 'my buffer'  
    myBuf.Display();  
  
    // assignment opperator  
    myBuf = yourBuf;  
  
    // Display 'your buffer'  
    myBuf.Display();  
}  
```  
  
```Output  
my buffer  
your buffer  
```  
  
## <a name="type-of-the-this-pointer"></a>this ポインターの型  
 **この**によって関数の宣言でポインターの型を変更することができます、 **const**と`volatile`キーワード。 これらのキーワードの属性を持つものとして関数を宣言するには、関数の引数リストの後にキーワードを追加します。  
  
 次の例について考えます。  
  
```  
// type_of_this_pointer1.cpp  
class Point  
{  
    unsigned X() const;  
};  
int main()  
{  
}  
```  
  
 上記のコードが、メンバー関数を宣言`X`を**この**ポインターとして扱われます、 **const**へのポインター、 **const**オブジェクト。 組み合わせ*cv mod リスト*オプションを使用できますが、常にによって指されるオブジェクトを変更**この**ではなく、**この**ポインター自体です。 次の宣言が関数を宣言するため、 `X`;**この**ポインターが、 **const**へのポインター、 **const**オブジェクト。  
  
```  
// type_of_this_pointer2.cpp  
class Point  
{  
    unsigned X() const;  
};  
int main()  
{  
}  
```  
  
 型**この**メンバー関数は、次の構文によって記述場所*cv 修飾子リスト*メンバー関数宣言子から決定でき、 **const**または**揮発性**(または両方) および*クラス型*クラスの名前を指定します。  
  
 *[cv 修飾子リスト] で、クラス型*** \* const この  **  
  
 つまり、**この**は常に const ポインターです。 再割り当てすることはできません。  **Const**または`volatile`メンバー関数の宣言で使用されている修飾子が指すクラス インスタンスに適用**この**その関数のスコープにします。  
  
 次の表は、これらの修飾子の機能について詳細を示します。  
  
### <a name="semantics-of-this-modifiers"></a>this の修飾子のセマンティクス  
  
|修飾子|説明|  
|--------------|-------------|  
|**const**|メンバー データを変更することはできません。されていないメンバー関数を呼び出すことはできません**const**です。|  
|`volatile`|メンバー データはアクセスされるたびにメモリから読み込まれます。特定の最適化は無効になります。|  
  
 渡すとエラーには、 **const**オブジェクトではないメンバー関数を**const**です。 同様に、`volatile` オブジェクトを、`volatile` でないメンバー関数に渡すとエラーになります。  
  
 メンバー関数として宣言**const**メンバー データを変更できません-このような関数で、**この**ポインターへのポインターは、 **const**オブジェクト。  
  
> [!NOTE]
>  コンス トラクターとデストラクターとして宣言することはできません**const**または`volatile`です。 これらを指定できます、ただしで呼び出される**const**または`volatile`オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)   
 
