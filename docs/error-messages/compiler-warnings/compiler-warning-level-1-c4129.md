---
title: "コンパイラの警告 (レベル 1) C4129 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4129
dev_langs: C++
helpviewer_keywords: C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1efeca1e597af8e7f96b2854fcbcfc49b000009a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4129"></a>コンパイラの警告 (レベル 1) C4129
'character': 認識できない文字エスケープ シーケンス  
  
 `character`次の円記号 (\\) の文字または文字列定数は認識されません、有効なエスケープ シーケンスとして。 バック スラッシュは無視され、印刷されません。 バック スラッシュの後ろの文字が出力されます。  
  
 1 つの円記号を印刷するには、二重の円記号を指定 (\\\\)。  
  
 C++ 標準で 2.13.2 セクションでは、エスケープ シーケンスをについて説明します。  
  
 次の例では、C4129 が生成されます。  
  
```  
// C4129.cpp  
// compile with: /W1  
int main() {  
   char array1[] = "\/709";   // C4129  
   char array2[] = "\n709";   // OK  
}  
```