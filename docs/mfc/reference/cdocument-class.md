---
title: "CDocument クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocument
dev_langs:
- C++
helpviewer_keywords:
- documents [C++], serialization
- files [C++], documents
- command handling, documents and
- documents [C++], document classes
- documents [C++], multiple views
- serialization [C++], documents and
- CDocument class
- command routing, documents and
- views [C++], document
- documents [C++], command routing
ms.assetid: e5a2891d-e1e1-4599-8c7e-afa9b4945446
caps.latest.revision: 21
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
ms.openlocfilehash: 4d64b95f77139d984b855e710f3951434e489dd5
ms.lasthandoff: 02/24/2017

---
# <a name="cdocument-class"></a>CDocument クラス
ユーザーが定義するドキュメント クラスの基本機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CDocument : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDocument::CDocument](#cdocument)|`CDocument` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDocument::AddView](#addview)|ビューをドキュメントにアタッチします。|  
|[CDocument::BeginReadChunks](#beginreadchunks)|チャンクの読み取りを初期化します。|  
|[CDocument::CanCloseFrame](#cancloseframe)|オーバーライド可能な高度なこのドキュメントを表示するフレーム ウィンドウを閉じる前に呼び出されます。|  
|[CDocument::ClearChunkList](#clearchunklist)|チャンクのリストをクリアします。|  
|[CDocument::ClearPathName](#clearpathname)|ドキュメント オブジェクトのパスをクリアします。|  
|[のに](#deletecontents)|ドキュメントのクリーンアップを実行するには、呼び出されます。|  
|[CDocument::FindChunk](#findchunk)|指定した GUID のチャンクを検索します。|  
|[CDocument::GetAdapter](#getadapter)|実装するオブジェクトへのポインターを返します`IDocument`インターフェイスです。|  
|[CDocument::GetDocTemplate](#getdoctemplate)|ドキュメントの種類を説明するドキュメント テンプレートへのポインターを返します。|  
|[CDocument::GetFile](#getfile)|必要なポインターを返す`CFile`オブジェクトです。|  
|[CDocument::GetFirstViewPosition](#getfirstviewposition)|最初の位置を返しますビューの一覧で。イテレーションを開始するために使用します。|  
|[CDocument::GetNextView](#getnextview)|ドキュメントに関連付けられているビューのリストを反復処理します。|  
|[CDocument::GetPathName](#getpathname)|ドキュメントのデータ ファイルのパスを返します。|  
|[CDocument::GetThumbnail](#getthumbnail)|サムネイルを表示するサムネイル プロバイダーで使用されるビットマップを作成するには、呼び出されます。|  
|[CDocument::GetTitle](#gettitle)|ドキュメントのタイトルを取得します。|  
|[CDocument::InitializeSearchContent](#initializesearchcontent)|検索ハンドラーの内容の検索を初期化するために呼び出されます。|  
|[CDocument::IsModified](#ismodified)|最後に保存されてから、ドキュメントが変更されたかどうかを示します。|  
|[CDocument::IsSearchAndOrganizeHandler](#issearchandorganizehandler)|指示するかどうかのこのインスタンス`CDocument`検索 >/documents/report1.rdl」の整理ハンドラーのオブジェクトが作成されました。|  
|[CDocument::LoadDocumentFromStream](#loaddocumentfromstream)|ストリームからドキュメント データを読み込むと呼ばれます。|  
|[CDocument::OnBeforeRichPreviewFontChanged](#onbeforerichpreviewfontchanged)|リッチ プレビューのフォントが変更される前に呼び出されます。|  
|[CDocument::OnChangedViewList](#onchangedviewlist)|ビューが追加またはドキュメントから削除した後に呼び出されます。|  
|[は](#onclosedocument)|ドキュメントを閉じると呼ばれます。|  
|[CDocument::OnCreatePreviewFrame](#oncreatepreviewframe)|リッチ プレビュー用のプレビュー枠を作成する必要があるときに、フレームワークによって呼び出されます。|  
|[CDocument::OnDocumentEvent](#ondocumentevent)|ドキュメントのイベントに応答フレームワークによって呼び出されます。|  
|[CDocument::OnDrawThumbnail](#ondrawthumbnail)|サムネイルのコンテンツを描画する派生クラスでは、このメソッドをオーバーライドします。|  
|[CDocument::OnLoadDocumentFromStream](#onloaddocumentfromstream)|ストリームからドキュメント データを読み込むことが必要な場合に、フレームワークによって呼び出されます。|  
|[CDocument::OnNewDocument](#onnewdocument)|新しいドキュメントを作成するには、呼び出されます。|  
|[CDocument::OnOpenDocument](#onopendocument)|既存のドキュメントを開くと呼ばれます。|  
|[CDocument::OnPreviewHandlerQueryFocus](#onpreviewhandlerqueryfocus)|プレビュー ハンドラーの GetFocus 関数を呼び出してから HWND を返すように指示します。|  
|[CDocument::OnPreviewHandlerTranslateAccelerator](#onpreviewhandlertranslateaccelerator)|プレビュー ハンドラーが実行されているプロセスのメッセージ ポンプから渡されたキーストロークを処理するプレビュー ハンドラーに指示します。|  
|[CDocument::OnRichPreviewBackColorChanged](#onrichpreviewbackcolorchanged)|リッチ プレビューの背景色が変更されたときに呼び出されます。|  
|[CDocument::OnRichPreviewFontChanged](#onrichpreviewfontchanged)|リッチ プレビューのフォントが変更されたときに呼び出されます。|  
|[CDocument::OnRichPreviewSiteChanged](#onrichpreviewsitechanged)|リッチ プレビューのサイトが変更されたときに呼び出されます。|  
|[CDocument::OnRichPreviewTextColorChanged](#onrichpreviewtextcolorchanged)|リッチ プレビュー テキストの色が変更されたときに呼び出されます。|  
|[単一](#onsavedocument)|ドキュメントをディスクに保存するには、呼び出されます。|  
|[CDocument::OnUnloadHandler](#onunloadhandler)|プレビュー ハンドラーがアンロードされるときに、フレームワークによって呼び出されます。|  
|[CDocument::PreCloseFrame](#precloseframe)|フレーム ウィンドウが閉じられる前に呼び出されます。|  
|[CDocument::ReadNextChunkValue](#readnextchunkvalue)|次のチャンク値を読み取ります。|  
|[CDocument::ReleaseFile](#releasefile)|他のアプリケーションで使用できるようにするファイルを解放します。|  
|[CDocument::RemoveChunk](#removechunk)|指定した GUID のチャンクを削除します。|  
|[CDocument::RemoveView](#removeview)|ドキュメントからビューをデタッチします。|  
|[CDocument::ReportSaveLoadException](#reportsaveloadexception)|オーバーライド可能な高度な開いているときに呼び出されますまたは保存操作は、例外のため完了できません。|  
|[に対して、順番](#savemodified)|オーバーライド可能な高度なドキュメントを保存するかどうかをユーザーに確認するには、呼び出されます。|  
|[CDocument::SetChunkValue](#setchunkvalue)|チャンク値を設定します。|  
|[CDocument::SetModifiedFlag](#setmodifiedflag)|最後に保存されてから、ドキュメントを変更したことを示すフラグを設定します。|  
|[CDocument::SetPathName](#setpathname)|ドキュメントで使用されるデータ ファイルのパスを設定します。|  
|[CDocument::SetTitle](#settitle)|ドキュメントのタイトルを設定します。|  
|[CDocument::UpdateAllViews](#updateallviews)|ドキュメントのすべてのビューが変更されたことを通知します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDocument::OnFileSendMail](#onfilesendmail)|ドキュメントを添付してメール メッセージを送信します。|  
|[CDocument::OnUpdateFileSendMail](#onupdatefilesendmail)|メールのサポートが存在する場合は、メール送信コマンドを有効にします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDocument::m_bGetThumbnailMode](#m_bgetthumbnailmode)|指定する`CDocument`の縮小表示 dllhost によってオブジェクトが作成されます。 チェックインする`CView::OnDraw`です。|  
|[CDocument::m_bPreviewHandlerMode](#m_bpreviewhandlermode)|指定する`CDocument`の prevhost によってオブジェクトが作成された`Rich Preview`します。 チェックインする`CView::OnDraw`です。|  
|[CDocument::m_bSearchMode](#m_bsearchmode)|指定する`CDocument`インデクサーまたはその他の検索アプリケーションによってオブジェクトが作成されます。|  
|[CDocument::m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|リッチ プレビュー ウィンドウの背景色を指定します。 この色は、ホストによって設定されます。|  
|[CDocument::m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|リッチ プレビュー ウィンドウの前景色を指定します。 この色は、ホストによって設定されます。|  
|[CDocument::m_lfRichPreviewFont](#m_lfrichpreviewfont)|リッチ プレビュー ウィンドウのテキストのフォントを指定します。 このフォントの情報は、ホストによって設定されます。|  
  
## <a name="remarks"></a>コメント  
 ドキュメントでは、ユーザーは、通常ファイルを開くコマンドを使用して開くし、名前を付けて保存 で保存されるデータの単位を表します。  
  
 **CDocument**ドキュメントの作成、読み込み、保存などの標準的な操作をサポートしています。 フレームワークによって定義されたインターフェイスを使用して、ドキュメントを操作する**CDocument**します。  
  
 アプリケーションのドキュメントの&1; つ以上の型をサポートできます。たとえば、アプリケーションでは、スプレッドシートやテキスト ドキュメントの両方をサポート可能性があります。 ドキュメントの種類によっても、関連するドキュメント テンプレートドキュメント テンプレートは、どのようなリソース (たとえば、メニューのアイコン、またはアクセラレータ テーブル) のドキュメントの種類の使用を指定します。 各ドキュメントには、それに関連するへのポインターが含まれています。`CDocTemplate`オブジェクトです。  
  
 ユーザーを使用するドキュメントと対話する、 [CView](../../mfc/reference/cview-class.md)それに関連付けられているオブジェクト。 フレーム ウィンドウにドキュメントのイメージをレンダリングし、ユーザー入力をドキュメント上で操作として解釈するビュー。 ドキュメントには、複数のビューが関連付けられていることができます。 ユーザーは、ドキュメントのウィンドウが開いたら、フレームワークはビューを作成し、ドキュメントにアタッチします。 ドキュメント テンプレートは、ドキュメントの種類を表示する使用ビューとフレームのウィンドウの種類を指定します。  
  
 ドキュメント、framework の標準の一部では、ルーティング コマンドし、その結果、名前を付けて保存 メニュー項目などの標準的なユーザー インターフェイス コンポーネントからコマンドを受信します。 ドキュメントでは、アクティブなビューで転送されたコマンドを受信します。 ドキュメントでは、特定のコマンドを処理しない場合は、それを管理するドキュメント テンプレートにコマンドを転送します。  
  
 ドキュメントのデータが変更されると、そのビューの各変更を反映させる必要があります。 **CDocument**提供、 [UpdateAllViews](#updateallviews)ビューが自身を再描画必要に応じて、このような変更のビューに通知するためのメンバー関数。 フレームワークには、閉じる前に、変更されたファイルを保存するユーザーもメッセージが表示されます。  
  
 一般的なアプリケーションでドキュメントを実装するには、次の操作を行う必要があります。  
  
-   クラスを派生**CDocument**ドキュメントの種類ごとにします。  
  
-   各ドキュメントのデータを格納するためのメンバー変数を追加します。  
  
-   読み取りと、ドキュメントのデータを変更するためのメンバー関数を実装します。 ドキュメントのビューとは、これらのメンバー関数の最も重要なユーザーです。  
  
-   オーバーライド、[指定](../../mfc/reference/cobject-class.md#serialize)文書のデータ ディスクとの間の読み取りし、書き込みをするドキュメント クラスのメンバー関数。  
  
 **CDocument**メール サポート (MAPI) が存在する場合、メールを使用して、ドキュメントの送信をサポートします。 記事を参照してください[MAPI](../../mfc/mapi.md)と[MFC での MAPI サポート](../../mfc/mapi-support-in-mfc.md)します。  
  
 詳細については**CDocument**を参照してください[シリアル化](../../mfc/serialization-in-mfc.md)、[ドキュメント/ビュー アーキテクチャに関するトピック](../../mfc/document-view-architecture.md)、および[ドキュメント/ビューの作成](../../mfc/document-view-creation.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocument`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="a-nameaddviewa--cdocumentaddview"></a><a name="addview"></a>CDocument::AddView  
 この関数では、ビューを文書に添付します。  
  
```  
void AddView(CView* pView);
```  
  
### <a name="parameters"></a>パラメーター  
 `pView`  
 追加するビューを指します。  
  
### <a name="remarks"></a>コメント  
 この関数は、ドキュメントに関連付けられているビューの一覧に、指定されたビューを追加します。また、関数は、このドキュメントに、ビューのドキュメントのポインターを設定します。 フレームワークは、新しく作成されたビュー オブジェクトをドキュメントにアタッチするときにこの関数を呼び出しますこれは、または分割ウィンドウを分割すると、新しいウィンドウの 新しいファイルを開く、またはコマンドを応答で発生します。  
  
 手動で作成して、ビューをアタッチする場合にのみ、この関数を呼び出します。 ドキュメントとビューを定義することによって接続フレームワークをできるように、通常、 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)ドキュメント クラス、ビュー クラスとフレーム ウィンドウ クラスに関連付けるオブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocViewSDI&#12;](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]  
  
##  <a name="a-namebeginreadchunksa--cdocumentbeginreadchunks"></a><a name="beginreadchunks"></a>CDocument::BeginReadChunks  
 チャンクの読み取りを初期化します。  
  
```  
virtual void BeginReadChunks ();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namecancloseframea--cdocumentcancloseframe"></a><a name="cancloseframe"></a>CDocument::CanCloseFrame  
 ドキュメントを表示するフレーム ウィンドウが閉じられる前に、フレームワークによって呼び出されます。  
  
```  
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFrame`  
 ドキュメントにアタッチされているビューのフレーム ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 フレーム ウィンドウを閉じるには安全である場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、その他のフレーム ウィンドウのドキュメントを表示するかを確認します。 指定したフレーム ウィンドウがドキュメントを表示する最後の&1; つの場合は、関数が変更された場合は、ドキュメントを保存するように求めるプロンプトを表示します。 フレーム ウィンドウが閉じられたときに特別な処理を実行する場合は、この関数をオーバーライドします。 これは、高度なオーバーライドします。  
  
##  <a name="a-namecdocumenta--cdocumentcdocument"></a><a name="cdocument"></a>CDocument::CDocument  
 構築、 **CDocument**オブジェクトです。  
  
```  
CDocument();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、ドキュメントの作成を行います。 オーバーライド、[でも実質的](#onnewdocument)ドキュメント単位での初期化を実行するメンバー関数をこれはシングル ドキュメント インターフェイス (SDI) アプリケーションで特に重要です。  
  
##  <a name="a-nameclearchunklista--cdocumentclearchunklist"></a><a name="clearchunklist"></a>CDocument::ClearChunkList  
 チャンクのリストをクリアします。  
  
```  
virtual void ClearChunkList ();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameclearpathnamea--cdocumentclearpathname"></a><a name="clearpathname"></a>CDocument::ClearPathName  
 ドキュメント オブジェクトのパスをクリアします。  
  
```  
virtual void ClearPathName();
```  
  
### <a name="remarks"></a>コメント  
 パスをオフにすると、`CDocument`オブジェクトにより、アプリケーションで、ドキュメントが次に保存されている場合、ユーザーに通知します。 これにより、**保存**コマンドのような動作が、**名前を付けて保存**コマンドです。  
  
##  <a name="a-namedeletecontentsa--cdocumentdeletecontents"></a><a name="deletecontents"></a>のに  
 破棄することがなく、文書のデータを削除するフレームワークによって呼び出され、 **CDocument**オブジェクト自体です。  
  
```  
virtual void DeleteContents();
```  
  
### <a name="remarks"></a>コメント  
 ドキュメントが破棄される直前に呼び出されます。 再利用される前に、ドキュメントが空であることを確認するが呼び出されます。 これは、ドキュメントを&1; つのみを使用して、SDI アプリケーションにとって特に重要です。作成または別のドキュメントを開くたびに、ドキュメントが再利用します。 編集すべてクリア またはドキュメントのデータをすべて削除するようなコマンドを実装するには、この関数を呼び出します。 この関数の既定の実装は、何も行いません。 ドキュメント内のデータを削除するには、この関数をオーバーライドします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&57;](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]  
  
##  <a name="a-namefindchunka--cdocumentfindchunk"></a><a name="findchunk"></a>CDocument::FindChunk  
 指定した GUID のチャンクを検索します。  
  
```  
virtual POSITION FindChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>パラメーター  
 `guid`  
 検索するチャンクの GUID を指定します。  
  
 `pid`  
 検索するには、チャンクの PID を指定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、内部のチャンク リスト内の位置。 それ以外の場合`NULL`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetadaptera--cdocumentgetadapter"></a><a name="getadapter"></a>CDocument::GetAdapter  
 実装するオブジェクトにポインターを返す、`IDocument`インターフェイスです。  
  
```  
virtual ATL::IDocument* GetAdapter();
```  
  
### <a name="return-value"></a>戻り値  
 実装するオブジェクトへのポインター、`IDocument`インターフェイスです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetdoctemplatea--cdocumentgetdoctemplate"></a><a name="getdoctemplate"></a>CDocument::GetDocTemplate  
 この関数では、このドキュメントの種類のドキュメント テンプレートへのポインターを取得します。  
  
```  
CDocTemplate* GetDocTemplate() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このドキュメントの種類のドキュメント テンプレートへのポインターまたは**NULL**ドキュメントがドキュメント テンプレートによって管理されていない場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&58;](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]  
  
##  <a name="a-namegetfilea--cdocumentgetfile"></a><a name="getfile"></a>CDocument::GetFile  
 ポインターを取得するには、このメンバー関数を呼び出す、`CFile`オブジェクトです。  
  
```  
virtual CFile* GetFile(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CFileException* pError);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFileName`  
 必要なファイルのパスを表す文字列。 相対パスまたは絶対パスがあります。  
  
 `pError`  
 操作の完了ステータスを示す既存のファイルの例外オブジェクトへのポインター。  
  
 `nOpenFlags`  
 共有とアクセス モードです。 ファイルを開くときに実行するアクションを指定します。 CFile コンス トラクターに示されているオプションを組み合わせて、[ほか](../../mfc/reference/cfile-class.md#cfile)ビットごとの OR を使用して、(|) 演算子。 1 つのアクセス許可と&1; つの共有オプションが必要です。**modeCreate**と**modeNoInherit**モードは省略可能です。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CFile`オブジェクトです。  
  
##  <a name="a-namegetfirstviewpositiona--cdocumentgetfirstviewposition"></a><a name="getfirstviewposition"></a>CDocument::GetFirstViewPosition  
 この関数では、ドキュメントに関連付けられているビューの一覧の最初のビューの位置を取得します。  
  
```  
virtual POSITION GetFirstViewPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**を反復処理に使用できる値、 [GetNextView](#getnextview)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&59;](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="a-namegetnextviewa--cdocumentgetnextview"></a><a name="getnextview"></a>CDocument::GetNextView  
 すべてのドキュメントのビューを反復処理するには、この関数を呼び出します。  
  
```  
virtual CView* GetNextView(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `rPosition`  
 参照、**位置**を以前の呼び出しによって返される値、`GetNextView`または[GetFirstViewPosition](#getfirstviewposition)メンバー関数。 この値である必要があります**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 指定されるビューへのポインター`rPosition`します。  
  
### <a name="remarks"></a>コメント  
 指定されるビューを返します`rPosition`し、設定`rPosition`に、**位置**一覧には、次のビューの値。 リスト内の最後は、取得したビュー`rPosition`に設定されている**NULL**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&59;](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="a-namegetpathnamea--cdocumentgetpathname"></a><a name="getpathname"></a>CDocument::GetPathName  
 この関数では、ドキュメントのディスク ファイルの完全修飾パスを取得します。  
  
```  
const CString& GetPathName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメントの完全修飾パス。 ドキュメントが保存されていないかに関連付けられているディスク ファイルがない場合、この文字列が空です。  
  
##  <a name="a-namegetthumbnaila--cdocumentgetthumbnail"></a><a name="getthumbnail"></a>CDocument::GetThumbnail  
 サムネイルを表示する縮小表示のプロバイダーによって使用されるビットマップを作成します。  
  
```  
virtual BOOL GetThumbnail(
    UINT cx,  
    HBITMAP* phbmp,  
    DWORD* pdwAlpha);
```  
  
### <a name="parameters"></a>パラメーター  
 `cx`  
 ビットマップの高さと幅を指定します。  
  
 `phbmp`  
 関数が成功した場合、ビットマップへのハンドルが含まれています。  
  
 `pdwAlpha`  
 関数が成功した場合は、アルファ チャネルの値を指定する DWORD が含まれています。  
  
### <a name="return-value"></a>戻り値  
 返します。`TRUE`しました。 そうしないと、サムネイルのビットマップが作成された場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegettitlea--cdocumentgettitle"></a><a name="gettitle"></a>CDocument::GetTitle  
 この関数では、ドキュメントのファイル名から派生した通常、ドキュメントのタイトルを取得します。  
  
```  
const CString& GetTitle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメントのタイトル。  
  
##  <a name="a-nameinitializesearchcontenta--cdocumentinitializesearchcontent"></a><a name="initializesearchcontent"></a>CDocument::InitializeSearchContent  
 検索ハンドラーの内容の検索を初期化するために呼び出されます。  
  
```  
virtual void InitializeSearchContent ();
```  
  
### <a name="remarks"></a>コメント  
 検索コンテンツを初期化する派生クラスでは、このメソッドをオーバーライドします。 コンテンツで区切られた文字列である必要があります「;」です。 たとえば、"ポイントです。四角形です。ole アイテム"です。  
  
##  <a name="a-nameismodifieda--cdocumentismodified"></a><a name="ismodified"></a>CDocument::IsModified  
 最後に保存されてから、ドキュメントが変更されたかどうかを判断するには、この関数を呼び出します。  
  
```  
virtual BOOL IsModified();
```  
  
### <a name="return-value"></a>戻り値  
 前回の保存後、ドキュメントが変更された場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="a-nameissearchandorganizehandlera--cdocumentissearchandorganizehandler"></a><a name="issearchandorganizehandler"></a>CDocument::IsSearchAndOrganizeHandler  
 通知するかどうかのこのインスタンス`CDocument`検索 >/documents/report1.rdl」の整理ハンドラー用に作成されました。  
  
```  
BOOL IsSearchAndOrganizeHandler() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します。`TRUE`場合のこのインスタンス`CDocument`検索 >/documents/report1.rdl」の整理ハンドラー用に作成されました。  
  
### <a name="remarks"></a>コメント  
 この関数が返す現在`TRUE`のプロセス サーバーの外に実装されている豊富なプレビュー ハンドラーに対してのみです。 (M_bPreviewHandlerMode、m_bSearchMode、m_bGetThumbnailMode) は、適切なフラグを設定するにはこの関数の戻り値をアプリケーション レベルで`TRUE`します。  
  
##  <a name="a-nameloaddocumentfromstreama--cdocumentloaddocumentfromstream"></a><a name="loaddocumentfromstream"></a>CDocument::LoadDocumentFromStream  
 ストリームからドキュメント データを読み込むと呼ばれます。  
  
```  
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,  
    DWORD dwGrfMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStream`  
 ストリームへのポインター。 このストリームは、シェルによって提供されます。  
  
 `dwGrfMode`  
 ストリームへのアクセス モード。  
  
### <a name="return-value"></a>戻り値  
 読み込み操作が成功すると、それ以外の場合の HRESULT エラー コードの場合は S_OK です。  
  
### <a name="remarks"></a>コメント  
 ストリームからデータを読み込む方法をカスタマイズする派生クラスでこのメソッドをオーバーライドすることができます。  
  
##  <a name="a-namembgetthumbnailmodea--cdocumentmbgetthumbnailmode"></a><a name="m_bgetthumbnailmode"></a>CDocument::m_bGetThumbnailMode  
 指定する、`CDocument`の縮小表示 dllhost によってオブジェクトが作成します。 チェックインする`CView::OnDraw`です。  
  
```  
BOOL m_bGetThumbnailMode;  
```  
  
### <a name="remarks"></a>コメント  
 `TRUE`サムネイルの dllhost でドキュメントが作成されたことを示します。  
  
##  <a name="a-namembpreviewhandlermodea--cdocumentmbpreviewhandlermode"></a><a name="m_bpreviewhandlermode"></a>CDocument::m_bPreviewHandlerMode  
 指定する、`CDocument`リッチ プレビュー用 prevhost によってオブジェクトが作成されます。 チェックインする`CView::OnDraw`です。  
  
```  
BOOL m_bPreviewHandlerMode;  
```  
  
### <a name="remarks"></a>コメント  
 `TRUE`リッチ プレビュー用 prevhost によってドキュメントが作成されたことを示します。  
  
##  <a name="a-namembsearchmodea--cdocumentmbsearchmode"></a><a name="m_bsearchmode"></a>CDocument::m_bSearchMode  
 指定する、`CDocument`インデクサーによって、または他の検索アプリケーションでオブジェクトが作成されました。  
  
```  
BOOL m_bSearchMode;  
```  
  
### <a name="remarks"></a>コメント  
 `TRUE`インデクサーによって、または他の検索アプリケーションでドキュメントが作成されたことを示します。  
  
##  <a name="a-namemclrrichpreviewbackcolora--cdocumentmclrrichpreviewbackcolor"></a><a name="m_clrrichpreviewbackcolor"></a>CDocument::m_clrRichPreviewBackColor  
 リッチ プレビュー ウィンドウの背景色を指定します。 この色は、ホストによって設定されます。  
  
```  
COLORREF m_clrRichPreviewBackColor;  
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namemclrrichpreviewtextcolora--cdocumentmclrrichpreviewtextcolor"></a><a name="m_clrrichpreviewtextcolor"></a>CDocument::m_clrRichPreviewTextColor  
 リッチ プレビュー ウィンドウの前景色を指定します。 この色は、ホストによって設定されます。  
  
```  
COLORREF m_clrRichPreviewTextColor;  
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namemlfrichpreviewfonta--cdocumentmlfrichpreviewfont"></a><a name="m_lfrichpreviewfont"></a>CDocument::m_lfRichPreviewFont  
 リッチ プレビュー ウィンドウのテキストのフォントを指定します。 このフォントの情報は、ホストによって設定されます。  
  
```  
CFont m_lfRichPreviewFont;  
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonbeforerichpreviewfontchangeda--cdocumentonbeforerichpreviewfontchanged"></a><a name="onbeforerichpreviewfontchanged"></a>CDocument::OnBeforeRichPreviewFontChanged  
 リッチ プレビューのフォントが変更される前に呼び出されます。  
  
```  
virtual void OnBeforeRichPreviewFontChanged();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonchangedviewlista--cdocumentonchangedviewlist"></a><a name="onchangedviewlist"></a>CDocument::OnChangedViewList  
 ビューが追加またはドキュメントから削除した後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnChangedViewList();
```  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装を確認するかどうか最後のビューが削除されている場合は、ドキュメントを削除します。 フレームワークを追加またはビューを削除するときに、特別な処理を実行する場合は、この関数をオーバーライドします。 たとえば、ビューを関連付けることがない場合にも開いたままにドキュメントを作成する場合は、この関数をオーバーライドします。  
  
##  <a name="a-nameonclosedocumenta--cdocumentonclosedocument"></a><a name="onclosedocument"></a>は  
 ドキュメントが閉じられると、通常、ファイルを閉じる コマンドの一部として、フレームワークによって呼び出されます。  
  
```  
virtual void OnCloseDocument();
```  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装、ドキュメントを表示するために使用されるフレームのすべてを破棄し、ビューを閉じ、ドキュメントの内容を消去およびを呼び出して、 [DeleteContents](#deletecontents)ドキュメントのデータを削除するメンバー関数。  
  
 フレームワーク ドキュメントの終了時に、特別なクリーンアップ処理を実行する場合は、この関数をオーバーライドします。 たとえば、ドキュメントは、データベースのレコードを表している場合、データベースを閉じるには、この関数をオーバーライドします。 この関数の基底クラスのバージョンは、オーバーライドから呼び出す必要があります。  
  
##  <a name="a-nameoncreatepreviewframea--cdocumentoncreatepreviewframe"></a><a name="oncreatepreviewframe"></a>CDocument::OnCreatePreviewFrame  
 リッチ プレビュー用のプレビュー枠を作成する必要があるときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnCreatePreviewFrame();
```  
  
### <a name="return-value"></a>戻り値  
 返します。`TRUE`フレームが正常に作成されている場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondocumenteventa--cdocumentondocumentevent"></a><a name="ondocumentevent"></a>CDocument::OnDocumentEvent  
 ドキュメントのイベントに応答フレームワークによって呼び出されます。  
  
```  
virtual void OnDocumentEvent(DocumentEvent deEvent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `deEvent`  
 イベントの型を記述する列挙型。  
  
### <a name="remarks"></a>コメント  
 複数のクラスがドキュメントのイベントの影響を与える可能性があります。 クラスの他にも影響を与えるドキュメント イベントを処理するため、このメソッドは、 [CDocument クラス](../../mfc/reference/cdocument-class.md)します。 現在のドキュメントのイベントに応答する必要があります唯一のクラスは、 [CDataRecoveryHandler クラス](../../mfc/reference/cdatarecoveryhandler-class.md)します。 `CDocument`クラスの効果を処理する上書き可能なその他の方法には、`CDocument`です。  
  
 次の表に、可能な値`deEvent`およびに対応するイベントです。  
  
|値|対応するイベント|  
|-----------|-------------------------|  
|`onAfterNewDocument`|新しいドキュメントが作成されました。|  
|`onAfterOpenDocument`|新しいドキュメントを開きました。|  
|`onAfterSaveDocument`|ドキュメントを保存します。|  
|`onAfterCloseDocument`|ドキュメントが閉じられました。|  
  
##  <a name="a-nameondrawthumbnaila--cdocumentondrawthumbnail"></a><a name="ondrawthumbnail"></a>CDocument::OnDrawThumbnail  
 縮小表示を描画する派生クラスでは、このメソッドをオーバーライドします。  
  
```  
virtual void OnDrawThumbnail(
    CDC& dc,  
    LPRECT lprcBounds);
```  
  
### <a name="parameters"></a>パラメーター  
 `dc`  
 デバイス コンテキストへの参照。  
  
 `lprcBounds`  
 縮小表示を描画する領域の外接する四角形を指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonfilesendmaila--cdocumentonfilesendmail"></a><a name="onfilesendmail"></a>CDocument::OnFileSendMail  
 常駐しているメール ホストを介してメッセージ (存在する場合) に送信ドキュメントの添付ファイルとしてします。  
  
```  
void OnFileSendMail();
```  
  
### <a name="remarks"></a>コメント  
 `OnFileSendMail`呼び出し[呼び出す必要はありません](#onsavedocument)(保存) は、電子メールで送信し、一時ファイルに新規または変更されたドキュメントをシリアル化します。 ドキュメントが変更されていない場合は、一時ファイルは必要ありません。オリジナルが送信されます。 `OnFileSendMail`MAPI32 を読み込みます。DLL が読み込まれていない場合。  
  
 特殊な実装`OnFileSendMail`の[COleDocument](../../mfc/reference/coledocument-class.md)複合ファイルを正しく処理されます。  
  
 **CDocument**メール サポート (MAPI) が存在する場合、メールを使用して、ドキュメントの送信をサポートします。 記事を参照してください[MAPI トピック](../../mfc/mapi.md)と[MFC での MAPI サポート](../../mfc/mapi-support-in-mfc.md)します。  
  
##  <a name="a-nameonloaddocumentfromstreama--cdocumentonloaddocumentfromstream"></a><a name="onloaddocumentfromstream"></a>CDocument::OnLoadDocumentFromStream  
 ドキュメント データをストリームから読み込むことが必要な場合に、フレームワークによって呼び出されます。  
  
```  
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,  
    DWORD grfMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStream`  
 受信ストリームへのポインター。  
  
 `grfMode`  
 ストリームへのアクセス モード。  
  
### <a name="return-value"></a>戻り値  
 負荷が正常に終了した場合は S_OKそれ以外の場合はエラー コード。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonnewdocumenta--cdocumentonnewdocument"></a><a name="onnewdocument"></a>CDocument::OnNewDocument  
 ファイルの新規作成 コマンドの一部として、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnNewDocument();
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメントが正常に初期化されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装、 [DeleteContents](#deletecontents)ドキュメントが空で、クリーンとして新しいドキュメントをマークすることを確認します。 新しいドキュメントのデータ構造を初期化するには、この関数をオーバーライドします。 この関数の基底クラスのバージョンは、オーバーライドから呼び出す必要があります。  
  
 SDI アプリケーションでファイルの新規作成 を選択すると、フレームワークは新しいレコードを作成するのではなく、既存のドキュメントを再初期化するのにこの関数を使用します。 マルチ ドキュメント インターフェイス (MDI) アプリケーションの新しいファイルを選択する、フレームワークは毎回、新しいドキュメントを作成しを初期化するには、この関数を呼び出します。 SDI アプリケーションで有効にする新しいコマンドのコンス トラクターではなく、この関数の中に初期化コードを配置する必要があります。  
  
 あるをケースがあることに注意してください`OnNewDocument`が&2; 回呼び出されます。 これは、ActiveX ドキュメント サーバーとして、ドキュメントが埋め込まれている場合に発生します。 関数は最初に呼び出される、`CreateInstance`メソッド (によって公開されている、 `COleObjectFactory`-派生クラス) と&2; 番目の時間によって、`InitNew`メソッド (によって公開されている、 `COleServerDoc`-派生クラス)。  
  
### <a name="example"></a>例  
 次の例では、別のドキュメント オブジェクトの初期化の方法を示します。  
  
 [!code-cpp[NVC_MFCDocView&#60;](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#61;](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&62;](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
##  <a name="a-nameonopendocumenta--cdocumentonopendocument"></a><a name="onopendocument"></a>CDocument::OnOpenDocument  
 ファイルを開く コマンドの一部として、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszPathName`  
 開かれているドキュメントのパスを指します。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、ドキュメントが正常に読み込まれました。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装は、指定したファイルを開き、 [DeleteContents](#deletecontents)ドキュメントが空であることを確認するメンバー関数を呼び出して[指定](../../mfc/reference/cobject-class.md#serialize)ファイルを読み取るための内容、およびクリーンとしてマークします。 アーカイブ機構やファイル メカニズム以外を使用する場合は、この関数をオーバーライドします。 たとえば、ドキュメントが別のファイルではなく、データベース内のレコードを表すアプリケーションを作成する場合があります。  
  
 フレームワークでこの関数を使用して、既存の再初期化する場合は、ユーザーがファイルを開くコマンドを選択中の SDI アプリケーション、 **CDocument**新しいレコードを作成するのではなく、オブジェクトです。 フレームワークの作成新しい場合は、ユーザーが、MDI アプリケーションでファイルを開く、 **CDocument**たびにオブジェクトを初期化するには、この関数を呼び出します。 SDI アプリケーションで有効にするファイルを開くコマンドのコンス トラクターではなく、この関数の中に初期化コードを配置する必要があります。  
  
### <a name="example"></a>例  
 次の例では、別のドキュメント オブジェクトの初期化の方法を示します。  
  
 [!code-cpp[NVC_MFCDocView&#60;](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#61;](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&62;](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&63;](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]  
  
##  <a name="a-nameonpreviewhandlerqueryfocusa--cdocumentonpreviewhandlerqueryfocus"></a><a name="onpreviewhandlerqueryfocus"></a>CDocument::OnPreviewHandlerQueryFocus  
 プレビュー ハンドラーを呼び出し元から取得した HWND を返すように指示、`GetFocus`関数です。  
  
```  
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `phwnd`  
 [out]このメソッドが戻るときに、呼び出しで返される HWND へのポインターを含む、`GetFocus`プレビュー ハンドラーのフォア グラウンド スレッドからの関数です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK を返します。または、それ以外の場合、エラー値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonpreviewhandlertranslateacceleratora--cdocumentonpreviewhandlertranslateaccelerator"></a><a name="onpreviewhandlertranslateaccelerator"></a>CDocument::OnPreviewHandlerTranslateAccelerator  
 プレビュー ハンドラーが実行されているプロセスのメッセージ ポンプから渡されたキーストロークを処理するプレビュー ハンドラーに指示します。  
  
```  
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```  
  
### <a name="parameters"></a>パラメーター  
 `pmsg`  
 [in]ウィンドウ メッセージへのポインター。  
  
### <a name="return-value"></a>戻り値  
 キー入力メッセージは、プレビュー ハンドラーで処理できる、ハンドラーはそれを処理し、S_OK を返します。 使用してホストには、プレビュー ハンドラーでは、キー入力メッセージを処理できない場合`IPreviewHandlerFrame::TranslateAccelerator`します。 ホストは、メッセージを処理する場合、このメソッドは、S_OK を返します。 ホストにメッセージが処理されない場合、このメソッドは S_FALSE を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonrichpreviewbackcolorchangeda--cdocumentonrichpreviewbackcolorchanged"></a><a name="onrichpreviewbackcolorchanged"></a>CDocument::OnRichPreviewBackColorChanged  
 リッチ プレビューの背景色が変更されたときに呼び出されます。  
  
```  
virtual void OnRichPreviewBackColorChanged();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonrichpreviewfontchangeda--cdocumentonrichpreviewfontchanged"></a><a name="onrichpreviewfontchanged"></a>CDocument::OnRichPreviewFontChanged  
 リッチ プレビューのフォントが変更されたときに呼び出されます。  
  
```  
virtual void OnRichPreviewFontChanged();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonrichpreviewsitechangeda--cdocumentonrichpreviewsitechanged"></a><a name="onrichpreviewsitechanged"></a>CDocument::OnRichPreviewSiteChanged  
 リッチ プレビューのサイトが変更されたときに呼び出されます。  
  
```  
virtual void OnRichPreviewSiteChanged();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonrichpreviewtextcolorchangeda--cdocumentonrichpreviewtextcolorchanged"></a><a name="onrichpreviewtextcolorchanged"></a>CDocument::OnRichPreviewTextColorChanged  
 リッチ プレビュー テキストの色が変更されたときに呼び出されます。  
  
```  
virtual void OnRichPreviewTextColorChanged();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonsavedocumenta--cdocumentonsavedocument"></a><a name="onsavedocument"></a>単一  
 ファイルの保存またはファイル名を付けてコマンドの一部として、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszPathName`  
 ファイルの保存先とする完全修飾パスを指します。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、ドキュメントが正常に保存されました。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装は、指定したファイルを開き[指定](../../mfc/reference/cobject-class.md#serialize)ドキュメントのデータを書き込むファイル、および、マークとしてドキュメントをクリーニングします。 フレームワークは、ドキュメントを保存するときに、特別な処理を実行する場合は、この関数をオーバーライドします。 たとえば、ドキュメントが別のファイルではなく、データベース内のレコードを表すアプリケーションを作成する場合があります。  
  
##  <a name="a-nameonunloadhandlera--cdocumentonunloadhandler"></a><a name="onunloadhandler"></a>CDocument::OnUnloadHandler  
 プレビュー ハンドラーが読み込まれるときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnUnloadHandler();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonupdatefilesendmaila--cdocumentonupdatefilesendmail"></a><a name="onupdatefilesendmail"></a>CDocument::OnUpdateFileSendMail  
 により、**判定**コマンドのメール サポート (MAPI) が存在するかどうか。  
  
```  
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCmdUI`  
 ポインター、 [CCmdUI](../../mfc/reference/ccmdui-class.md)オブジェクトに関連付けられている、**判定**コマンドです。  
  
### <a name="remarks"></a>コメント  
 それ以外の場合、関数は、削除、**判定**コマンドのメニューで、上記の区切り記号を含む、または必要に応じて項目のメニューの下です。 場合に、MAPI が有効になっている MAPI32 します。DLL は、パスにおよび、WIN の [メール] セクションできます。INI ファイル、MAPI =&1; です。 ほとんどのアプリケーションでは、[ファイル] メニューにこのコマンドを配置できます。  
  
 **CDocument**メール サポート (MAPI) が存在する場合、メールを使用して、ドキュメントの送信をサポートします。 記事を参照してください[MAPI トピック](../../mfc/mapi.md)と[MFC での MAPI サポート](../../mfc/mapi-support-in-mfc.md)します。  
  
##  <a name="a-nameprecloseframea--cdocumentprecloseframe"></a><a name="precloseframe"></a>CDocument::PreCloseFrame  
 フレーム ウィンドウが破棄される前に、このメンバー関数がフレームワークによって呼び出されます。  
  
```  
virtual void PreCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFrame`  
 ポインター、 [CFrameWnd](../../mfc/reference/cframewnd-class.md)を保持する、関連付けられている**CDocument**オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 カスタムのクリーンアップが、基本クラスも必ずオーバーライドできます。  
  
 既定値は`PreCloseFrame`何も**CDocument**します。 **CDocument**の派生クラス[COleDocument](../../mfc/reference/coledocument-class.md)と[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)このメンバー関数を使用します。  
  
##  <a name="a-namereadnextchunkvaluea--cdocumentreadnextchunkvalue"></a><a name="readnextchunkvalue"></a>CDocument::ReadNextChunkValue  
 次のチャンク値を読み取ります。  
  
```  
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppValue`  
 [out]関数から制御が戻るとき`ppValue`読み取られた値が含まれています。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namereleasefilea--cdocumentreleasefile"></a><a name="releasefile"></a>CDocument::ReleaseFile  
 このメンバー関数は、他のアプリケーションで使用を利用できるように、ファイルを解放するためにフレームワークによって呼び出されます。  
  
```  
virtual void ReleaseFile(
    CFile* pFile,  
    BOOL bAbort);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFile`  
 リリースされる CFile オブジェクトへのポインター。  
  
 `bAbort`  
 ファイルがいずれかを使用して解放されるかどうかを示す`CFile::Close`または`CFile::Abort`です。 **FALSE**を使用して解放する場合は、ファイル[先](../../mfc/reference/cfile-class.md#close)です。**TRUE**を使用して解放する場合は、ファイル[解放](../../mfc/reference/cfile-class.md#abort)します。  
  
### <a name="remarks"></a>コメント  
 場合`bAbort`は**TRUE**、`ReleaseFile`呼び出し`CFile::Abort`、され、ファイルを解放します。 `CFile::Abort`例外はスローしません。  
  
 場合`bAbort`は**FALSE**、`ReleaseFile`呼び出し`CFile::Close`され、ファイルを解放します。  
  
 ファイルが解放される前に、ユーザーによる操作を要求するには、この関数をオーバーライドします。  
  
##  <a name="a-nameremovechunka--cdocumentremovechunk"></a><a name="removechunk"></a>CDocument::RemoveChunk  
 指定した GUID のチャンクを削除します。  
  
```  
virtual void RemoveChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>パラメーター  
 `Guid`  
 削除するチャンクの GUID を指定します。  
  
 `Pid`  
 削除するチャンクの PID を指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameremoveviewa--cdocumentremoveview"></a><a name="removeview"></a>CDocument::RemoveView  
 ドキュメントからビューをデタッチするには、この関数を呼び出します。  
  
```  
void RemoveView(CView* pView);
```  
  
### <a name="parameters"></a>パラメーター  
 `pView`  
 削除されるビューへのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数は、ドキュメントに関連付けられているビューの一覧を指定されたビューを削除します。また、ビューのドキュメントのポインターを設定し**NULL**します。 フレーム ウィンドウが閉じているか、分割ウィンドウのウィンドウが閉じているときに、この関数は、フレームワークによって呼び出されます。  
  
 ビューを手動でデタッチされている場合にのみ、この関数を呼び出します。 ドキュメントとビューを定義することでデタッチ フレームワークをできるように、通常、 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)ドキュメント クラス、ビュー クラスとフレーム ウィンドウ クラスに関連付けるオブジェクト。  
  
 使用例を参照してください[AddView](#addview)実装のサンプルについてです。  
  
##  <a name="a-namereportsaveloadexceptiona--cdocumentreportsaveloadexception"></a><a name="reportsaveloadexception"></a>CDocument::ReportSaveLoadException  
 例外がスローされた場合に呼び出されます (通常、 [CFileException](../../mfc/reference/cfileexception-class.md)または[CArchiveException](../../mfc/reference/carchiveexception-class.md)) を保存またはドキュメントの読み込み中にします。  
  
```  
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,  
    CException* e,  
    BOOL bSaving,  
    UINT nIDPDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszPathName`  
 しようとしたドキュメントの名前を指すの保存または読み込みします。  
  
 *e*  
 スローされた例外を指します。 あります**NULL**します。  
  
 *bSaving*  
 どのような操作が実行中だったことを示すフラグします。ドキュメントが保存されている場合、0、ドキュメントの読み込み中の場合 0 以外の値。  
  
 `nIDPDefault`  
 関数により特定の&1; つ指定されていない場合に表示されるエラー メッセージの識別子。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、例外オブジェクトを検査し、具体的には、原因を説明するエラー メッセージを探します。 特定のメッセージが見つからない場合、または場合*e*は**NULL**で指定された一般的なメッセージ、`nIDPDefault`パラメーターを使用します。 この関数は、エラー メッセージを含むメッセージ ボックスを表示します。 その他のカスタマイズされたエラー メッセージを提供する場合は、この関数をオーバーライドします。 これは、高度なオーバーライドします。  
  
##  <a name="a-namesavemodifieda--cdocumentsavemodified"></a><a name="savemodified"></a>に対して、順番  
 変更後のドキュメントが終了する前に、フレームワークによって呼び出されます。  
  
```  
virtual BOOL SaveModified();
```  
  
### <a name="return-value"></a>戻り値  
 続行するには、ドキュメントを閉じるセーフである場合は 0 以外。ドキュメントは閉じていない場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装では、ユーザーに確認する、ドキュメントに変更を保存するかどうか行われている場合、メッセージ ボックスが表示されます。 プログラムには、別のプロンプトを表示する手順が必要な場合は、この関数をオーバーライドします。 これは、高度なオーバーライドします。  
  
##  <a name="a-namesetchunkvaluea--cdocumentsetchunkvalue"></a><a name="setchunkvalue"></a>CDocument::SetChunkValue  
 チャンク値を設定します。  
  
```  
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `pValue`  
 設定するチャンク値を指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetmodifiedflaga--cdocumentsetmodifiedflag"></a><a name="setmodifiedflag"></a>CDocument::SetModifiedFlag  
 ドキュメントの変更を行った後は、この関数を呼び出します。  
  
```  
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bModified`  
 ドキュメントが変更されているかどうかを示すフラグします。  
  
### <a name="remarks"></a>コメント  
 一貫してこの関数を呼び出すことでは、フレームワークがドキュメントを閉じる前に変更を保存するユーザーを求めることを確認します。 通常、既定値を使用する必要があります**TRUE**の`bModified`パラメーター。 クリーンにドキュメントを (変更なし) マークするには、値は、この関数を呼び出す**FALSE**します。  
  
##  <a name="a-namesetpathnamea--cdocumentsetpathname"></a><a name="setpathname"></a>CDocument::SetPathName  
 この関数では、ドキュメントのディスク ファイルの完全修飾パスを指定します。  
  
```  
virtual void SetPathName(
    LPCTSTR lpszPathName,  
    BOOL bAddToMRU = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszPathName`  
 ドキュメントのパスとして使用する文字列へのポインター。  
  
 `bAddToMRU`  
 ファイル名を追加するかどうか、最近使用した MRU ファイル リストを決定します。 場合**true の場合、**場合は、ファイル名が追加**FALSE**は追加されません。  
  
### <a name="remarks"></a>コメント  
 値に応じて`bAddToMRU`パスの追加、または、アプリケーションによって管理される最近使用したリストに追加されません。 いくつかのドキュメントがディスク ファイルに関連付けられていないことに注意してください。 オープンと保存のために、フレームワークで使用されるファイルの既定の実装をオーバーライドする場合にのみ、この関数を呼び出します。  
  
##  <a name="a-namesettitlea--cdocumentsettitle"></a><a name="settitle"></a>CDocument::SetTitle  
 この関数では、ドキュメントのタイトル (フレーム ウィンドウのタイトル バーに表示される文字列) を指定します。  
  
```  
virtual void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszTitle`  
 ドキュメントのタイトルとして使用する文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出すと、ドキュメントを表示するすべてのフレーム ウィンドウのタイトルが更新されます。  
  
##  <a name="a-nameupdateallviewsa--cdocumentupdateallviews"></a><a name="updateallviews"></a>CDocument::UpdateAllViews  
 ドキュメントが変更された後は、この関数を呼び出します。  
  
```  
void UpdateAllViews(
    CView* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSender`  
 ドキュメントを変更するビューへのポインターまたは**NULL**場合、すべてのビューを更新します。  
  
 `lHint`  
 変更に関する情報が含まれています。  
  
 `pHint`  
 変更に関する情報を格納するオブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 呼び出した後は、この関数を呼び出す必要があります、 [SetModifiedFlag](#setmodifiedflag)メンバー関数。 この関数で指定されるビューを除く、文書に添付された各ビューに通知`pSender`ドキュメントが変更されています。 通常このから関数を呼び出す、ビュー クラスをユーザーには、ビューを使用して、ドキュメントが変更された後です。  
  
 この関数は、 [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate)送信以外、ドキュメントのビューの各メンバー関数を表示する受け渡し`pHint`と`lHint`です。 ドキュメントに加えられた変更はビューに情報を渡すには、これらのパラメーターを使用します。 使用して情報をエンコードする`lHint`定義することや、 [CObject](../../mfc/reference/cobject-class.md)-派生したクラスを変更についての情報を格納および使用するこのクラスのオブジェクトを渡す`pHint`します。 オーバーライド、`CView::OnUpdate`でメンバー関数、 [CView](../../mfc/reference/cview-class.md)に渡された情報に基づいて、ビューの表示の更新を最適化するためにクラスを派生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&64;](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC のサンプルは](../../visual-cpp-samples.md)   
 [MFC サンプル SNAPVW](../../visual-cpp-samples.md)   
 [MFC サンプル NPP](../../visual-cpp-samples.md)   
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [CView クラス](../../mfc/reference/cview-class.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)

