---
title: "ビュー クラス (アーキテクチャ) | Microsoft Docs"
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
  - "コントロール ビュー"
  - "フォーム ビューとレコード ビュー"
  - "ビュー クラス"
  - "ビュー クラス, アーキテクチャ"
ms.assetid: 8894579a-1436-441e-b985-83711061e495
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ビュー クラス (アーキテクチャ)
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
  
 [CHtmlView](../mfc/reference/chtmlview-class.md)  
 アプリケーション内で Web 参照のコントロールをサポートします。  コントロールは、MFC の動的な HTML をサポートします。  
  
 [COLEDBRecordView](../mfc/reference/coledbrecordview-class.md)  
 フォーム ビューへの OLE DB サポートを提供します。  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 直接 ODBC \(Open Database Connectivity\) データ ソースに接続されているフォーム ビューを提供します。  すべてのフォーム ビューと同様に、`CRecordView` はダイアログ ボックス テンプレートに基づいています。  
  
## コントロール ビュー  
 コントロール ビューは、ビューとしてコントロールを表示します。  
  
 [CCtrlView](../mfc/reference/cctrlview-class.md)  
 すべての基本クラスは、Windows のコントロールには、関連を検索します。  コントロールに基づくビューについて、次に説明します。  
  
 [CEditView](../Topic/CEditView%20Class.md)  
 Windows 標準エディット コントロールを含むビューは [CEdit](../Topic/CEdit%20Class.md)を参照します\)。  エディット コントロール サポート機能をテキスト編集、検索、置換、およびスクロールします。  
  
 [CRichEditView](../mfc/reference/cricheditview-class.md)  
 Windows のリッチ エディット コントロールを含むビューは [CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)を参照します\)。  エディット コントロールの機能に加えて、リッチ エディット コントロールは、フォント、色、段落書式と埋め込まれたな OLE オブジェクトをサポートします。  
  
 [CListView](../mfc/reference/clistview-class.md)  
 Windows のリスト コントロールを含むビューは [CListCtrl](../Topic/CListCtrl%20Class.md)を参照します\)。  リスト コントロールは、ファイル エクスプローラーの右ペインに似たアイコンや文字列を表示します。  
  
 [CTreeView](../mfc/reference/ctreeview-class.md)  
 Windows コモン ツリー コントロールを含むビューは [CTreeCtrl](../mfc/reference/ctreectrl-class.md)を参照します\)。  ツリー コントロールは、ファイル エクスプローラーの左ペインに似た階層で表示されるアイコン、配列、および文字列を表示します。  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)