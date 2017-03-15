---
title: "ファイル読み出し/書き込みアクセス定数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
helpviewer_keywords: 
  - "アクセス (ファイル読み取り/書き込みの定数に)"
  - "定数 [C++], ファイル属性"
  - "ファイルの読み取り/書き込みアクセス定数"
  - "読み書き両用アクセス定数"
  - "書き込みアクセス定数"
ms.assetid: 56cd1d22-39a5-4fcf-bea2-7046d249e8ee
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ファイル読み出し/書き込みアクセス定数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
#include <stdio.h>  
```  
  
## 解説  
 これらの定数は、アクセスの種類 \(「a」、「r」、または「w」要求\) ファイルに指定します。  [変換モード](../c-runtime-library/file-translation-constants.md) \(「b」または「t」\) パターンと [ディスクにコミット モード](../Topic/Commit-To-Disk%20Constants.md) 両方 \(「c」または「n」アクセスの種類と\) を指定できます。  
  
 アクセスの種類について、次に説明します。  
  
 **"a"**  
 ファイル \(追加など\) の末尾に書き込み用に開く; あるファイルを最初に作成します。  すべての書き込み操作はファイルの末尾に出現します。  ファイル ポインターは `fseek` または **巻き戻し**を使用して移動することもできますが、書き込み操作の前にファイルの末尾に、常に移動されます。  
  
 **"a\+"**  
 上と同じですが、読み取りを割り当てます。  
  
 **"r"**  
 読み取り用に開きます。  ファイルが存在しないか、ファイルを開く呼び出しは失敗します。  
  
 **"r\+"**  
 読み取りと書き込みの両方のモードで開きます。  ファイルが存在しないか、ファイルを開く呼び出しは失敗します。  
  
 **"w"**  
 書き込み用に空のファイルを開きます。  指定したファイルが既に存在すると、そのファイルの内容は破棄されます。  
  
 **"w\+"**  
 読み取りと書き込みの両方のモードで空のファイルを開きます。  指定したファイルが既に存在すると、そのファイルの内容は破棄されます。  
  
 「r\+」、「w\+」、または「a\+」の型を指定すると、読み取りと書き込みの両方を行うことができます \(ファイルは「更新」で開いた呼ばれます\)。  ただし、読み取りと書き込みを切り替える場合、中間の `fflush`、`fsetpos`、`fseek`、または **巻き戻し** 操作が必要です。  現在位置を `fsetpos` または `fseek` 操作に指定できます。  
  
## 参照  
 [\_fdopen、\_wfdopen](../Topic/_fdopen,%20_wfdopen.md)   
 [fopen、\_wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen、\_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)   
 [\_fsopen、\_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [\_popen、\_wpopen](../c-runtime-library/reference/popen-wpopen.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)