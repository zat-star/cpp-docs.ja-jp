---
title: "C++ プログラムの起動と終了 | Microsoft Docs"
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
  - "テキスト ストリームのコントロール"
  - "Function Main プロシージャ"
  - "main 関数, プログラムの起動"
  - "標準 C++ ライブラリ, プログラムの起動と終了"
  - "スタートアップ コード, および C++ プログラムの終了"
  - "実行の終了"
ms.assetid: f72c8f76-f507-4ddd-a270-7b60f4fed625
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C++ プログラムの起動と終了
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C \+\+ プログラムは、.プログラムがプログラム起動時にプログラムの終了のが記載されている数と同じ操作をここに入力します。  
  
 対象の環境の呼び出しの前に静的存続期間を持つすべてのオブジェクトを指定する定数の初期値を保存すると、プログラム `main`関数は、このような静的オブジェクトの残りのコンストラクターを実行します。  実行順序が変換単位の間に指定されませんが、それでも [入出力ストリーム](../standard-library/iostreams-conventions.md) のオブジェクトがこれらの静的コンストラクターで使用するために適切に初期化されると想定できます。  これらのコントロールのテキスト ストリームは次の操作:  
  
-   [cin](../Topic/cin.md) —標準入力の場合。  
  
-   [標準出力ストリーム](../Topic/cout.md) —標準出力の場合。  
  
-   [標準エラー ストリーム](../Topic/cerr.md) —いない標準エラー出力の場合。  
  
-   [障害物](../Topic/clog.md) —バッファリングされた標準エラー出力の場合。  
  
 静的オブジェクトに呼び出されたデストラクター内でこれらのオブジェクトをプログラムの終了中に使用できます。  
  
 `main` から戻る、`exit` を呼び出す C と同様にすべての関数をレジストリの逆の順序で `atexit` に登録されている呼び出します。  このようなからスローされた例外は、登録されている関数呼び出し `terminate`。  
  
## 参照  
 [STL の概要](../standard-library/cpp-standard-library-overview.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)