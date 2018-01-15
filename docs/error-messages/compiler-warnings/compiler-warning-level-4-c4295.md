---
title: "コンパイラの警告 (レベル 4) C4295 |Microsoft ドキュメント"
ms.custom: 
ms.date: 1/09/2018
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
ms.workload: cplusplus
ms.openlocfilehash: 56ffdce8c2790a3944a8f79753177bc80e249778
ms.sourcegitcommit: bc086a7acbe2d9fd77d115f269cc2a0dbeeb5b88
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2018
---
# <a name="compiler-warning-level-4-c4295"></a>コンパイラの警告 (レベル 4) C4295
  
> '*配列*': 配列が小さすぎるため、終端の null 文字を含める  
  
配列の初期化が、配列の最後の文字は、null ではありません。文字列として配列にアクセスすると、予期しない結果が生じる場合があります。  
  
## <a name="example"></a>例  
  
次の例では、C4295 を生成します。 この問題を解決する可能性がありますを宣言する配列のサイズを保持するより大きなから、初期化文字列または終端の null は、これは、配列のインテントのクリアを配列初期化子リストを使用してでした`char`null で終わる文字列ではありません。  
  
```C  
// C4295.c
// compile with: /W4


int main() {
   char a[3] = "abc";           // C4295
   char b[3] = {'d', 'e', 'f'}; // No warning
   a[0] = b[2];
}
```
