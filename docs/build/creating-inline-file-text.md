---
title: "インライン ファイルのテキストの作成 | Microsoft Docs"
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
  - "インライン ファイル, 作成 (テキストを)"
  - "NMAKE プログラム, インライン ファイル"
  - "テキスト, インライン ファイル"
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# インライン ファイルのテキストの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

インライン ファイルは、一時的な場合と持続的な場合があります。  
  
## 構文  
  
```  
  
      inlinetext  
.  
.  
.  
<<[KEEP | NOKEEP]  
```  
  
## 解説  
 コマンドの後の最初の行で *inlinetext* を指定します。  独立した行の先頭に二重山かっこで終わる \(\<\<\) を配置します。  ファイルには、区切りのかっこまでのすべての *inlinetext* が格納されます。  *inlinetext* では、マクロの展開とマクロでの代入を使用できますが、ディレクティブやメイクファイルのコメントは使用できません。  空白、タブ、および改行文字は、リテラルとして扱われます。  
  
 一時ファイルはセッションの存続期間が終わるまで存在し、ほかのコマンドで再利用できます。  終了を示す山形かっこの後に **KEEP** を指定すると、NMAKE セッションの後もファイルを維持できます。名前のないファイルは、生成されたファイル名を付けてディスクに保存されます。  一時ファイルとして処理するには、**NOKEEP** を指定するか、または何も指定しません。  **KEEP** と **NOKEEP** の表記では、大文字と小文字が区別されません。  
  
## 参照  
 [メイクファイルのインライン ファイル](../build/inline-files-in-a-makefile.md)