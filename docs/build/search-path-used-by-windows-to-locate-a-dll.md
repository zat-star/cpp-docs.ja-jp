---
title: "Windows が使用する DLL 検索パス | Microsoft Docs"
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
  - "DLL [C++], Windows 検索パス"
  - "検索 (DLL を)"
  - "既知の DLL の検索 [C++]"
  - "検出 (DLL を)"
  - "検索パス [C++]"
  - "検索 [C++], DLL"
  - "Windows [C++], DLL 検索パス"
ms.assetid: 84bfb380-ad7b-4962-b2d0-51b19a45f1bb
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Windows が使用する DLL 検索パス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

暗黙的なリンクと明示的なリンクの両方で、Windows は、Kernel32.dll や User32.dll などの "既知の DLL" を最初に検索します。  次に、以下に示す順序で DLL が検索されます。  
  
1.  実行中のプロセスの実行形式モジュールがあるフォルダー。  
  
2.  現在のフォルダー。  
  
3.  Windows システム フォルダー。  このフォルダーへのパスは、**GetSystemDirectory** 関数が取得します。  
  
4.  Windows ディレクトリ。  このフォルダーへのパスは、**GetWindowsDirectory** 関数が取得します。  
  
5.  環境変数 PATH 内に記述されたフォルダー。  
  
    > [!NOTE]
    >  環境変数 LIBPATH は使用しません。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [暗黙的なリンク](../Topic/Linking%20Implicitly.md)  
  
-   [明示的なリンク](../build/linking-explicitly.md)  
  
-   [リンク方式の使い分け](../build/determining-which-linking-method-to-use.md)  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)