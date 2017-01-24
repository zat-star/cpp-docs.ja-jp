---
title: "ストリームの制御 | Microsoft Docs"
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
  - "Controlling Streams"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "制御 (ストリームを)"
  - "ストリーム"
  - "ストリーム, 制御"
ms.assetid: 267e9013-9afc-45f6-91e3-ca093230d9d9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ストリームの制御
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[fopen](../c-runtime-library/reference/fopen-wfopen.md) は 型 `FILE`オブジェクトのアドレスを返します。  複数のライブラリ関数に `stream` の引数として開いたファイルのさまざまな操作を実行するには、このアドレスを使用します。  バイトのストリームは、すべての入力を各文字が [fputc](../c-runtime-library/reference/fputc-fputwc.md)を呼び出すことによって書き込まれるように読み取り、すべての出力が行われます。各文字が [fgetc](../Topic/fgetc,%20fgetwc.md)を呼び出してように実行されます。  柔軟なストリームには、すべての入力を各文字が [fputwc](../c-runtime-library/reference/fputc-fputwc.md)を呼び出すことによって書き込まれるように読み取り、すべての出力が行われます。各文字が [fgetwc](../Topic/fgetc,%20fgetwc.md)を呼び出してように実行されます。  
  
 [fclose](../c-runtime-library/reference/fclose-fcloseall.md)を呼び出してファイルを閉じることができます。これに `FILE` オブジェクトのアドレスは無効です。  
  
 `FILE` オブジェクトは、次の要素を含むストリームの状態を保存する:  
  
-   読み取りまたは書き込みがエラーを関数によってエラー インジケーターを設定する 0 以外のの。  
  
-   EOF が読み取り時ファイルの端に当たった関数によって 0 以外のに設定します。  
  
-   ファイル位置インジケーターはストリームにファイルが確認要求を配置することは、読み取りまたは書き込みを行うためのバイトを指定します。  
  
-   [ストリームの状態](../Topic/Stream%20States.md) は、あるいは濃淡繰り返すことをバイト指向ことをストリームを読み込むか、または書き込みを受け入れるかどうか、ストリームがバインドされているかどうかを指定します。  
  
-   変換状態は部分的に作成されたか、生成された汎用的なマルチバイト文字の状態、またはファイルへのバイト シーケンスの状態を記録します\)。  
  
-   ファイル バッファーはストリームに読み取り操作と書き込み操作のパフォーマンスを改善するためにライブラリ関数が使用できる配列オブジェクトのアドレスとサイズを指定します。  
  
 `FILE` オブジェクトは、そのオブジェクトで使用されることを指定するファイル バッファーに格納された値を変更せずにします。  ライブラリ関数への `FILE` オブジェクトをコピーしてその `stream` の引数として移植性を考慮してコピーのアドレスを使用することはできません。  
  
## 参照  
 [ファイルとストリーム](../c-runtime-library/files-and-streams.md)