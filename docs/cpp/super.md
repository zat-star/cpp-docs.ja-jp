---
title: "_ _super |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __super_cpp
dev_langs:
- C++
helpviewer_keywords:
- __super keyword [C++]
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
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
ms.openlocfilehash: 64600f8cf642b0c7906873a73aa4da41897a57f5
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="super"></a>__super
**Microsoft 固有の仕様**  
  
 オーバーライドする関数について、基底クラス実装を呼び出すことを明示できます。  
  
## <a name="syntax"></a>構文  
  
```  
  
__super::  
member_function  
();  
  
```  
  
## <a name="remarks"></a>コメント  
 オーバーロード解決フェーズ時にすべてのアクセス可能な基底クラス メソッドが考慮され、最優先の一致を示す関数が呼び出されます。  
  
 `__super` は、メンバー関数の本体でのみ表示できます。  
  
 `__super` は、using 宣言と共に使用することはできません。 参照してください[宣言を使用して](../cpp/using-declaration.md)詳細についてはします。  
  
 導入に伴い[属性](../windows/cpp-attributes-reference.md)コードを挿入する、コードがわからない場合がありますが、名前に呼び出すメソッドを含む 1 つまたは複数の基底クラスを含めることがあります。  
  
## <a name="example"></a>例  
  
```  
// deriv_super.cpp  
// compile with: /c  
struct B1 {  
   void mf(int) {}  
};  
  
struct B2 {  
   void mf(short) {}  
  
   void mf(char) {}  
};  
  
struct D : B1, B2 {  
   void mf(short) {  
      __super::mf(1);   // Calls B1::mf(int)  
      __super::mf('s');   // Calls B2::mf(char)  
   }  
};  
```  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)
