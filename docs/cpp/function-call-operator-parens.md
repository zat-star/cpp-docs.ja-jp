---
title: "関数呼び出し演算子: () | Microsoft Docs"
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
  - "( ) 関数呼び出し演算子"
  - "() 関数呼び出し演算子"
  - "関数呼び出し演算子 ( )"
  - "関数呼び出し, C++ 関数"
  - "関数呼び出し, operator"
  - "関数 [C++], 関数呼び出し演算子"
  - "後置演算子"
ms.assetid: 50c92e59-a4bf-415a-a6ab-d66c679ee80a
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 関数呼び出し演算子: ()
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

後置式の後ろに関数呼び出し演算子 **\( \)** を付けると、関数呼び出しが指定されます。  
  
## 構文  
  
```  
  
postfix-expression   
( [argument-expression-list ] )  
```  
  
## 解説  
 関数呼び出し演算子への引数は、コンマで区切ったゼロ個以上の式 \(関数への実引数\) です。  
  
 *postfix\-expression* は、関数アドレス \(たとえば、関数の識別子または関数ポインターの値\) に評価される必要があります。*argument\-expression\-list* は、式の \(コンマ区切りの\) リストで、各式の値 \(引数\) が関数に渡されます。  *argument\-expression\-list* 引数は空の場合もあります。  
  
 *postfix\-expression* は、次のいずれかの種類である必要があります。  
  
-   関数の戻り値の型 `T`。  以下に宣言例を示します。  
  
    ```  
    T func( int i )  
    ```  
  
-   関数の戻り値の型へのポインター `T`。  以下に宣言例を示します。  
  
    ```  
    T (*func)( int i )  
    ```  
  
-   関数の戻り値の型への参照 `T`。  以下に宣言例を示します。  
  
    ```  
    T (&func)(int i)  
    ```  
  
-   メンバー関数の逆参照戻り値の型へのポインター `T`。  以下に、関数呼び出しの例を示します。  
  
    ```  
    (pObject->*pmf)();  
    (Object.*pmf)();  
    ```  
  
## 使用例  
 次の例では、3 個の引数を持つ標準ライブラリ関数 `strcat_s` を呼び出しています。  
  
```  
// expre_Function_Call_Operator.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string>  
  
// STL name space  
using namespace std;  
  
int main()  
{  
    enum  
    {  
        sizeOfBuffer = 20  
    };  
  
    char s1[ sizeOfBuffer ] = "Welcome to ";  
    char s2[ ] = "C++";  
  
    strcat_s( s1, sizeOfBuffer, s2 );  
  
    cout << s1 << endl;  
}  
```  
  
  **Welcome to C\+\+**   
## 関数呼び出しの結果  
 関数呼び出しは、関数が参照型として宣言されていない限り結果が r 値になります。  参照の戻り値の型を持つ関数は左辺値に評価され、次のように代入ステートメントの左側で使用できます。  
  
```  
// expre_Function_Call_Results.cpp  
// compile with: /EHsc  
#include <iostream>  
class Point  
{  
public:  
    // Define "accessor" functions as  
    // reference types.  
    unsigned& x() { return _x; }  
    unsigned& y() { return _y; }  
private:  
    unsigned _x;  
    unsigned _y;  
};  
  
using namespace std;  
int main()  
{  
    Point ThePoint;  
  
    ThePoint.x() = 7;           // Use x() as an l-value.  
    unsigned y = ThePoint.y();  // Use y() as an r-value.  
  
    // Use x() and y() as r-values.  
    cout << "x = " << ThePoint.x() << "\n"  
         << "y = " << ThePoint.y() << "\n";  
}  
```  
  
 前のコードは、`Point`x と *y* の座標を表すプライベート データ オブジェクトを含む  *というクラスを定義します。* これらのデータ オブジェクトを変更し、値を取得する必要があります。  このプログラムは、このようなクラスのいくつかの設計の 1 つに過ぎません。`GetX` と `SetX` または `GetY` と `SetY` 関数を使う設計も可能です。  
  
 クラス型を返す関数、クラス型へのポインター、またはクラス型への参照は、メンバー選択演算子の左のオペランドとして使用できます。  したがって、次のコードは有効です。  
  
```  
// expre_Function_Results2.cpp  
class A {  
public:  
   A() {}  
   A(int i) {}  
   int SetA( int i ) {  
      return (I = i);  
   }  
  
   int GetA() {  
      return I;  
   }  
  
private:  
   int I;  
};  
  
A func1() {  
   A a = 0;  
   return a;  
}  
  
A* func2() {  
   A *a = new A();  
   return a;  
}  
  
A& func3() {  
   A *a = new A();  
   A &b = *a;  
   return b;  
}  
  
int main() {  
   int iResult = func1().GetA();  
   func2()->SetA( 3 );  
   func3().SetA( 7 );  
}  
```  
  
 関数は再帰的に呼び出すことができます。  関数の宣言に関する詳細については、「[関数指定子](../misc/function-specifiers.md)」および「[メンバー関数](../Topic/Member%20Functions%20\(C++\).md)」を参照してください。  関連資料は「[プログラムとリンケージ](../cpp/program-and-linkage-cpp.md)」にあります。  
  
## 参照  
 [後置式](../cpp/postfix-expressions.md)   
 [C\+\+ Operators](../misc/cpp-operators.md)   
 [C\+\+ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [関数呼び出し](../c-language/function-call-c.md)   
 [\(NOTINBUILD\) Function Declarations](http://msdn.microsoft.com/ja-jp/3f9b4e14-60d2-47c1-acd8-4fa8fc988be7)