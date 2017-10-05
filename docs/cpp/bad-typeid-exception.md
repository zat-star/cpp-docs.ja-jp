---
title: "bad_typeid 例外 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bad_typeid
dev_langs:
- C++
helpviewer_keywords:
- bad_typeid exception
- exceptions, bad_typeid
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
caps.latest.revision: 7
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
ms.openlocfilehash: ea7dc85862622180038cf520ef92b752b65eba84
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="badtypeid-exception"></a>bad_typeid 例外
`bad_typeid`によって例外がスローされます、 [typeid 演算子](../cpp/typeid-operator.md)と演算子のオペランド`typeid`NULL ポインターです。  
  
## <a name="syntax"></a>構文  
  
```  
  
      catch (bad_typeid)  
   statement  
```  
  
## <a name="remarks"></a>コメント  
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
  
 次の例は、`typeid` 例外をスローしている `bad_typeid` 演算子を示しています。  
  
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
  
## <a name="output"></a>出力  
  
```  
Object is NULL  
```  
  
## <a name="see-also"></a>関連項目  
 [ランタイム型情報](../cpp/run-time-type-information.md)   
 [キーワード](../cpp/keywords-cpp.md)
