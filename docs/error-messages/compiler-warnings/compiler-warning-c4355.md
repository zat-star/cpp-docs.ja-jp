---
title: "コンパイラの警告 C4355 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 061ad3df17cf9c86fbc5ac98048932aff8b0b25b
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4355"></a>コンパイラの警告 C4355
'this' : ベース メンバー初期化リストで使用されました。  
  
 **この**ポインターが非静的メンバー関数内でのみ有効です。 これは、基本クラスの初期化子リストで使用できません。  
  
 基底クラスのコンス トラクターおよびクラス メンバーのコンス トラクターは、前に呼び出されます**この**コンス トラクターです。 実際には、別のコンス トラクターに未構築のオブジェクトにポインターを渡さしました。 その他のコンス トラクターは、メンバーにアクセスまたはこのメンバー関数を呼び出し、結果は定義できません。 使用しないで、**この**すべての構築が完了するまでのポインター。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。  
  
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
