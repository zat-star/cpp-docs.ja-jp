---
title: "コンパイラ エラー C3920 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3920
dev_langs: C++
helpviewer_keywords: C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e2bf82de4e32c2b0ae586c78c69ce474947c3ec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3920"></a>コンパイラ エラー C3920
' operator ': 後置インクリメント/デクリメントの WinRT または CLR 演算子の後置形式は定義できません WinRT または CLR 演算子には、対応するプレフィックスを呼び出す WinRT または CLR 演算子 (op_Increment/op_Decrement) が、後置形式のセマンティクスで  
  
 Windows Runtime および CLR は後置演算子をサポートしておらず、ユーザー定義後置演算子は許可されていません。  前置演算子は定義でき、プレ インクリメント演算でもポスト インクリメント演算でも前置演算子が使用されます。  
  
 次の例では、C3920 を生成し、その修正方法を示しています。  
  
```  
// C3920.cpp  
// compile with: /clr /LD  
public value struct V {  
   static V operator ++(V me, int)  
   // try the following line instead  
   // static V operator ++(V me)  
   {   // C3920  
      me.m_i++;  
      return me;  
   }  
  
   int m_i;  
};  
  
```