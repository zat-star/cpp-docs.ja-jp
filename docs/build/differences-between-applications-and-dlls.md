---
title: "アプリケーションと DLL の違い | Microsoft Docs"
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
  - "アプリケーション [C++], および DLL"
  - "DLL [C++], およびアプリケーション"
  - "実行可能ファイル [C++], DLL およびアプリケーション"
ms.assetid: 8f271523-d8d0-4ad1-84d2-0c5645d7fd5b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# アプリケーションと DLL の違い
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DLL とアプリケーションは、どちらも実行可能なプログラム モジュールですが、いくつかの相違点があります。  エンドユーザーにとって最もわかりやすい違いは、DLL は直接実行できるプログラムではない点です。  システム側から見ると、アプリケーションと DLL には次の 2 つの根本的な違いがあります。  
  
-   アプリケーションはシステム内で稼働する複数のインスタンスを同時に持つことができるのに対し、DLL のインスタンスは 1 つしかありません。  
  
-   アプリケーションは、スタック、グローバル メモリ、ファイル ハンドル、メッセージ キューなどを持つことができるのに対し、DLL はそれらを持つことはできません。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [DLL からのエクスポート](../build/exporting-from-a-dll.md)  
  
-   [DLL と実行形式のリンク](../build/linking-an-executable-to-a-dll.md)  
  
-   [DLL の初期化](../build/initializing-a-dll.md)  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [DLL の利点](../build/advantages-of-using-dlls.md)  
  
-   [非 MFC DLL: 概要](../Topic/Non-MFC%20DLLs:%20Overview.md)  
  
-   [MFC と静的にリンクされるレギュラー DLL](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [MFC と動的にリンクされるレギュラー DLL](../Topic/Regular%20DLLs%20Dynamically%20Linked%20to%20MFC.md)  
  
-   [拡張 DLL : 概要](../build/extension-dlls-overview.md)  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)