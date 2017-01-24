---
title: "/PDBALTPATH (別の PDB パスを使用) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/pdbaltpath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pdb ファイル, パス"
  - "/PDBALTPATH dumpbin オプション"
  - "PDB ファイル, パス"
  - "PDBALTPATH dumpbin オプション"
  - "-PDBALTPATH dumpbin オプション"
ms.assetid: 72e200aa-e2c3-4ad8-b687-25528da1aaaf
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /PDBALTPATH (別の PDB パスを使用)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDBALTPATH:pdb_file_name  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 *pdb\_file\_name*  
 .pdb ファイルのパスとファイル名です。  
  
## 解説  
 このオプションを使って、コンパイルされたバイナリ ファイルにプログラム データベース \(.pdb\) ファイルの別の場所を提供します。  通常、リンカーは作成するバイナリの中に .pdb ファイルの場所を記録します。  このオプションを使って .pdb ファイルに異なるパスとファイル名を提供できます。  \/PDBALTPATH で提供される情報は、実際の .pdb ファイルの場所や名前を変更するわけではなく、リンカーがバイナリ ファイルに書き込む情報を変更します。  これにより、ビルド コンピューターのファイル構造とは独立したパスを提供できます。  このオプションの 2 つの一般的な使用方法は、ネットワーク パスまたはパス情報のないファイルを提供することです。  
  
 *pdb\_file\_name* の値は、任意の文字列、環境変数、または **%\_PDB%** にすることができます。  リンカーは **%SystemRoot%** などの環境変数をその値に拡張します。  リンカーは環境変数 **%\_PDB%** および **%\_EXT%** を定義します。  **%\_PDB%** は実際の .pdb ファイルのファイル名にパス情報がないまま拡張し、**%\_EXT%** は生成された実行ファイルの拡張子です。  
  
## 参照  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)   
 [\/PDBPATH](../../build/reference/pdbpath.md)