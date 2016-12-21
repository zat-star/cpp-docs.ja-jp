---
title: "ヘルパー関数について | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__delayLoadHelper 関数"
  - "__delayLoadHelper2 関数"
  - "遅延読み込み (DLL を), ヘルパー関数"
  - "delayhlp.cpp"
  - "delayimp.h"
  - "delayimp.lib"
  - "ヘルパー関数"
ms.assetid: 6279c12c-d908-4967-b0b3-cabfc3e91d3d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ヘルパー関数について
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

実行時に DLL を実際に読み込むのは、リンカーがサポートする遅延読み込み用のヘルパー関数です。  ヘルパー関数の動作をカスタマイズするには、Delayimp.lib で提供されているヘルパー関数を使用する代わりに、独自の関数を作成し、プログラムにリンクします。  1 つのヘルパー関数で、すべての遅延読み込み DLL を処理できます。  
  
 独自のヘルパー関数を作成すると、DLL またはインポートの名前に基づいて特定の処理を実行できます。  
  
 ヘルパー関数は以下の処理を行います。  
  
-   格納されているライブラリ ハンドルを調べて、ライブラリが読み込み済みかどうかを確認します。  
  
-   **LoadLibrary** を呼び出して、DLL を読み込みます。  
  
-   **GetProcAddress** を呼び出して、プロシージャのアドレスを取得します。  
  
-   遅延インポート読み込みサンクに制御を返して、現在読み込まれているエントリ ポイントを呼び出します。  
  
 ヘルパー関数は、以下の時点で、プログラムの通知フックにコールバックできます。  
  
-   ヘルパー関数が起動したとき  
  
-   ヘルパー関数から **LoadLibrary** を呼び出す直前  
  
-   ヘルパー関数から **GetProcAddress** を呼び出す直前  
  
-   ヘルパー関数から **LoadLibrary** への呼び出しが失敗した場合  
  
-   ヘルパー関数から **GetProcAddress** への呼び出しが失敗した場合  
  
-   ヘルパー関数の処理が終了した後  
  
 これらの各フック ポイントでは、ヘルパー ルーチンの通常の処理を変更する値を返すことができます。ただし、遅延インポート読み込みサンクへ戻る処理は変更できません。  
  
 既定のヘルパー コードは、vc\\include フォルダーの Delayhlp.cpp と Delayimp.h にあり、vc\\lib フォルダーの Delayimp.lib にコンパイルされています。  独自のヘルパー関数を作成しない場合は、コンパイル時にこのライブラリをインクルードする必要があります。  
  
 ヘルパー関数の詳細については、次のトピックを参照してください。  
  
-   [Visual C\+\+ 6.0 以降の DLL 遅延読み込みヘルパー関数の変更点](../../build/reference/changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)  
  
-   [呼び出し規約、パラメーター、および戻り値の型](../../build/reference/calling-conventions-parameters-and-return-type.md)  
  
-   [構造体と定数の定義](../../build/reference/structure-and-constant-definitions.md)  
  
-   [必要な値の計算](../../build/reference/calculating-necessary-values.md)  
  
-   [遅延読み込みした DLL のアンロード](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
## 参照  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)