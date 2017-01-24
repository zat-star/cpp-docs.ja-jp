---
title: "メニューとリソース : コンテナーの変更点 | Microsoft Docs"
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
  - "IDP_OLE_INIT_FAILED"
  - "IDP_FAILED_TO_CREATE"
  - "VK_ESCAPE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アクセラレータ テーブル [C++], コンテナー アプリケーション"
  - "アプリケーションのアクセラレータ テーブル [C++]"
  - "CONTAIN チュートリアル"
  - "IDP_FAILED_TO_CREATE マクロ"
  - "IDP_OLE_INIT_FAILED マクロ"
  - "リンク (メニュー項目)"
  - "OLE コンテナー, メニューとリソース"
  - "ビジュアル編集, アプリケーションのメニューとリソース"
  - "VK_ESCAPE キー"
ms.assetid: 425448be-8ca0-412e-909a-a3a9ce845288
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# メニューとリソース : コンテナーの変更点
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、ビジュアル編集コンテナー アプリケーションのメニューやそのほかのリソースに加える必要がある変更を示しています。  
  
 コンテナー アプリケーションの変更の 2 種類が行われる必要があります: 埋め込み先編集の有効化に使用する新しいリソースの OLE ビジュアル編集と追加をサポートする既存のリソースに変更します。  コンテナー アプリケーションを作成するときにアプリケーション ウィザードを使用する場合、これらの手順は、され、カスタマイズが必要な場合があります。  
  
 アプリケーション ウィザードを使用して、OCLIENT.RC でこれらの変更がどのように実装されるかを参照する OCLIENT サンプル アプリケーションのリソース スクリプトを表示することもできます。  MFC の OLE [OCLIENT](../top/visual-cpp-samples.md)サンプルを参照してください。  
  
 この記事で説明されているトピックは次のとおりです。:  
  
-   [コンテナーのメニューの追加](#_core_container_menu_additions)  
  
-   [アクセラレータ テーブルの追加](#_core_container_application_accelerator_table_additions)  
  
-   [ストリング テーブルの追加](#_core_string_table_additions_for_container_applications)  
  
##  <a name="_core_container_menu_additions"></a> コンテナーのメニューの追加  
 編集メニューで、次の要素を追加する必要があります:  
  
|項目|目的|  
|--------|--------|  
|**新しいオブジェクトを挿入します。**|OLE のオブジェクトの挿入ダイアログ ボックスをドキュメントにリンクされたを埋め込まれたアイテムが挿入されます。|  
|**リンク貼り付け**|ドキュメントにクリップボードのアイテムへのリンクを貼り付けます。|  
|**OLE 動詞**|選択した項目の主動詞を呼び出します。  このメニュー項目のテキストが、選択した項目の主動詞を反映するように変更します。|  
|**リンク**|OLE を既存のリンク アイテムを変更して編集しますリンク ダイアログ ボックスを開きます。|  
  
 表示されているこの記事の変更はソース ファイルに加えて、Microsoft Foundation Class ライブラリの実装に必要な AFXOLECL.RC を含める必要があります。  \) 新しいオブジェクトが唯一の必須メニュー追加です。  そのほかの項目を追加することもできますが、ここに示されているものが一般的です。  
  
 含まれる項目の埋め込み先編集の有効化をサポートするには、コンテナー アプリケーションの新しいメニューを作成する必要があります。  このメニューは同じファイル メニューから構成され、ファイルが開いているときは、その中に配置される 2 種類の区切り記号は、ウィンドウのポップアップ メニューを使用します。  アクティブになったときにこれらの区切り記号はサーバー コンポーネント \(\)\) がメニュー項目 \(アプリケーションを配置する方法を示すために使用されます。  このメニューのマージの詳細については、「[メニューとリソース: メニューのマージ](../mfc/menus-and-resources-menu-merging.md)」を参照してください。  
  
##  <a name="_core_container_application_accelerator_table_additions"></a> コンテナー アプリケーションのアクセラレータ テーブルの追加  
 コンテナー アプリケーションのアクセラレータ テーブル リソースにわずかな変更は、埋め込み先編集の有効化をサポートする必要があります。  最初の変更は、ユーザーが埋め込み先での編集モードを取り消すには、Esc キー\) \(Esc キーを押すこともできます。  主要なアクセラレータ テーブルに次のエントリを追加する:  
  
|ID|キー|型|  
|--------|--------|-------|  
|**ID\_CANCEL\_EDIT\_CNTR**|VK\_ESCAPE|**VIRTKEY**|  
  
 2 番目の変更は、埋め込み先編集の有効化用に作成された新しいメニュー リソースに対応する新しいアクセラレータ テーブルを作成します。  この表に上記の **VK\_ESCAPE** エントリに加えてファイルとウィンドウ メニューのエントリがあります。  次の例では、MFC のサンプル [コンテナー](../top/visual-cpp-samples.md)で埋め込み先編集の有効化用に作成されたアクセラレータ テーブルです:  
  
|ID|キー|型|  
|--------|--------|-------|  
|`ID_FILE_NEW`|Ctrl \+ N|**VIRTKEY**|  
|`ID_FILE_OPEN`|Ctrl \+ O|**VIRTKEY**|  
|**ID\_FILE\_SAVE**|Ctrl \+ S|**VIRTKEY**|  
|**ID\_FILE\_PRINT**|Ctrl \+ P|**VIRTKEY**|  
|**ID\_NEXT\_PANE**|VK\_F6|**VIRTKEY**|  
|**ID\_PREV\_PANE**|SHIFT\+VK\_F6|**VIRTKEY**|  
|**ID\_CANCEL\_EDIT\_CNTR**|VK\_ESCAPE|**VIRTKEY**|  
  
##  <a name="_core_string_table_additions_for_container_applications"></a> コンテナー アプリケーションのストリング テーブルの追加  
 コンテナー アプリケーションのストリング テーブルに対する変更の大部分は [コンテナーのメニューの追加](#_core_container_menu_additions)で説明した追加メニュー項目に対応します。  チームは各メニュー項目が表示されたときに、ステータス バーに表示されるテキストを指定します。  たとえば、アプリケーション ウィザードで生成されたストリング テーブルのエントリを次に示します。:  
  
|ID|String|  
|--------|------------|  
|**IDP\_OLE\_INIT\_FAILED**|OLE の初期化に失敗しました。  OLE ライブラリのバージョンが正しいことを確認してください。|  
|**IDP\_FAILED\_TO\_CREATE**|オブジェクトの作成に失敗しました。  オブジェクトがシステム レジストリに入力してください。|  
  
## 参照  
 [メニューとリソース \(OLE\)](../mfc/menus-and-resources-ole.md)   
 [メニューとリソース : サーバーの変更点](../mfc/menus-and-resources-server-additions.md)