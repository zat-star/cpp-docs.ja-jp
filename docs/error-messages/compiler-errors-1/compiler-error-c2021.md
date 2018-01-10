---
title: "コンパイラ エラー C2021 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2021
dev_langs: C++
helpviewer_keywords: C2021
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fd62bc02ce871f87101ebd255690e2ff3d81d176
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2021"></a>コンパイラ エラー C2021
'character' でなく指数の値が必要です  
  
 浮動小数点定数の指数として使用される文字は、有効な数値ではありません。 範囲内にある指数部を使用することを確認します。  
  
## <a name="example"></a>例  
 次の例では、C2021 が生成されます。  
  
```  
// C2021.cpp  
float test1=1.175494351E;   // C2021  
```  
  
## <a name="example"></a>例  
 考えられる解決方法:  
  
```  
// C2021b.cpp  
// compile with: /c  
float test2=1.175494351E8;  
```