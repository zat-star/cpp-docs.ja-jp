---
title: "COleServerDoc クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleServerDoc
- AFXOLE/COleServerDoc
- AFXOLE/COleServerDoc::COleServerDoc
- AFXOLE/COleServerDoc::ActivateDocObject
- AFXOLE/COleServerDoc::ActivateInPlace
- AFXOLE/COleServerDoc::DeactivateAndUndo
- AFXOLE/COleServerDoc::DiscardUndoState
- AFXOLE/COleServerDoc::GetClientSite
- AFXOLE/COleServerDoc::GetEmbeddedItem
- AFXOLE/COleServerDoc::GetItemClipRect
- AFXOLE/COleServerDoc::GetItemPosition
- AFXOLE/COleServerDoc::GetZoomFactor
- AFXOLE/COleServerDoc::IsDocObject
- AFXOLE/COleServerDoc::IsEmbedded
- AFXOLE/COleServerDoc::IsInPlaceActive
- AFXOLE/COleServerDoc::NotifyChanged
- AFXOLE/COleServerDoc::NotifyClosed
- AFXOLE/COleServerDoc::NotifyRename
- AFXOLE/COleServerDoc::NotifySaved
- AFXOLE/COleServerDoc::OnDeactivate
- AFXOLE/COleServerDoc::OnDeactivateUI
- AFXOLE/COleServerDoc::OnDocWindowActivate
- AFXOLE/COleServerDoc::OnResizeBorder
- AFXOLE/COleServerDoc::OnShowControlBars
- AFXOLE/COleServerDoc::OnUpdateDocument
- AFXOLE/COleServerDoc::RequestPositionChange
- AFXOLE/COleServerDoc::SaveEmbedding
- AFXOLE/COleServerDoc::ScrollContainerBy
- AFXOLE/COleServerDoc::UpdateAllItems
- AFXOLE/COleServerDoc::CreateInPlaceFrame
- AFXOLE/COleServerDoc::DestroyInPlaceFrame
- AFXOLE/COleServerDoc::GetDocObjectServer
- AFXOLE/COleServerDoc::OnClose
- AFXOLE/COleServerDoc::OnExecOleCmd
- AFXOLE/COleServerDoc::OnFrameWindowActivate
- AFXOLE/COleServerDoc::OnGetEmbeddedItem
- AFXOLE/COleServerDoc::OnReactivateAndUndo
- AFXOLE/COleServerDoc::OnSetHostNames
- AFXOLE/COleServerDoc::OnSetItemRects
- AFXOLE/COleServerDoc::OnShowDocument
dev_langs:
- C++
helpviewer_keywords:
- servers, OLE
- OLE server applications, managing server documents
- container/server applications
- OLE server documents
- COleServerDoc class
- server documents, OLE
- OLE containers, server documents
ms.assetid: a9cdd96a-e0ac-43bb-9203-2c29237e965c
caps.latest.revision: 24
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: db50c2a5709fbc07d0e0db99a4cffc733c4b6ead
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="coleserverdoc-class"></a>COleServerDoc クラス
OLE サーバー ドキュメントの基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleServerDoc::COleServerDoc](#coleserverdoc)|`COleServerDoc` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleServerDoc::ActivateDocObject](#activatedocobject)|関連付けられている DocObject ドキュメントをアクティブにします。|  
|[COleServerDoc::ActivateInPlace](#activateinplace)|埋め込み先編集用にドキュメントをアクティブにします。|  
|[COleServerDoc::DeactivateAndUndo](#deactivateandundo)|サーバーのユーザー インターフェイスを無効になります。|  
|[COleServerDoc::DiscardUndoState](#discardundostate)|元に戻す状態情報を破棄します。|  
|[COleServerDoc::GetClientSite](#getclientsite)|基になるポインターを取得`IOleClientSite`インターフェイスです。|  
|[COleServerDoc::GetEmbeddedItem](#getembeddeditem)|ドキュメント全体を表す項目へのポインターを返します。|  
|[COleServerDoc::GetItemClipRect](#getitemcliprect)|埋め込み先編集のための現在のクリッピング四角形を返します。|  
|[COleServerDoc::GetItemPosition](#getitemposition)|埋め込み先編集のためのコンテナー アプリケーションのクライアント領域を基準と、現在の位置四角を返します。|  
|[先](#getzoomfactor)|ズームの倍率をピクセル単位で返します。|  
|[COleServerDoc::IsDocObject](#isdocobject)|ドキュメントが DocObject かを調べます。|  
|[COleServerDoc::IsEmbedded](#isembedded)|ドキュメントをコンテナー ドキュメントに埋め込まれているか実行されているスタンドアロンにするかどうかを示します。|  
|[COleServerDoc::IsInPlaceActive](#isinplaceactive)|返します。`TRUE`場合は、項目が現在の場所でアクティブ化します。|  
|[COleServerDoc::NotifyChanged](#notifychanged)|ユーザーがドキュメントを変更したコンテナーに通知します。|  
|[COleServerDoc::NotifyClosed](#notifyclosed)|ユーザーがドキュメントを閉じたことをコンテナーに通知します。|  
|[COleServerDoc::NotifyRename](#notifyrename)|ユーザーがドキュメントの名前を変更が、コンテナーに通知します。|  
|[COleServerDoc::NotifySaved](#notifysaved)|ユーザーがドキュメントを保存したことをコンテナーに通知します。|  
|[COleServerDoc::OnDeactivate](#ondeactivate)|アクティブなアイテムを非アクティブにするときに、フレームワークによって呼び出されます。|  
|[COleServerDoc::OnDeactivateUI](#ondeactivateui)|コントロールおよびインプレース アクティブ化用に作成されたその他のユーザー インターフェイス要素を破棄するためにフレームワークによって呼び出されます。|  
|[COleServerDoc::OnDocWindowActivate](#ondocwindowactivate)|コンテナーのドキュメントのフレーム ウィンドウがアクティブ化または非アクティブ化されたときに、フレームワークによって呼び出されます。|  
|[COleServerDoc::OnResizeBorder](#onresizeborder)|コンテナー アプリケーションのフレーム ウィンドウまたはドキュメント ウィンドウのサイズ変更時に、フレームワークによって呼び出されます。|  
|[COleServerDoc::OnShowControlBars](#onshowcontrolbars)|または、埋め込み先編集用のコントロール バーを非表示にフレームワークによって呼び出されます。|  
|[COleServerDoc::OnUpdateDocument](#onupdatedocument)|埋め込みアイテムをあるサーバーのドキュメントを保存すると、アイテムのコンテナーのコピーを更新するときに、フレームワークによって呼び出されます。|  
|[から](#requestpositionchange)|埋め込み先編集フレームの位置を変更します。|  
|[COleServerDoc::SaveEmbedding](#saveembedding)|ドキュメントの保存先コンテナー アプリケーションに通知します。|  
|[COleServerDoc::ScrollContainerBy](#scrollcontainerby)|コンテナーのドキュメントをスクロールします。|  
|[COleServerDoc::UpdateAllItems](#updateallitems)|ユーザーがドキュメントを変更したコンテナーに通知します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleServerDoc::CreateInPlaceFrame](#createinplaceframe)|埋め込み先編集のためのフレーム ウィンドウを作成するために、フレームワークによって呼び出されます。|  
|[COleServerDoc::DestroyInPlaceFrame](#destroyinplaceframe)|埋め込み先編集のフレーム ウィンドウを破棄するためにフレームワークによって呼び出されます。|  
|[COleServerDoc::GetDocObjectServer](#getdocobjectserver)|新しいを作成するには、この関数をオーバーライド`CDocObjectServer`オブジェクトし、このドキュメントが DocObject コンテナーであることを示します。|  
|[COleServerDoc::OnClose](#onclose)|コンテナーは、ドキュメントを閉じるに要求したときに、フレームワークによって呼び出されます。|  
|[COleServerDoc::OnExecOleCmd](#onexecolecmd)|指定のコマンドを実行するか、コマンドのヘルプを表示します。|  
|[COleServerDoc::OnFrameWindowActivate](#onframewindowactivate)|コンテナーのフレーム ウィンドウがアクティブ化または非アクティブ化されたときに、フレームワークによって呼び出されます。|  
|[COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)|取得すると呼ばれる、`COleServerItem`ドキュメント全体を表します。 埋め込みアイテムを取得するために使用します。 必要な実装です。|  
|[されて](#onreactivateandundo)|埋め込み先編集中に行われた変更を元に戻すために、フレームワークによって呼び出されます。|  
|[COleServerDoc::OnSetHostNames](#onsethostnames)|コンテナーは、埋め込みオブジェクトのウィンドウのタイトルを設定すると、フレームワークによって呼び出されます。|  
|[COleServerDoc::OnSetItemRects](#onsetitemrects)|コンテナー アプリケーションのウィンドウ内の埋め込み先編集フレーム ウィンドウの位置に、フレームワークによって呼び出されます。|  
|[COleServerDoc::OnShowDocument](#onshowdocument)|または、ドキュメントを非表示にフレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 サーバー ドキュメントを含めることができます[実際](../../mfc/reference/coleserveritem-class.md)埋め込みまたはリンクされた項目へのサーバー インターフェイスを表すオブジェクト。 埋め込みアイテムを編集するためのコンテナーが、サーバー アプリケーションを起動すると、アイテムが独自サーバー ドキュメントとして読み込まれます`COleServerDoc`オブジェクトには、1 つだけ含まれる`COleServerItem`ドキュメント全体で構成されるオブジェクト。 リンク アイテムを編集するためのコンテナーが、サーバー アプリケーションを起動すると、既存のドキュメントがディスクから読み込まれますリンクされた項目を示すために、ドキュメントの内容の一部が強調表示されます。  
  
 `COleServerDoc`オブジェクトの項目を含めることも、 [COleClientItem](../../mfc/reference/coleclientitem-class.md)クラスです。 これにより、コンテナー/サーバー アプリケーションを作成することができます。 フレームワークが正しく保存する機能を提供、`COleClientItem`項目を処理中に、`COleServerItem`オブジェクトです。  
  
 サーバー アプリケーションがリンクをサポートしていない場合をサーバー ドキュメントには常にドキュメントとして全体の埋め込みオブジェクトを表す&1; つだけのサーバー アイテムが含まれます。 サーバー アプリケーションはリンクもサポートしている場合、選択範囲をクリップボードにコピーするたびにサーバー項目を作成する必要があります。  
  
 使用する`COleServerDoc`、クラスの派生、および実装、 [OnGetEmbeddedItem](#ongetembeddeditem)メンバー関数は、埋め込みアイテムをサポートするようサーバーを使用します。 クラスを派生`COleServerItem`、ドキュメントに項目を実装し、そのクラスからのオブジェクトを返す`OnGetEmbeddedItem`します。  
  
 リンクされた項目をサポートするために`COleServerDoc`提供、 [OnGetLinkedItem](../../mfc/reference/colelinkingdoc-class.md#ongetlinkeditem)メンバー関数。 既定の実装を使用したり、ドキュメントの項目を管理する方法がある場合は、メソッドをオーバーライドすることができます。  
  
 1 つ必要がある`COleServerDoc`-サーバーの各種類のドキュメント、アプリケーションがサポートするクラスを派生します。 などの場合は、サーバー アプリケーションでは、ワークシートとグラフをサポートする必要があります&2; `COleServerDoc`-クラスを派生します。  
  
 サーバーの詳細については、記事を参照してください。[サーバー: サーバーを実装する](../../mfc/servers-implementing-a-server.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [直接](../../mfc/reference/colelinkingdoc-class.md)  
  
 `COleServerDoc`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="activatedocobject"></a>COleServerDoc::ActivateDocObject  
 関連付けられている DocObject ドキュメントをアクティブにします。  
  
```  
void ActivateDocObject();
```  
  
### <a name="remarks"></a>コメント  
 既定では、 `COleServerDoc` (DocObjects とも呼ばれる) アクティブなドキュメントをサポートしていません。 このサポートを有効にするには、「 [GetDocObjectServer](#getdocobjectserver)とクラス[関数](../../mfc/reference/cdocobjectserver-class.md)します。  
  
##  <a name="activateinplace"></a>COleServerDoc::ActivateInPlace  
 埋め込み先編集用に項目をアクティブにします。  
  
```  
BOOL ActivateInPlace();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合 0 の場合、つまり、アイテムが完全にオープンであります。  
  
### <a name="remarks"></a>コメント  
 この関数では、インプレース アクティブ化に必要なすべての操作を実行します。 で埋め込み先フレーム ウィンドウを作成が有効しアイテム サイズ、共通のメニューとその他のコントロールを設定、ビューにスクロールしておよびで埋め込み先フレーム ウィンドウにフォーカスを設定します。  
  
 この関数の既定の実装によって[COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow)します。 アプリケーションは、埋め込み (再生) などの他の動詞をサポートしている場合は、この関数を呼び出します。  
  
##  <a name="coleserverdoc"></a>COleServerDoc::COleServerDoc  
 構築、 `COleServerDoc` OLE システム Dll に接続しなくてもオブジェクトです。  
  
```  
COleServerDoc();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[COleLinkingDoc::Register](../../mfc/reference/colelinkingdoc-class.md#register) OLE に通信を開始します。 使用している場合[関数](../../mfc/reference/coletemplateserver-class.md)、アプリケーションで`COleLinkingDoc::Register`によって呼び出されます`COleLinkingDoc`の実装の`OnNewDocument`、 `OnOpenDocument`、および`OnSaveDocument`です。  
  
##  <a name="createinplaceframe"></a>COleServerDoc::CreateInPlaceFrame  
 フレームワークでは、埋め込み先編集のためのフレーム ウィンドウを作成するには、この関数を呼び出します。  
  
```  
virtual COleIPFrameWnd* CreateInPlaceFrame(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 コンテナー アプリケーションの親ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 埋め込み先フレーム ウィンドウへのポインターまたは**NULL**失敗した場合。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、ドキュメント テンプレートで指定した情報を使用して、フレームを作成します。 使用されるビューは、ドキュメント用に作成された最初のビューです。 このビューは一時的に元のフレームからデタッチされ、新しく作成されたフレームにアタッチされます。  
  
 これは、高度なオーバーライドします。  
  
##  <a name="deactivateandundo"></a>COleServerDoc::DeactivateAndUndo  
 アプリケーション サポートを元に戻すし、ユーザーが項目をアクティブ化したら、編集する前に元に戻す場合は、この関数を呼び出します。  
  
```  
BOOL DeactivateAndUndo();
```  
  
### <a name="return-value"></a>戻り値  
 正常に完了した場合はゼロ以外、それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 コンテナー アプリケーションを作成するには、Microsoft Foundation Class ライブラリを使用して、この関数の呼び出しを実行すると[COleClientItem::OnDeactivateAndUndo](../../mfc/reference/coleclientitem-class.md#ondeactivateandundo)に呼び出される非アクティブ化するサーバーのユーザー インターフェイスです。  
  
##  <a name="destroyinplaceframe"></a>COleServerDoc::DestroyInPlaceFrame  
 フレームワークでは、埋め込み先フレーム ウィンドウを破棄し、サーバー アプリケーションのドキュメント ウィンドウをインプレースでアクティブ化する前に状態に戻すには、この関数を呼び出します。  
  
```  
virtual void DestroyInPlaceFrame(COleIPFrameWnd* pFrameWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFrameWnd`  
 破棄される埋め込み先フレーム ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 これは、高度なオーバーライドします。  
  
##  <a name="discardundostate"></a>COleServerDoc::DiscardUndoState  
 ユーザーは、元に戻すことができない編集操作を実行する場合は、その元に戻す状態情報を破棄するコンテナー アプリケーションを強制するには、この関数を呼び出します。  
  
```  
BOOL DiscardUndoState();
```  
  
### <a name="return-value"></a>戻り値  
 正常に完了した場合はゼロ以外、それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 この関数は、元に戻すをサポートしているサーバーでは、それ以外の場合は使用できません元に戻す状態情報で利用できるリソースを解放しているため、提供されます。  
  
##  <a name="getclientsite"></a>COleServerDoc::GetClientSite  
 基になるポインターを取得`IOleClientSite`インターフェイスです。  
  
```  
LPOLECLIENTSITE GetClientSite() const;  
```  
  
### <a name="return-value"></a>戻り値  
 基になるポインターを取得[していること](http://msdn.microsoft.com/library/windows/desktop/ms693706)インターフェイスです。  
  
##  <a name="getdocobjectserver"></a>COleServerDoc::GetDocObjectServer  
 新しいを作成するには、この関数をオーバーライド`CDocObjectServer`項目し、ポインターを返します。  
  
```  
virtual CDocObjectServer* GetDocObjectServer(LPOLEDOCUMENTSITE pDocSite);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDocSite`  
 ポインター、`IOleDocumentSite`が、このドキュメントをサーバーに接続するインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CDocObjectServer`です。**NULL**場合は、操作に失敗しました。  
  
### <a name="remarks"></a>コメント  
 DocObject サーバーをアクティブにするタイミング、以外の戻り値**NULL**ポインターは、クライアントが DocObjects をサポートできることを示しています。 既定の実装**NULL**します。  
  
 DocObjects をサポートしているドキュメントの一般的な実装は単純に新しい割り当て`CDocObjectServer`オブジェクトし、呼び出し元に戻ります。 例:  
  
 [!code-cpp[NVC_MFCOleServer&#3;](../../mfc/codesnippet/cpp/coleserverdoc-class_1.cpp)]  
  
##  <a name="getembeddeditem"></a>COleServerDoc::GetEmbeddedItem  
 この関数では、ドキュメント全体を表すアイテムへのポインターを取得します。  
  
```  
COleServerItem* GetEmbeddedItem();
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメント全体を表す項目へのポインター**NULL**場合は、操作に失敗しました。  
  
### <a name="remarks"></a>コメント  
 呼び出す[COleServerDoc::OnGetEmbeddedItem](#ongetembeddeditem)実装のない既定の仮想関数。  
  
##  <a name="getitemcliprect"></a>COleServerDoc::GetItemClipRect  
 呼び出す、`GetItemClipRect`インプレース編集されているアイテムのクリッピング四角形の座標を取得します。  
  
```  
void GetItemClipRect(LPRECT lpClipRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpClipRect`  
 ポインター、`RECT`構造体、または`CRect`をアイテムのクリッピング四角形の座標を取得するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 座標は、コンテナー アプリケーション ウィンドウのクライアント領域を基準と (ピクセル単位)。  
  
 クリッピング四角形の外側描画は発生しません。 通常は、描画は、自動的に制限されています。 この関数を使用してドキュメントの表示部分の外部ユーザーがスクロールされたといったかどうかを判断するには呼び出しを使用して必要に応じて、必要な場合は、スクロール コンテナー ドキュメント[ScrollContainerBy](#scrollcontainerby)します。  
  
##  <a name="getitemposition"></a>COleServerDoc::GetItemPosition  
 呼び出す、`GetItemPosition`インプレース編集中の項目の座標を取得するメンバー関数。  
  
```  
void GetItemPosition(LPRECT lpPosRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPosRect`  
 ポインター、`RECT`構造体、または`CRect`をアイテムの座標を取得するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 座標は、コンテナー アプリケーション ウィンドウのクライアント領域を基準と (ピクセル単位)。  
  
 項目を (または非表示) の範囲を特定する現在のクリッピング四角形で比較できるアイテムの位置を画面にします。  
  
##  <a name="getzoomfactor"></a>先  
 `GetZoomFactor`メンバー関数は、埋め込み先編集のアクティブ化されているアイテムの「倍率」を決定します。  
  
```  
BOOL GetZoomFactor(
    LPSIZE lpSizeNum = NULL,  
    LPSIZE lpSizeDenom = NULL,  
    LPCRECT lpPosRect = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lpSizeNum*  
 クラスのオブジェクトへのポインター`CSize`倍率の分子を保持します。 できる**NULL**します。  
  
 *lpSizeDenom*  
 クラスのオブジェクトへのポインター`CSize`倍率の分母を保持します。 できる**NULL**します。  
  
 `lpPosRect`  
 クラスのオブジェクトへのポインター`CRect`アイテムの新しい位置を記述します。 この引数は場合**NULL**関数は、項目の現在の位置を使用します。  
  
### <a name="return-value"></a>戻り値  
 インプレースで、項目が起動された場合は 0 以外を編集し、その倍率が以外の 100% (1:1) です。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ズームの倍率、(ピクセル単位) は、現在の大きさに対するアイテムのサイズの比率です。 コンテナー アプリケーションが、項目の範囲において、本来のエクステントを設定していない場合 (によって決定される[COleServerItem::OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent)) を使用します。  
  
 関数は、分子と分母の項目の「ズームの倍率」に、最初の&2; つの引数を設定します。 アイテムがインプレース編集されていない場合、関数は、既定値は 100% (または 1 対 1) にこれらの引数を設定し、0 を返します。 詳細については、テクニカル ノート 40: を参照してください。 [MFC/OLE 埋め込み先サイズ変更とズーム](../../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md)します。  
  
##  <a name="isdocobject"></a>COleServerDoc::IsDocObject  
 ドキュメントが DocObject かを調べます。  
  
```  
BOOL IsDocObject() const;  
```  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合は、ドキュメントが DocObject; それ以外の場合**FALSE**します。  
  
##  <a name="isembedded"></a>COleServerDoc::IsEmbedded  
 呼び出す、`IsEmbedded`ドキュメントがコンテナー内に埋め込まれたオブジェクトを表すかどうかを調べます。  
  
```  
BOOL IsEmbedded() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、`COleServerDoc`オブジェクトがオブジェクトを表すドキュメントのコンテナーで埋め込み。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 コンテナー アプリケーションのリンクによる操作することがありますが、ファイルから読み込まれたドキュメントが埋め込まれていません。 コンテナー ドキュメントに埋め込まれているドキュメントが埋め込まれていると見なされます。  
  
##  <a name="isinplaceactive"></a>COleServerDoc::IsInPlaceActive  
 呼び出す、`IsInPlaceActive`アイテムが現在インプレース アクティブ状態であるかどうかを調べます。  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、`COleServerDoc`オブジェクトはインプレース アクティブ。 それ以外の場合に 0 です。  
  
##  <a name="notifychanged"></a>COleServerDoc::NotifyChanged  
 この関数では、ドキュメントが変更されたドキュメントに接続されているすべてのリンクされた項目に通知します。  
  
```  
void NotifyChanged();
```  
  
### <a name="remarks"></a>コメント  
 通常、ユーザーがサーバー ドキュメントのサイズなどのグローバルな属性を変更した後、この関数を呼び出します。 OLE アイテムは、自動リンクを使用して、ドキュメントにリンクされて、変更を反映するように、項目が更新されます。 Microsoft Foundation Class ライブラリに記述されたコンテナー アプリケーションで、 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange)のメンバー関数`COleClientItem`が呼び出されます。  
  
> [!NOTE]
>  この関数は、OLE 1 と互換性のために含まれています。 新しいアプリケーションを使用する必要があります[UpdateAllItems](#updateallitems)します。  
  
##  <a name="notifyclosed"></a>COleServerDoc::NotifyClosed  
 この関数では、ドキュメントが閉じられているコンテナーに通知します。  
  
```  
void NotifyClosed();
```  
  
### <a name="remarks"></a>コメント  
 [ファイル] メニューから [閉じる] コマンドを選択すると`NotifyClosed`によって呼び出される`COleServerDoc`の実装、[通常](../../mfc/reference/cdocument-class.md#onclosedocument)メンバー関数。 Microsoft Foundation Class ライブラリに記述されたコンテナー アプリケーションで、 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange)のメンバー関数`COleClientItem`が呼び出されます。  
  
##  <a name="notifyrename"></a>COleServerDoc::NotifyRename  
 ユーザーには、サーバーのドキュメントが名前を変更した後は、この関数を呼び出します。  
  
```  
void NotifyRename(LPCTSTR lpszNewName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszNewName`  
 サーバー ドキュメントの新しい名前を指定する文字列へのポインターこれは、通常、完全修飾パスです。  
  
### <a name="remarks"></a>コメント  
 [ファイル] メニューから名前を付けて保存コマンドを選択すると`NotifyRename`によって呼び出される`COleServerDoc`の実装、[呼び出す必要はありません](../../mfc/reference/cdocument-class.md#onsavedocument)メンバー関数。 この関数は、OLE システム Dll で、さらに、コンテナーへの通知を通知します。 Microsoft Foundation Class ライブラリに記述されたコンテナー アプリケーションで、 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange)のメンバー関数`COleClientItem`が呼び出されます。  
  
##  <a name="notifysaved"></a>COleServerDoc::NotifySaved  
 ユーザーがサーバーのドキュメントを保存した後は、この関数を呼び出します。  
  
```  
void NotifySaved();
```  
  
### <a name="remarks"></a>コメント  
 [ファイル] メニューから [保存] コマンドを選択すると`NotifySaved`によって呼び出されます`COleServerDoc`の実装の[呼び出す必要はありません](../../mfc/reference/cdocument-class.md#onsavedocument)します。 この関数は、OLE システム Dll で、さらに、コンテナーへの通知を通知します。 Microsoft Foundation Class ライブラリに記述されたコンテナー アプリケーションで、 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange)のメンバー関数`COleClientItem`が呼び出されます。  
  
##  <a name="onclose"></a>COleServerDoc::OnClose  
 コンテナーは、サーバーのドキュメントを閉じることを要求するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnClose(OLECLOSE dwCloseOption);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCloseOption`  
 列挙値`OLECLOSE`です。 このパラメーターには、次のいずれかの値を指定できます。  
  
- `OLECLOSE_SAVEIFDIRTY`変更された場合は、ファイルが保存されます。  
  
- `OLECLOSE_NOSAVE`ファイルが保存されることがなく閉じられます。  
  
- `OLECLOSE_PROMPTSAVE`ファイルが変更された場合は、保存することは求められます。  
  
### <a name="remarks"></a>コメント  
 既定の実装`CDocument::OnCloseDocument`します。  
  
 詳細およびその他の値は、「[子](http://msdn.microsoft.com/library/windows/desktop/ms680623)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="ondeactivate"></a>COleServerDoc::OnDeactivate  
 現在の実行中である埋め込みまたはリンクされたアイテムを非アクティブにするときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>コメント  
 この関数は、コンテナー アプリケーションのユーザー インターフェイスを元の状態に復元し、メニューやインプレース アクティブ化用に作成されたその他のコントロールを破棄します。  
  
 元に戻す状態情報を無条件に解放するこの時点でします。  
  
 詳細については、記事を参照してください[アクティベーション](../../mfc/activation-cpp.md).。  
  
##  <a name="ondeactivateui"></a>COleServerDoc::OnDeactivateUI  
 アクティブなアイテムを非アクティブにすると呼び出されます。  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>パラメーター  
 `bUndoable`  
 編集が完了できるかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 この関数は、コンテナー アプリケーションのユーザー インターフェイスを任意のメニューおよびインプレース アクティブ化用に作成されたその他のコントロールを非表示の元の状態に復元します。  
  
 常に、フレームワークを設定`bUndoable`に**FALSE**します。 サーバーは、元に戻すをサポートし、元に戻すことができる操作は場合に、基本クラス実装を呼び出す`bUndoable`に設定**TRUE**します。  
  
##  <a name="ondocwindowactivate"></a>COleServerDoc::OnDocWindowActivate  
 フレームワークでは、アクティブにするか、埋め込み先編集のドキュメント ウィンドウを非アクティブ化するには、この関数を呼び出します。  
  
```  
virtual void OnDocWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 `bActivate`  
 ドキュメント ウィンドウをアクティブ化または非アクティブにするかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、削除か、適切なフレーム レベルのユーザー インターフェイス要素を追加します。 アイテムを持つドキュメントがアクティブまたは非アクティブになるときに、追加操作を実行する場合は、この関数をオーバーライドします。  
  
 詳細については、記事を参照してください[アクティベーション](../../mfc/activation-cpp.md).。  
  
##  <a name="onexecolecmd"></a>COleServerDoc::OnExecOleCmd  
 フレームワークでは、指定したコマンドを実行またはコマンドのヘルプを表示するには、この関数を呼び出します。  
  
```  
virtual HRESULT OnExecOleCmd(
    const GUID* pguidCmdGroup,  
    DWORD nCmdID,  
    DWORD nCmdExecOpt,  
    VARIANTARG* pvarargIn,  
    VARIANTARG* pvarargOut);
```  
  
### <a name="parameters"></a>パラメーター  
 `pguidCmdGroup`  
 コマンドのセットを識別する GUID へのポインター。 できる**NULL**を既定のコマンド グループを示します。  
  
 `nCmdID`  
 実行するコマンド。 識別されるグループである必要があります`pguidCmdGroup`します。  
  
 *nCmdExecOut*  
 方法は、コマンド、1 つ以上の次の値をオブジェクトを実行する、**する**列挙体。  
  
 **OLECMDEXECOPT_DODEFAULT**  
  
 **OLECMDEXECOPT_PROMPTUSER**  
  
 **OLECMDEXECOPT_DONTPROMPTUSER**  
  
 **OLECMDEXECOPT_SHOWHELP**  
  
 `pvarargIn`  
 ポインター、 **VARIANTARG**コマンドの入力引数を格納しています。 できる**NULL**します。  
  
 `pvarargOut`  
 ポインター、 **VARIANTARG**コマンドから出力される戻り値を受信します。 できる**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`成功した場合は、次のエラー コードのいずれか。  
  
|値|説明|  
|-----------|-----------------|  
|**E_UNEXPECTED**|予期しないエラーが発生しました|  
|**E_FAIL**|エラーが発生しました|  
|**E_NOTIMPL**|MFC を示す変換し、コマンドをディスパッチするべきで自体|  
|**OLECMDERR_E_UNKNOWNGROUP**|`pguidCmdGroup`非**NULL**ですが認識されているコマンド グループが指定されていません|  
|**OLECMDERR_E_NOTSUPPORTED**|`nCmdID`グループ内の有効なコマンドとして認識されません。`pguidCmdGroup`|  
|**OLECMDERR_DISABLED**|指定されたコマンド`nCmdID`は無効になり、実行することはできません|  
|**OLECMDERR_NOHELP**|呼び出し元がで指定されたコマンドのヘルプを要求しました`nCmdID`ヘルプは使用できませんが、|  
|**OLECMDERR_CANCELED**|ユーザーは、実行をキャンセルしました。|  
  
### <a name="remarks"></a>コメント  
 `COleCmdUI`有効にする、更新、および DocObject ユーザー インターフェイスのコマンドの他のプロパティを設定するために使用します。 コマンドが初期化された後でそれらを実行できる`OnExecOleCmd`です。  
  
 フレームワークは、変換および OLE ドキュメント コマンドをディスパッチする前に、関数を呼び出します。 OLE ドキュメントの標準のコマンドを処理するには、この関数をオーバーライドする必要はありませんが、独自のコマンドを処理またはパラメーターを受け入れるか、結果を返すコマンドを処理する場合は、この関数をオーバーライドを指定する必要があります。  
  
 ほとんどのコマンドの引数を受け取るしたりしないで値を返します。 ほとんどのコマンドの呼び出し元を渡すことができます**NULL**の`pvarargIn`と`pvarargOut`です。 入力値を必要とするコマンドの呼び出し元は、宣言し、初期化を**VARIANTARG**変数内の変数にポインターを渡すと`pvarargIn`です。 コマンドについては、単一の値を必要とする、引数をで直接保存することができます、 **VARIANTARG**関数に渡されました。 内に複数の引数をパッケージ化する必要があります、 **VARIANTARG**サポートされる型のいずれかを使用して (よう`IDispatch`と**SAFEARRAY** )。  
  
 同様に、コマンドは、呼び出し元の引数を返す場合を想定して宣言、 **VARIANTARG**に初期化`VT_EMPTY`でそのアドレスを渡すと`pvarargOut`です。 コマンドが単一の値を返す場合、オブジェクトで直接その値を格納できます`pvarargOut`します。 複数の出力値に適した何らかの方法でパッケージ化する必要があります、 **VARIANTARG**します。  
  
 この関数の基本クラスの実装では説明、**対応**コマンドの対象とする適切なハンドラーをコマンドに関連する構造体。 基本クラスの実装は、戻り値または引数を受け取るしないコマンドでのみ動作します。 引数または戻り値をコマンドを処理する必要がある場合は、この関数をオーバーライドして、動作確認する必要があります、`pvarargIn`と`pvarargOut`パラメーター自分でします。  
  
##  <a name="onframewindowactivate"></a>COleServerDoc::OnFrameWindowActivate  
 フレームワークは、コンテナー アプリケーションのフレーム ウィンドウがアクティブまたは非アクティブになるときに、この関数を呼び出します。  
  
```  
virtual void OnFrameWindowActivate(BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 `bActivate`  
 フレーム ウィンドウをアクティブ化または非アクティブにするかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、フレーム ウィンドウのヘルプ モードをキャンセルします。 フレーム ウィンドウがアクティブ化または非アクティブになる場合は、特別な処理を実行する場合は、この関数をオーバーライドします。  
  
 詳細については、記事を参照してください[アクティベーション](../../mfc/activation-cpp.md).。  
  
##  <a name="ongetembeddeditem"></a>COleServerDoc::OnGetEmbeddedItem  
 コンテナー アプリケーションが作成または埋め込みアイテムを編集するサーバー アプリケーションを呼び出すときに、フレームワークによって呼び出されます。  
  
```  
virtual COleServerItem* OnGetEmbeddedItem() = 0;  
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメント全体を表す項目へのポインター**NULL**場合は、操作に失敗しました。  
  
### <a name="remarks"></a>コメント  
 既定の実装はありません。 ドキュメント全体を表す項目を返す関数をオーバーライドする必要があります。 この戻り値のオブジェクトをする必要があります、 `COleServerItem`-クラスを派生します。  
  
##  <a name="onreactivateandundo"></a>されて  
 フレームワークは、インプレース アクティブ化、変更すると、および後で非アクティブ化された項目に加えられた変更を元に戻すを選択すると、この関数を呼び出します。  
  
```  
virtual BOOL OnReactivateAndUndo();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も返す以外**FALSE**失敗を示すにします。  
  
 アプリケーションは、元に戻すをサポートしている場合は、この関数をオーバーライドします。 通常、元に戻す操作を実行しを呼び出して、項目をアクティブ化する`ActivateInPlace`です。 コンテナー アプリケーションが、Microsoft Foundation Class ライブラリに記述されている場合は、呼び出し`COleClientItem::ReactivateAndUndo`呼び出される場合は、この関数が発生します。  
  
##  <a name="onresizeborder"></a>COleServerDoc::OnResizeBorder  
 フレームワークは、コンテナー アプリケーションのフレーム ウィンドウのサイズを変更するときに、この関数を呼び出します。  
  
```  
virtual void OnResizeBorder(
    LPCRECT lpRectBorder,  
    LPOLEINPLACEUIWINDOW lpUIWindow,  
    BOOL bFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRectBorder`  
 ポインター、`RECT`構造体、または`CRect`罫線の座標を指定するオブジェクト。  
  
 `lpUIWindow`  
 クラスのオブジェクトへのポインター**埋め込み**現在の埋め込み先編集セッションを所有しています。  
  
 *b フレーム*  
 **TRUE**場合`lpUIWindow`コンテナー アプリケーションの最上位のフレーム ウィンドウで、指すまたは**FALSE**場合`lpUIWindow`コンテナー アプリケーションのドキュメント レベルのフレーム ウィンドウをポイントします。  
  
### <a name="remarks"></a>コメント  
 この関数は、サイズを変更し、ツールバーと新しいウィンドウのサイズに従ってその他のユーザー インターフェイス要素を調整します。  
  
 詳細については、次を参照してください。[埋め込み](http://msdn.microsoft.com/library/windows/desktop/ms680716)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 これは、高度なオーバーライドします。  
  
##  <a name="onsethostnames"></a>COleServerDoc::OnSetHostNames  
 コンテナーを設定またはこのドキュメントのホスト名を変更するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnSetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszHost`  
 コンテナー アプリケーションの名前を指定する文字列へのポインター。  
  
 `lpszHostObj`  
 ドキュメントのコンテナーの名前を指定する文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、このドキュメントを参照するすべてのビューにドキュメントのタイトルを変更します。  
  
 アプリケーションが、別のメカニズムを通じて、タイトルを設定する場合は、この関数をオーバーライドします。  
  
##  <a name="onsetitemrects"></a>COleServerDoc::OnSetItemRects  
 フレームワークでは、コンテナー アプリケーションのフレーム ウィンドウ内で、埋め込み先編集フレーム ウィンドウを配置するには、この関数を呼び出します。  
  
```  
virtual void OnSetItemRects(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPosRect`  
 ポインター、`RECT`構造体、または`CRect`コンテナー アプリケーションのクライアント領域を基準との埋め込み先フレーム ウィンドウの位置を指定するオブジェクト。  
  
 `lpClipRect`  
 ポインター、`RECT`構造体、または`CRect`で埋め込み先フレーム ウィンドウのクリッピング長方形を指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 必要な場合は、ビューのズームの倍率を更新するには、この関数をオーバーライドします。  
  
 通常、この関数はへの応答で呼び出されます。、`RequestPositionChange`呼び出すには、は埋め込み先アイテムの位置の変更を要求するコンテナーによっていつでも呼び出すことができます。  
  
##  <a name="onshowcontrolbars"></a>COleServerDoc::OnShowControlBars  
 フレームワークで識別されるフレーム ウィンドウに関連付けられているサーバー アプリケーションのコントロール バーを非表示には、この関数を呼び出します`pFrameWnd`します。  
  
```  
virtual void OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFrameWnd`  
 フレーム ウィンドウのコントロール バーを非表示または表示する必要がありますへのポインター。  
  
 `bShow`  
 コントロール バーを表示または非表示かどうかを決定します。  
  
### <a name="remarks"></a>コメント  
 既定の実装は、フレーム ウィンドウによって所有されているすべてのコントロール バーを列挙または非表示にし、それらを示しています。  
  
##  <a name="onshowdocument"></a>COleServerDoc::OnShowDocument  
 フレームワークによって、`OnShowDocument`関数の場合、サーバーのドキュメントを非表示または表示する必要があります。  
  
```  
virtual void OnShowDocument(BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 `bShow`  
 ドキュメントへのユーザー インターフェイスを表示するか非表示になっているかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 場合`bShow`は**TRUE**既定の実装は、必要に応じて、サーバー アプリケーションをアクティブにし、コンテナー アプリケーションが、項目が表示されるように、そのウィンドウをスクロールします。 場合`bShow`は**FALSE**、既定の実装への呼び出しを使用して、アイテムを非アクティブに`OnDeactivate`を破棄または&1; つ目以外のドキュメント用に作成されたすべてのフレーム ウィンドウを非表示にします。 表示されているドキュメントが残っていない場合、既定の実装には、サーバー アプリケーションが非表示にします。  
  
##  <a name="onupdatedocument"></a>COleServerDoc::OnUpdateDocument  
 複合ドキュメントに埋め込まれたアイテムは、文書を保存するときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnUpdateDocument();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、ドキュメントが正常に更新されました。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装、 [COleServerDoc::NotifySaved](#notifysaved)と[COleServerDoc::SaveEmbedding](#saveembedding)メンバーが機能し、クリーンとしてマークします。 特別な埋め込みアイテムを更新するときの処理を実行する場合は、この関数をオーバーライドします。  
  
##  <a name="requestpositionchange"></a>から  
 コンテナー アプリケーションにアイテムの位置を変更するには、このメンバー関数を呼び出します。  
  
```  
void RequestPositionChange(LPCRECT lpPosRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPosRect`  
 ポインター、`RECT`構造体、または`CRect`アイテムの新しい位置を格納するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 通常、この関数は呼び出されます (と共に`UpdateAllItems`)、インプレース アクティブな項目内のデータが変更されました。 この呼び出しでは、次のコンテナーがありますまたはを呼び出して、変更を実行しなかったり`OnSetItemRects`します。 返される位置は、要求されるとは異なる場合があります。  
  
##  <a name="saveembedding"></a>COleServerDoc::SaveEmbedding  
 この関数では、埋め込みオブジェクトを保存するコンテナー アプリケーションに指示します。  
  
```  
void SaveEmbedding();
```  
  
### <a name="remarks"></a>コメント  
 この関数はから自動的に呼び出されます。`OnUpdateDocument`します。 この関数がにより、アイテムをディスク上で更新されるので、通常、特定のユーザーの操作の結果としてのみと呼ばれるであることに注意してください。  
  
##  <a name="scrollcontainerby"></a>COleServerDoc::ScrollContainerBy  
 呼び出す、`ScrollContainerBy`で示されます (ピクセル単位) の量でコンテナーのドキュメントをスクロールするメンバー関数を`sizeScroll`します。  
  
```  
BOOL ScrollContainerBy(CSize sizeScroll);
```  
  
### <a name="parameters"></a>パラメーター  
 `sizeScroll`  
 スクロールするコンテナー ドキュメントは、距離を示します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 正の値が右にスクロール ダウンを示します負の値を示すを左にスクロールします。  
  
##  <a name="updateallitems"></a>COleServerDoc::UpdateAllItems  
 この関数では、ドキュメントが変更されたドキュメントに接続されているすべてのリンクされた項目に通知します。  
  
```  
void UpdateAllItems(
    COleServerItem* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSender`  
 ドキュメントを変更する項目へのポインターまたは**NULL**場合、すべての項目を更新します。  
  
 `lHint`  
 変更に関する情報が含まれています。  
  
 `pHint`  
 変更に関する情報を格納するオブジェクトへのポインター。  
  
 `nDrawAspect`  
 アイテムの描画する方法を決定します。 これから値、`DVASPECT`列挙します。 このパラメーターには、次のいずれかの値を指定できます。  
  
- `DVASPECT_CONTENT`項目は、そのコンテナー内の埋め込みオブジェクトとして表示できるように表されます。  
  
- `DVASPECT_THUMBNAIL`閲覧ツールで表示されることができるように、「縮小」表現ではアイテムが表示されます。  
  
- `DVASPECT_ICON`項目がアイコンで表されます。  
  
- `DVASPECT_DOCPRINT`[ファイル] メニューから [印刷] コマンドを使用して印刷した場合のように、項目が表されます。  
  
### <a name="remarks"></a>コメント  
 通常、ユーザーがサーバーのドキュメントを変更した後は、この関数を呼び出します。 OLE アイテムは、自動リンクを使用して、ドキュメントにリンクされて、変更を反映するように、項目が更新されます。 Microsoft Foundation Class ライブラリに記述されたコンテナー アプリケーションで、 [OnChange](../../mfc/reference/coleclientitem-class.md#onchange)のメンバー関数`COleClientItem`が呼び出されます。  
  
 この関数は、`OnUpdate`メンバー関数の各項目を渡す送信以外、ドキュメントの項目を`pHint`、 `lHint`、および`nDrawAspect`です。 ドキュメントに加えられた変更に関する項目に情報を渡すには、これらのパラメーターを使用します。 使用して情報をエンコードする`lHint`するかを定義、 `CObject`-派生したクラスを変更についての情報を格納および使用するこのクラスのオブジェクトを渡す`pHint`します。 オーバーライド、`OnUpdate`でメンバー関数、 `COleServerItem`-その表現が変更されたかどうかに応じて、各項目の更新を最適化するためにクラスを派生します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [直接クラス](../../mfc/reference/colelinkingdoc-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDocument クラス](../../mfc/reference/coledocument-class.md)   
 [直接クラス](../../mfc/reference/colelinkingdoc-class.md)   
 [関数のクラス](../../mfc/reference/coletemplateserver-class.md)

