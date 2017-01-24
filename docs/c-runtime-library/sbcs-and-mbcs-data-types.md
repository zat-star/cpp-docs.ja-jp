---
title: "SBCS および MBCS データ型 | Microsoft Docs"
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
  - "MBCS"
  - "SBCS"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "SBCS および MBCS データ型"
  - "データ型 [C]、MBCS および SBCS"
ms.assetid: 4c3ef9da-e397-48d4-800e-49dba36db171
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# SBCS および MBCS データ型
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

1 文字のマルチバイト文字を処理するかマルチバイト文字の 1 バイトは `unsigned``int` の引数を使用して、`MBCS` Microsoft ランタイム ライブラリ ルーチンが \(WHERE 0x00 \<\= 文字値 \<\= 0x00 \<~ 0xFFFF、\= バイト値 \<\= 0xFF\)。  文字列のコンテキスト内でマルチバイトのバイトまたは文字を処理する `MBCS` ルーチンは、マルチバイト文字列を `unsigned` `char` 型のポインターとして表現することを想定しています。  
  
> [!CAUTION]
>  マルチバイト文字の各バイトは 8 ビットの `char` 型で表現できます。  ただし、0x7F より大きい値を持つ `char` 型の `SBCS` または `MBCS` の 1 バイト文字は負になります。  このような文字を直接 `int` 型または `long` 型に変換すると、コンパイラが結果を符号拡張するため、予測できない結果が生じる場合があります。  
  
 したがって、マルチバイト文字のバイトを表現するには、8 ビットの `unsigned char` 型を使用します。  つまり、結果を負の値にしない場合は、`char` 型の 1 バイト文字を `unsigned char` 型に変換してから `int` 型や `long` 型に変換します。  
  
 `SBCS` 文字列処理関数の中には、\(符号付きの\) `char*` パラメーターを取得するものがあります。このため、`_MBCS` を定義すると、型の不一致を知らせる警告メッセージがコンパイラから出力される場合があります。  この警告を避けるには、次の 3 とおりの方法があります。一番効率的な方法から順に示します。  
  
1.  TCHAR.H の "タイプ セーフ" なインライン関数を使用します。  これが既定の動作です。  
  
2.  「指示するコマンド ラインの `_MB_MAP_DIRECT` を定義して」TCHAR.H マクロを使用します。  この場合は、型を手作業で一致させる必要があります。  これは、最も速い方法ですが、タイプ セーフではありません。  
  
3.  TCHAR.H の "タイプ セーフ" な静的リンク ライブラリ関数を使用します。  この場合は、コマンド ラインで定数 `_NO_INLINING` を定義します。  これは、一番時間がかかりますが、一番タイプ セーフな方法です。  
  
## 参照  
 [国際化](../c-runtime-library/internationalization.md)   
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)