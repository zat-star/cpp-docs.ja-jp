---
title: "コンパイラ エラー C2553 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2553
dev_langs: C++
helpviewer_keywords: C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 623a09c54333ef62de7a7924cc4be02ff1b2c726
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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