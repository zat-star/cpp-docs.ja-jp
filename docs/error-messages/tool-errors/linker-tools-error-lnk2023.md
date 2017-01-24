---
title: "リンカ ツール エラー LNK2023 | Microsoft Docs"
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
  - "LNK2023"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2023"
ms.assetid: c99e35a8-739a-4a20-a715-29b8c3744703
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK2023
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

不適切な dll またはエントリ \<ポイント dll またはエントリ ポイント\>  
  
 リンカーが間違ったバージョンの msobj90.dll を読み込んでいます。  link.exe とパスに指定した msobj90.dll が同じバージョンかどうかを確認してください。  
  
 msobj90.dll の依存ファイルが存在しない可能性があります。  msobj90.dll の依存ファイルは、次のとおりです。  
  
-   Msvcr90.dll  
  
-   Kernel32.dll  
  
 コンピューターで、msobj90.dll の古いコピーが他に存在していないかどうかをチェックしてください。