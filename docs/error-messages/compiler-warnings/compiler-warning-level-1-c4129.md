---
title: コンパイラの警告 (レベル 1) C4129 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C4129
dev_langs:
- C++
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6405c7c156f34b49ab892304ee51a6b996ac2595
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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