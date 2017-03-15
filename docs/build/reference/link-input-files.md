---
title: "LINK の入力ファイル | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コマンド入力 (リンカー ファイルの) [C++]"
  - "ファイル [C++], LINK"
  - "インポート ライブラリ [C++], リンカー ファイル"
  - "入力ファイル [C++], LINK"
  - "LINK ツール [C++], 入力ファイル"
  - "リンカー [C++], 入力ファイル"
  - "モジュール定義ファイル"
  - "モジュール定義ファイル, リンカー ファイル"
  - "リソース [C++], リンカー ファイル"
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# LINK の入力ファイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

リンカーには、オブジェクト、インポート ライブラリ、標準ライブラリ、リソース、モジュール定義、コマンド入力などが入ったファイルが必要です。  LINK では、ファイル名の拡張子からファイルの内容を判断せずに、  入力ファイルの内容を調べてそのファイルの種類を判定します。  
  
 コマンド ラインのオブジェクト ファイルは、コマンド ラインで指定された順に処理されます。  ライブラリも、コマンド ラインで指定された順に検索されます。ただし、ライブラリからオブジェクト ファイルに読み込まれたときに未解決のシンボルは、最初にそのライブラリ内で検索され、次にコマンド ラインおよび [\/DEFAULTLIB \(既定のライブラリの指定\)](../../build/reference/defaultlib-specify-default-library.md) ディレクティブでそのライブラリの後にあるライブラリが検索されます。その後、コマンド ラインの最初から他のライブラリが検索されます。  
  
> [!NOTE]
>  LINK では、応答ファイルとオーダー ファイル内のセミコロン \(またはその他の文字\) をコメントの開始位置とは見なしません。  モジュール定義ファイル \(.def\) のセミコロンだけがコメントの始まりと見なされます。  
  
 LINK では、次の入力ファイルを使用します。  
  
-   [.obj ファイル](../../build/reference/dot-obj-files-as-linker-input.md)  
  
-   [.netmodule ファイル](../Topic/.netmodule%20Files%20as%20Linker%20Input.md)  
  
-   [.lib ファイル](../../build/reference/dot-lib-files-as-linker-input.md)  
  
-   [.exp ファイル](../../build/reference/dot-exp-files-as-linker-input.md)  
  
-   [.def ファイル](../../build/reference/dot-def-files-as-linker-input.md)  
  
-   [.pdb ファイル](../../build/reference/dot-pdb-files-as-linker-input.md)  
  
-   [.res ファイル](../../build/reference/dot-res-files-as-linker-input.md)  
  
-   [.exe ファイル](../Topic/.Exe%20Files%20as%20Linker%20Input.md)  
  
-   [.txt ファイル](../../build/reference/dot-txt-files-as-linker-input.md)  
  
-   [.ilk ファイル](../../build/reference/dot-ilk-files-as-linker-input.md)  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)