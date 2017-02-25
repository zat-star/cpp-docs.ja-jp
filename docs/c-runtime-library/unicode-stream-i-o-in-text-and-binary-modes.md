---
title: "テキスト モードとバイナリ モードの Unicode ストリーム入出力 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.io"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "I/O [CRT], Unicode ストリーム"
  - "ストリーム入出力ルーチン"
  - "Unicode ストリーム入出力"
  - "Unicode, ストリーム入出力ルーチン"
ms.assetid: 68be0c3e-a9e6-4fd5-b34a-1b5207f0e7d6
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# テキスト モードとバイナリ モードの Unicode ストリーム入出力
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unicode のストリーム I\/O ルーチン \(`fwprintf`、`fwscanf`、`fgetwc`、`fputwc`、`fgetws`、または `fputws`など\) テキスト モード \(既定\) で開いているファイルを操作すると、2 種類の文字変換:が行われます。  
  
-   UNICODE に MBCS または MBCS に UNICODE の変換。  Unicode ストリーム I\/O 関数がテキスト モードで実行するときは、ソースまたはターゲットのストリームはマルチバイト文字のシーケンスと見なされます。  このため、Unicode ストリーム入力関数はマルチバイト文字をワイド文字に変換し、`mbtowc` 関数を呼び出した場合と同様の効果を得ます。  同様の理由で、Unicode ストリーム出力関数は、`wctomb` 関数が呼び出されたかのように、ワイド文字をマルチバイト文字に変換します。  
  
-   –復帰とライン フィード \(CR\-LF\) に変換します。  この変換は MBCS – Unicode 変換の前に \(Unicode ストリームの入力関数の場合\) – Unicode と MBCS の変換後に発生します \(Unicode ストリームの出力関数の場合\)。  入力中、各–復帰とライン フィードのペアは、単一のライン フィードの文字に変換されます。  出力中、各ライン フィードの文字は–復帰とライン フィードの組み合わせに変換されます。  
  
 ただし、Unicode ストリーム I\/O 関数がバイナリ モードで実行すると、ファイルは Unicode であると見なされ、CR\-LF の変換または文字変換は入力または出力中に発生しません。  \_setmode \(\_fileno \(stdin\)、\_O\_BINARY\) ;を使用します。手順正しく UNICODE のテキスト ファイルの wcin を使用します。  
  
## 参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)   
 [入出力](../Topic/Input%20and%20Output.md)