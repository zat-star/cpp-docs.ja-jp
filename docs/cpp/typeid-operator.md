---
title: "typeid 演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "typeid 演算子"
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# typeid 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
      typeid(   
      type-id  
       )  
typeid( expression )  
```  
  
## 解説  
 `typeid` 演算子は、オブジェクトの型を実行時に決定できるようにします。  
  
 `typeid` の結果は、**const type\_info&** です。  値は、使用されている `typeid` の形式に応じて、*type\-id* または *expression* の形式を表す **type\_info** オブジェクトへの参照です。  詳細については、[type\_info クラス](../cpp/type-info-class.md)を参照してください。  
  
 `typeid` 演算子は、マネージ型 \(抽象宣言子またはインスタンス\) では機能しません。指定された型の <xref:System.Type> の取得の詳細については、「[typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md)」を参照してください。  
  
 `typeid` 演算子は、オブジェクトの実際の型を指定された静的な情報によって判断できない場合に、ポリモーフィックなクラス型の左辺値への適用時にランタイム チェックを実行します。  そのようなケースを次に示します。  
  
-   クラスへの参照  
  
-   \* で逆参照されるポインター  
  
-   添字付きのポインター \(\[ \]\)  \(一般に、ポリモーフィックな型へのポインターで添字を使用すると、安全ではないことに注意してください\)。  
  
 式が基底クラス型を指し示していても、実際にはオブジェクトがその基底クラスから派生した型である場合、派生クラスの **type\_info** 参照が結果になります。  *式*はポリモーフィック型 \(仮想関数のあるクラス\) をポイントする必要があります。  それ以外の場合、結果は *expression* で参照される静的クラスの **type\_info** です。  さらに、ポインターが指し示すオブジェクトが使用されるように、ポインターを逆参照する必要があります。  ポインターの逆参照が行われない場合、結果はポインターが指しているものではなく、ポインターの **type\_info** です。  次に例を示します。  
  
```  
// expre_typeid_Operator.cpp  
// compile with: /GR /EHsc  
#include <iostream>  
#include <typeinfo.h>  
  
class Base {  
public:  
   virtual void vvfunc() {}  
};  
  
class Derived : public Base {};  
  
using namespace std;  
int main() {  
   Derived* pd = new Derived;  
   Base* pb = pd;  
   cout << typeid( pb ).name() << endl;   //prints "class Base *"  
   cout << typeid( *pb ).name() << endl;   //prints "class Derived"  
   cout << typeid( pd ).name() << endl;   //prints "class Derived *"  
   cout << typeid( *pd ).name() << endl;   //prints "class Derived"  
   delete pd;  
}  
```  
  
 式がポインターを逆参照し、そのポインターの値がゼロの場合、**typeid** は [bad\_typeid 例外](../cpp/bad-typeid-exception.md)をスローします。  ポインターが有効なオブジェクトを指し示していない場合、`__non_rtti_object` 例外がスローされ、オブジェクトが無効 \(無効なポインターであるか、コードが [\/GR](../Topic/-GR%20\(Enable%20Run-Time%20Type%20Information\).md) でコンパイルされていない\) であるため、\(アクセス違反などの\) エラーをトリガーした RTTI を分析しようとしていることが示されます。  
  
 式がオブジェクトの基底クラスへのポインターまたは参照でない場合、結果は式の静的な型を表す **type\_info** 参照になります。  式の *static type* は、コンパイル時に既知のときに式の型を参照します。  実行セマンティクスは、式の静的な型を評価するときは無視されます。  さらに、式の静的な型を判断するときに、参照は可能な限り無視されます。  
  
```  
// expre_typeid_Operator_2.cpp  
#include <typeinfo>  
  
int main()  
{  
   typeid(int) == typeid(int&); // evaluates to true  
}  
```  
  
 **typeid** は、テンプレート パラメーターの型を決定するためにテンプレート内で使用することもできます。  
  
```  
// expre_typeid_Operator_3.cpp  
// compile with: /c  
#include <typeinfo>  
template < typename T >   
T max( T arg1, T arg2 ) {  
   cout << typeid( T ).name() << "s compared." << endl;  
   return ( arg1 > arg2 ? arg1 : arg2 );  
}  
```  
  
## 参照  
 [ランタイム型情報](../Topic/Run-Time%20Type%20Information.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)