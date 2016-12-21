---
title: "C++ 標準ライブラリの概要 | Microsoft Docs"
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
  - "ヘッダー, C++ ライブラリ"
  - "ライブラリ, 標準 C++"
  - "標準 C++ ライブラリ"
  - "標準 C++ ライブラリ, ヘッダー"
ms.assetid: 7acb83a4-da73-4ad3-bc30-a71289db7f60
caps.latest.revision: 16
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C++ 標準ライブラリの概要
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

すべての C\+\+ ライブラリのエンティティは 1 つ以上の標準ヘッダーで宣言または定義されます。  この実装には C\+\+ 標準では必要ない 2 つの追加ヘッダー、`<hash_map>` と `<hash_set>` が含まれています。  この実装がサポートするヘッダーの完全な一覧については、「[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)」を参照してください。  
  
 C\+\+ ライブラリのフリースタンディング実装では、これらのヘッダーの一部のみが提供されます。  
  
|||  
|-|-|  
|[\<cstddef\>](../Topic/%3Ccstddef%3E.md)|[\<cstdlib\>](../standard-library/cstdlib.md) \(少なくとも関数 `abort`、`atexit`、`exit` を宣言する\)|  
|[\<exception\>](../standard-library/exception.md)|[\<limits\>](../standard-library/limits.md)|  
|[\<new\>](../standard-library/new.md)|[\<cstdarg\>](../Topic/%3Ccstdarg%3E.md)|  
  
 C\+\+ のライブラリのヘッダーには 2 つの広範な再分割があります。  
  
-   [iostreams](../standard-library/iostreams-conventions.md) の規則  
  
-   [標準テンプレート ライブラリのサンプル](../misc/standard-template-library.md)の規則  
  
 このセクションでは、以下のセクションについて説明します。  
  
-   [C\+\+ ライブラリ ヘッダーの使用](../standard-library/using-cpp-library-headers.md)  
  
-   [C\+\+ ライブラリの規則](../standard-library/cpp-library-conventions.md)  
  
-   [iostreams の規則](../standard-library/iostreams-conventions.md)  
  
-   [C\+\+ プログラムの起動と終了](../standard-library/cpp-program-startup-and-termination.md)  
  
-   [安全なライブラリ: C\+\+ 標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)  
  
-   [チェックを行う反復子](../standard-library/checked-iterators.md)  
  
-   [反復子のデバッグのサポート](../standard-library/debug-iterator-support.md)  
  
-   [標準テンプレート ライブラリ](../misc/standard-template-library.md)  
  
-   [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)  
  
-   [stdext 名前空間](../Topic/stdext%20Namespace.md)  
  
-   [正規表現 \(C\+\+\)](../standard-library/regular-expressions-cpp.md)  
  
 Visual C\+\+ ランタイム ライブラリの詳細については、「[CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)」を参照してください。  
  
## 参照  
 [C\+\+ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)