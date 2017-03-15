---
title: "データ オブジェクトとデータ ソース : 操作 | Microsoft Docs"
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
  - "クリップボード [C++], 判断 (使用できる形式を)"
  - "クリップボード [C++], 渡す (書式情報を)"
  - "データ オブジェクト [C++], 操作"
  - "データ ソース [C++], データ操作"
  - "データ ソース [C++], 判断 (使用できる形式を)"
  - "データ ソース [C++], 挿入 (データを)"
  - "遅延レンダリング [C++]"
  - "OLE [C++], データ オブジェクト"
  - "OLE [C++], データ ソース"
ms.assetid: f7f27e77-bb5d-4131-b819-d71bf929ebaf
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# データ オブジェクトとデータ ソース : 操作
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

データ オブジェクトまたはデータ ソースの後で作成された場合、挿入などのデータの一般的な操作を実行することができ、形式を列挙する削除、データなどです。  ここでは、最も一般的な操作を完了するために必要な手法について説明します。  ここでは、次の内容について説明します。  
  
-   [データ ソースにデータを挿入できます。](#_core_inserting_data_into_a_data_source)  
  
-   [データ オブジェクトで使用できる形式を決定します。](#_core_determining_the_formats_available_in_a_data_object)  
  
-   [データ オブジェクトからのデータの取得](#_core_retrieving_data_from_a_data_object)  
  
##  <a name="_core_inserting_data_into_a_data_source"></a> データ ソースにデータを挿入できます。  
 データがデータ ソースに挿入したりデータをすばやくまたはオンデマンドで指定されているかによって、およびメディアをで指定されているかどうかを指定します。  これは次のとおりです。  
  
### フィード データ、\(現在の描画\)  
  
-   データを提供するすべてのクリップボード形式を `COleDataSource::CacheGlobalData` に繰り返し呼び出し。  メモリに格納すると、ハンドルを使用するクリップボード データ形式、およびオプションで、データを表す **FORMATETC** 構造体を渡します。  
  
     または  
  
-   **STGMEDIUM** 構造体を直接使用する場合は、上記のオプションの `COleDataSource::CacheGlobalData` の代わりに `COleDataSource::CacheData` を呼び出します。  
  
### フィード データに応じて \(遅延レンダリング\)  
 これは高度なトピックです。  
  
-   データを提供するすべてのクリップボード形式を `COleDataSource::DelayRenderData` に繰り返し呼び出し。  使用するクリップボード形式、およびオプションで、データを表す **FORMATETC** 構造体を渡します。  データが要求されると、フレームワークは、オーバーライドする必要 `COleDataSource::OnRenderData`を呼び出します。  
  
     または  
  
-   データを提供するために `CFile` オブジェクトを使用して前のオプションの `COleDataSource::DelayRenderData` の代わりに `COleDataSource::DelayRenderFileData` を呼び出します。  データが要求されると、フレームワークは、オーバーライドする必要 `COleDataSource::OnRenderFileData`を呼び出します。  
  
##  <a name="_core_determining_the_formats_available_in_a_data_object"></a> データ オブジェクトで使用できる形式を決定します。  
 アプリケーションは、ユーザーにデータを貼り付けることを有効にする前に処理できるにクリップボード形式が存在するかどうかを確認する必要があります。  これを行うには、アプリケーションは次のようにする必要があります:  
  
1.  `COleDataObject` オブジェクトと **FORMATETC** 構造を作成します。  
  
2.  クリップボードのデータとデータ オブジェクトを関連付けるには、データ オブジェクトの `AttachClipboard` メンバー関数を呼び出します。  
  
3.  以下のいずれかを実行します。  
  
    -   必要な形式が一つしかないデータ オブジェクトの `IsDataAvailable` メンバー関数を呼び出します。  これは時間クリップボードのデータがアプリケーションよりも多くの形式をサポートする格納します。  
  
         または  
  
    -   クリップボードに使用できる形式を列挙できるようにデータ オブジェクトの `BeginEnumFormats` メンバー関数を呼び出します。  クリップボードは、アプリケーションがサポートする形式を返すか、これ以上の形式がなくなるまで `GetNextFormat` を呼び出します。  
  
 `ON_UPDATE_COMMAND_UI`を使用する場合、貼り付けを、編集メニューの特殊な項目を貼り付けることもできるようになります。  これを行うには、`CMenu::EnableMenuItem` または `CCmdUI::Enable`を呼び出します。  コンテナー アプリケーションがメニュー項目にする必要がある場合に機能の詳細については、[メニューとリソース: コンテナーの追加](../mfc/menus-and-resources-container-additions.md)を参照し。  
  
##  <a name="_core_retrieving_data_from_a_data_object"></a> データ オブジェクトからのデータの取得  
 データ形式を決定したら、後は、データ オブジェクトからデータを取得することです。  そのため、ユーザーはデータを配置する場所をとするアプリケーションは、関数を呼び出します。  データは次のメディアの 1 つがで使用する:  
  
|Medium|呼び出される関数|  
|------------|--------------|  
|グローバル メモリ \(`HGLOBAL`\)|`COleDataObject::GetGlobalData`|  
|ファイル \(`CFile`\)|`COleDataObject::GetFileData`|  
|**STGMEDIUM** 構造 体 \(`IStorage`\)|`COleDataObject::GetData`|  
  
 一般に、メディアはクリップボード形式とともに指定します。  たとえば、**CF\_EMBEDDEDSTRUCT** オブジェクトは **STGMEDIUM** 構造体を必要とする `IStorage` のメディアに必要です。  したがって **STGMEDIUM** 構造体を受け入れることができる、これらの関数の 1 であるため、`GetData` を使用します。  
  
 クリップボード形式が `IStream` または `HGLOBAL` の中にある場合は、フレームワークはデータを参照する `CFile` にポインターを提供できます。  アプリケーションは、ファイルからデータをインポートすることがありますと同様にデータを取得するために、読み取られるファイルを使用できます。  基本的に、データ ソースの `OnRenderData` と `OnRenderFileData` ルーチンにクライアント側インターフェイスです。  
  
 ユーザーは同じ形式で他のデータのなどのドキュメントには、データを単に挿入できます。  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [ドラッグ アンド ドロップする](../mfc/drag-and-drop-ole.md)  
  
-   [クリップボード](../mfc/clipboard.md)  
  
## 参照  
 [データ オブジェクトとデータ ソース \(OLE\)](../mfc/data-objects-and-data-sources-ole.md)   
 [COleDataObject クラス](../mfc/reference/coledataobject-class.md)   
 [COleDataSource クラス](../mfc/reference/coledatasource-class.md)