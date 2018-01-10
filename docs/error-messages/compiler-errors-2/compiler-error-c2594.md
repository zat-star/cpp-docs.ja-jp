---
title: "コンパイラ エラー C2594 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2594
dev_langs: C++
helpviewer_keywords: C2594
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d4cca18672aad77e051ff4428dc115c53cd5ddad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2594"></a>コンパイラ エラー C2594
'operator': 'type1' から 'type2' へのあいまいな変換  
  
 変換なし*type1*に*type2*が他のより直接的なです。 変換を 2 つの考えられる解決策をお勧め*type1*に*type2*です。 直接変換を定義する 1 つ目は*type1*に*type2*からの変換のシーケンスを指定するのには、2 番目のオプションと*type1*に*type2*です。  
  
 次の例では、C2594 を生成します。 エラーに推奨される解決策は、変換のシーケンスを示します。  
  
```  
// C2594.cpp  
// compile with: /c  
struct A{};  
struct I1 : A {};  
struct I2 : A {};  
struct D : I1, I2 {};  
  
A *f (D *p) {  
   return (A*) (p);    // C2594  
  
// try the following line instead  
// return static_cast<A *>(static_cast<I1 *>(p));  
}  
```