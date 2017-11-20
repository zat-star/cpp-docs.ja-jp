---
title: "コンパイラ エラー C3195 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3195
dev_langs: C++
helpviewer_keywords: C3195
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e6e95ce1592c98fae59869e0153ee27c0f727397
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3195"></a>コンパイラ エラー C3195
'operator' : 予約されているため、値型または ref クラスのメンバーとして使用することはできません。 CLR または WinRT の演算子は、'operator' キーワードを使用して定義されなければなりません  
  
コンパイラは、C++ マネージ拡張構文を使用した演算子定義を検出しました。 演算子には、C++ 構文を使用する必要があります。  
  
次の例では、C3195 を生成し、その修正方法を示しています。  
  
```  
// C3195.cpp  
// compile with: /clr /LD  
#using <mscorlib.dll>  
value struct V {  
   static V op_Addition(V v, int i);   // C3195  
   static V operator +(V v, char c);   // OK for new C++ syntax   
};  
```