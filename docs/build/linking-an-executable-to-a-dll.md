---
title: "DLL と実行形式のリンク | Microsoft Docs"
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
  - "DLL [C++], リンク"
  - "動的読み込みリンク [C++]"
  - "実行可能ファイル [C++], リンク (DLL に)"
  - "明示的なリンク [C++]"
  - "暗黙のリンク [C++]"
  - "リンク [C++], DLL"
  - "読み込み (DLL を) [C++]"
  - "実行時 [C++], リンク"
ms.assetid: 7592e276-dd6e-4a74-90c8-e1ee35598ea3
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# DLL と実行形式のリンク
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

実行可能ファイルを DLL とリンクするには、次の 2 つの方法があります。  
  
-   [暗黙的なリンク](../Topic/Linking%20Implicitly.md)  
  
-   [明示的なリンク](../build/linking-explicitly.md)  
  
 暗黙的リンクは、静的読み込み、または読み込み時の動的リンクと見なされることがあります。  暗黙的リンクは、動的読み込み、またはランタイム動的リンクと見なされることがあります。  
  
 暗黙的リンクの場合、DLL を使う実行形式は、DLL の作成元から提供されるインポート ライブラリ \(.lib ファイル\) とリンクします。  オペレーティング システムは、DLL を使う実行形式の読み込み時にその DLL を読み込みます。  クライアントの実行形式は、その実行形式内に含まれている関数を呼び出す場合と同じように、DLL のエクスポート関数を呼び出します。  
  
 明示的リンクの場合、DLL を使う実行形式は、関数呼び出しを行って、DLL を明示的に読み込み\/アンロードしたり、DLL のエクスポート関数にアクセスします。  クライアントの実行形式は、関数ポインターを通じてエクスポート関数を呼び出します。  
  
 実行形式は、リンク方式に関係なく同じ DLL を使うことができます。  さらに、これらの機構は相互に排他的ではありません。つまり、ある実行形式は、DLL と暗黙的にリンクでき、別の実行形式は、DLL と明示的にアタッチできます。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [インポート ライブラリとエクスポート ファイル](../build/reference/working-with-import-libraries-and-export-files.md)  
  
-   [リンク方式の使い分け](../build/determining-which-linking-method-to-use.md)  
  
-   [Windows が使用する DLL 検索パス](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)