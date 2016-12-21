---
title: "MFC DLL 内で使用できない MFC クラスまたは関数 | Microsoft Docs"
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
  - "DLL [C++], MFC"
  - "DLL [C++], 制限事項"
  - "MFC DLL [C++], 制限事項"
ms.assetid: 18e2f1cb-4f72-4d3a-a951-3488208872c7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# MFC DLL 内で使用できない MFC クラスまたは関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

拡張 DLL は、クライアント アプリケーションの `CWinApp` 派生クラスを使用します。  拡張 DLL は、固有の `CWinApp` 派生クラスを持てません。  
  
 レギュラー DLL には、MFC アプリケーションの場合と同じく、`CWinApp` 派生クラスと、そのアプリケーション クラスの 1 つのオブジェクトの存在が必要です。  ただし、アプリケーションの `CWinApp` オブジェクトとは異なり、DLL の `CWinApp` オブジェクトにはメイン メッセージ ポンプがありません。  
  
 `CWinApp::Run` の機構は DLL では使用できないため、アプリケーションはメイン メッセージ ポンプを所有しています。  DLL でモードレス ダイアログ ボックスを開く場合、または DLL 固有のメイン フレーム ウィンドウがある場合は、DLL がエクスポートしたルーチンをアプリケーションのメイン メッセージ ポンプで呼び出す必要があります。このルーチンが、DLL のアプリケーション オブジェクトの `CWinApp::PreTranslateMessage` メンバー関数を呼び出します。  
  
## 参照  
 [DLL に関してよく寄せられる質問](../build/dll-frequently-asked-questions.md)