---
title: "FreeLibrary と AfxFreeLibrary | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "FreeLibrary"
  - "AfxFreeLibrary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "拡張 DLL [C++]、アンロード"
  - "AfxFreeLibrary メソッド"
  - "アンロード (DLL を)"
  - "FreeLibrary メソッド"
  - "DLL [C++]、リンク"
  - "明示的なリンク [C++]"
  - "DLL [C++]、アンロード"
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# FreeLibrary と AfxFreeLibrary
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DLL モジュールが不要になったときに [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188) DLL の呼び出しに関数を明示的にリンクするプロセス。  この関数は、モジュールの参照回数を減らし、参照回数が 0 になると、プロセスのアドレス空間へのマップからそのモジュールを削除します。  
  
 MFC アプリケーションでは、拡張 DLL をアンロードするために `FreeLibrary` の代わりに [AfxFreeLibrary](../Topic/AfxFreeLibrary.md) を使用します。  `AfxFreeLibrary` のインターフェイス \(関数プロトタイプ\) は、`FreeLibrary` と同じです。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [暗黙的なリンク](../Topic/Linking%20Implicitly.md)  
  
-   [リンク方式の使い分け](../build/determining-which-linking-method-to-use.md)  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [LoadLibrary と AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)   
 [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188)   
 [AfxFreeLibrary](../Topic/AfxFreeLibrary.md)