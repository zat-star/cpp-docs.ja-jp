---
title: "変換モード定数 | Microsoft Docs"
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
  - "_O_BINARY"
  - "_O_TEXT"
  - "_O_RAW"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_O_BINARY 定数"
  - "_O_RAW 定数"
  - "_O_TEXT 定数"
  - "O_BINARY 定数"
  - "O_RAW 定数"
  - "O_TEXT 定数"
  - "変換定数"
  - "変換モード (ファイル I/O)"
  - "変換, 定数"
  - "変換, モード"
ms.assetid: a5993bf4-7e7a-47f9-83c3-e46332b85579
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 変換モード定数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
#include <fcntl.h>  
  
```  
  
## 解説  
 `_O_BINARY` と `_O_TEXT` の記号定数はファイルの変換モード \(`_open` と `_sopen`\) またはストリーム \(`_setmode`\) の変換モードを調べます。  
  
 有効な値は以下のものがあります。  
  
 `_O_TEXT`  
 テキスト \(変換\) モードをでファイルを開きます。  –復帰とライン フィード \(CR\-LF\) の組み合わせは、入力時に一つのライン フィード \(LF\) に変換されます。  ライン フィードの文字が出力の CR\-LF の組み合わせに変換されます。  また、Ctrl \+ Z は入力時に EOF \(end\-of\-file\) 文字として解釈されます。  読み取り\/書き込み用に、読み取ることで開かれたファイルでは `fopen` がファイル末尾に Ctrl \+ Z があるかどうかを確認し、それを、可能な場合は削除します。  これは `fseek` と `ftell` 関数を使用すると、ファイルの終了内で移動するには `fseek` ファイル末尾付近で正しく動作してしまうためです。  
  
 `_O_BINARY`  
 バイナリ \(無変換\) モードをでファイルを開きます。  上記の変換は行われません。  
  
 `_O_RAW`  
 `_O_BINARY` と同じ。  C 2.0 互換はサポートされます。  
  
 詳細については、「[テキストとファイル I\/O バイナリ モード](../c-runtime-library/text-and-binary-mode-file-i-o.md) と [ファイルの変換](../c-runtime-library/file-translation-constants.md)」を参照してください。  
  
## 参照  
 [\_open、\_wopen](../c-runtime-library/reference/open-wopen.md)   
 [\_pipe](../c-runtime-library/reference/pipe.md)   
 [\_sopen、\_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [\_setmode](../c-runtime-library/reference/setmode.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)