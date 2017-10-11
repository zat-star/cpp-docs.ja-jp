---
title: "コンパイラの警告 C4485 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4485
dev_langs:
- C++
helpviewer_keywords:
- C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 435e49a857e3c448ac7e5f7ef00bb9032320aa25
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4485"></a>コンパイラの警告 C4485
'override_function': 基本 ref クラス メソッド 'base_class_function' と一致しますがマークされている 'new' または 'override';'new' (および 'virtual') と見なされます  
  
 アクセサーのオーバーライドの有無、`virtual`キーワード、基本クラスのアクセサー関数では、ですが、`override`または`new`指定子がオーバーライドする関数のシグネチャの一部ではありません。 追加、`new`または`override`この警告を解決するのには指定子。  
  
 参照してください[オーバーライド](../../windows/override-cpp-component-extensions.md)と[new (の新しいスロット vtable)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)詳細についてはします。  
  
 C4485 は常に、エラーとして発行されます。 使用して、[警告](../../preprocessor/warning.md)を抑制する状況 C4485 プラグマ。  
  
## <a name="example"></a>例  
 次のサンプルの生成 C4485  
  
```  
// C4485.cpp  
// compile with: /clr  
delegate void Del();  
  
ref struct A {  
   virtual event Del ^E;  
};  
  
ref struct B : A {  
   virtual event Del ^E;   // C4485  
};  
  
ref struct C : B {  
   virtual event Del ^E {  
      void raise() override {}  
      void add(Del ^) override {}  
      void remove(Del^) override {}  
   }  
};  
```
