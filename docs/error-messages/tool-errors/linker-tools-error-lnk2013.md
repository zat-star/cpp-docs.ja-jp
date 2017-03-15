---
title: "リンカ ツール エラー LNK2013 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2013"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2013"
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# リンカ ツール エラー LNK2013
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fixup type フィックスアップのオーバーフローです。ターゲット 'symbol name' が範囲を超えています。  
  
 ターゲット シンボルが命令の位置から離れすぎているため、リンカーは必要なアドレスまたはオフセットを指定された命令に収めることができません。  
  
 この問題を解決するには、複数のイメージを作成する方法と、命令とターゲットが近くなるように [\/ORDER](../../build/reference/order-put-functions-in-order.md) オプションを使用する方法があります。  
  
 シンボルがユーザー定義シンボルであり、コンパイラが生成したシンボルでない場合は、次の処理を実行して、エラーを解決することもできます。  
  
-   静的関数を非静的関数に変更します。  
  
-   静的関数を含むコード セクションを呼び出し側と同じ名前に変更します。  
  
 `DUMPBIN /SYMBOLS` を使用して、関数が静的かどうかを調べます。