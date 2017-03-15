---
title: "リンカ ツール エラー LNK1201 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1201"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1201"
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# リンカ ツール エラー LNK1201
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プログラム データベース 'filename' に書き込めません。ディスク容量不足、パスが無効、また十分な特権がない可能性があります。  
  
 LINK は出力ファイルのプログラム データベース \(PDB\) に書き込むことができませんでした。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  ファイルが破損しています。  PDB ファイルを削除し、再リンクしてください。  
  
2.  ディスクに十分な空き容量がないため、ファイルを書き込むことができません。  
  
3.  ドライブを使用できません。ネットワーク上の問題が原因と考えられます。  
  
4.  リンクを試みているプログラムでデバッガーがアクティブになっています。  
  
5.  ヒープ スペースがありません。詳細については、「[致命的なエラー C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md)」を参照してください。