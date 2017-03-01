---
title: "COleDocument クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDocument
dev_langs:
- C++
helpviewer_keywords:
- COleDocument class
- OLE documents, base class
- OLE containers, client items
- visual editing, OLE document base class
- OLE documents
- documents, OLE
ms.assetid: dc2ecb99-03e1-44c7-bb69-48056dd1b672
caps.latest.revision: 23
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 73bd1bc5c2c93e180b42a79cf23ab98360887c31
ms.lasthandoff: 02/24/2017

---
# <a name="coledocument-class"></a>COleDocument クラス
ビジュアル編集をサポートする OLE ドキュメントの基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class COleDocument : public CDocument  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleDocument::COleDocument](#coledocument)|`COleDocument` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleDocument::AddItem](#additem)|ドキュメントが管理しているアイテムの一覧に項目を追加します。|  
|[COleDocument::ApplyPrintDevice](#applyprintdevice)|ドキュメント内のすべてのクライアント アイテムの出力先のデバイスを設定します。|  
|[COleDocument::EnableCompoundFile](#enablecompoundfile)|OLE 構造化ストレージ ファイル形式で格納されるドキュメントをさせます。|  
|[COleDocument::GetInPlaceActiveItem](#getinplaceactiveitem)|現在の実行中である OLE アイテムを返します。|  
|[COleDocument::GetNextClientItem](#getnextclientitem)|反復処理するためには、クライアントの次の項目を取得します。|  
|[COleDocument::GetNextItem](#getnextitem)|反復処理するためには、ドキュメントの次の項目を取得します。|  
|[COleDocument::GetNextServerItem](#getnextserveritem)|反復処理するためには、サーバーの次の項目を取得します。|  
|[COleDocument::GetPrimarySelectedItem](#getprimaryselecteditem)|ドキュメント内には、プライマリの選択した OLE アイテムを返します。|  
|[COleDocument::GetStartPosition](#getstartposition)|初期のイテレーションを開始する位置を取得します。|  
|[COleDocument::HasBlankItems](#hasblankitems)|ドキュメント内の空のアイテムを確認します。|  
|[COleDocument::OnShowViews](#onshowviews)|表示と非表示のドキュメントはときに呼び出されます。|  
|[COleDocument::RemoveItem](#removeitem)|ドキュメントが管理しているアイテムの一覧から項目を削除します。|  
|[COleDocument::UpdateModifiedFlag](#updatemodifiedflag)|含まれている OLE アイテムのいずれかが変更された場合の変更としては、ドキュメントをマークします。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleDocument::OnEditChangeIcon](#oneditchangeicon)|アイコンの変更 メニューのコマンドのイベントを処理します。|  
|[COleDocument::OnEditConvert](#oneditconvert)|1 つの型から別の埋め込みまたはリンクされているオブジェクトの変換を処理します。|  
|[COleDocument::OnEditLinks](#oneditlinks)|[編集] メニューのリンク コマンドのイベントを処理します。|  
|[COleDocument::OnFileSendMail](#onfilesendmail)|ドキュメントを添付してメール メッセージを送信します。|  
|[COleDocument::OnUpdateEditChangeIcon](#onupdateeditchangeicon)|アイコンの編集/変更メニュー オプションのコマンドの UI を更新するためにフレームワークによって呼び出されます。|  
|[COleDocument::OnUpdateEditLinksMenu](#onupdateeditlinksmenu)|コマンド UI/リンクの編集 メニューのオプションを更新するためにフレームワークによって呼び出されます。|  
|[COleDocument::OnUpdateObjectVerbMenu](#onupdateobjectverbmenu)|編集コマンド UI を更新するためにフレームワークによって呼び出される/ *ObjectName*メニュー オプションとからアクセスされる動詞サブメニュー/ *ObjectName*します。|  
|[COleDocument::OnUpdatePasteLinkMenu](#onupdatepastelinkmenu)|メニュー オプションを選択して貼り付けのコマンドの UI を更新するためにフレームワークによって呼び出されます。|  
|[COleDocument::OnUpdatePasteMenu](#onupdatepastemenu)|貼り付けのメニュー オプションのコマンドの UI を更新するためにフレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 `COleDocument`派生した**CDocument**、これにより、OLE アプリケーションを Microsoft Foundation Class ライブラリによって提供されるドキュメント/ビュー アーキテクチャを使用します。  
  
 `COleDocument`コレクションとして、ドキュメントを扱う[CDocItem](../../mfc/reference/cdocitem-class.md) OLE アイテムを処理するオブジェクト。 コンテナーとサーバーの両方のアプリケーションでは、自分のドキュメントは、OLE アイテムを保持できる必要がありますので、このようなアーキテクチャが必要です。 [実際](../../mfc/reference/coleserveritem-class.md)と[COleClientItem](../../mfc/reference/coleclientitem-class.md)から派生した両方のクラス`CDocItem`アプリケーションと OLE アイテム間の相互作用を管理します。  
  
 単純なコンテナー アプリケーションを作成している場合からドキュメント クラスを派生させる`COleDocument`します。 ドキュメントが含まれている埋め込みアイテムへのリンクをサポートしているコンテナー アプリケーションを作成している場合からドキュメント クラスを派生させる[直接](../../mfc/reference/colelinkingdoc-class.md)します。 アプリケーションまたは組み合わせのコンテナー/サーバーのサーバーを作成する場合からドキュメント クラスを派生させる[COleServerDoc](../../mfc/reference/coleserverdoc-class.md)します。 `COleLinkingDoc``COleServerDoc`から派生した`COleDocument`ので、これらのクラスで使用できるすべてのサービスを継承する、`COleDocument`と**CDocument**します。  
  
 使用する`COleDocument`クラスの派生、およびアプリケーションの非 OLE データと埋め込みまたはリンクされた項目を管理する機能を追加します。 定義する場合`CDocItem`-をアプリケーションのネイティブのデータを格納するクラスを派生によって定義された既定の実装を使用する`COleDocument`OLE と非 OLE データの両方を格納します。 OLE アイテムとは切り離して、非 OLE データを格納するための独自のデータ構造を設計することもできます。 詳細については、記事を参照してください[コンテナー: 複合ファイル](../../mfc/containers-compound-files.md).。  
  
 **CDocument**メール サポート (MAPI) が存在する場合、メールを使用して、ドキュメントの送信をサポートします。 `COleDocument`更新が[OnFileSendMail](#onfilesendmail)複合ドキュメントを正しく処理します。 詳細については、記事を参照してください[MAPI](../../mfc/mapi.md)と[MFC での MAPI サポート](../../mfc/mapi-support-in-mfc.md).。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `COleDocument`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="a-nameadditema--coledocumentadditem"></a><a name="additem"></a>COleDocument::AddItem  
 この関数では、ドキュメントに項目を追加します。  
  
```  
virtual void AddItem(CDocItem* pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 追加されるドキュメントの項目へのポインター。  
  
### <a name="remarks"></a>コメント  
 呼び出された場合に、この関数を明示的に呼び出す必要はありません、`COleClientItem`または`COleServerItem`ドキュメントへのポインターを受け取るコンス トラクターです。  
  
##  <a name="a-nameapplyprintdevicea--coledocumentapplyprintdevice"></a><a name="applyprintdevice"></a>COleDocument::ApplyPrintDevice  
 埋め込まれているすべての出力先のデバイスを変更するには、この関数を呼び出す[COleClientItem](../../mfc/reference/coleclientitem-class.md)アプリケーションのコンテナー ドキュメント内の項目。  
  
```  
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);  
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptd`  
 ポインター、 **DVTARGETDEVICE**データ構造は、新しい出力先のデバイスに関する情報が含まれています。 できる**NULL**します。  
  
 `ppd`  
 ポインター、 **PRINTDLG**新しい出力先のデバイスに関する情報を含むデータ構造体。 できる**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、すべてのアイテムの出力先のデバイスの更新が、それらの項目のプレゼンテーション キャッシュは更新されません。 アイテムのプレゼンテーションのキャッシュを更新するには、呼び出す[COleClientItem::UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink)します。  
  
 この関数に対する引数には、ターゲット デバイスを識別するために使用して OLE 情報が含まれます。 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843)構造体には、Windows に共通の印刷 ダイアログ ボックスを初期化するために使用する情報が含まれています。 ユーザーがダイアログ ボックスを閉じた後、Windows は、この構造体でユーザーの選択に関する情報を返します。 `m_pd`のメンバー、 [CPrintDialog](../../mfc/reference/cprintdialog-class.md)オブジェクトが、 **PRINTDLG**構造体。  
  
 詳細については、次を参照してください。、 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 詳細については、次を参照してください。、 [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namecoledocumenta--coledocumentcoledocument"></a><a name="coledocument"></a>COleDocument::COleDocument  
 `COleDocument` オブジェクトを構築します。  
  
```  
COleDocument();
```  
  
##  <a name="a-nameenablecompoundfilea--coledocumentenablecompoundfile"></a><a name="enablecompoundfile"></a>COleDocument::EnableCompoundFile  
 複合ファイル形式を使用してドキュメントを格納する場合は、この関数を呼び出します。  
  
```  
void EnableCompoundFile(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnable`  
 複合ファイルのサポートを有効または無効になっているかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 これは構造化ストレージとも呼ばれます。 通常のコンス トラクターからこの関数を呼び出す、 `COleDocument`-クラスを派生します。 複合ドキュメントの詳細については、記事を参照してください[コンテナー: 複合ファイル](../../mfc/containers-compound-files.md).。  
  
 このメンバー関数が呼び出されない場合は、構造化されていない (「フラット」) ファイル形式でドキュメントに格納されています。  
  
 複合ファイルのサポートを有効になっているまたはドキュメントで無効にすると、ドキュメントの有効期間中に、設定を変更できません必要があります。  
  
##  <a name="a-namegetinplaceactiveitema--coledocumentgetinplaceactiveitem"></a><a name="getinplaceactiveitem"></a>COleDocument::GetInPlaceActiveItem  
 識別されるビューを含むフレーム ウィンドウ内の場所に項目を OLE を取得するには、この関数の呼び出しが現在アクティブ`pWnd`します。  
  
```  
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 コンテナーのドキュメントを表示するウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 1 つ、インプレース アクティブ OLE アイテムへのポインター**NULL**かどうか項目がない OLE 現在「インプレース アクティブ」状態にします。  
  
##  <a name="a-namegetnextclientitema--coledocumentgetnextclientitem"></a><a name="getnextclientitem"></a>COleDocument::GetNextClientItem  
 この関数へのアクセス、文書内のクライアント アイテムの各繰り返しを呼び出します。  
  
```  
COleClientItem* GetNextClientItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 参照、**位置**値のセットを前回呼び出したときを`GetNextClientItem`; 初期値は、`GetStartPosition`メンバー関数。  
  
### <a name="return-value"></a>戻り値  
 ドキュメントでは、次のクライアント アイテムへのポインターまたは**NULL**クライアント項目がある場合。  
  
### <a name="remarks"></a>コメント  
 値は、各呼び出しの後に`pos`したりクライアント アイテムとは限りませんが、ドキュメントの次の項目に設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer&#1;](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]  
  
##  <a name="a-namegetnextitema--coledocumentgetnextitem"></a><a name="getnextitem"></a>COleDocument::GetNextItem  
 この関数では、各ドキュメント内のアイテムにアクセスするには、繰り返しです。  
  
```  
virtual CDocItem* GetNextItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 参照、**位置**値のセットを前回呼び出したときを`GetNextItem`; 初期値は、`GetStartPosition`メンバー関数。  
  
### <a name="return-value"></a>戻り値  
 指定した位置にあるドキュメント項目へのポインター。  
  
### <a name="remarks"></a>コメント  
 値は、各呼び出しの後に`pos`に設定されている、**位置**ドキュメントの次の項目の値。 取得した要素がドキュメントの新しい値の最後の要素である場合`pos`は**NULL**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer&#2;](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]  
  
##  <a name="a-namegetnextserveritema--coledocumentgetnextserveritem"></a><a name="getnextserveritem"></a>COleDocument::GetNextServerItem  
 この関数へのアクセス サーバーのアイテム、ドキュメント内の各繰り返しを呼び出します。  
  
```  
COleServerItem* GetNextServerItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 参照、**位置**値のセットを前回呼び出したときを`GetNextServerItem`; 初期値は、`GetStartPosition`メンバー関数。  
  
### <a name="return-value"></a>戻り値  
 このドキュメントでは、次のサーバー項目へのポインターまたは**NULL** server 項目がある場合。  
  
### <a name="remarks"></a>コメント  
 値は、各呼び出しの後に`pos`がまたはサーバーのアイテムとは限りませんが、ドキュメントの次の項目に設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleServer&#2;](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]  
  
##  <a name="a-namegetprimaryselecteditema--coledocumentgetprimaryselecteditem"></a><a name="getprimaryselecteditem"></a>COleDocument::GetPrimarySelectedItem  
 指定したビューで現在選択されている OLE アイテムを取り出すためにフレームワークによって呼び出されます。  
  
```  
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```  
  
### <a name="parameters"></a>パラメーター  
 `pView`  
 ドキュメントを表示するアクティブなビュー オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 選択されている、1 つの OLE アイテムへのポインター**NULL** OLE アイテムが選択されていないまたは複数のいずれかを選択します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、保持されている OLE の一覧に&1; つ選択したアイテムのアイテムを検索し、ポインターを返します。 選択すると、項目がないかどうか、または複数の項目が選択されている、関数を返します**NULL**します。 オーバーライドする必要があります、`CView::IsSelected`この機能が動作するようにビュー クラスのメンバー関数。 OLE アイテムを格納する、独自のメソッドがある場合は、この関数をオーバーライドします。  
  
##  <a name="a-namegetstartpositiona--coledocumentgetstartposition"></a><a name="getstartposition"></a>COleDocument::GetStartPosition  
 この関数では、ドキュメント内の最初の項目の位置を取得します。  
  
```  
virtual POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**ドキュメントの項目を反復処理を開始するために使用される値**NULL**ドキュメントにアイテムがありません。  
  
### <a name="remarks"></a>コメント  
 返された値を渡す`GetNextItem`、 `GetNextClientItem`、または`GetNextServerItem`です。  
  
##  <a name="a-namehasblankitemsa--coledocumenthasblankitems"></a><a name="hasblankitems"></a>COleDocument::HasBlankItems  
 この関数では、ドキュメントにブランク アイテムが含まれるかどうかを判断します。  
  
```  
BOOL HasBlankItems() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメントには、ブランク アイテムが含まれている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 空のアイテムは、1 つの四角形は空です。  
  
##  <a name="a-nameoneditchangeicona--coledocumentoneditchangeicon"></a><a name="oneditchangeicon"></a>COleDocument::OnEditChangeIcon  
 OLE の [アイコンの変更] ダイアログ ボックスを表示し、ダイアログ ボックスで、ユーザーが選択したアイコンに現在選択されている OLE アイテムを表すアイコンを変更します。  
  
```  
afx_msg void OnEditChangeIcon();
```  
  
### <a name="remarks"></a>コメント  
 `OnEditChangeIcon`作成し、起動、`COleChangeIconDialog`アイコンの変更 ダイアログ ボックス。  
  
##  <a name="a-nameoneditconverta--coledocumentoneditconvert"></a><a name="oneditconvert"></a>COleDocument::OnEditConvert  
 OLE の 変換 ダイアログ ボックスが表示されますに変換したりに従ってユーザーの選択 ダイアログ ボックスで現在選択されている OLE アイテムをアクティブにできます。  
  
```  
afx_msg void OnEditConvert();
```  
  
### <a name="remarks"></a>コメント  
 `OnEditConvert`作成し、起動、`COleConvertDialog`変換 ダイアログ ボックス。  
  
 変換の例では、ワードパッドのドキュメントに、Microsoft Word 文書を変換です。  
  
##  <a name="a-nameoneditlinksa--coledocumentoneditlinks"></a><a name="oneditlinks"></a>COleDocument::OnEditLinks  
 [リンク] ダイアログ ボックスが表示されます。  
  
```  
afx_msg void OnEditLinks();
```  
  
### <a name="remarks"></a>コメント  
 `OnEditLinks`作成し、起動、`COleLinksDialog`リンク ダイアログ ボックスをユーザーがリンクされたオブジェクトを変更できるようにします。  
  
##  <a name="a-nameonfilesendmaila--coledocumentonfilesendmail"></a><a name="onfilesendmail"></a>COleDocument::OnFileSendMail  
 常駐しているメール ホストを介してメッセージ (存在する場合) に送信ドキュメントの添付ファイルとしてします。  
  
```  
afx_msg void OnFileSendMail();
```  
  
### <a name="remarks"></a>コメント  
 `OnFileSendMail`呼び出し`OnSaveDocument`(保存) は、電子メールで送信し、一時ファイルに新規または変更されたドキュメントをシリアル化します。 ドキュメントが変更されていない場合は、一時ファイルは必要ありません。オリジナルが送信されます。 `OnFileSendMail`MAPI32 を読み込みます。DLL が読み込まれていない場合。  
  
 実装とは異なり`OnFileSendMail`の**CDocument**、この関数は、複合ファイルを正しく処理されます。  
  
 詳細については、次を参照してください、 [MAPI トピック](../../mfc/mapi.md)と[MFC での MAPI サポート](../../mfc/mapi-support-in-mfc.md)記事.。  
  
##  <a name="a-nameonshowviewsa--coledocumentonshowviews"></a><a name="onshowviews"></a>COleDocument::OnShowViews  
 フレームワークは、状態の変更、ドキュメントの表示/非表示の後にこの関数を呼び出します。  
  
```  
virtual void OnShowViews(BOOL bVisible);
```  
  
### <a name="parameters"></a>パラメーター  
 `bVisible`  
 ドキュメントが表示または非表示になるかどうかを示します。  
  
### <a name="remarks"></a>コメント  
 この関数の既定のバージョンでは、何も行いません。 オーバーライド場合は、アプリケーションが、ドキュメントの表示/非表示が変更されたときに、特別な処理を実行する必要があります。  
  
##  <a name="a-nameonupdateeditchangeicona--coledocumentonupdateeditchangeicon"></a><a name="onupdateeditchangeicon"></a>COleDocument::OnUpdateEditChangeIcon  
 編集 メニュー、アイコンの変更 コマンドを更新するためにフレームワークによって呼び出されます。  
  
```  
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCmdUI`  
 ポインター、`CCmdUI`構造体を表す] メニューの [更新プログラムのコマンドを生成します。 更新ハンドラーは、**を有効にする**のメンバー関数、`CCmdUI`を構造化`pCmdUI`ユーザー インターフェイスを更新します。  
  
### <a name="remarks"></a>コメント  
 `OnUpdateEditChangeIcon`有効なアイコンが、ドキュメントに存在するかどうかによって、コマンドのユーザー インターフェイスを更新します。 動作を変更するには、この関数をオーバーライドします。  
  
##  <a name="a-nameonupdateeditlinksmenua--coledocumentonupdateeditlinksmenu"></a><a name="onupdateeditlinksmenu"></a>COleDocument::OnUpdateEditLinksMenu  
 [編集] メニューのリンクのコマンドを更新するため、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCmdUI`  
 ポインター、`CCmdUI`構造体を表す] メニューの [更新プログラムのコマンドを生成します。 更新ハンドラーは、**を有効にする**のメンバー関数、`CCmdUI`を構造化`pCmdUI`ユーザー インターフェイスを更新します。  
  
### <a name="remarks"></a>コメント  
 以降で、ドキュメント内の最初の OLE アイテム`OnUpdateEditLinksMenu`各項目にアクセスする、項目は、リンクし、リンクである場合、リンクのコマンドを有効にするかどうかをテストします。 動作を変更するには、この関数をオーバーライドします。  
  
##  <a name="a-nameonupdateobjectverbmenua--coledocumentonupdateobjectverbmenu"></a><a name="onupdateobjectverbmenu"></a>COleDocument::OnUpdateObjectVerbMenu  
 更新するためにフレームワークによって呼び出されます、 *ObjectName*コマンドを編集 メニューからアクセスされる動詞 サブメニューで、 *ObjectName*コマンド、場所*ObjectName* OLE オブジェクトの名前は、ドキュメントに埋め込まれます。  
  
```  
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCmdUI`  
 ポインター、`CCmdUI`構造体を表す] メニューの [更新プログラムのコマンドを生成します。 更新ハンドラーは、**を有効にする**のメンバー関数、`CCmdUI`を構造化`pCmdUI`ユーザー インターフェイスを更新します。  
  
### <a name="remarks"></a>コメント  
 `OnUpdateObjectVerbMenu`更新プログラム、 *ObjectName*ドキュメントでは有効なオブジェクトが存在するかどうかによって、コマンドのユーザー インターフェイスです。 オブジェクトが存在する場合、 *ObjectName* [編集] メニューのコマンドが有効にします。 このメニュー コマンドが選択されている動詞のサブメニューが表示されます。 動詞サブメニューには、編集やプロパティなどなどのオブジェクトで使用できるすべての動詞コマンドが含まれています。 動作を変更するには、この関数をオーバーライドします。  
  
##  <a name="a-nameonupdatepastelinkmenua--coledocumentonupdatepastelinkmenu"></a><a name="onupdatepastelinkmenu"></a>COleDocument::OnUpdatePasteLinkMenu  
 OLE のリンク アイテムをクリップボードから貼り付けできるかどうかを調べるためにフレームワークによって呼び出されます。  
  
```  
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCmdUI`  
 ポインター、`CCmdUI`構造体を表す] メニューの [更新プログラムのコマンドを生成します。 更新ハンドラーは、**を有効にする**のメンバー関数、`CCmdUI`を構造化`pCmdUI`ユーザー インターフェイスを更新します。  
  
### <a name="remarks"></a>コメント  
 貼り付け コマンドが有効になっているか、アイテムがドキュメントに貼り付けできるかどうかによって無効になっています。  
  
##  <a name="a-nameonupdatepastemenua--coledocumentonupdatepastemenu"></a><a name="onupdatepastemenu"></a>COleDocument::OnUpdatePasteMenu  
 OLE 埋め込みアイテムをクリップボードから貼り付けできるかどうかを調べるためにフレームワークによって呼び出されます。  
  
```  
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCmdUI`  
 ポインター、`CCmdUI`構造体を表す] メニューの [更新プログラムのコマンドを生成します。 更新ハンドラーは、**を有効にする**のメンバー関数、`CCmdUI`を構造化`pCmdUI`ユーザー インターフェイスを更新します。  
  
### <a name="remarks"></a>コメント  
 [貼り付け] コマンドとボタンが有効になっているまたはアイテムがドキュメントに貼り付けできるかどうかによって無効になっています。  
  
##  <a name="a-nameremoveitema--coledocumentremoveitem"></a><a name="removeitem"></a>COleDocument::RemoveItem  
 ドキュメントから項目を削除するには、この関数を呼び出します。  
  
```  
virtual void RemoveItem(CDocItem* pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 削除するドキュメントの項目へのポインター。  
  
### <a name="remarks"></a>コメント  
 通常必要はありませんこの関数を明示的に呼び出すデストラクターによって呼び出される`COleClientItem`と`COleServerItem`です。  
  
##  <a name="a-nameupdatemodifiedflaga--coledocumentupdatemodifiedflag"></a><a name="updatemodifiedflag"></a>COleDocument::UpdateModifiedFlag  
 含まれている OLE アイテムのいずれかが変更された場合に変更されたドキュメントをマークするには、この関数を呼び出します。  
  
```  
virtual void UpdateModifiedFlag();
```  
  
### <a name="remarks"></a>コメント  
 これにより、ドキュメントのネイティブのデータが変更されていない場合でもを閉じる前に、ドキュメントの保存先のユーザー入力を求めるフレームワークことができます。  
  
## <a name="see-also"></a>関連項目  
 [MFC のサンプルのコンテナー](../../visual-cpp-samples.md)   
 [MFC サンプル MFCBIND](../../visual-cpp-samples.md)   
 [CDocument クラス](../../mfc/reference/cdocument-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




