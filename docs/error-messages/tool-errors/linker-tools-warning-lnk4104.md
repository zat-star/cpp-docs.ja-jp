---
title: "リンカー ツールの警告 LNK4104 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4104"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4104"
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# リンカー ツールの警告 LNK4104
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

シンボル 'symbol' のエクスポートは PRIVATE になります。  
  
 `symbol` は以下のいずれかです。  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllGetDocumentation`  
  
-   `DllInitialize`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllRegisterServerExW`  
  
-   `DllUnload`  
  
-   `DllUnregisterServer`  
  
-   `RasCustomDeleteEntryNotify`  
  
-   `RasCustomDial`  
  
-   `RasCustomDialDlg`  
  
-   `RasCustomEntryDlg`  
  
 DLL 用のインポート ライブラリをビルドし、上の関数をモジュール定義ファイルで PRIVATE と指定せずにエクスポートすると、この警告が発生します。  通常、これらの関数は、OLE 専用にエクスポートします。  これらの関数をインポート ライブラリに含むと、ライブラリにリンクしたプログラムが間違って呼び出し、動作が異常になることがあります。  PRIVATE キーワードの詳細については、「[EXPORTS](../Topic/EXPORTS.md)」を参照してください。