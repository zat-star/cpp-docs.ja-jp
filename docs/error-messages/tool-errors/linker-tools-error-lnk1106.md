---
title: "リンカ ツール エラー LNK1106 | Microsoft Docs"
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
  - "LNK1106"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1106"
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK1106
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルが無効であるか、またはディスクの空き領域がありません : location にシークできません。  
  
 メモリ マップト ファイルの位置 `location` に読み書きできません。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  ディスクに空きがありません。  
  
     十分なディスク容量を確保して、リンクを再試行します。  
  
2.  ネットワーク上でリンクを試みたことによるエラーである可能性があります。  
  
     ネットワークによっては、リンカーが使用するメモリ マップト ファイルに完全には対応していないものがあります。  ローカル ディスクでリンクを試行します。  
  
3.  ディスクに不良ブロックがあります。  
  
     このようなエラーはオペレーティング システムとディスクのハードウェアによって検出されますが、ディスク検査プログラムを実行することもできます。  
  
4.  ヒープ スペースがありません。  
  
     詳細については、「[致命的なエラー C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md)」を参照してください。