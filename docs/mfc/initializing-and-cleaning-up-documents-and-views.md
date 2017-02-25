---
title: "ドキュメントとビューの初期化と後処理 | Microsoft Docs"
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
  - "ドキュメント オブジェクト, 有効期間"
  - "ドキュメント, クリーンアップ"
  - "ドキュメント, 初期化"
  - "初期化 (ドキュメントを)"
  - "初期化 (オブジェクトを), ドキュメント オブジェクト"
  - "初期化 (ビューを)"
  - "ビュー, クリーンアップ"
  - "ビュー, 初期化"
ms.assetid: 95d6f09b-a047-4079-856a-ae7d0548e9d2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ドキュメントとビューの初期化と後処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ドキュメントとビューの後に初期化およびクリーンアップするために、次のガイドラインを使用する:  
  
-   フレームワークは、ドキュメントやビューを初期化します; それらに追加したデータを初期化します。  
  
-   フレームワークは、ドキュメントとビューを閉じるときにクリーンアップします; それらのドキュメントとビューのメンバー関数からヒープに割り当てたメモリを解放しなければなりません。  
  
> [!NOTE]
>  アプリケーション全体の初期化はクラス `CWinApp`の [InitInstance](../Topic/CWinApp::InitInstance.md) のメンバー関数のオーバーライドで推奨されるであるアプリケーション全体のクリーンアップは `CWinApp` のメンバー関数 [ExitInstance](../Topic/CWinApp::ExitInstance.md)のオーバーライドで推奨されることを再度呼び出す場合。  
  
 MDI アプリケーションのドキュメントのライフ サイクル \(およびフレーム ウィンドウとビューまたはビュー\) は次のとおりです。:  
  
1.  動的生成中に、ドキュメントのコンストラクターが呼び出されます。  
  
2.  新しい各ドキュメントについては、"ドキュメントの [OnNewDocument](../Topic/CDocument::OnNewDocument.md) または [OnOpenDocument](../Topic/CDocument::OnOpenDocument.md) が呼び出されます。  
  
3.  ユーザーは、有効期間内にドキュメントと対話します。  通常は、ユーザーがデータを選択し、編集するビューによってドキュメント データを操作しているときに発生します。  ビューは、ストレージや他のビューを更新するためのドキュメントの変更を渡します。  この間はドキュメントとビューは、コマンドを処理する場合があります。  
  
4.  フレームワークは、ドキュメントに固有のデータを削除するに [DeleteContents](../Topic/CDocument::DeleteContents.md) を呼び出します。  
  
5.  ドキュメントのデストラクターが呼び出されます。  
  
 SDI アプリケーションでは、ドキュメントが最初に作成されたときに、手順 1 では、一度だけ実行されます。  その後、手順 2 から新しいドキュメントを開くたびに 4 が先に実行されます。  新しいドキュメントが既存のドキュメント オブジェクトを再利用します。  最後に、アプリケーションが終了すると、手順 5 を実行します。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [ドキュメントとビューの初期化](../mfc/initializing-documents-and-views.md)  
  
-   [ドキュメントやビューをクリーンアップすること](../Topic/Cleaning%20Up%20Documents%20and%20Views.md)  
  
## 参照  
 [ドキュメント\/ビュー アーキテクチャ](../Topic/Document-View%20Architecture.md)