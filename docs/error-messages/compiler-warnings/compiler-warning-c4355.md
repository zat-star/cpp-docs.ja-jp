---
title: "コンパイラの警告 C4355 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4355
dev_langs:
- C++
helpviewer_keywords:
- C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 93b6a78365e493cbfea656e608b7bd3d77e600eb
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-c4355"></a>コンパイラの警告 C4355
'this' : ベース メンバー初期化リストで使用されました。  
  
 **この**ポインターが非静的メンバー関数内でのみ有効です。 これは、基底クラスの初期化子リストで使用できません。  
  
 前に、基底クラスのコンス トラクターとクラス メンバーのコンス トラクターが呼び出されます**この**コンス トラクターです。 実際には、別のコンス トラクターに渡してオブジェクトへのポインターをクリアしました。 その他のコンス トラクターは、メンバーにアクセスまたは、このメンバー関数を呼び出して、結果が定義されていることができます。 使用しないでください、**この**すべての構築が完了するまでのポインター。  
  
 既定では、この警告はオフに設定されています。 参照してください[コンパイラの警告ことは既定で無効](../../preprocessor/compiler-warnings-that-are-off-by-default.md)の詳細。  
  
 次の例では、C4355 が生成されます。  
  
```  
// C4355.cpp  
// compile with: /w14355 /c  
#include <tchar.h>  
  
class CDerived;  
class CBase {  
public:  
   CBase(CDerived *derived): m_pDerived(derived) {};  
   ~CBase();  
   virtual void function() = 0;  
  
   CDerived * m_pDerived;  
};  
  
class CDerived : public CBase {  
public:  
   CDerived() : CBase(this) {};   // C4355 "this" used in derived c'tor  
   virtual void function() {};  
};  
  
CBase::~CBase() {  
   m_pDerived -> function();  
}  
  
int main() {  
   CDerived myDerived;  
}  
```
