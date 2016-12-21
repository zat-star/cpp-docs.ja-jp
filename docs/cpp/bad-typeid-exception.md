---
title: "bad_typeid 例外 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "bad_typeid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_typeid 例外"
  - "例外, bad_typeid"
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# bad_typeid 例外
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`typeid` のオペランドが NULL ポインターである場合、[typeid 演算子](../cpp/typeid-operator.md)により `bad_typeid` 例外がスローされます。  
  
## 構文  
  
```  
  
      catch (bad_typeid)  
   statement  
```  
  
## 解説  
 `bad_typeid` のインターフェイスは次のとおりです。  
  
```  
class bad_typeid : public exception  
{  
public:  
   bad_typeid(const char * _Message = "bad typeid");  
   bad_typeid(const bad_typeid &);  
   virtual ~bad_typeid();  
};  
```  
  
 次の例は、`bad_typeid` 例外をスローしている `typeid` 演算子を示しています。  
  
```  
// expre_bad_typeid.cpp  
// compile with: /EHsc /GR  
#include <typeinfo.h>  
#include <iostream>  
  
class A{  
public:  
   // object for class needs vtable  
   // for RTTI  
   virtual ~A();  
};  
  
using namespace std;  
int main() {  
A* a = NULL;  
  
try {  
   cout << typeid(*a).name() << endl;  // Error condition  
   }  
catch (bad_typeid){  
   cout << "Object is NULL" << endl;  
   }  
}  
```  
  
## 出力  
  
```  
Object is NULL  
```  
  
## 参照  
 [ランタイム型情報](../Topic/Run-Time%20Type%20Information.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)