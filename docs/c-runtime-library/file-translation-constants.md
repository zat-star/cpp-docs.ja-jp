---
title: "ファイル変換定数 | Microsoft Docs"
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
  - "c.constants.file"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "定数 [C++], ファイル変換モード"
  - "ファイル変換 [C++]"
  - "ファイル変換 [C++], 定数"
  - "変換定数"
  - "変換, 定数"
  - "変換, ファイル変換定数"
ms.assetid: 49b13bf3-442e-4d19-878b-bd1029fa666a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ファイル変換定数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
#include <stdio.h>  
```  
  
## 解説  
 これらの定数は、変換モードを指定します。**"b"** または **"t"**\)。  モードは文字にアクセス \(**"r"**、**"w"**、**"a"**、**"r\+"**、**"w\+"**、**"a\+"**\) の型が含まれます。  
  
 変換モードは次のとおりです。:  
  
 **t**  
 テキスト \(変換\) モードで開きます。  このモードでは、復帰とライン フィード \(CR\-LF\) の組み合わせは、入力時に一つのライン フィード \(LF\) に変換され、LF の文字が出力の CR\-LF の組み合わせに変換されます。  また、Ctrl \+ Z は入力時に EOF \(end\-of\-file\) 文字として解釈されます。  \/書き込み用に読み取るか、読み取ることで開かれたファイルでは `fopen` がファイル末尾に Ctrl \+ Z があるかどうかを確認し、それを、可能な場合は削除します。  これは `fseek` と `ftell` 関数を使用すると、ファイルの終了内で移動するには `fseek` ファイル末尾付近で正しく動作してしまうためです。  
  
> [!NOTE]
>  **t** オプションは `fopen` と `freopen`の ANSI 標準の一部ではありません。  これは ANSI 互換が必要な場合は Microsoft 拡張機能で使用しないでください。  
  
 **b**  
 バイナリ \(無変換\) モードで開きます。  上記の変換は行われません。  
  
 **t** または **b** を mode に指定しないと、変換モードは既定のモードの変数 [\_fmode](../c-runtime-library/fmode.md)によって定義されます。  テキストとバイナリ モードの使用方法の詳細については、「[テキストとバイナリ モードは I\/O があります](../c-runtime-library/text-and-binary-mode-file-i-o.md)」を参照してください。  
  
## 参照  
 [\_fdopen、\_wfdopen](../Topic/_fdopen,%20_wfdopen.md)   
 [fopen、\_wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen、\_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)   
 [\_fsopen、\_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)