---
title: "コンパイラの警告 (レベル 1) C4964 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4964
dev_langs: C++
helpviewer_keywords: C4964
ms.assetid: b89c9274-8a92-4b7c-aa30-3fbb1b68ac73
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 272e9dec1a0f587d4e381e482f7bbf089cc8e4c9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4964"></a>コンパイラの警告 (レベル 1) C4964
最適化のオプションが指定されていません。プロファイル情報は収集されません。  
  
 [/GL](../../build/reference/gl-whole-program-optimization.md)と[/LTCG](../../build/reference/ltcg-link-time-code-generation.md)最適化なしですが、指定された要求されたため、.pgc ファイルは生成されませんし、そのため、プロファイル ガイド付き最適化することはできません。  
  
 .Pgc ファイルをアプリケーションを実行するときに生成する場合は、いずれかを指定、 [/O](../../build/reference/o-options-optimize-code.md)コンパイラ オプション。  
  
 次の例では、C4964 が生成されます。  
  
```  
// C4964.cpp  
// compile with: /W1 /GL /link /ltcg:pgi  
// C4964 expected  
// Add /O2, for example, to the command line to resolve this warning.  
int main() {  
   int i;  
}  
```