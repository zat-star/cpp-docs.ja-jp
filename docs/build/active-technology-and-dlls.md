---
title: "Active テクノロジと DLL | Microsoft Docs"
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
  - "Active テクノロジ [C++]"
  - "オートメーション [C++], DLL"
  - "DLL [C++], Active テクノロジ"
  - "インプロセス サーバー DLL"
  - "MFC DLL [C++], Active テクノロジ"
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Active テクノロジと DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Active テクノロジを使うと、オブジェクト サーバーを DLL 内部に完全に実装できます。  このようなサーバーをインプロセス サーバーと呼びます。  MFC は、インプロセス サーバーのビジュアル編集の全機能を完全にサポートするわけではありません。Active テクノロジはサーバーがコンテナーのメイン メッセージ ループにフックする手段を提供しないというのが主な理由です。  MFC がアクセラレータ キーやアイドルタイム プロセッシングを処理するには、コンテナー アプリケーションのメッセージ ループへのアクセスが必要です。  
  
 オートメーション サーバーの作成中、サーバーにユーザー インターフェイスがまったくない場合は、サーバーをインプロセス サーバーにして、DLL に完全に組み込むことができます。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [オートメーション サーバー](../mfc/automation-servers.md)  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)