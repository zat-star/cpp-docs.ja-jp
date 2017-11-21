---
title: "コンパイラの警告 (レベル 4) C4295 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4295
dev_langs: C++
helpviewer_keywords: C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5815aab6163c7dc6ffa8bf89bbf56259724d02b5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4295"></a>コンパイラの警告 (レベル 4) C4295
  
> '*配列*': 配列が小さすぎるため、終端の null 文字を含める  
  
 配列の初期化が、配列の最後の文字は、null ではありません。配列にアクセスすると、予期しない結果が生じる場合があります。  
  
## <a name="example"></a>例  
  
 次の例では、C4295 を生成します。 この問題を解決する可能性がありますを宣言する配列のサイズ終端を保持するために、大規模な初期化子から null です。  
  
```C  
// C4295.c  
// compile with: /W4  
  
int main() {  
   char a[3] = "abc";   // C4295  
}  
```