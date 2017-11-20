---
title: "コンパイラの警告 (レベル 1) C4142 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4142
dev_langs: C++
helpviewer_keywords: C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7426b1ff7b22382617e2ab6cec4e54456a117aec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4142"></a>コンパイラの警告 (レベル 1) C4142
型の害のない再定義されています  
  
 型は、生成されたコードに影響が方法で再定義されていません。  
  
 次のような原因をチェックして問題を解決するには:  
  
-   派生クラスのメンバー関数では、基本クラスの対応するメンバー関数から異なる戻り値の型があります。  
  
-   定義されている型、`typedef`別の構文を使用して、コマンドが再定義します。  
  
 次の例では、C4142 が生成されます。  
  
```  
// C4142.c  
// compile with: /W1  
float X2;  
X2 = 2.0 + 1.0;   // C4142  
  
int main() {  
   float X2;  
   X2 = 2.0 + 1.0;   // OK  
}  
```