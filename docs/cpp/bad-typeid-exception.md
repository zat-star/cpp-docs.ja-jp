---
title: "bad_typeid 例外 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bad_typeid
- bad_typeid_cpp
dev_langs: C++
helpviewer_keywords:
- bad_typeid exception
- exceptions [C++], bad_typeid
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9409bd83132877f73b58e12cb9503c41a3dc3cf9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="see-also"></a>参照  
 [ランタイム型情報](../cpp/run-time-type-information.md)   
 [キーワード](../cpp/keywords-cpp.md)