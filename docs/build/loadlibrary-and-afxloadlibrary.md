---
title: "LoadLibrary と AfxLoadLibrary | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LoadLibrary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxLoadLibrary メソッド"
  - "DLL [C++], AfxLoadLibrary"
  - "DLL [C++], LoadLibrary"
  - "明示的なリンク [C++]"
  - "LoadLibrary メソッド"
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# LoadLibrary と AfxLoadLibrary
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プロセスに DLL を明示的にリンクする場合は、[LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187) \(または [AfxLoadLibrary](../Topic/AfxLoadLibrary.md)\) を呼び出します。  この関数が正常終了した場合、呼び出し元プロセスのアドレス空間に指定された DLL が割り当てられ、DLL へのハンドルが返されます。このハンドルは、`GetProcAddress` や `FreeLibrary` など、明示的リンクに必要な他の関数で使用できます。  
  
 `LoadLibrary` は、暗黙リンクと同じ検索シーケンスで DLL を探します。  システムが DLL を見つけられない場合、またはエントリ ポイント関数が FALSE を返した場合、`LoadLibrary` は NULL を返します。  `LoadLibrary` への呼び出しで指定される DLL モジュールが呼び出し元プロセスのアドレス空間に既に割り当てられている場合、この関数は DLL のハンドルを返し、モジュールの参照カウントをインクリメントします。  
  
 DLL にエントリ ポイント関数が含まれる場合、オペレーティング システムは、`LoadLibrary` を呼び出したスレッドのコンテキスト内でその関数を呼び出します。  `LoadLibrary` の前回の呼び出しに対応する `FreeLibrary` 関数呼び出しが行われていないために、DLL が既にプロセスにアタッチされている場合は、エントリ ポイント関数は呼び出されません。  
  
 拡張 DLL を読み込む MFC アプリケーションでは、`LoadLibrary` の代わりに `AfxLoadLibrary` を使用することをお勧めします。  `LoadLibrary` を呼び出す前に、`AfxLoadLibrary` でスレッド同期を処理します。  `AfxLoadLibrary` のインターフェイス \(関数プロトタイプ\) は、`LoadLibrary` と同じです。  
  
 Windows が DLL を読み込むことができない場合は、プロセスでエラーからの回復を試みることができます。  たとえば、プロセスがユーザーにエラーを通知して、ユーザーに DLL への別のパスを指定するよう要求できます。  
  
> [!IMPORTANT]
>  Windows NT 4、Windows 2000、または Windows XP \(SP1 以前\) でコードを実行する場合は、必ず DLL の完全パスを指定してください。  これらのオペレーティング システムでファイルが読み込まれると、最初に現在のディレクトリが検索されます。  ファイルのパスを指定していないと、目的のファイルでないファイルが読み込まれる場合があります。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [暗黙的なリンク](../Topic/Linking%20Implicitly.md)  
  
-   [リンク方式の使い分け](../build/determining-which-linking-method-to-use.md)  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [Windows が使用する DLL 検索パス](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
-   [FreeLibrary と AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)   
 [LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187)   
 [AfxLoadLibrary](../Topic/AfxLoadLibrary.md)