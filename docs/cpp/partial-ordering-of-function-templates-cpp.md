---
title: "関数テンプレートの部分的な順序付け (C++) | Microsoft Docs"
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
  - "関数テンプレートの部分的な順序付け"
ms.assetid: 0c17347d-0e80-47ad-b5ac-046462d9dc73
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 関数テンプレートの部分的な順序付け (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

関数呼び出しの引数リストと一致する複数の関数テンプレートを使用できます。  C\+\+ では、呼び出す関数を指定するために、関数テンプレートの部分的な順序が定義されています。  順序が部分的なのは、同等に特殊化されていると見なされるテンプレートが存在するためです。  
  
 コンパイラは、使用できる最も特殊化されたテンプレート関数を一致候補から選択します。  たとえば、型 **T** を受け取る関数テンプレートと、**T\*** を受け取る別の関数テンプレートがある場合は、**T\*** バージョンはより特殊化されていると見なされ、両方のテンプレートで有効な一致があっても、引数がポインター型である場合は常に汎用の **T** バージョンよりも優先されます。  
  
 1 つの関数テンプレート候補がより特殊化されたかどうかを確認するには、次の手順を使用します。  
  
1.  T1 および T2 の 2 つの関数テンプレートを考えます。  
  
2.  T1 内のパラメーターを架空の一意の型 X に置き換えます。  
  
3.  T1 のパラメーター リストで、T2 がそのパラメーター リストの有効なテンプレートであるかどうかを確認します。  暗黙の変換は無視します。  
  
4.  T1 と T2 を逆にして、同じ処理を繰り返します。  
  
5.  1 つのテンプレートが他のテンプレートの有効なテンプレート引数リストであっても、その逆が当てはまらない場合、そのテンプレートは他のテンプレートよりも特殊化されていないと見なされます。  前の手順を使用して両方のテンプレートが相互に有効な引数となる場合、両者は同等に特殊化されていると見なされ、これらを使用しようとすると、あいまいな呼び出しになります。  
  
6.  次の規則を使用します。  
  
    1.  特定の型を受け取るテンプレートは、ジェネリック型引数を受け取るテンプレートよりも特殊化されます。  
  
    2.  **T\*** だけを受け取るテンプレートは **T** だけを受け取るテンプレートよりも特殊化されます。その理由は、仮定の型 **X\*** は **T** テンプレート引数の有効な引数ですが、**X** は **T\*** テンプレート引数の有効な引数ではないためです。  
  
    3.  **const T** は、**T** より特殊化されています。その理由は、**const X** は **T** テンプレート引数の有効な引数ですが、**X** は **const T** テンプレート引数の有効な引数ではないためです。  
  
    4.  **const T\*** は、**T\*** より特殊化されています。その理由は、**const X\*** は **T\*** テンプレート引数の有効な引数ですが、**X\*** は **const T\*** テンプレート引数の有効な引数ではないためです。  
  
7.  次のサンプルは、Visual C\+\+ .NET 2003 で標準の仕様のとおりに動作します。  
  
```  
// partial_ordering_of_function_templates.cpp  
// compile with: /EHsc  
#include <iostream>  
  
extern "C" int printf(const char*,...);  
template <class T> void f(T) {  
   printf_s("Less specialized function called\n");  
}  
  
template <class T> void f(T*) {  
   printf_s("More specialized function called\n");  
}  
  
template <class T> void f(const T*) {  
   printf_s("Even more specialized function for const T*\n");  
}  
  
int main() {  
   int i =0;  
   const int j = 0;  
   int *pi = &i;  
   const int *cpi = &j;  
  
   f(i);   // Calls less specialized function.  
   f(pi);  // Calls more specialized function.  
   f(cpi); // Calls even more specialized function.  
   // Without partial ordering, these calls would be ambiguous.  
}  
```  
  
### 出力  
  
```  
Less specialized function called  
More specialized function called  
Even more specialized function for const T*  
```  
  
## 参照  
 [関数テンプレート](../cpp/function-templates.md)