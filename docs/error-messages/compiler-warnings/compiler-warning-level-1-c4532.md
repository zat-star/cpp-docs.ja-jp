---
title: "コンパイラの警告 (レベル 1) C4532 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4532
dev_langs: C++
helpviewer_keywords: C4532
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5cec2f70dfa6781c237cc1c08079904c7b48e171
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4532"></a>コンパイラの警告 (レベル 1) C4532
'continue': _ _finally/finally にブロックからのジャンプが動作を終了処理時に定義されていません  
  
 コンパイラでは、次のキーワードのいずれかが発生しました。  
  
-   [continue](../../cpp/continue-statement-cpp.md)  
  
-   [break](../../cpp/break-statement-cpp.md)  
  
-   [goto](../../cpp/goto-statement-cpp.md)  
  
 ジャンプを発生、 [_ _finally](../../cpp/try-finally-statement.md)または[finally](../../dotnet/finally.md)異常終了時にブロックします。  
  
 終了ハンドラーの実行中に、スタックが展開されるときに例外が発生する場合、(、`__finally`または finally ブロック)、コードがの外部にジャンプして、`__finally`する前にブロック、`__finally`ブロック終了すると、動作が定義されていません。 コントロールは可能性があります、例外が正しく処理されないため、アンワインド コードに返されません。  
  
 場合の外に移動する必要があります、 **_ _finally**ブロックは、最初に異常終了を確認します。  
  
 次の例には、C4532; が生成されます。単にコメントを使用して、警告を解決するのには、ジャンプ ステートメント アウトします。  
  
```  
// C4532.cpp  
// compile with: /W1  
// C4532 expected  
int main() {  
   int i;  
   for (i = 0; i < 10; i++) {  
      __try {  
      } __finally {  
         // Delete the following line to resolve.  
         continue;  
      }  
  
      __try {  
      } __finally {  
         // Delete the following line to resolve.  
         break;  
      }  
   }  
}  
```