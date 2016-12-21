---
title: "テクニカル ノート 25: ドキュメント、ビュー、フレームの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.creation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ドキュメント, ビューとフレームの作成"
  - "TN025"
ms.assetid: 09254d72-6e1d-43db-80e9-693887dbeda2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# テクニカル ノート 25: ドキュメント、ビュー、フレームの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。  結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。  最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 ここでは、WinApps DocTemplates、ドキュメント、ビュー、およびフレームの作成および所有権問題について説明します。  
  
## WinApp  
 システムに `CWinApp` の 1 種類のオブジェクトがあります。  
  
 これは、.NET Framework の `WinMain`の内部実装によって静的に作成され、初期化されます。  `CWinApp` から便利な処理を行うために派生しなければなりません \(例外: 拡張 DLL は `DllMain` にされます `CWinApp` のインスタンスの初期化を指定する必要はありません\)。  
  
 `CWinApp` の 1 種類のオブジェクトはドキュメント テンプレート \(`CPtrList`\) のリストを所有します。  一つ以上のアプリケーションに対してドキュメント テンプレートです。  DocTemplates は通常 `CWinApp::InitInstance`のリソース ファイル \(つまり、文字列配列\) から読み込まれます。  
  
```  
pTemplate = new CDocTemplate(IDR_MYDOCUMENT, ...);  
AddDocTemplate(pTemplate);  
```  
  
 `CWinApp` の 1 種類のオブジェクトは、アプリケーションのすべてのフレーム ウィンドウを所有します。  アプリケーションのメイン フレーム ウィンドウが **CWinApp::m\_pMainWnd**に格納するように; AppWizard と自動的に許可されない場合、通常 `InitInstance` の実装の `m_pMainWnd` を設定します。  シングル ドキュメント インターフェイス \(SDI \(SDI\) のメイン アプリケーション フレーム ウィンドウ、または唯一のドキュメント フレーム ウィンドウとして動作する手段が 1 `CFrameWnd` です。  マルチ ドキュメント インターフェイス \(MDI\) では、子を `CFrameWnd`s.含むメイン アプリケーション フレーム ウィンドウとして機能する MDI フレーム \(クラス `CMDIFrameWnd`\) です。  各子ウィンドウには、クラス `CMDIChildWnd` \(`CFrameWnd`から派生\) 機能を多数のドキュメント フレーム ウィンドウを 1 文字としてそのです。  
  
## DocTemplates  
 `CDocTemplate` はドキュメントの作成者および manager です。  これは、作成するドキュメントを所有します。  アプリケーションが次のリソース ベースの方法を使用した場合 `CDocTemplate`から派生する必要はありません。  
  
 SDI アプリケーションでは、クラス `CSingleDocTemplate` は 1 個の開いているドキュメントを監視します。  MDI アプリケーションでは、`CMultiDocTemplate` クラスは、テンプレートから作成されたすべての現在開いているドキュメントのリスト \(`CPtrList`\) を保持します。  `CDocTemplate::AddDocument` と `CDocTemplate::RemoveDocument` はテンプレートからドキュメントを追加または削除する仮想メンバー関数を提供します。  `CDocTemplate` は Friend です **CDocument** のそのドキュメントを作成したドキュメント テンプレートが指すように **CDocument::m\_pDocTemplate** の保護されたなバック ポインターを設定します。  
  
 `CWinApp` が 順番にすべてのドキュメント テンプレートを呼び出す既定の `OnFileOpen` の実装を処理します。  実装は、開いているドキュメントを既に検索や、新しいドキュメントを開くどの形式を決定が含まれます。  
  
 `CDocTemplate` は ドキュメントとフレームの UI のバインディングを管理します。  
  
 `CDocTemplate` は 匿名のなドキュメントの数を保持します。  
  
## CDocument  
 **CDocument** は `CDocTemplate`によって所有されます。  
  
 ドキュメント `CPtrList` \(\) が表示されているドキュメントに現在開いているビューの一覧があります。`CView`から派生される\)。  
  
 ドキュメントは作成\/破棄するためのビューが作成されると、相互に接続されます。  ドキュメントを閉じる \(つまり、ファイルを使用して、閉じる\)、すべての添付のビューが閉じます。  ドキュメントの最後のビューを閉じたとき \(つまり、ウィンドウ、閉じる\) ドキュメントが閉じます。  
  
 `CDocument::AddView`の `RemoveView` インターフェイスがビューのリストを保持するために使用されます。  **CDocument** は Friend です `CView` のその **CView::m\_pDocument** のバック ポインターを設定します。  
  
## CFrameWnd  
 `CFrameWnd` \(またはフレーム\) は、MFC 1.0 と同じロール、`CFrameWnd` クラスを新しいクラスを派生しないでさまざまな状況で使用するように設計されています。します。  派生クラス `CMDIFrameWnd` と `CMDIChildWnd` は、多くの標準コマンド既に実装されますが向上します。  
  
 `CFrameWnd` はフレームのクライアント領域のウィンドウを作成する必要があります。  通常、フレームのクライアント領域全体を占める 1 個のメイン ウィンドウがあります。  
  
 MDI フレーム ウィンドウの場合、クライアント領域が順番にすべての MDI 子フレーム ウィンドウの親である MDICLIENT のコントロールが格納されます。  SDI フレーム ウィンドウまたは MDI 子フレーム ウィンドウの場合は、クライアント領域は、通常 `CView`\-派生ウィンドウ オブジェクトが格納されます。  `CSplitterWnd`の場合は、ビューのクライアント領域は、`CSplitterWnd` ウィンドウ オブジェクトと `CView`が格納されます。派生ウィンドウ オブジェクト \(分割ペインにつき 1\) は `CSplitterWnd`ウィンドウの子として作成されます。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)