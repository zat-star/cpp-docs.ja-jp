---
title: "コンパイラの警告 (レベル 1) C4651 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4651"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4651"
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4651
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'definition' がプリコンパイル済みヘッダーに定義されていますが、現在のコンパイル処理には定義されていません。  
  
 定義はプリコンパイル済みヘッダーが生成されたときに指定されましたが、このコンパイル処理には含まれていません。  
  
 定義はプリコンパイル済みヘッダーでは有効ですが、残りのコードでは無効です。  
  
 プリコンパイル済みヘッダーが \/DSYMBOL を指定して作成されている場合、\/Yu コンパイル処理で \/DSYMBOL が指定されていないと、コンパイラはこの警告を生成します。\/Yu コマンド ラインに \/DSYMBOL を追加すると、この警告は解決します。