---
title: "MFC マクロとグローバル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- MFC, global functions and variables
- MFC, macros
- global functions, MFC
- macros, MFC
- global functions
- global variables, MFC
- Afx naming convention
- macros
ms.assetid: add4e33f-0e62-4d27-be14-896cb8675d22
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: d26b374e233326ac5acc97486edc8d38e6bf5d81
ms.openlocfilehash: 75db28c7be1ab497ba9656136d22b114b488c4ae
ms.lasthandoff: 02/24/2017

---
# <a name="mfc-macros-and-globals"></a>MFC マクロとグローバル
MFC (Microsoft Foundation Class) ライブラリは、(1) MFC クラス、(2) マクロおよびグローバル関数とグローバル変数の&2; つの主要な分野で構成されます。 クラスのメンバーではない関数や変数は、グローバル関数またはグローバル変数です。  
  
 MFC ライブラリと ATL (Active Template Library) は文字列変換マクロを共有します。 詳細については、次を参照してください。[文字列変換マクロ](../../atl/reference/string-conversion-macros.md)ATL のドキュメントにします。  
  
 MFC のマクロ、グローバル関数、およびグローバル変数には、次の機能が用意されています。  
  
## <a name="general-mfc"></a>汎用 MFC  
  
-   [データ型](../../mfc/reference/data-types-mfc.md)  
  
-   [MFC クラス オブジェクトの型キャスト](../../mfc/reference/type-casting-of-mfc-class-objects.md)  
  
-   [ランタイム オブジェクト モデル サービス](../../mfc/reference/run-time-object-model-services.md)  
  
-   [診断サービス](../../mfc/reference/diagnostic-services.md)  
  
-   [例外の処理](../../mfc/reference/exception-processing.md)  
  
-   [CString の書式指定とメッセージ ボックスの表示](../../mfc/reference/cstring-formatting-and-message-box-display.md)  
  
-   [メッセージ マップ](../../mfc/reference/message-map-macros-mfc.md)  
  
-   [アプリケーションの情報と管理](../../mfc/reference/application-information-and-management.md)  
  
-   [標準コマンド id とウィンドウ Id](../../mfc/reference/standard-command-and-window-ids.md)  
  
-   [コレクション クラスのヘルパー](../../mfc/reference/collection-class-helpers.md)  
  
-   [灰色とディザリングされたビットマップ関数](../../mfc/reference/gray-and-dithered-bitmap-functions.md)  
  
-   [標準的なダイアログ データ エクス (チェンジ DDX) のルーチン](../../mfc/reference/standard-dialog-data-exchange-routines.md)  
  
-   [標準的なダイアログ データ バリデーション (DDV) ルーチン](../../mfc/reference/standard-dialog-data-validation-routines.md)  
  
-   [AFX メッセージ](../../mfc/reference/afx-messages.md)  
  
-   [ツール バー コントロールのスタイル](../../mfc/reference/toolbar-control-styles.md)  
  
-   [Cmfcimagepaintarea::image_edit_mode 列挙体](cmfcimagepaintarea-image-edit-mode-enumeration.md)  

  
## <a name="database"></a>データベース  
  
-   [レコード フィールド エクス チェンジ (RFX) 関数](../../mfc/reference/record-field-exchange-functions.md)と[バルク レコード フィールド エクス チェンジ (bulk RFX) 関数](../../mfc/reference/record-field-exchange-functions.md)MFC ODBC クラス  
  
-   [レコード フィールド エクス (チェンジ DFX) 関数](../../mfc/reference/record-field-exchange-functions.md)MFC DAO クラス  
  
-   [CRecordView と CDaoRecordView のダイアログ データ エクス (チェンジ DDX) 関数](../../mfc/reference/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md)(MFC ODBC と DAO クラス)  
  
-   [OLE コントロールのダイアログ データ エクス (チェンジ DDX) 関数](../../mfc/reference/dialog-data-exchange-functions-for-ole-controls.md)  
  
-   [オープン データベース コネクティビティ (ODBC) API 関数を直接呼び出すマクロとグローバル](../../mfc/reference/database-macros-and-globals.md)  
  
-   [DAO データベース エンジンの初期化と終了](../../mfc/reference/dao-database-engine-initialization-and-termination.md)  
  
## <a name="internet"></a>インターネット  
  
-   [インターネット URL 解析用グローバル関数](../../mfc/reference/internet-url-parsing-globals.md)  
  
## <a name="dhtml--dhtml-event-maps"></a>DHTML/DHTML のイベント マップ  
  
-   [DHTML ダイアログ データ エクス (チェンジ DDX) ヘルパー マクロ](../../mfc/reference/ddx-dhtml-helper-macros.md)  
  
-   [DHTML イベント マップ](../../mfc/reference/dhtml-event-maps.md)  
  
## <a name="ole"></a>OLE  
  
-   [OLE の初期化](../../mfc/reference/ole-initialization.md)  
  
-   [アプリケーションの制御](../../mfc/reference/application-control.md)  
  
-   [ディスパッチ マップ](../../mfc/reference/dispatch-maps.md)  
  
 さらに、呼び出される関数は、MFC [AfxEnableControlContainer](http://msdn.microsoft.com/library/7aa0b9d2-5329-4bc3-9d41-856e30fe2c2b)により完全にサポートする MFC 4.0 で開発されたすべての OLE コンテナーが OLE コントロールを埋め込むことです。  
  
## <a name="ole-controls"></a>OLE コントロール  
  
-   [Variant パラメーター型定数](../../mfc/reference/variant-parameter-type-constants.md)  
  
-   [タイプ ライブラリ アクセス](../../mfc/reference/type-library-access.md)  
  
-   [プロパティ ページ](../../mfc/reference/property-pages-mfc.md)  
  
-   [イベント マップ](../../mfc/reference/event-maps.md)  
  
-   [イベント シンク マップします。](../../mfc/reference/event-sink-maps.md)  
  
-   [コネクション マップ](../../mfc/reference/connection-maps.md)  
  
-   [OLE コントロールの登録](../../mfc/reference/registering-ole-controls.md)  
  
-   [クラス ファクトリとライセンス](../../mfc/reference/class-factories-and-licensing.md)  
  
-   [OLE コントロールの永続化](../../mfc/reference/persistence-of-ole-controls.md)  
  
 このセクションの最初の部分では、上に示した各カテゴリについて簡単に説明し、カテゴリ内の各グローバル関数、グローバル変数、およびマクロの一覧を簡単な機能説明と共に示します。 次に、MFC ライブラリのグローバル関数、グローバル変数、およびマクロについて説明します。  
  
> [!NOTE]
>  グローバル関数の多くはプレフィックス "Afx" で始まります。ただし、ダイアログ データ エクスチェンジ (DDX) 関数や多くのデータベース関数など、一部に例外もあります。 すべてのグローバル変数はプリフィックス "afx" で始まります。 マクロは特定のプリフィックスでは始まりませんが、すべて大文字を使用します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../mfc/class-library-overview.md)




