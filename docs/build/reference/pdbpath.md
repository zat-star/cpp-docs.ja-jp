---
title: "/PDBPATH | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/pdbpath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pdb ファイル, パス"
  - "/PDBPATH dumpbin オプション"
  - "PDB ファイル, パス"
  - "PDBPATH dumpbin オプション"
  - "-PDBPATH dumpbin オプション"
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /PDBPATH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDBPATH[:VERBOSE] filename  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 *filename*  
 一致する .pdb ファイルを検索する .dll ファイルまたは .exe ファイルの名前。  
  
 VERBOSE \(省略可能\)  
 .pdb ファイルの検索が行われた全ディレクトリをレポートします。  
  
## 解説  
 \/PDBPATH を指定すると、デバッガーが .pdb ファイルを検索したときと同じパスでコンピューターの検索が行われて、*filename* で指定したファイルに対応する .pdb ファイルがある場合に報告されます。  
  
 Visual Studio デバッガーを使っている場合は、デバッガーが、デバッグ中のファイルとは異なるバージョンの .pdb ファイルを使用しているために問題が発生する場合があります。  
  
 次のパスについて .pdb ファイルの検索が行われます。  
  
-   実行可能ファイルが存在している場所。  
  
-   実行可能ファイルに書き込まれた PDB の場所。  通常は、イメージがリンクされた時点での場所です。  
  
-   Visual Studio IDE で設定されている検索パス。  
  
-   \_NT\_SYMBOL\_PATH 環境変数および \_NT\_ALT\_SYMBOL\_PATH 環境変数で定義されているパス。  
  
-   Windows ディレクトリ。  
  
## 参照  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)   
 [\/PDBALTPATH \(別の PDB パスを使用\)](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)