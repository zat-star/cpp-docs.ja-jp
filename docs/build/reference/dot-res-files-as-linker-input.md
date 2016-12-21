---
title: "リンカー入力としての .res ファイル | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".res ファイル (リンカー入力)"
  - "リンク [C++], リソース ファイル"
  - "RES ファイル (リンカー入力)"
  - "リソース ファイル, リンク"
ms.assetid: 9c37ab00-97df-4d9a-91cd-6bf132970683
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー入力としての .res ファイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プログラムをリンクするときは、入力ファイルとしてリソース ファイル \(.res\) を指定できます。  .res ファイルは、リソース コンパイラ \(RC: Resource Compiler\) が作成したファイルです。  LINK は、.res ファイルを自動的に COFF 形式に変換します。  したがって、CVTRES.exe ツールは、LINK.exe と同じディレクトリか、環境変数 PATH で指定したディレクトリに置く必要があります。  
  
## 参照  
 [LINK の入力ファイル](../../build/reference/link-input-files.md)   
 [リンカー オプション](../../build/reference/linker-options.md)