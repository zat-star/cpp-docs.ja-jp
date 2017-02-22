---
title: "BSCMAKE エラー BK1506 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "BK1506"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1506"
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# BSCMAKE エラー BK1506
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイル 'filename' を開けません。\[: reason\]  
  
 ファイルを開けません。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  ファイルが別のプロセスによってロックされています。  `reason` に "**Permission denied**" と表示されている場合は、ブラウザーがこのファイルを使用している可能性があります。  \[Browse\] ウィンドウを閉じて、ビルドし直してください。  
  
2.  ディスクの空き領域が不足しています。  
  
3.  ハードウェア エラーです。  
  
4.  指定した出力ファイル名が既存のサブフォルダー名と重複しています。