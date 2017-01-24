---
title: "MFC マクロとグローバル | Microsoft Docs"
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
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Afx 名前付け規則"
  - "グローバル関数"
  - "グローバル関数, MFC"
  - "グローバル変数, MFC"
  - "マクロ"
  - "マクロ, MFC"
  - "MFC, グローバル関数とグローバル変数"
  - "MFC, マクロ"
ms.assetid: add4e33f-0e62-4d27-be14-896cb8675d22
caps.latest.revision: 18
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC マクロとグローバル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC \(Microsoft Foundation Class\) ライブラリは、\(1\) MFC クラス、\(2\) マクロおよびグローバル関数とグローバル変数の 2 つの主要な分野で構成されます。  クラスのメンバーではない関数や変数は、グローバル関数またはグローバル変数です。  
  
 MFC ライブラリと ATL \(Active Template Library\) は文字列変換マクロを共有します。  詳細については、ATL のドキュメントの「[文字列変換に関するマクロ](../../atl/reference/string-conversion-macros.md)」を参照してください。  
  
 MFC のマクロ、グローバル関数、およびグローバル変数には、次の機能が用意されています。  
  
## 汎用 MFC  
  
-   [データ型](../Topic/Data%20Types%20\(MFC\).md)  
  
-   [MFC クラス オブジェクトの型キャスト](../../mfc/reference/type-casting-of-mfc-class-objects.md)  
  
-   [ランタイム オブジェクト モデル サービス](../../mfc/reference/run-time-object-model-services.md)  
  
-   [診断サービス](../Topic/Diagnostic%20Services.md)  
  
-   [例外処理](../../mfc/reference/exception-processing.md)  
  
-   [CString の書式指定とメッセージ ボックスの表示](../../mfc/reference/cstring-formatting-and-message-box-display.md)  
  
-   [メッセージ マップ](../../mfc/reference/message-map-macros-mfc.md)  
  
-   [アプリケーションの情報と管理](../Topic/Application%20Information%20and%20Management.md)  
  
-   [標準コマンド ID とウィンドウ ID](../../mfc/reference/standard-command-and-window-ids.md)  
  
-   [コレクション クラスのヘルパー](../../mfc/reference/collection-class-helpers.md)  
  
-   [淡色表示 \(灰色\) ビットマップ関数とディザリングされたビットマップ関数](../../mfc/reference/gray-and-dithered-bitmap-functions.md)  
  
-   [標準的なダイアログ データ エクスチェンジ ルーチン](../Topic/Standard%20Dialog%20Data%20Exchange%20Routines.md)  
  
-   [標準的なダイアログ データ バリデーション \(DDV\) ルーチン](../../mfc/reference/standard-dialog-data-validation-routines.md)  
  
-   [AFX メッセージ](../../mfc/reference/afx-messages.md)  
  
-   [ツール バー コントロールのスタイル](../Topic/ToolBar%20Control%20Styles.md)  
  
-   [CMFCImagePaintArea::IMAGE\_EDIT\_MODE 列挙体](../Topic/CMFCImagePaintArea::IMAGE_EDIT_MODE%20Enumeration.md)  
  
## データベース  
  
-   [レコード フィールド エクスチェンジ \(RFX\) 関数](../../mfc/reference/record-field-exchange-functions.md)と[バルク レコード フィールド エクスチェンジ \(Bulk RFX\) 関数](../../mfc/reference/record-field-exchange-functions.md) \(MFC ODBC クラス\)  
  
-   [レコード フィールド エクスチェンジ \(RFX\) 関数](../../mfc/reference/record-field-exchange-functions.md) \(MFC DAO クラス\)  
  
-   [CRecordView と CDaoRecordView のダイアログ データ エクスチェンジ \(DDX\) 関数](../../mfc/reference/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) \(MFC ODBC クラスと MFC DAO クラス\)  
  
-   [OLE コントロールのダイアログ データ エクスチェンジ \(DDX\) 関数](../../mfc/reference/dialog-data-exchange-functions-for-ole-controls.md)  
  
-   [ODBC \(Open Database Connectivity\) API 関数を直接呼び出すマクロとグローバル](../../mfc/reference/database-macros-and-globals.md)  
  
-   [DAO データベース エンジンの初期化と終了](../../mfc/reference/dao-database-engine-initialization-and-termination.md)  
  
## インターネット  
  
-   [インターネット URL 解析用グローバル](../Topic/Internet%20URL%20Parsing%20Globals.md)  
  
## DHTML\/DHTML のイベント マップ  
  
-   [DHTML dialog data exchange \(DDX\) ヘルパー マクロ](../../mfc/reference/ddx-dhtml-helper-macros.md)  
  
-   [DHTML イベント マップ](../../mfc/reference/dhtml-event-maps.md)  
  
## OLE  
  
-   [OLE の初期化](../../mfc/reference/ole-initialization.md)  
  
-   [アプリケーションの制御](../../mfc/reference/application-control.md)  
  
-   [ディスパッチ マップ](../../mfc/reference/dispatch-maps.md)  
  
 MFC には、上記に加え、MFC 4.0 で開発されたすべての OLE コンテナーで埋め込み OLE コントロールを完全にサポートできるようにする関数 [AfxEnableControlContainer](../Topic/AfxEnableControlContainer.md) も用意されています。  
  
## OLE コントロール  
  
-   [Variant パラメーター型の定数](../Topic/Variant%20Parameter%20Type%20Constants.md)  
  
-   [タイプ ライブラリ アクセス](../../mfc/reference/type-library-access.md)  
  
-   [プロパティ ページ](../../mfc/reference/property-pages-mfc.md)  
  
-   [イベント マップ](../../mfc/reference/event-maps.md)  
  
-   [イベント シンク マップ](../../mfc/reference/event-sink-maps.md)  
  
-   [コネクション マップ](../../mfc/reference/connection-maps.md)  
  
-   [OLE コントロールの登録](../Topic/Registering%20OLE%20Controls.md)  
  
-   [クラス ファクトリとライセンス](../../mfc/reference/class-factories-and-licensing.md)  
  
-   [OLE コントロールの永続化](../../mfc/reference/persistence-of-ole-controls.md)  
  
 このセクションの最初の部分では、上に示した各カテゴリについて簡単に説明し、カテゴリ内の各グローバル関数、グローバル変数、およびマクロの一覧を簡単な機能説明と共に示します。  次に、MFC ライブラリのグローバル関数、グローバル変数、およびマクロについて説明します。  
  
> [!NOTE]
>  グローバル関数の多くはプレフィックス "Afx" で始まります。ただし、ダイアログ データ エクスチェンジ \(DDX\) 関数や多くのデータベース関数など、一部に例外もあります。  すべてのグローバル変数はプリフィックス "afx" で始まります。  マクロは特定のプリフィックスでは始まりませんが、すべて大文字を使用します。  
  
## 参照  
 [クラスの概要](../../mfc/class-library-overview.md)