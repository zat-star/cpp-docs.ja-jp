---
title: "インライン ファイルの指定 | Microsoft Docs"
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
  - "ファイル [C++], インライン"
  - "インライン ファイル [C++], 指定 (NMAKE を)"
  - "NMAKE プログラム, インライン ファイル"
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# インライン ファイルの指定
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*ファイル名* を指定するコマンドに 2 個の山かっこ \(\<\<\) を指定します。  山形かっこには、マクロ展開は使用できません。  
  
## 構文  
  
```  
<<[filename]  
```  
  
## 解説  
 コマンドが実行されると、山形かっこは *filename* \(指定されている場合\) または NMAKE で生成された一意の名前で置換されます。  *filename* は、空白またはタブを挿入せず、山形かっこの直後に指定する必要があります。  パスも指定できます。  拡張子は必要ありません。  *filename* が指定されている場合、ファイルは現在のディレクトリまたは指定されたディレクトリに作成されます。また、同じ名前のファイルが既に存在する場合は、そのファイルが上書きされます。*filename* が指定されていない場合、ファイルは TMP ディレクトリ \(TMP 環境変数が定義されていない場合は現在のディレクトリ\) に作成されます。  前の *filename* が再利用される場合は、NMAKE によって前のファイルが置換されます。  
  
## 参照  
 [メイクファイルのインライン ファイル](../build/inline-files-in-a-makefile.md)