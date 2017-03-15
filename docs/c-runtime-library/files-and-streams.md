---
title: "ファイルとストリーム | Microsoft Docs"
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
  - "ファイル [C++]"
  - "ストリーム"
ms.assetid: f61e712b-eac9-4c28-bb18-97c3786ef387
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# ファイルとストリーム
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プログラムを対象の環境とファイルを読み書きすることで行われます。  ファイルは次のとおりです。:  
  
-   、繰り返し読み書きができるデータ セット。  
  
-   プログラムによって生成されたバイトのストリーム \(パイプラインなど\)。  
  
-   から受け取ったか、周辺機器に送信されたバイトのストリーム。  
  
 最後の 2 項目は対話型ファイルです。  ファイルには、通常、プログラムと対話するための主な方法です。  —ライブラリ関数を呼び出すことによって、これらのすべての種類のファイルとほぼ同じ方法で処理されます。  これらの機能のほとんどを宣言するために標準ヘッダーをインクルード含まれています。  
  
 ファイルの操作の多くを実行する前に開く必要があります。  ファイルを開き、そのストリーム標準 C ライブラリ内のデータ構造にさまざまな種類のファイル間の相違点光沢上に関連付けます。  ライブラリは FILE 型のオブジェクトの各ストリームの状態を維持します。  
  
 対象の環境でプログラム起動前に 3 個のファイルを開きます。  2 番目の引数と [fopen、\_wfopen](../c-runtime-library/reference/fopen-wfopen.md) ライブラリ関数を呼び出してファイルを開くことができます。\(`fopen` 関数の使用は推奨されていません。代わりに [fopen\_s、\_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)\) 最初の引数はファイル名です。  2 番目の引数は、指定する C\+\+.文字列です:  
  
-   ファイルからデータを読み取るか、またはその両方にデータを記述するかどうか。  
  
-   ファイルの新しいコンテンツの前にない \(または作成するファイル\) を生成するため、または既存の内容をそのまま維持するかどうか。  
  
-   ファイルに書き込むかが既存のコンテンツを変更するか、またはファイルの末尾にのみバイトを付ける必要があります。  
  
-   テキスト ストリームまたはバイナリ ストリームを処理するかどうか。  
  
 ファイルが正常に開いた場合、\(バイト ストリーム\) あるいは濃淡方向化、ストリームがバイト指向であるかどうかを調べることができます。広い Stream\)。  ストリームが最初にバインドされます。  ストリームを操作するために、特定の関数を呼び出すと、それをバイト指向、間に他の関数に対するその方向の柔軟な注意してください。  確立されて、ストリームは [fclose](../c-runtime-library/reference/fclose-fcloseall.md) または [freopen](../c-runtime-library/reference/freopen-wfreopen.md)への呼び出しによって閉じるまで方向を保持します。  
  
 P.J.による © 1989\-2001 年。  Plauger とは Brodie。  All rights reserved.  
  
## 参照  
 [テキスト ストリームとバイナリ ストリーム](../c-runtime-library/text-and-binary-streams.md)   
 [バイト ストリームとワイド ストリーム](../c-runtime-library/byte-and-wide-streams.md)   
 [ストリームの制御](../c-runtime-library/controlling-streams.md)   
 [ストリームの状態](../Topic/Stream%20States.md)