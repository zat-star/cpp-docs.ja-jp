---
title: "_ _if_exists ステートメント |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __if_exists_cpp
dev_langs:
- C++
helpviewer_keywords:
- identifiers, testing for existence
- symbols, testing for existence
- __if_exists keyword [C++]
ms.assetid: d3eb34b6-f3a9-4063-a286-b62a28c0c7fa
caps.latest.revision: 10
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
ms.openlocfilehash: 3d0eaa00abb1f833ef491fc27bfee01790776edb
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="ifexists-statement"></a>__if_exists ステートメント
`__if_exists` ステートメントは、指定された識別子があるかどうかをテストします。 ID が存在する場合、指定されたステートメント ブロックが実行されます。  
  
## <a name="syntax"></a>構文  
  
```  
__if_exists ( identifier ) {   
statements  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`identifier`|存在をテストしたい識別子。|  
|`statements`|場合に実行する 1 つまたは複数のステートメント`identifier`が存在します。|  
  
## <a name="remarks"></a>コメント  
  
> [!CAUTION]
>  最も信頼できる結果を得るには、次の制約に基づいて `__if_exists` ステートメントを使用します。  
  
-   テンプレートではなく、単純型にのみ `__if_exists` ステートメントを適用します。  
  
-   クラスの内部または外部の識別子に `__if_exists` ステートメントを適用します。 ローカル変数に `__if_exists` ステートメントを適用しないでください。  
  
-   `__if_exists` ステートメントは関数の本体でのみ使用します。 関数本体の外側では、`__if_exists` ステートメントは完全に定義された型のみテストできます。  
  
-   オーバーロードされた関数をテストする場合、特定の形式のオーバーロードはテストできません。  
  
 補完する、`__if_exists`ステートメントは、 [_ _if_not_exists](../cpp/if-not-exists-statement.md)ステートメントです。  
  
## <a name="example"></a>例  
 この例ではテンプレートを使用していますが、これは推奨されません。  
  
```  
// the__if_exists_statement.cpp  
// compile with: /EHsc  
#include <iostream>  
  
template<typename T>  
class X : public T {  
public:  
   void Dump() {  
      std::cout << "In X<T>::Dump()" << std::endl;  
  
      __if_exists(T::Dump) {  
         T::Dump();  
      }  
  
      __if_not_exists(T::Dump) {  
         std::cout << "T::Dump does not exist" << std::endl;  
      }  
   }     
};  
  
class A {  
public:  
   void Dump() {  
      std::cout << "In A::Dump()" << std::endl;  
   }  
};  
  
class B {};  
  
bool g_bFlag = true;  
  
class C {  
public:  
   void f(int);  
   void f(double);  
};  
  
int main() {   
   X<A> x1;  
   X<B> x2;  
  
   x1.Dump();  
   x2.Dump();  
  
   __if_exists(::g_bFlag) {  
      std::cout << "g_bFlag = " << g_bFlag << std::endl;  
   }  
  
   __if_exists(C::f) {  
      std::cout << "C::f exists" << std::endl;  
   }  
  
   return 0;  
}  
```  
  
## <a name="output"></a>出力  
  
```  
In X<T>::Dump()  
In A::Dump()  
In X<T>::Dump()  
T::Dump does not exist  
g_bFlag = 1  
C::f exists  
```  
  
## <a name="see-also"></a>関連項目  
 [選択ステートメント](../cpp/selection-statements-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [__if_not_exists ステートメント](../cpp/if-not-exists-statement.md)
