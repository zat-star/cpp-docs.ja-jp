---
title: bad_typeid 例外 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- bad_typeid
- bad_typeid_cpp
dev_langs:
- C++
helpviewer_keywords:
- bad_typeid exception
- exceptions [C++], bad_typeid
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0771f5e93ba473c9ae1101996e8276bec4cd432a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
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