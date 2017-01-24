---
title: "MFC DLL から複数のスレッドを作成する方法 | Microsoft Docs"
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
  - "DLL [C++], マルチスレッド"
  - "MFC DLL [C++], マルチスレッド"
  - "マルチスレッド処理 [C++], DLL"
  - "スレッド処理 [MFC], DLL"
ms.assetid: 41d5b5e6-a7d3-42bf-b641-f1245abd1c59
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# MFC DLL から複数のスレッドを作成する方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

スレッドごとにローカル格納領域を割り当てる **TlsAlloc** などの Win32 スレッド ローカル ストレージ \(TLS\) 関数を使用すると、MFC DLL で複数のスレッドを安全に作成できます。ただし、初期化中は例外です。  一方、MFC DLL で **\_\_declspec\(thread\)** を使用してスレッド ローカル ストレージを割り当てた場合は、クライアント アプリケーションを DLL に暗黙にリンクする必要があります。  クライアント アプリケーションを DLL に明示的にリンクする **LoadLibrary** を呼び出しても、DLL を読み込むことはできません。  MFC DLL 内で複数のスレッドを作成する方法の詳細については、サポート技術情報の「PRB: Calling LoadLibrary\(\) to Load a DLL That Has Static TLS \(Q118816\)」を参照してください。  
  
 スタートアップ \(初期化\) 中に MFC スレッドを新規作成する MFC DLL をアプリケーションで読み込むと、応答が停止します。  たとえば、以下の関数の中で `AfxBeginThread` または `CWinThread::CreateThread` を呼び出してスレッドを作成しようとした場合です。  
  
-   レギュラー DLL 内の `CWinApp` 派生オブジェクトの `InitInstance`  
  
-   レギュラー DLL 内の `DllMain` 関数または **RawDllMain** 関数  
  
-   拡張 DLL 内の `DllMain` 関数または **RawDllMain** 関数  
  
 初期化中のスレッド作成の詳細については、サポート技術情報の「PRB: Cannot Create an MFC Thread During DLL Startup \(Q142243\)」を参照してください。  
  
## 参照  
 [DLL に関してよく寄せられる質問](../build/dll-frequently-asked-questions.md)