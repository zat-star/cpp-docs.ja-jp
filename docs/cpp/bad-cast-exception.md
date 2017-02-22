---
title: "bad_cast 例外 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "bad_cast"
  - "bad_cast_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_cast キーワード [C++]"
  - "例外, bad_cast"
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# bad_cast 例外
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`bad_cast` 例外は、参照型へのキャストが失敗した結果として `dynamic_cast` 演算子によってスローされます。  
  
## 構文  
  
```  
catch (bad_cast)  
   statement  
```  
  
## 解説  
 `bad_cast` のインターフェイスは次のとおりです。  
  
```  
class bad_cast : public exception {  
public:  
   bad_cast(const char * _Message = "bad cast");  
   bad_cast(const bad_cast &);  
   virtual ~bad_cast();  
};  
```  
  
 次のコードには、`bad_cast` 例外をスローする、失敗した `dynamic_cast` の例が含まれます。  
  
```  
// expre_bad_cast_Exception.cpp  
// compile with: /EHsc /GR  
#include <typeinfo.h>  
#include <iostream>  
  
class Shape {  
public:  
   virtual void virtualfunc() const {}  
};  
  
class Circle: public Shape {  
public:  
   virtual void virtualfunc() const {}  
};  
  
using namespace std;  
int main() {  
   Shape shape_instance;  
   Shape& ref_shape = shape_instance;  
   try {  
      Circle& ref_circle = dynamic_cast<Circle&>(ref_shape);   
   }  
   catch (bad_cast b) {  
      cout << "Caught: " << b.what();  
   }  
}  
```  
  
 キャストされているオブジェクト \(Shape\) が、指定したキャスト型 \(Circle\) から派生していないため、例外がスローされます。  例外を回避するには、`main` に次の宣言を追加します。  
  
```  
Circle circle_instance;  
Circle& ref_circle = circle_instance;  
```  
  
 次に、`try` ブロックのキャストの意味を次のように反転させます。  
  
```  
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);  
```  
  
## 参照  
 [dynamic\_cast 演算子](../cpp/dynamic-cast-operator.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [C\+\+ 例外処理](../cpp/cpp-exception-handling.md)