---
title: "テキスト モードとバイナリ モードのファイル入出力 | Microsoft Docs"
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
  - "c.io"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "バイナリ アクセス"
  - "バイナリ アクセス, バイナリ モードのファイル I/O"
  - "ファイル [C++], オープン関数"
  - "関数 [CRT], ファイル アクセス"
  - "I/O [CRT], バイナリ"
  - "I/O [CRT], テキスト ファイル"
  - "I/O [CRT], 変換モード"
  - "テキスト ファイル, I/O"
  - "変換モード (ファイル I/O)"
  - "変換, モード"
ms.assetid: 3196e321-8b87-4609-b302-cd6f3c516051
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# テキスト モードとバイナリ モードのファイル入出力
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ファイル I\/O 操作はファイルを開くモードで 2 種類の変換モード、テキストまたはバイナリの 1 つがで行われます。  データ ファイルは、通常、テキスト モードで処理されます。  ファイルの変換モードを制御するには、1 つが:できます  
  
-   選択されたファイルを開くときに現在の既定の設定を保持し、別のモードを指定します。  
  
-   出力新しく開かれたファイルの既定のモードを変更するには [\_set\_fmode](../c-runtime-library/reference/set-fmode.md) 関数を使用します。  現在の既定のモードは、[\_get\_fmode](../c-runtime-library/reference/get-fmode.md) を使用します。  最初の既定の設定は、テキスト モード \(`_O_TEXT`\) です。  
  
-   変更します。プログラムのグローバル変数 [\_fmode](../c-runtime-library/fmode.md) の設定によって直接変換を既定モード。  関数 `_set_fmode` はこの変数の値を設定しますが、これらを直接設定できます。  
  
 [\_open](../c-runtime-library/reference/open-wopen.md)、[fopen](../c-runtime-library/reference/fopen-wfopen.md)、[fopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)、[freopen](../c-runtime-library/reference/freopen-wfreopen.md)、[freopen\_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)、[\_fsopen](../c-runtime-library/reference/fsopen-wfsopen.md) または [\_sopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)などのファイル Open 関数を呼び出すと、関数 [\_set\_fmode](../c-runtime-library/reference/set-fmode.md)に適切な引数を指定して、`_fmode` の現在の既定の設定をオーバーライドできます。  `stdin`、`stdout`と `stderr` のストリームは、テキスト モードで既定で開きます; これらのファイルを開くときにもこの既定をオーバーライドできます。  使用 [\_setmode](../c-runtime-library/reference/setmode.md) はファイルの後でファイル記述子を使用して変換モードを変更する開いています。  
  
## 参照  
 [入出力](../Topic/Input%20and%20Output.md)   
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)