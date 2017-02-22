---
title: "インライン ファイルの再利用 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "インライン ファイル, 再利用 (NMAKE を)"
  - "NMAKE プログラム, インライン ファイル"
  - "改訂 (インライン ファイルを)"
ms.assetid: d42dbffb-2cef-4ccb-9a1f-20b8ef81481c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# インライン ファイルの再利用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

インライン ファイルを再利用するには、ファイルが定義され、最初に使用される同じまたは別のコマンド ラインで、*ファイル名*、および再利用の *ファイル名を* 指定せずに \<\< 指定 \<\<します。  インライン ファイルを作成するコマンドは、そのファイルを使用するすべてのコマンドの前に実行する必要があります。  
  
## 参照  
 [メイクファイルのインライン ファイル](../build/inline-files-in-a-makefile.md)