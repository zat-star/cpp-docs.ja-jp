---
title: "ドキュメントの使い方 | Microsoft Docs"
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
  - "データ [MFC], ドキュメント"
  - "データ [MFC], 読み取り"
  - "ドキュメント/ビュー アーキテクチャ [C++], ドキュメント"
  - "ドキュメント [C++]"
  - "ドキュメント [C++], C++ アプリケーション"
  - "ファイル [C++]"
  - "ファイル [C++], 書き込み"
  - "印刷 [MFC], ドキュメント"
  - "読み取り (データを) [C++], ドキュメントとビュー"
  - "ビュー [C++], C++ アプリケーション"
  - "書き込み (ファイルへの) [C++]"
ms.assetid: f390d6d8-d0e1-4497-9b6a-435f7ce0776c
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ドキュメントの使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

協力して、ドキュメントとビュー:  
  
-   アプリケーション固有の [データ](../mfc/managing-data-with-document-data-variables.md)が含まれ、管理、および表示する。  
  
-   [ドキュメント データの変数](../mfc/managing-data-with-document-data-variables.md) から成るデータを処理するためのインターフェイスを提供します。  
  
-   [読み取りおよび書き込みファイル](../mfc/serializing-data-to-and-from-files.md)に参加できます。  
  
-   [印刷中](../mfc/role-of-the-view-in-printing.md)に参加できます。  
  
-   アプリケーションのコマンドとメッセージの最も[ハンドル](../mfc/handling-commands-in-the-document.md)。  
  
 ドキュメントは、マネージ データに特に関係します。  ドキュメント クラスのメンバー変数にデータは、通常、保存します。  ビューの表示と更新のデータにアクセスするために、これらの変数を使用します。  ドキュメントの既定のシリアル化機構は、ファイルに対する読み取りと書き込みデータを管理します。  ドキュメントは、コマンドできます \(**WM\_COMMAND**以外のない Windows メッセージを処理\)。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [CDocument からドキュメント クラスを派生すること](../mfc/deriving-a-document-class-from-cdocument.md)  
  
-   [ドキュメント データ変数のデータ管理](../mfc/managing-data-with-document-data-variables.md)  
  
-   [ファイルに対するデータのシリアル化](../mfc/serializing-data-to-and-from-files.md)  
  
-   [シリアル化機構をバイパス](../mfc/bypassing-the-serialization-mechanism.md)  
  
-   [ドキュメントの処理コマンド](../mfc/handling-commands-in-the-document.md)  
  
-   [OnNewDocument のメンバー関数](../Topic/CDocument::OnNewDocument.md)  
  
-   [DeleteContents のメンバー関数](../Topic/CDocument::DeleteContents.md)  
  
## 参照  
 [ドキュメント\/ビュー アーキテクチャ](../Topic/Document-View%20Architecture.md)