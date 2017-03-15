---
title: "this ポインター | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "this"
  - "this_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "非静的メンバー関数"
  - "ポインター, クラスのインスタンスへの"
  - "このポインター"
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# this ポインター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**this** ポインターは、**class** 型、`struct` 型、**union** 型の非静的メンバー関数内でのみアクセスできるポインターです。  これは、呼び出されるメンバー関数によって処理されるオブジェクトを指します。  静的メンバー関数には **this** ポインターはありません。  
  
## 構文  
  
```  
  
        this   
this->member-identifier  
```  
  
## 解説  
 オブジェクトの **this** ポインターはオブジェクト自体の一部ではないため、オブジェクトの `sizeof` ステートメントの結果に反映されません。  その代わりに、非静的メンバー関数がオブジェクトに対して呼び出されると、オブジェクトのアドレスが関数の隠し引数としてコンパイラに渡されます。  たとえば、次の関数を呼び出してみましょう。  
  
```  
myDate.setMonth( 3 );  
```  
  
 これは次のように解釈できます。  
  
```  
setMonth( &myDate, 3 );  
```  
  
 このオブジェクトのアドレスは、メンバー関数内から **this** ポインターとして取得できます。  ほとんどの **this** は暗黙的に使用されます。  ただしクラスのメンバーを参照する場合は、明示的に **this** を使用することもできます \(必須ではありません\)。  例:  
  
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
  
 **this** ポインターはまた、自己参照を防止するためにも使用されます。  
  
```  
if (&Object != this) {  
// do not execute in cases of self-reference  
```  
  
> [!NOTE]
>  **this** ポインターは変更できないため、**this** への代入はできません。  C\+\+ の初期の実装では、**this** への代入ができました。  
  
 **this** ポインターは、状況によっては、直接使用されることがあります。たとえば、現在のオブジェクトのアドレスが必要なときに、自己参照用のデータ構造体を操作する場合などです。  
  
## 使用例  
  
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
  
  **my buffer**  
**your buffer**   
## this ポインターの型  
 **this** ポインターの型は、関数宣言でキーワード **const** と `volatile` を使用して変更できます。  これらのキーワードの属性を持つものとして関数を宣言するには、関数の引数リストの後にキーワードを追加します。  
  
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
  
 前のコードはメンバー関数 `X` を宣言し、その中で **this** ポインターは **const** オブジェクトへの **const** ポインターとして扱われています。  *cv\-mod\-list* オプションは組み合わせて使用できますが、これは **this** ポインターそのものではなく、**this** によって指されるオブジェクトを常に変更します。  したがって、次の宣言は関数 `X` を宣言します。**this** ポインターは **const** オブジェクトへの **const** ポインターです。  
  
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
  
 メンバー関数の **this** の型は次の構文で記述されます。ここで *cv\-qualifier\-list* はメンバー関数宣言子から決定され、**const** または **volatile** \(またはその両方\) を指定でき、*class\-type* はクラスの名前です。  
  
 *\[cv\-qualifier\-list\] class\-type*  **\* const this**  
  
 言い換えれば、**this** は常に const ポインターです。再割り当てはできません。  メンバー関数の宣言で使用される **const** 修飾子または `volatile` 修飾子は、その関数のスコープ内で **this** が指すクラス インスタンスに適用されます。  
  
 次の表は、これらの修飾子の機能について詳細を示します。  
  
### this の修飾子のセマンティクス  
  
|修飾子|説明|  
|---------|--------|  
|**const**|メンバー データを変更できません。**const** でないメンバー関数を呼び出すことはできません。|  
|`volatile`|メンバー データはアクセスされるたびにメモリから読み込まれます。特定の最適化は無効になります。|  
  
 **const** オブジェクトを、**const** でないメンバー関数に渡すとエラーになります。  同様に、`volatile` オブジェクトを、`volatile` でないメンバー関数に渡すとエラーになります。  
  
 **const** として宣言されたメンバー関数はメンバー データを変更できません。そのような関数では、**this** ポインターは **const** オブジェクトへのポインターです。  
  
> [!NOTE]
>  コンストラクターとデストラクターを **const** または `volatile` として宣言することはできません。  ただし、**const** または `volatile` オブジェクトについて呼び出すことはできます。  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [this ポインターの型](../misc/type-of-this-pointer.md)   
 [引数一致と this ポインター](../misc/argument-matching-and-the-this-pointer.md)