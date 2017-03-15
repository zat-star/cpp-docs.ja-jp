---
title: "DLL でのオートメーション | Microsoft Docs"
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
  - "オートメーション [C++], DLL"
  - "DLL [C++], オートメーション"
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# DLL でのオートメーション
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC DLL ウィザードの \[オートメーション\] チェック ボックスをオンにすると、以下の機能が使用できるようになります。  
  
-   初期オブジェクト記述言語 \(.ODL\) ファイル  
  
-   Afxole.h 用のインクルード ディレクティブ ファイル STDAFX.h  
  
-   **AfxDllGetClassObject** 関数を呼び出す `DllGetClassObject` 関数の実装  
  
-   **AfxDllCanUnloadNow** 関数を呼び出す `DllCanUnloadNow` 関数の実装  
  
-   [COleObjectFactory::UpdateRegistryAll](../Topic/COleObjectFactory::UpdateRegistryAll.md) 関数を呼び出す `DllRegisterServer` 関数の実装  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [オートメーション サーバー](../mfc/automation-servers.md)  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)