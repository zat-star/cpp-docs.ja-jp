---
title: "複数のインライン ファイル | Microsoft Docs"
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
  - "インライン ファイル, 複数の NMAKE"
  - "複数のインライン ファイル"
  - "NMAKE プログラム, インライン ファイル"
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 複数のインライン ファイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コマンドでは、複数のインライン ファイルを作成できます。  
  
## 構文  
  
```  
  
      command << <<  
inlinetext  
<<[KEEP | NOKEEP]  
inlinetext  
<<[KEEP | NOKEEP]  
```  
  
## 解説  
 ファイルごとに、インライン テキストを指定し、区切り記号を含む終了行を最後に挿入します。  2 番目のファイルのテキストは、最初のファイルの区切り行の次の行から始めます。  
  
## 参照  
 [メイクファイルのインライン ファイル](../build/inline-files-in-a-makefile.md)