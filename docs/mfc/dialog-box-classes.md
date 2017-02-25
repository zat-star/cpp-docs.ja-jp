---
title: "ダイアログ ボックス クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.dialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コモン ダイアログ クラス"
  - "ダイアログ ボックス クラス"
  - "OLE コモン ダイアログ クラス"
  - "プロパティ シート クラス"
  - "タブ ダイアログ ボックス"
ms.assetid: db75da23-4eff-4c6c-beae-79cf046fbce9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ダイアログ ボックス クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CDialog` クラスとその派生クラスは、ダイアログ ボックスの機能をカプセル化します。  ダイアログ ボックスがウィンドウの特別な型であるため、`CDialog` は `CWnd`から派生されます。  ダイアログ クラスを `CDialog` から派生するか、開始または保存などの標準のダイアログ ボックスにコモン ダイアログ クラスの 1 を、フォントや色を選択するか、検索置換操作を開始したり、さまざまな OLE 関連の操作を実行するファイル、出力使用します。  
  
 [CDialog](../mfc/reference/cdialog-class.md)  
 すべてのダイアログ ボックスの基本クラス、モーダルおよびモードレス両方。  
  
 [CDataExchange](../Topic/CDataExchange%20Class.md)  
 データ交換提供とダイアログ ボックスの検証情報。  
  
## コモン ダイアログ  
 これらのダイアログ ボックス クラスは、Windows のコモン ダイアログ ボックスをカプセル化します。  これらは、複雑なダイアログ ボックスの使いやすい実装を提供します。  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
 すべてのコモン ダイアログ ボックスの基本クラスです。  
  
 [CFileDialog](../Topic/CFileDialog%20Class.md)  
 ファイルを開くか、または保存するために、標準のダイアログ ボックスを表示します。  
  
 [CColorDialog](../mfc/reference/ccolordialog-class.md)  
 色を選択するために、標準のダイアログ ボックスを表示します。  
  
 [CFontDialog](../mfc/reference/cfontdialog-class.md)  
 フォントを選択するために、標準のダイアログ ボックスを表示します。  
  
 [CFindReplaceDialog](../Topic/CFindReplaceDialog%20Class.md)  
 検索置換操作の標準のダイアログ ボックスを表示します。  
  
 [CPrintDialog](../Topic/CPrintDialog%20Class.md)  
 ファイルを印刷するために、標準のダイアログ ボックスを表示します。  
  
 [CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)  
 Windows 2000 の印刷プロパティ シートが用意されています。  
  
 [CPageSetupDialog](../mfc/reference/cpagesetupdialog-class.md)  
 印刷マージンの設定や変更のに追加サポートとともにページ設定ダイアログ ボックスによって提供されるサービスをカプセル化します。  
  
## OLE コモン ダイアログ  
 OLE\)、いくつかのコモン ダイアログ ボックスを追加します。  これらのクラスは OLE コモン ダイアログ ボックスをカプセル化します。  
  
 [COleDialog](../mfc/reference/coledialog-class.md)  
 すべての OLE ダイアログ ボックスの一般的な実装を格納するために、フレームワークによって使用されます。  ユーザー カテゴリのすべてのダイアログ ボックス クラスは、この基本クラスから派生されます。  `COleDialog` を直接 使用することはできません。  
  
 [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)  
 オブジェクトの挿入ダイアログ ボックスで、新しい OLE リンクされたまたは埋め込まれたアイテムを挿入するための標準のユーザー インターフェイスが表示されます。  
  
 [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)  
 貼り付け時に特殊なダイアログ ボックス、編集の貼り付けコマンドを実装するための標準的なユーザー インターフェイスが表示されます。  
  
 [COleLinksDialog](../mfc/reference/colelinksdialog-class.md)  
 Edit リンク ダイアログ ボックス、リンクされた項目に関する変更情報の標準のユーザー インターフェイスが表示されます。  
  
 [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)  
 変更アイコン ダイアログ ボックス、埋め込まれた OLE のまたはリンク アイテムに関連付けられているアイコンを変更するための標準のユーザー インターフェイスが表示されます。  
  
 [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)  
 変換ダイアログ ボックス、1 種類のから別のプロジェクトに OLE アイテムを変換するための標準のユーザー インターフェイスが表示されます。  
  
 [COlePropertiesDialog](../Topic/COlePropertiesDialog%20Class.md)  
 Windows に共通の OLE プロパティ ダイアログ ボックスをカプセル化します。  共通の OLE プロパティ ダイアログ ボックスは、Windows の標準に準拠した OLE ドキュメント アイテムのプロパティを表示および変更するための簡単な方法を提供します。  
  
 [COleUpdateDialog](../Topic/COleUpdateDialog%20Class.md)  
 更新ダイアログ ボックス、ドキュメントのすべてのリンクを更新するための標準的なユーザー インターフェイスが表示されます。  ダイアログ ボックスを閉じる更新プロシージャが完了に示す、プログレス インジケーターが含まれます。  
  
 [COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)  
 ソースの変更ダイアログ ボックスで、リンク先またはソースを変更するための標準のユーザー インターフェイスが表示されます。  
  
 [COleBusyDialog](../mfc/reference/colebusydialog-class.md)  
 使用するサーバーを表示し、ダイアログ ボックスを応答しないサーバーがビジー アプリケーションに処理の標準ユーザー インターフェイス呼び出します。  通常 [COleMessageFilter](../mfc/reference/colemessagefilter-class.md) の実装によって自動的に表示されます。  
  
## プロパティ シート クラス  
 プロパティ シート クラスには、アプリケーションがプロパティ シート \(タブ付きダイアログを使用できるようになります。  プロパティ シートは、ダイアログ ボックスの多くのコントロールを整理する効率的です。  
  
 [CPropertyPage](../mfc/reference/cpropertypage-class.md)  
 プロパティ シート内の個々のページを提供します。  プロパティ シートに追加するページごとに `CPropertyPage` からクラスを派生してください。  
  
 [CPropertySheet](../mfc/reference/cpropertysheet-class.md)  
 複数のプロパティ ページにフレームを提供します。  プロパティ シートを一度に実装するに `CPropertySheet` のプロパティ シート クラスを派生してください。  
  
 [COlePropertyPage クラス](../mfc/reference/colepropertypage-class.md)  
 ダイアログ ボックスのようなグラフィカル インターフェイスの OLE コントロールのプロパティが表示されます。  
  
## HTML ベースのダイアログ クラス  
 [CDHtmlDialog](../Topic/CDHtmlDialog%20Class.md)  
 ダイアログ リソースではなく、HTML を含むユーザー インターフェイスを実装するダイアログ ボックスを作成するために使用します。  
  
 [CMultiPageDHtmlDialog](../mfc/reference/cmultipagedhtmldialog-class.md)  
 複数の HTML ページを順番に表示し、各ページのイベントを処理します。  
  
## 関連クラス  
 これらのクラスは、基本的にダイアログ ボックスではありませんが、ダイアログ ボックス テンプレートを使用して、ダイアログ ボックスの多くがあります。  
  
 [CDialogBar](../mfc/reference/cdialogbar-class.md)  
 ダイアログ ボックス テンプレートに基づくコントロール バーです。  
  
 [CFormView](../mfc/reference/cformview-class.md)  
 レイアウトがダイアログ ボックス テンプレートで定義されるスクロール ビュー。  ダイアログ ボックス テンプレートに基づいてユーザー インターフェイスを実装するに `CFormView` からクラスを派生してください。  
  
 [CDaoRecordView クラス](../mfc/reference/cdaorecordview-class.md)  
 直接 Data Access Object \(DAO\) のレコードセット オブジェクトにアタッチされるフォーム ビューを提供します。  すべてのフォーム ビューと同様に、`CDaoRecordView` はダイアログ ボックス テンプレートに基づいています。  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 直接 ODBC \(Open Database Connectivity\) データ ソースに接続されているフォーム ビューを提供します。  すべてのフォーム ビューと同様に、`CRecordView` はダイアログ ボックス テンプレートに基づいています。  
  
 [CPrintInfo](../mfc/reference/cprintinfo-structure.md)  
 印刷や印刷プレビュー ジョブに関する情報が格納された構造体。  [CView](../Topic/CView%20Class.md)の印刷アーキテクチャで使用されます。  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)