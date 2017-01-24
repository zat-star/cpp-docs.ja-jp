---
title: "各種 MFC オブジェクト間の関係 | Microsoft Docs"
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
  - "MFC オブジェクトのリレーションシップ"
  - "MFC, リレーションシップ (キー オブジェクト間の)"
  - "オブジェクト [C++], リレーションシップ"
  - "リレーションシップ, MFC オブジェクト"
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 各種 MFC オブジェクト間の関係
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

すると、パースペクティブにドキュメント\/ビューの作成手順を考慮して、実行中のプログラムを置いて: ドキュメント、ビューの格納に使用されたフレーム ウィンドウとビューはドキュメントに関連付けられています。  
  
-   ドキュメントは、このドキュメントを作成したドキュメント テンプレートによってドキュメントやポインターの一覧を保持します。  
  
-   ビューはドキュメントへのポインターを保持し、親フレーム ウィンドウの子です。  
  
-   ドキュメント フレーム ウィンドウは、現在アクティブなビューへのポインターを保持します。  
  
-   ドキュメント テンプレートは、開いているドキュメントのリストを保持します。  
  
-   アプリケーションでは、ドキュメント テンプレートのリストを保持します。  
  
-   Windows は、開いているすべてのウィンドウを管理するので、ユーザーにメッセージを送信できます。  
  
 これらの関係はドキュメント\/ビューの作成時に設定されます。  実行中のプログラムのオブジェクトが他のオブジェクトにアクセスする方法を次の表に示します。  オブジェクトは、アプリケーションのオブジェクトに [AfxGetAppCWinApp](../Topic/AfxGetApp.md)関数を呼び出すことで、ポインターを取得できます。  
  
### アプリケーションの Other Objects へのアクセス権を得ること  
  
|オブジェクトから|他のオブジェクトにアクセスする方法|  
|--------------|-----------------------|  
|Document|ドキュメントの一覧にアクセスするために [GetFirstViewPosition](../Topic/CDocument::GetFirstViewPosition.md) と [GetNextView](../Topic/CDocument::GetNextView.md) を使用します。<br /><br /> ドキュメント テンプレートを取得する [GetDocTemplate](../Topic/CDocument::GetDocTemplate.md) 呼び出し。|  
|ビュー|ドキュメントを取得 [GetDocument](../Topic/CView::GetDocument.md) 呼び出し。<br /><br /> フレーム ウィンドウを取得 [GetParentFrame](../Topic/CWnd::GetParentFrame.md) 呼び出し。|  
|ドキュメント フレーム ウィンドウ|現在のビューを取得 [GetActiveView](../Topic/CFrameWnd::GetActiveView.md) 呼び出し。<br /><br /> ドキュメントを現在のビューに接続するに [GetActiveDocument](../Topic/CFrameWnd::GetActiveDocument.md) を呼び出します。|  
|MDI フレーム ウィンドウ|現在アクティブな [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)を取得 [MDIGetActive](../Topic/CMDIFrameWnd::MDIGetActive.md) 呼び出し。|  
  
 通常、フレーム ウィンドウの 1 種類のビューがありますが、場合によっては、分割ウィンドウのように、同じフレーム ウィンドウは、複数のビューが含まれます。  フレーム ウィンドウには、現在アクティブなビューへのポインターを保持します; ポインターは別のビューがアクティブに更新されます。  
  
> [!NOTE]
>  メイン フレーム ウィンドウへのポインターは、アプリケーションの [m\_pMainWnd](../Topic/CWinThread::m_pMainWnd.md) オブジェクトのメンバー変数に格納されます。  `CWinApp` の `InitInstance` のメンバー関数をオーバーライドする `OnFileNew` への呼び出しによって `m_pMainWnd` を設定します。  `OnFileNew`を呼び出さないと、独自 `InitInstance` の変数の値を設定する必要があります。SDI COM コンポーネント \(サーバー\) アプリケーションは \/Embedding コマンド ラインにある変数を設定していない可能性があります\)。これで、`m_pMainWnd` が `CWinApp`ではなくクラス `CWinThread` のメンバーであることに注意してください。  
  
## 参照  
 [ドキュメント テンプレートとドキュメント\/ビューの作成手順](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [ドキュメント テンプレートの作成](../Topic/Document%20Template%20Creation.md)   
 [ドキュメントおよびビューの作成](../mfc/document-view-creation.md)   
 [新しいドキュメント、ウィンドウ、ビューの作成](../Topic/Creating%20New%20Documents,%20Windows,%20and%20Views.md)