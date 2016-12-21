---
title: "リンカ ツール エラー LNK1140 | Microsoft Docs"
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
  - "LNK1140"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1140"
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK1140
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プログラム データベース モジュールが多すぎます。\/PDB:NONE オプションを指定して再リンクしてください。  
  
 プロジェクトに含まれるモジュール数が 4096 を超えています。  
  
### 次のような解決策を使用して問題を解決するには  
  
1.  [\/PDB:NONE](../../build/reference/pdb-use-program-database.md) オプションを指定して再リンクしてください。  
  
2.  モジュールのいくつかをデバッグ情報なしでコンパイルしてください。  
  
3.  モジュールの数を減らしてください。