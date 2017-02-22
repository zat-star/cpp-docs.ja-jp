---
title: "コンパイラ エラー C2893 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2893"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2893"
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# コンパイラ エラー C2893
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

関数テンプレート 'template name' の特定に失敗しました。  
  
 コンパイラでは、関数テンプレートの特殊な形式を作成できませんでした。  このエラーにはさまざまな原因が考えられます。  
  
 通常、C2893 エラーを解決するには、関数のシグネチャを見直して、それぞれの型をインスタンス化できることを確認します。  
  
## 使用例  
 C2893 は、`f` のテンプレート パラメーター `T` が `std::map<int,int>` であると推測されるが、`std::map<int,int>` がメンバー `data_type` を持たないことから発生します \(`T::data_type` は `T = std::map<int,int>` ではインスタンス化できません\)。  次の例では C2893 エラーが生成されます。  
  
```  
// C2893.cpp  
// compile with: /c /EHsc  
#include<map>  
using namespace std;  
class MyClass {};  
  
template<class T>   
inline typename T::data_type  
// try the following line instead  
// inline typename  T::mapped_type  
f(T const& p1, MyClass const& p2);  
  
template<class T>  
void bar(T const& p1) {  
    MyClass r;  
    f(p1,r);   // C2893  
}  
  
int main() {  
   map<int,int> m;  
   bar(m);  
}  
```