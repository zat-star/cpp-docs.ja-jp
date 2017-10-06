---
title: "bad_cast 例外 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bad_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- exceptions, bad_cast
- bad_cast keyword [C++]
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
caps.latest.revision: 9
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
ms.openlocfilehash: 70758ca099853f94ad06b8a9f5029203a480a772
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="badcast-exception"></a>bad_cast 例外
`bad_cast` 例外は、参照型へのキャストが失敗した結果として `dynamic_cast` 演算子によってスローされます。  
  
## <a name="syntax"></a>構文  
  
```  
catch (bad_cast)  
   statement  
```  
  
## <a name="remarks"></a>コメント  
 `bad_cast` のインターフェイスは次のとおりです。  
  
```  
class bad_cast : public exception {  
public:  
   bad_cast(const char * _Message = "bad cast");  
   bad_cast(const bad_cast &);  
   virtual ~bad_cast();  
};  
```  
  
 次のコードには、`dynamic_cast` 例外をスローする、失敗した `bad_cast` の例が含まれます。  
  
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
  
 キャストされているオブジェクト (Shape) が、指定したキャスト型 (Circle) から派生していないため、例外がスローされます。 例外を回避するには、`main` に次の宣言を追加します。  
  
```  
Circle circle_instance;  
Circle& ref_circle = circle_instance;  
```  
  
 次に、`try` ブロックのキャストの意味を次のように反転させます。  
  
```  
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);  
```  
  
## <a name="see-also"></a>関連項目  
 [dynamic_cast 演算子](../cpp/dynamic-cast-operator.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [C++ 例外処理](../cpp/cpp-exception-handling.md)
