---
title: "コンパイラの警告 (レベル 1) C4393 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4393
dev_langs: C++
helpviewer_keywords: C4393
ms.assetid: 353a0539-d1ea-4c1b-8849-c9b321ec9842
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 76c29081f2423464f235e7ff15b76b7bdcb35d3a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4393"></a>コンパイラの警告 (レベル 1) C4393
'var': const リテラル データ メンバーに影響を与えません無視されます。  
  
 A[リテラル](../../windows/literal-cpp-component-extensions.md)データ メンバーを定数としても指定されました。  リテラル データ メンバーには、const からわかるように、のでする必要はありませんを追加する宣言に定数。  
  
 次の例では、C4393 が生成されます。  
  
```  
// C4393.cpp  
// compile with: /clr /W1 /c  
ref struct Y1 {  
   literal const int staticConst = 10;   // C4393  
   literal int staticConst2 = 10;   // OK  
};  
```