---
title: "コンパイラ エラー C2553 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2553
dev_langs:
- C++
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a1b701773ccb5156a6365e938b0deea6d8e7f15e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2553"></a>コンパイラ エラー C2553
'base_function': 仮想関数をオーバーライドするには、'override_function' とは異なる型が戻り値  
  
 派生クラス内の関数は、基底クラスの仮想関数をオーバーライドしようとしていますが、派生クラスの関数は基底クラス関数と同じ戻り値の型がありません。  オーバーライド関数のシグネチャは、オーバーライドされる関数のシグネチャと一致する必要があります。  
  
 次の例では、C2553 が生成されます。  
  
```  
// C2553.cpp  
// compile with: /clr /c  
ref struct C {  
   virtual void f();  
};  
  
ref struct D : C {  
   virtual int f() override ;   // C2553   
  
   // try the following line instead  
   // virtual void f() override;  
};  
```