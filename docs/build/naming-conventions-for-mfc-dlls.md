---
title: "MFC DLL の名前付け規則 | Microsoft Docs"
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
  - "DLL [C++], ライブラリ名"
  - "DLL [C++], 名前付け規則"
  - "ライブラリ [C++], MFC DLL 名"
  - "MFC DLL [C++], 名前付け規則"
  - "MFC ライブラリ [C++], 名前付け規則"
  - "名前付け規則 [C++], MFC DLL"
  - "共有 DLL バージョン [C++]"
ms.assetid: 0db9c3f3-87d3-40e8-8964-250f9d2a2209
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# MFC DLL の名前付け規則
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC に含まれる DLL やライブラリの名前は、一定の規則に従って命名されます。  この規則に従うと、目的に応じて DLL やライブラリを簡単に使い分けることができます。  
  
 これらの DLL を使用するアプリケーションや拡張 DLL をビルドするためのインポート ライブラリの名前は、DLL と同じ基本名で、拡張子だけが .lib となります。  
  
### 共有 DLL の名前付け規則  
  
|\[DLL\]|説明|  
|-------------|--------|  
|MFCx0.DLL|MFC DLL、ANSI リリース バージョン|  
|MFCx0U.DLL|MFC DLL、Unicode リリース バージョン|  
|MFCx0D.DLL|MFC DLL、ANSI デバッグ バージョン|  
|MFCx0UD.DLL|MFC DLL、Unicode デバッグ バージョン|  
  
 共有 DLL バージョンの MFC と動的にリンクするときは、アプリケーションと拡張 DLL のどちらからリンクする場合でも、製品には MFCx0.DLL を含める必要があります。  Unicode をサポートするアプリケーションの場合は、代わりに MFCx0U.DLL を含めます。  
  
 MFC と DLL を静的にリンクする場合は、MFC のスタティック ライブラリのいずれかとリンクします。  これらのバージョンには、規則 \[N&#124;U\]AFXCW\[D\].LIB に従って名前が付けられます。  詳細については、「[ライブラリの名前付け規則](../Topic/Library%20Naming%20Conventions.md) \(MFC\)」の表「スタティック リンク ライブラリの名前付け規則」を参照してください。  
  
 アプリケーションと共に配布される Visual C\+\+ DLL リストについては、Visual Studio インストールに含まれる Redist.txt を参照してください。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [ライブラリの名前付け規則](../Topic/Library%20Naming%20Conventions.md)  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)