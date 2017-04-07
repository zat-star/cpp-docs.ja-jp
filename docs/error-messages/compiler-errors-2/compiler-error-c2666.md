---
title: "コンパイラ エラー C2666 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2666
dev_langs:
- C++
helpviewer_keywords:
- C2666
ms.assetid: 78364d15-c6eb-439a-9088-e04a0176692b
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 2ce61109a2d428bbaa5fffdf4bd39de46d09a077
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2666"></a>コンパイラ エラー C2666
'identifier': 数値のオーバー ロードがある同様の変換  
  
 オーバー ロードされた関数または演算子があいまいです。   仮パラメーター リストは、あいまいさを解決するのには、コンパイラのすぎるような可能性があります。  このエラーを解決するには、1 つ以上の実際のパラメーターを明示的にキャストします。  
  
 次の例では、C2666 が生成されます。  
  
```  
// C2666.cpp  
struct complex {  
   complex(double);  
};  
  
void h(int,complex);  
void h(double, double);  
  
int main() {  
   h(3,4);   // C2666  
}  
```  
  
 このエラーは、Visual Studio .NET 2003 で行ったコンパイラへの準拠作業の結果として生成できます。  
  
-   二項演算子とポインター型へのユーザー定義の変換  
  
-   修飾変換は、id 変換と同じではありません。  
  
 二項演算子の\<、>、 \<=、および > =、渡されるパラメーターは今すぐ暗黙的変換、オペランドの型パラメーターの型には、オペランドの型に変換するユーザー定義の変換演算子が定義されている場合。 これであいまいさが発生する可能性。  
  
 Visual Studio .NET 2003 および Visual Studio .NET のバージョンの Visual C の両方で有効なコードでは、関数の構文を使用して明示的にクラスの演算子を呼び出します。  
  
## <a name="example"></a>例  
  
```  
// C2666b.cpp  
#include <string.h>  
#include <stdio.h>  
  
struct T   
{  
    T( const T& copy )   
    {  
        m_str = copy.m_str;  
    }  
  
    T( const char* str )   
    {  
        int iSize = (strlen( str )+ 1);  
        m_str = new char[ iSize ];  
        if (m_str)  
            strcpy_s( m_str, iSize, str );  
    }  
  
    bool operator<( const T& RHS )   
    {  
        return m_str < RHS.m_str;  
    }  
  
    operator char*() const   
    {  
        return m_str;  
    }  
  
    char* m_str;  
};  
  
int main()   
{  
    T str1( "ABCD" );  
    const char* str2 = "DEFG";  
  
    // Error - Ambiguous call to operator<()  
    // Trying to convert str1 to char* and then call   
    // operator<( const char*, const char* )?  
    //  OR  
    // trying to convert str2 to T and then call  
    // T::operator<( const T& )?  
  
    if( str1 < str2 )   // C2666  
  
    if ( str1.operator < ( str2 ) )   // Treat str2 as type T  
        printf_s("str1.operator < ( str2 )\n");  
  
    if ( str1.operator char*() < str2 )   // Treat str1 as type char*  
        printf_s("str1.operator char*() < str2\n");  
}  
```  
  
## <a name="example"></a>例  
 次の例では、C2666 を生成されます。  
  
```  
// C2666c.cpp  
// compile with: /c  
  
enum E   
{  
    E_A,   E_B  
};  
  
class A   
{  
    int h(const E e) const {return 0; }  
    int h(const int i) { return 1; }  
    // Uncomment the following line to resolve.  
    // int h(const E e) { return 0; }  
  
    void Test()   
    {  
        h(E_A);   // C2666  
        h((const int) E_A);  
        h((int) E_A);  
    }  
};  
```
