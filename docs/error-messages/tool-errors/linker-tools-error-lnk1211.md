---
title: "リンカ ツール エラー LNK1211 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1211"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1211"
ms.assetid: 607400eb-4180-4892-817f-eedfa628af61
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK1211
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プリコンパイル済みの型情報が見つかりません。'filename' はリンクしていないか、上書きされています。  
  
 [\/Yc](../../build/reference/yc-create-precompiled-header-file.md) オプションを指定してコンパイルされたオブジェクト ファイルが、LINK コマンドで指定されていないか、または上書きされています。  
  
 プリコンパイル済みヘッダーを使用するデバッグ ライブラリを作成する場合、\/Yc と [\/Z7](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) を指定すると、Visual C\+\+ は CodeView デバッグ情報を含むプリコンパイル済みオブジェクト ファイルを生成します。  このエラーは、ライブラリにプリコンパイル済みオブジェクト ファイルを格納して、そのライブラリを使って実行可能イメージをビルドするときに、参照先のオブジェクト ファイルにプリコンパイル済みオブジェクト ファイルで定義した関数の中間参照がないときのみ発生します。  
  
 この問題を回避するには、次の 2 つの方法があります。  
  
-   [\/Yd](../../build/reference/yd-place-debug-information-in-object-file.md) コンパイラ オプションを指定して、プリコンパイル済みヘッダーから各オブジェクト モジュールに CodeView 情報を追加します。  この方法は、通常、大型のオブジェクト モジュールが生成されてアプリケーションのリンク所要時間が長くなる可能性があるため、あまり望ましくありません。  
  
-   [\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) を指定して、関数定義を含まないプリコンパイル済みヘッダー ファイルを作成するときに、任意の文字列の名前を渡します。  これにより、コンパイラに対して、プリコンパイル済みオブジェクト ファイル内でシンボルを作成し、そのシンボルへの参照を関連付けられたプリコンパイル済みヘッダー ファイルを使用している各オブジェクト ファイルで出力するように指示します。  
  
 **\/Yc** と **\/Yl** を指定してモジュールをコンパイルすると、コンパイラでは、`__@@_PchSym_@00@...@symbol_name` のようなシンボルが作成され、オブジェクト モジュールに格納されます。省略記号 \(...\) は、コンパイラにより生成される文字列を表します。  このプリコンパイル済みヘッダーを使用してコンパイルするソース ファイルは、指定したシンボルを参照します。このため、リンカーによりオブジェクト モジュールとライブラリからのデバッグ情報が組み込まれます。  
  
 このエラーの詳細については、サポート技術情報の「PRB: Build Errors Using Precompiled Header in Debugging Lib \(Q102697\)」を参照してください。