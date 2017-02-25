---
title: "関数テンプレート呼び出しのオーバーロード解決 | Microsoft Docs"
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
  - "関数テンプレートのオーバーロードの解決"
ms.assetid: a2918748-2cbb-4fc6-a176-e256f120bee4
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 関数テンプレート呼び出しのオーバーロード解決
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

関数テンプレートは同じ名前の非テンプレート関数をオーバーロードできます。  このシナリオでは、一意の特殊化により関数テンプレートをインスタンス化するため、関数呼び出しは、最初にテンプレート引数の推論を使用して解決されます。  テンプレート引数の推論が失敗した場合、他の関数オーバーロードが呼び出しを解決すると見なされます。  これらのオーバーロード \(候補の集合とも呼ばれます\) には、非テンプレート関数、およびその他のインスタンス化された関数テンプレートが含まれています。  テンプレート引数の推論に成功すると、オーバーロード解決の規則に従って最適な一致項目を決定するために、生成された関数は他の関数と比較されます。  詳細については、「[オーバーロード](../misc/overloading-cpp.md)」および「[引数の一致](../Topic/Argument%20Matching.md)」を参照してください。  
  
## 使用例  
 非テンプレート関数がテンプレート関数と同等に一致する場合、次の例の呼び出し `f(1, 1)` のように、\(テンプレート引数が明示的に指定されていない限り\) 非テンプレート関数が選択されます。  
  
```  
// template_name_resolution9.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
void f(int, int) { cout << "f(int, int)" << endl; }  
void f(char, char) { cout << "f(char, char)" << endl; }  
  
template <class T1, class T2>  
void f(T1, T2)  
{  
   cout << "void f(T1, T2)" << endl;  
};  
  
int main()  
{  
   f(1, 1);   // Equally good match; choose the nontemplate function.  
   f('a', 1); // Chooses the template function.  
   f<int, int>(2, 2);  // Template arguments explicitly specified.  
}  
```  
  
  **f\(int, int\)**  
**void f\(T1, T2\)**  
**void f\(T1, T2\)**   
## 使用例  
 非テンプレート関数が変換を必要とする場合は、正確に一致するテンプレート関数が推奨されます。次に例を示します。  
  
```  
// template_name_resolution10.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
void f(int, int) { cout << "f(int, int)" << endl; }  
  
template <class T1, class T2>  
void f(T1, T2)  
{  
   cout << "void f(T1, T2)" << endl;  
};  
  
int main()  
{  
   long l = 0;  
   int i = 0;  
   // Call the template function f(long, int) because f(int, int)  
   // would require a conversion from long to int.  
   f(l, i);  
}  
```  
  
  **void f\(T1, T2\)**   
## 参照  
 [名前解決](../cpp/templates-and-name-resolution.md)   
 [typename](../Topic/typename.md)   
 [テンプレート引数の推論](../Topic/Template%20Argument%20Deduction.md)