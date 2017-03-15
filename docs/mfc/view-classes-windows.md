---
title: "ビュー クラス (Windows) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.view"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "フォーム ビューとレコード ビュー"
  - "分割ウィンドウ クラス"
  - "ビュー クラス, Windows"
ms.assetid: b11683fb-9f43-4de3-9499-2b55775f9870
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ビュー クラス (Windows)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CView` と派生クラスは、フレーム ウィンドウのクライアント領域を表す子ウィンドウです。  ビューにデータを表示し、ドキュメントの入力を受け付けます。  
  
 ビュー クラスはドキュメントテンプレート オブジェクトを使用してドキュメント クラスおよびフレーム ウィンドウ クラスに関連付けられます。  
  
 [CView](../Topic/CView%20Class.md)  
 ドキュメントのデータのアプリケーション固有のビューの基本クラスです。  ビューに表示されるデータは、データの編集または選択するには、ユーザー入力を受け入れ。  `CView`からビュー クラスを派生してください。  
  
 [CScrollView](../mfc/reference/cscrollview-class.md)  
 スクロール機能をビューの基本クラスです。  自動スクロールの `CScrollView` からビュー クラスを派生してください。  
  
## フォームとレコード ビュー  
 フォーム ビューは、ビューをスクロールします。  これらはダイアログ ボックス テンプレートに基づいています。  
  
 レコード ビューは、フォーム ビューから派生されます。  ダイアログ ボックス テンプレートに加え、また、データベースへの接続があります。  
  
 [CFormView](../mfc/reference/cformview-class.md)  
 レイアウトがダイアログ ボックス テンプレートで定義されるスクロール ビュー。  ダイアログ ボックス テンプレートに基づいてユーザー インターフェイスを実装するに `CFormView` からクラスを派生してください。  
  
 [CDaoRecordView クラス](../mfc/reference/cdaorecordview-class.md)  
 直接 Data Access Object \(DAO\) のレコードセット オブジェクトにアタッチされるフォーム ビューを提供します。  すべてのフォーム ビューと同様に、`CDaoRecordView` はダイアログ ボックス テンプレートに基づいています。  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 直接 ODBC \(Open Database Connectivity\) データ ソースに接続されているフォーム ビューを提供します。  すべてのフォーム ビューと同様に、`CRecordView` はダイアログ ボックス テンプレートに基づいています。  
  
 [CHtmlEditView](../mfc/reference/chtmleditview-class.md)  
 WebBrowser 編集プラットフォームの機能を提供する HTML フォーム ビュー。  
  
## コントロール ビュー  
 コントロール ビューは、ビューとしてコントロールを表示します。  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 すべての基本クラスは、Windows のコントロールには、関連を検索します。  コントロールに基づくビューについて、次に説明します。  
  
 [CEditView](../Topic/CEditView%20Class.md)  
 Windows 標準エディット コントロールを含むビューは [CEdit](../Topic/CEdit%20Class.md)を参照します\)。  エディット コントロール サポート機能をテキスト編集、検索、置換、およびスクロールします。  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 Windows のリッチ エディット コントロールを含むビューは [CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)を参照します\)。  エディット コントロールの機能に加えて、リッチ エディット コントロールは、フォント、色、段落書式と埋め込まれたな OLE オブジェクトをサポートします。  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Windows のリスト コントロールを含むビューは [CListCtrl](../Topic/CListCtrl%20Class.md)を参照します\)。  リスト項目コントロールには、それぞれファイル エクスプローラーの右ペインに似たアイコンから成るとラベルのコレクションを、では表示されます。  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Windows コモン ツリー コントロールを含むビューは [CTreeCtrl](../mfc/reference/ctreectrl-class.md)を参照します\)。  ツリー コントロールは、エクスプローラーの左ペインにアイコンとラベルで配置する同様の階層的な一覧が表示されます。  
  
## 関連クラス  
 `CSplitterWnd` は 一つのフレーム ウィンドウ内の複数のビューを持つことができます。  `CPrintDialog` と `CPrintInfo` はビューの印刷や印刷プレビューの機能をサポートします。  `CRichEditDoc` と `CRichEditCntrItem` は `CRichEditView` と OLE コンテナーの機能を実装するために使用されます。  
  
 [CSplitterWnd](../mfc/reference/csplitterwnd-class.md)  
 ユーザーが複数のペインに分割できるウィンドウ。  これらのペインはユーザーがサイズ変更できるまたは固定サイズになります。  
  
 [CPrintDialog](../Topic/CPrintDialog%20Class.md)  
 ファイルを印刷するために、標準のダイアログ ボックスを表示します。  
  
 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)  
 印刷や印刷プレビュー ジョブに関する情報が格納された構造体。  アーキテクチャを印刷する `CView` に使用されます。  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 `CRichEditView`にある OLE クライアント項目のリストを保持します。  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 `CRichEditView`に格納された OLE アイテムへのクライアント側アクセスを提供します。  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)