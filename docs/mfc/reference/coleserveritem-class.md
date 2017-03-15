---
title: "実際のクラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleServerItem
dev_langs:
- C++
helpviewer_keywords:
- servers, OLE
- OLE server applications, managing server documents
- OLE server applications, server interfaces
- OLE server documents
- COleServerItem class
ms.assetid: 80256df6-3888-4256-944b-787d4b2e6b0d
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
ms.openlocfilehash: 49dd8cc258ebf96c91ac8ff1190f9a830b6bb5ec
ms.lasthandoff: 02/24/2017

---
# <a name="coleserveritem-class"></a>実際のクラス
OLE アイテムへのサーバー インターフェイスが用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class COleServerItem : public CDocItem  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleServerItem::COleServerItem](#coleserveritem)|`COleServerItem` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleServerItem::AddOtherClipboardData](#addotherclipboarddata)|内でプレゼンテーションと変換の形式の配置、`COleDataSource`オブジェクトです。|  
|[COleServerItem::CopyToClipboard](#copytoclipboard)|項目をクリップボードにコピーします。|  
|[判定できます。](#dodragdrop)|ドラッグ アンド ドロップ操作を実行します。|  
|[COleServerItem::GetClipboardData](#getclipboarddata)|データ転送 (ドラッグ アンド ドロップするかクリップボード) で使用するためには、データ ソースを取得します。|  
|[COleServerItem::GetDocument](#getdocument)|アイテムが含まれるサーバーのドキュメントを返します。|  
|[COleServerItem::GetEmbedSourceData](#getembedsourcedata)|取得、 **CF_EMBEDSOURCE** OLE アイテムのデータです。|  
|[COleServerItem::GetItemName](#getitemname)|アイテムの名前を返します。 リンクされた項目のみに使用されます。|  
|[COleServerItem::GetLinkSourceData](#getlinksourcedata)|取得、 `CF_LINKSOURCE` OLE アイテムのデータです。|  
|[COleServerItem::GetObjectDescriptorData](#getobjectdescriptordata)|取得、 **CF_OBJECTDESCRIPTOR** OLE アイテムのデータです。|  
|[COleServerItem::IsConnected](#isconnected)|項目が現在アクティブなコンテナーに接続されているかどうかを示します。|  
|[COleServerItem::IsLinkedItem](#islinkeditem)|項目がリンクされている OLE アイテムを表すかどうかを示します。|  
|[COleServerItem::NotifyChanged](#notifychanged)|自動リンクの更新では、すべてのコンテナーを更新します。|  
|[COleServerItem::OnDoVerb](#ondoverb)|動詞を実行するには、呼び出されます。|  
|[:Ondraw](#ondraw)|コンテナー アイテムの描画を要求するときに呼び出されます必要な実装です。|  
|[COleServerItem::OnDrawEx](#ondrawex)|特殊なアイテムの描画に呼び出されます。|  
|[COleServerItem::OnGetClipboardData](#ongetclipboarddata)|クリップボードにコピーされるデータを取得するためにフレームワークによって呼び出されます。|  
|[COleServerItem::OnGetExtent](#ongetextent)|OLE アイテムのサイズを取得するためにフレームワークによって呼び出されます。|  
|[COleServerItem::OnInitFromData](#oninitfromdata)|指定したデータ転送オブジェクトのコンテンツを使用して OLE アイテムを初期化するためにフレームワークによって呼び出されます。|  
|[COleServerItem::OnQueryUpdateItems](#onqueryupdateitems)|リンク アイテムの更新が必要かどうかを判断するには、呼び出されます。|  
|[COleServerItem::OnRenderData](#onrenderdata)|遅延レンダリングの一部としてデータを取得します。|  
|[COleServerItem::OnRenderFileData](#onrenderfiledata)|データを取得、`CFile`遅延レンダリングの一部としてオブジェクトです。|  
|[COleServerItem::OnRenderGlobalData](#onrenderglobaldata)|データを取得、`HGLOBAL`遅延レンダリングの一部として。|  
|[COleServerItem::OnSetColorScheme](#onsetcolorscheme)|アイテムの配色を設定すると呼ばれます。|  
|[COleServerItem::OnSetData](#onsetdata)|アイテムのデータを設定すると呼ばれます。|  
|[COleServerItem::OnSetExtent](#onsetextent)|OLE アイテムのサイズを設定するためにフレームワークによって呼び出されます。|  
|[COleServerItem::OnUpdate](#onupdate)|呼ばれるは、ドキュメント、項目の一部が属している場合は変更されます。|  
|[COleServerItem::OnUpdateItems](#onupdateitems)|サーバー ドキュメントのすべてのアイテムのプレゼンテーションのキャッシュを更新するには、呼び出されます。|  
|[COleServerItem::SetItemName](#setitemname)|アイテムの名前を設定します。 リンクされた項目のみに使用されます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[は](#getdatasource)|変換形式の格納に使用されるオブジェクトを取得します。|  
|[COleServerItem::OnHide](#onhide)|OLE アイテムを非表示にするために、フレームワークによって呼び出されます。|  
|[COleServerItem::OnOpen](#onopen)|OLE アイテムを最上位レベルのウィンドウに表示するためにフレームワークによって呼び出されます。|  
|[COleServerItem::OnShow](#onshow)|コンテナーは、アイテムを表示する要求したときに呼び出されます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleServerItem::m_sizeExtent](#m_sizeextent)|OLE アイテムの量が表示されて、サーバーを通知します。|  
  
## <a name="remarks"></a>コメント  
 リンクされた項目には、サーバー ドキュメントの一部またはすべてを表すことができます。 埋め込みアイテムは、常に、サーバー全体のドキュメントを表します。  
  
 `COleServerItem`クラス定義が OLE システム ダイナミック リンク ライブラリ (Dll) によって呼び出されるオーバーライド可能なメンバー関数がいくつか通常コンテナー アプリケーションからの要求に応答します。 これらのメンバー関数では、コンテナー アプリケーションなど、さまざまな方法で間接的に項目を表示したり、その動詞を実行中またはさまざまな形式でデータの取得元で操作をできるようにします。  
  
 使用する`COleServerItem`、クラスの派生、および実装、 [OnDraw](#ondraw)と[Serialize](../../mfc/reference/cobject-class.md#serialize)メンバー関数。 `OnDraw`関数は、コンテナー アプリケーションは、複合ドキュメントを開いたときに表示できるように、項目のメタファイルを提供します。 `Serialize`関数の`CObject`埋め込まれたアイテム サーバーおよびコンテナーのアプリケーション間で転送されるようにする、項目のネイティブ形式を提供します。 [OnGetExtent](#ongetextent)アイテムのサイズのコンテナーを有効にすると、コンテナーに項目の元のサイズを提供します。  
  
 サーバーと関連トピックに関する詳細については、記事を参照してください。[サーバー: サーバーの実装](../../mfc/servers-implementing-a-server.md)と、コンテナー/サーバー アプリケーションの作成」の記事で[コンテナー: 高度な機能](../../mfc/containers-advanced-features.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleServerItem`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="a-nameaddotherclipboarddataa--coleserveritemaddotherclipboarddata"></a><a name="addotherclipboarddata"></a>COleServerItem::AddOtherClipboardData  
 指定した OLE アイテムのプレゼンテーションと変換の形式を配置するには、この関数を呼び出す`COleDataSource`オブジェクトです。  
  
```  
void AddOtherClipboardData(COleDataSource* pDataSource);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataSource`  
 ポインター、`COleDataSource`データを格納するオブジェクトします。  
  
### <a name="remarks"></a>コメント  
 実装している必要があります、 [OnDraw](#ondraw)アイテムの表示形式 (メタファイル画像) を提供するメンバー関数。 形式をサポートするその他の変換、それらの登録を使用して、 [COleDataSource](../../mfc/reference/coledatasource-class.md)によって返されるオブジェクト[GetDataSource](#getdatasource)させ、[は](#onrenderdata)をサポートする形式でデータを提供するメンバー関数。  
  
##  <a name="a-namecoleserveritema--coleserveritemcoleserveritem"></a><a name="coleserveritem"></a>COleServerItem::COleServerItem  
 構築、`COleServerItem`オブジェクトし、ドキュメントの項目のサーバー ドキュメントのコレクションに追加します。  
  
```  
COleServerItem(
    COleServerDoc* pServerDoc,  
    BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>パラメーター  
 `pServerDoc`  
 新しい項目を含む文書へのポインター。  
  
 `bAutoDelete`  
 リンクがリリースされたときに、オブジェクトを削除するかどうかを示すフラグします。 これを設定**FALSE**場合、`COleServerItem`オブジェクトは、削除する必要がありますドキュメントのデータに不可欠な要素です。 これを設定**TRUE**場合は、オブジェクトは、二次的な構造を削除するには、フレームワークをドキュメントのデータの範囲を識別するために使用します。  
  
##  <a name="a-namecopytoclipboarda--coleserveritemcopytoclipboard"></a><a name="copytoclipboard"></a>COleServerItem::CopyToClipboard  
 OLE アイテムをクリップボードにコピーするには、この関数を呼び出します。  
  
```  
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bIncludeLink`  
 これを設定**TRUE**リンク データをクリップボードにコピーする場合。 これを設定**FALSE**サーバー アプリケーションでは、リンクをサポートしていない場合。  
  
### <a name="remarks"></a>コメント  
 関数を使用して、 [OnGetClipboardData](#ongetclipboarddata)を作成するメンバー関数、 [COleDataSource](../../mfc/reference/coledatasource-class.md)サポートされている形式の OLE アイテムのデータを含むオブジェクト。 関数は、配置、`COleDataSource`オブジェクトを使用してクリップボードに、 [COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard)関数です。 `COleDataSource`オブジェクトには、項目のネイティブ データおよびで表される形式`CF_METAFILEPICT`形式だけをサポートするすべての変換形式のデータです。 実装している必要があります[Serialize](../../mfc/reference/cobject-class.md#serialize)と[OnDraw](#ondraw)動作するには、このメンバー関数にします。  
  
##  <a name="a-namedodragdropa--coleserveritemdodragdrop"></a><a name="dodragdrop"></a>判定できます。  
 呼び出す、`DoDragDrop`ドラッグ アンド ドロップ操作を実行するメンバー関数。  
  
```  
DROPEFFECT DoDragDrop(
    LPCRECT lpRectItem,  
    CPoint ptOffset,  
    BOOL bIncludeLink = FALSE,  
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,  
    LPCRECT lpRectStartDrag = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpRectItem*  
 クライアント領域を基準とのピクセル単位での画面で、項目の四角形。  
  
 `ptOffset`  
 オフセット`lpItemRect`がドラッグ時に、マウスの位置であります。  
  
 `bIncludeLink`  
 これを設定**TRUE**リンク データをクリップボードにコピーする場合。 設定**FALSE**アプリがリンクをサポートしていない場合。  
  
 `dwEffects`  
 ドラッグ ソースがドラッグ操作 (コピー、移動、およびリンクの組み合わせ) で許可する効果を決定します。  
  
 `lpRectStartDrag`  
 実際には、ドラッグの開始位置を定義する四角形へのポインター。 詳細については、「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 `DROPEFFECT` 列挙体の値。 ある場合`DROPEFFECT_MOVE`、元のデータを削除する必要があります。  
  
### <a name="remarks"></a>コメント  
 ドラッグ アンド ドロップ操作はすぐに開始されません。 マウス カーソルが指定された四角形のままになるまで待機している`lpRectStartDrag`または指定したミリ秒数が経過するまでです。 場合`lpRectStartDrag`は**NULL**、マウス カーソルが&1; つのピクセルを移動すると、ドラッグが開始されるように、既定の四角形を使用します。  
  
 遅延時間は、レジストリ キーの設定によって指定されます。 遅延時間を変更するにを呼び出して[CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring)または[cwinapp::writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint)します。 遅延時間を指定しない場合は、200 ミリ秒の既定値が使用されます。 ドラッグ遅延時間は、次のように格納されます。  
  
-   Windows NT ドラッグ遅延時間は、HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay に格納されます。  
  
-   Windows 3.x ドラッグ遅延時間は、WIN に格納されます。INI ファイルの [Windows} セクション。  
  
-   Windows 95/98 ドラッグ遅延時間は、WIN のキャッシュされたバージョンに格納されます。INI します。  
  
 遅延の情報は、レジストリに格納されている方法の詳細についてはドラッグのか。INI ファイルを参照してください[WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetclipboarddataa--coleserveritemgetclipboarddata"></a><a name="getclipboarddata"></a>COleServerItem::GetClipboardData  
 この関数を呼び出して、指定した入力[COleDataSource](../../mfc/reference/coledatasource-class.md)呼び出した場合、クリップボードにコピーされるすべてのデータを含むオブジェクト[CopyToClipboard](#copytoclipboard) (呼び出した場合、同じデータを転送もは[(dodragdrop を)](#dodragdrop))。  
  
```  
void GetClipboardData(
    COleDataSource* pDataSource,  
    BOOL bIncludeLink = FALSE,  
    LPPOINT lpOffset = NULL,  
    LPSIZE lpSize = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataSource`  
 ポインター、`COleDataSource`サポートされているすべての形式で OLE アイテムのデータを受け取るオブジェクト。  
  
 `bIncludeLink`  
 **TRUE**リンク データをクリップボードにコピーする場合。 **FALSE**サーバー アプリケーションでは、リンクをサポートしていない場合。  
  
 `lpOffset`  
 オブジェクトの元のマウス カーソルのピクセル単位のオフセット。  
  
 `lpSize`  
 ピクセル単位でオブジェクトのサイズ。  
  
### <a name="remarks"></a>コメント  
 この関数は、 [GetEmbedSourceData](#getembedsourcedata) OLE アイテムと呼び出しのネイティブのデータを取得するメンバー関数、 [AddOtherClipboardData](#addotherclipboarddata)プレゼンテーション形式といずれかを取得するメンバー関数が変換形式をサポートします。 場合`bIncludeLink`は**TRUE**、関数も呼び出します[GetLinkSourceData](#getlinksourcedata)リンク データ項目を取得します。  
  
 形式を格納する場合は、この関数をオーバーライドする`COleDataSource`オブジェクトによって提供されるそれらの形式の前後に`CopyToClipboard`します。  
  
##  <a name="a-namegetdatasourcea--coleserveritemgetdatasource"></a><a name="getdatasource"></a>は  
 取得するには、この関数を呼び出す、 [COleDataSource](../../mfc/reference/coledatasource-class.md)サーバー アプリケーションがサポートする変換形式の格納に使用されるオブジェクト。  
  
```  
COleDataSource* GetDataSource();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`COleDataSource`変換形式の格納に使用されるオブジェクト。  
  
### <a name="remarks"></a>コメント  
 操作データの転送中にさまざまな形式でデータを提供する、サーバー アプリケーションを実行する場合に、それらを使用して形式を登録、`COleDataSource`この関数によって返されるオブジェクト。 指定する場合など、**エディット**クリップボード操作やドラッグ アンド ドロップ操作の OLE アイテムの表現と形式を登録すると、`COleDataSource`オブジェクトがこの関数を返すと、上書き、 **OnRenderXxxData**データを提供するメンバー関数。  
  
##  <a name="a-namegetdocumenta--coleserveritemgetdocument"></a><a name="getdocument"></a>COleServerItem::GetDocument  
 この関数では、項目を含むドキュメントへのポインターを取得します。  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アイテムを保持するドキュメントへのポインター**NULL**場合は、項目は、ドキュメントの一部ではありません。  
  
### <a name="remarks"></a>コメント  
 これは、引数として渡された server ドキュメントへのアクセス、`COleServerItem`コンス トラクターです。  
  
##  <a name="a-namegetembedsourcedataa--coleserveritemgetembedsourcedata"></a><a name="getembedsourcedata"></a>COleServerItem::GetEmbedSourceData  
 取得するには、この関数を呼び出す、 **CF_EMBEDSOURCE** OLE アイテムのデータです。  
  
```  
void GetEmbedSourceData(LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpStgMedium`  
 ポインター、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)を受け取る、 **CF_EMBEDSOURCE** OLE アイテムのデータです。  
  
### <a name="remarks"></a>コメント  
 この形式には、項目のネイティブ データが含まれています。 実装している必要があります、`Serialize`適切に機能するには、この関数のメンバー関数。  
  
 結果を使用してデータ ソースに追加された[取得](../../mfc/reference/coledatasource-class.md#cachedata)します。 この関数[COleServerItem::OnGetClipboardData](#ongetclipboarddata)します。  
  
 詳細については、次を参照してください。 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetitemnamea--coleserveritemgetitemname"></a><a name="getitemname"></a>COleServerItem::GetItemName  
 アイテムの名前を取得するには、この関数を呼び出します。  
  
```  
const CString& GetItemName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 項目の名前。  
  
### <a name="remarks"></a>コメント  
 通常、この関数は、リンクされた項目に対してのみ呼び出します。  
  
##  <a name="a-namegetlinksourcedataa--coleserveritemgetlinksourcedata"></a><a name="getlinksourcedata"></a>COleServerItem::GetLinkSourceData  
 取得するには、この関数を呼び出す、 `CF_LINKSOURCE` OLE アイテムのデータです。  
  
```  
BOOL GetLinkSourceData(LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpStgMedium`  
 ポインター、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)を受け取る、 `CF_LINKSOURCE` OLE アイテムのデータです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この形式には、OLE アイテムと OLE アイテムを含むドキュメントの検索に必要な情報の種類を示す CLSID が含まれています。  
  
 結果を持つデータ ソースに追加、[取得](../../mfc/reference/coledatasource-class.md#cachedata)します。 この関数[OnGetClipboardData](#ongetclipboarddata)します。  
  
 詳細については、次を参照してください。 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namegetobjectdescriptordataa--coleserveritemgetobjectdescriptordata"></a><a name="getobjectdescriptordata"></a>COleServerItem::GetObjectDescriptorData  
 取得するには、この関数を呼び出す、 **CF_OBJECTDESCRIPTOR** OLE アイテムのデータです。  
  
```  
void GetObjectDescriptorData(
    LPPOINT lpOffset,  
    LPSIZE lpSize,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpOffset`  
 マウスのオフセットは、OLE アイテムの左上隅をクリックします。 できる**NULL**します。  
  
 `lpSize`  
 OLE アイテムのサイズ。 できる**NULL**します。  
  
 `lpStgMedium`  
 ポインター、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)を受け取る、 **CF_OBJECTDESCRIPTOR** OLE アイテムのデータです。  
  
### <a name="remarks"></a>コメント  
 情報は、コピー、 **STGMEDIUM**構造体を指す`lpStgMedium`します。 この形式には、貼り付け ダイアログ ボックスに必要な情報が含まれています。  
  
 詳細については、次を参照してください。 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameisconnecteda--coleserveritemisconnected"></a><a name="isconnected"></a>COleServerItem::IsConnected  
 OLE アイテムが接続されているかどうかに表示するには、この関数を呼び出します。  
  
```  
BOOL IsConnected() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アイテムが接続されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 OLE アイテムは、1 つまたは複数のコンテナーの項目への参照がある場合に接続されていると見なされます。 項目が接続されているは、参照カウントが 0 より大きい場合、または埋め込みアイテムである場合。  
  
##  <a name="a-nameislinkeditema--coleserveritemislinkeditem"></a><a name="islinkeditem"></a>COleServerItem::IsLinkedItem  
 この関数を呼び出して、OLE アイテムは、リンクされた項目を参照してください。  
  
```  
BOOL IsLinkedItem() const;  
```  
  
### <a name="return-value"></a>戻り値  
 項目がリンクされた項目の場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 項目が有効では、埋め込みアイテムのドキュメントの一覧に返されない場合、項目がリンクされます。 リンクされた項目は、コンテナーに接続できない場合もあります。  
  
 リンクと埋め込みの両方の項目に同じクラスを使用する一般的なになります。 `IsLinkedItem`何度もコードは一般的には、埋め込みアイテムとは異なる動作にリンクされた項目を作成できます。  
  
##  <a name="a-namemsizeextenta--coleserveritemmsizeextent"></a><a name="m_sizeextent"></a>COleServerItem::m_sizeExtent  
 このメンバーは、コンテナーの文書に表示されませんが、オブジェクトの量をサーバーに指示します。  
  
```  
CSize m_sizeExtent;  
```  
  
### <a name="remarks"></a>コメント  
 既定の実装[OnSetExtent](#onsetextent)このメンバーを設定します。  
  
##  <a name="a-namenotifychangeda--coleserveritemnotifychanged"></a><a name="notifychanged"></a>COleServerItem::NotifyChanged  
 リンクされた項目を変更した後は、この関数を呼び出します。  
  
```  
void NotifyChanged(DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>パラメーター  
 `nDrawAspect`  
 値、`DVASPECT`を OLE アイテムの特徴が変更されたかを示す列挙体です。 このパラメーターは、次の値のいずれかになります。  
  
- `DVASPECT_CONTENT`項目は、そのコンテナー内の埋め込みオブジェクトとして表示できるように表されます。  
  
- `DVASPECT_THUMBNAIL`閲覧ツールで表示されることができるように、「縮小」表現ではアイテムが表示されます。  
  
- `DVASPECT_ICON`項目がアイコンで表されます。  
  
- `DVASPECT_DOCPRINT`[ファイル] メニューから [印刷] コマンドを使用して印刷した場合のように、項目が表されます。  
  
### <a name="remarks"></a>コメント  
 コンテナー アイテムは、自動リンクを使用して、ドキュメントにリンクされて、変更を反映するように、項目が更新されます。 Microsoft Foundation Class ライブラリを使用して作成されたコンテナー アプリケーションに[として](../../mfc/reference/coleclientitem-class.md#onchange)は応答で呼び出されます。  
  
##  <a name="a-nameondoverba--coleserveritemondoverb"></a><a name="ondoverb"></a>COleServerItem::OnDoVerb  
 指定した動詞を実行するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDoVerb(LONG iVerb);
```  
  
### <a name="parameters"></a>パラメーター  
 `iVerb`  
 実行する動詞を指定します。 次のいずれかを指定できます。  
  
|値|説明|シンボル|  
|-----------|-------------|------------|  
|0|主動詞|`OLEIVERB_PRIMARY`|  
|1|セカンダリ動詞|(なし)|  
|– 1|編集するための表示項目|`OLEIVERB_SHOW`|  
|– 2|別のウィンドウで項目を編集します。|`OLEIVERB_OPEN`|  
|– 3|アイテムを非表示します。|`OLEIVERB_HIDE`|  
  
 –&1; の値は、通常、他の動詞のエイリアスです。 編集のオープンがサポートされていない場合、–&2; は-1 と同じ効果を持ちます。 その他の値を参照してください。 [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 コンテナー アプリケーションは、Microsoft Foundation Class ライブラリで記述された、この関数が呼び出されますときに、 [COleClientItem::Activate](../../mfc/reference/coleclientitem-class.md#activate)対応するメンバー関数`COleClientItem`オブジェクトが呼び出されるとします。 既定の実装、 [OnShow](#onshow)のメンバー関数の場合は主動詞または`OLEIVERB_SHOW`が指定されている[OnOpen](#onopen)場合セカンダリ動詞または`OLEIVERB_OPEN`が指定されていると[OnHide](#onhide)場合`OLEIVERB_HIDE`が指定されています。 既定の実装`OnShow`場合`iVerb`上に示した動詞のいずれかではありません。  
  
 主動詞がアイテムを表示しない場合は、この関数をオーバーライドします。 たとえば、項目が、録音物で、その主動詞が再生の場合は、項目を再生するサーバー アプリケーションを表示する必要はありません。  
  
 詳細については、次を参照してください。 [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameondrawa--coleserveritemondraw"></a><a name="ondraw"></a>:Ondraw  
 OLE 項目をメタファイルに描画するためにフレームワークで呼び出されます。  
  
```  
virtual BOOL OnDraw(
    CDC* pDC,  
    CSize& rSize) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 ポインター、 [CDC](../../mfc/reference/cdc-class.md)アイテムを描画する対象となるオブジェクト。 ディスプレイ コンテキストは、属性の関数が使えるように、自動的に属性ディスプレイ コンテキストに接続します。  
  
 `rSize`  
 サイズ、 **HIMETRIC**メタファイルを描画するための単位です。  
  
### <a name="return-value"></a>戻り値  
 項目が描画できた場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 OLE アイテムのメタファイル表現を使用して、コンテナー アプリケーションにアイテムを表示します。 メタファイルはによって使用されている場合は、コンテナー アプリケーションは、Microsoft Foundation Class ライブラリで記述された、[描画](../../mfc/reference/coleclientitem-class.md#draw)対応するメンバー関数[COleClientItem](../../mfc/reference/coleclientitem-class.md)オブジェクトです。 既定の実装はありません。 指定したデバイス コンテキストに項目を描画するには、この関数をオーバーライドする必要があります。  
  
##  <a name="a-nameondrawexa--coleserveritemondrawex"></a><a name="ondrawex"></a>COleServerItem::OnDrawEx  
 すべての描画するためのフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnDrawEx(
    CDC* pDC,  
    DVASPECT nDrawAspect,  
    CSize& rSize);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 ポインター、 [CDC](../../mfc/reference/cdc-class.md)アイテムを描画する対象となるオブジェクト。 DC は、属性の関数が使えるように、自動的に属性の DC に接続します。  
  
 `nDrawAspect`  
 `DVASPECT` 列挙体の値。 このパラメーターは、次の値のいずれかになります。  
  
- `DVASPECT_CONTENT`項目は、そのコンテナー内の埋め込みオブジェクトとして表示できるように表されます。  
  
- `DVASPECT_THUMBNAIL`閲覧ツールで表示されることができるように、「縮小」表現ではアイテムが表示されます。  
  
- `DVASPECT_ICON`項目がアイコンで表されます。  
  
- `DVASPECT_DOCPRINT`[ファイル] メニューから [印刷] コマンドを使用して印刷した場合のように、項目が表されます。  
  
 `rSize`  
 内の項目のサイズ**HIMETRIC**単位です。  
  
### <a name="return-value"></a>戻り値  
 項目が描画できた場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装`OnDraw`と`DVASPECT`に等しい`DVASPECT_CONTENT`。 そうしないと失敗します。  
  
 以外の場合、概要のプレゼンテーションにデータを提供するには、この関数をオーバーライド`DVASPECT_CONTENT`など`DVASPECT_ICON`または`DVASPECT_THUMBNAIL`です。  
  
##  <a name="a-nameongetclipboarddataa--coleserveritemongetclipboarddata"></a><a name="ongetclipboarddata"></a>COleServerItem::OnGetClipboardData  
 取得するためにフレームワークによって呼び出される、`COleDataSource`オブジェクトへの呼び出しによって、クリップボードに配置するとすべてのデータを含む、[置き](#copytoclipboard)メンバー関数。  
  
```  
virtual COleDataSource* OnGetClipboardData(
    BOOL bIncludeLink,  
    LPPOINT lpOffset,  
    LPSIZE lpSize);
```  
  
### <a name="parameters"></a>パラメーター  
 `bIncludeLink`  
 これを設定**TRUE**リンク データをクリップボードにコピーする場合。 これを設定**FALSE**サーバー アプリケーションでは、リンクをサポートしていない場合。  
  
 `lpOffset`  
 マウス ポインターのピクセル単位でオブジェクトの原点からのオフセット。  
  
 `lpSize`  
 ピクセル単位でオブジェクトのサイズ。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [COleDataSource](../../mfc/reference/coledatasource-class.md)クリップボードのデータを格納するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装を呼び出す[GetClipboardData](#getclipboarddata)します。  
  
##  <a name="a-nameongetextenta--coleserveritemongetextent"></a><a name="ongetextent"></a>COleServerItem::OnGetExtent  
 サイズを取得するためにフレームワークによって呼び出されます**HIMETRIC** OLE アイテムの単位です。  
  
```  
virtual BOOL OnGetExtent(
    DVASPECT nDrawAspect,  
    CSize& rSize);
```  
  
### <a name="parameters"></a>パラメーター  
 `nDrawAspect`  
 境界を取得する OLE アイテムの外観を指定します。 このパラメーターは、次の値のいずれかになります。  
  
- `DVASPECT_CONTENT`項目は、そのコンテナー内の埋め込みオブジェクトとして表示できるように表されます。  
  
- `DVASPECT_THUMBNAIL`閲覧ツールで表示されることができるように、「縮小」表現ではアイテムが表示されます。  
  
- `DVASPECT_ICON`項目がアイコンで表されます。  
  
- `DVASPECT_DOCPRINT`[ファイル] メニューから [印刷] コマンドを使用して印刷した場合のように、項目が表されます。  
  
 `rSize`  
 参照、 `CSize` OLE アイテムのサイズを受け取るオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 コンテナー アプリケーションは、Microsoft Foundation Class ライブラリで記述された、この関数が呼び出されますときに、 [GetExtent](../../mfc/reference/coleclientitem-class.md#getextent)対応するメンバー関数`COleClientItem`オブジェクトが呼び出されるとします。 既定の実装では、何も行われません。 実装しなければなりません、自分で。 OLE アイテムのサイズの要求を処理するときに、特別な処理を実行する場合は、この関数をオーバーライドします。  
  
##  <a name="a-nameonhidea--coleserveritemonhide"></a><a name="onhide"></a>COleServerItem::OnHide  
 OLE アイテムを非表示にするために、フレームワークによって呼び出されます。  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>コメント  
 既定の呼び出し**COleServerDoc::OnShowDocument (FALSE)**します。 この関数には、OLE アイテムを非表示にされたコンテナーも通知します。 OLE アイテムを非表示するときに、特別な処理を実行する場合は、この関数をオーバーライドします。  
  
##  <a name="a-nameoninitfromdataa--coleserveritemoninitfromdata"></a><a name="oninitfromdata"></a>COleServerItem::OnInitFromData  
 コンテンツを使用して OLE アイテムを初期化するためにフレームワークによって呼び出されます`pDataObject`します。  
  
```  
virtual BOOL OnInitFromData(
    COleDataObject* pDataObject,  
    BOOL bCreation);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 OLE アイテムを初期化するためのさまざまな形式でデータを含む OLE データ オブジェクトへのポインター。  
  
 `bCreation`  
 **TRUE**コンテナー アプリケーションで新しく作成される OLE アイテムを初期化するために、関数が呼び出されます。 **FALSE**既存の OLE アイテムの内容を置き換える、関数が呼び出されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 場合`bCreation`は**TRUE**コンテナーは、挿入、現在の選択に基づく新しいオブジェクトを実装している場合、この関数が呼び出されます。 選択したデータは、新しい OLE アイテムを作成するときに使用されます。 などのときのスプレッドシート プログラムでセルの範囲を選択し、新しいオブジェクトの挿入を使用してグラフを作成する値に基づいて選択範囲内です。 既定の実装では、何も行われません。 によって提供されるものと、許容される形式を選択するには、この関数をオーバーライド`pDataObject`し、指定したデータに基づいて OLE アイテムを初期化します。 これは、高度なオーバーライドします。  
  
 詳細については、次を参照してください。 [IOleObject::InitFromData](http://msdn.microsoft.com/library/windows/desktop/ms688510)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameonopena--coleserveritemonopen"></a><a name="onopen"></a>COleServerItem::OnOpen  
 配置ではなく、サーバー アプリケーションの別のインスタンスでは、OLE アイテムを表示するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnOpen();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装が OLE アイテムを含むドキュメントを表示する最初のフレーム ウィンドウをアクティブ化します。ミニ サーバーをアプリケーションには、既定の実装では、メイン ウィンドウが表示されます。 この関数には、OLE アイテムが開かれているコンテナーも通知します。  
  
 OLE アイテムを開くときに、特別な処理を実行する場合は、この関数をオーバーライドします。 これは特に、リンク アイテムが開かれたときに、リンクを選択範囲を設定するのには一般的です。  
  
 詳細については、次を参照してください。 [IOleClientSite::OnShowWindow](http://msdn.microsoft.com/library/windows/desktop/ms688658)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameonqueryupdateitemsa--coleserveritemonqueryupdateitems"></a><a name="onqueryupdateitems"></a>COleServerItem::OnQueryUpdateItems  
 現在のサーバーのドキュメント内のすべてのリンクされた項目は古くなっているかどうかを調べるためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnQueryUpdateItems();
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメントの更新の必要なアイテムがある場合は 0 以外。すべての項目が最新の状態の場合は 0。  
  
### <a name="remarks"></a>コメント  
 元のドキュメントが変更されても、ドキュメント内の変更を反映するようにリンクされた項目が更新されていない場合、項目は期限切れです。  
  
##  <a name="a-nameonrenderdataa--coleserveritemonrenderdata"></a><a name="onrenderdata"></a>COleServerItem::OnRenderData  
 指定した形式でデータを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRenderData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)情報が要求された形式を指定します。  
  
 `lpStgMedium`  
 指す、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)データが返される構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定した形式は、1 つに既に配置、`COleDataSource`オブジェクトを使用して、[に](../../mfc/reference/coledatasource-class.md#delayrenderdata)または[DelayRenderFileData](../../mfc/reference/coledatasource-class.md#delayrenderfiledata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装を呼び出す[関数](#onrenderfiledata)または[によって](#onrenderglobaldata)、それぞれ、指定されたストレージ メディアがファイルまたはメモリの場合。 これらの形式のどちらを指定する場合、既定の実装は 0 を返し、何も行われません。  
  
 場合`lpStgMedium` ->  *tymed*は**TYMED_NULL**、 **STGMEDIUM**を割り当てる必要がされ、設定で指定された*tymed-> lpFormatEtc*します。 ない場合**TYMED_NULL**、 **STGMEDIUM**のデータが配置を入力する必要があります。  
  
 これは、高度なオーバーライドします。 要求された形式と媒体で、データを提供するには、この関数をオーバーライドします。 によっては、データを代わりにこの関数の他のバージョンのいずれかを上書きする可能性があります。 データが小さなサイズに固定と容量の場合は、オーバーライド`OnRenderGlobalData`します。 データをファイル内や可変サイズのオーバーライド`OnRenderFileData`します。  
  
 詳細については、次を参照してください。 [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431)、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)、および[TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameonrenderfiledataa--coleserveritemonrenderfiledata"></a><a name="onrenderfiledata"></a>COleServerItem::OnRenderFileData  
 ストレージ メディア ファイルは、指定した形式でデータを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRenderFileData(
    LPFORMATETC lpFormatEtc,  
    CFile* pFile);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)情報が要求された形式を指定します。  
  
 `pFile`  
 指す、`CFile`データが表示されるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定した形式は、1 つに既に配置、`COleDataSource`オブジェクトを使用して、[に](../../mfc/reference/coledatasource-class.md#delayrenderdata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装を返すだけ**FALSE**します。  
  
 これは、高度なオーバーライドします。 要求された形式と媒体で、データを提供するには、この関数をオーバーライドします。 によって、データは、代わりにこの関数の他のバージョンのいずれかをオーバーライドすることができます。 複数のストレージ メディアを処理する場合は、オーバーライド[は](#onrenderdata)です。 データをファイル内や可変サイズのオーバーライド[可変](#onrenderfiledata)します。  
  
 詳細については、次を参照してください。 [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameonrenderglobaldataa--coleserveritemonrenderglobaldata"></a><a name="onrenderglobaldata"></a>COleServerItem::OnRenderGlobalData  
 指定されたストレージ メディアがグローバル メモリのときに、指定した形式でデータを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnRenderGlobalData(
    LPFORMATETC lpFormatEtc,  
    HGLOBAL* phGlobal);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 指す、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)情報が要求された形式を指定します。  
  
 `phGlobal`  
 データが返されるグローバル メモリへのハンドルへのポインター。 メモリが割り当てられていない場合、このパラメーターが指定できます**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定した形式は、1 つに既に配置、`COleDataSource`オブジェクトを使用して、[に](../../mfc/reference/coledatasource-class.md#delayrenderdata)遅延レンダリングするためのメンバー関数。 この関数の既定の実装を返すだけ**FALSE**します。  
  
 場合`phGlobal`は**NULL**から、新規`HGLOBAL`割り当てられで返される必要があります`phGlobal`します。 それ以外の場合、`HGLOBAL`によって指定された`phGlobal`データが格納される必要があります。 内に配置するデータの量、`HGLOBAL`メモリ ブロックの現在のサイズを超えることはできません。 また、ブロックより大きなサイズに再割り当てできることはできません。  
  
 これは、高度なオーバーライドします。 要求された形式と媒体で、データを提供するには、この関数をオーバーライドします。 によっては、データを代わりにこの関数の他のバージョンのいずれかを上書きする可能性があります。 複数のストレージ メディアを処理する場合は、オーバーライド[は](#onrenderdata)です。 データをファイル内や可変サイズのオーバーライド[可変](#onrenderfiledata)します。  
  
 詳細については、次を参照してください。 [IDataObject::GetData](http://msdn.microsoft.com/library/windows/desktop/ms678431)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameonsetcolorschemea--coleserveritemonsetcolorscheme"></a><a name="onsetcolorscheme"></a>COleServerItem::OnSetColorScheme  
 OLE アイテムを編集するときに使用するカラー パレットを指定するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnSetColorScheme(const LOGPALETTE* lpLogPalette);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpLogPalette`  
 Windows へのポインター[保持](http://msdn.microsoft.com/library/windows/desktop/dd145040)構造体。  
  
### <a name="return-value"></a>戻り値  
 カラー パレットを使用する場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 コンテナー アプリケーションは、Microsoft Foundation Class ライブラリを使用して記述された、この関数が呼び出されますときに、 [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971)対応する関数`COleClientItem`オブジェクトが呼び出されるとします。 既定の実装**FALSE**します。 推奨パレットを使用する場合は、この関数をオーバーライドします。 サーバー アプリケーションは、推奨パレットを使用する必要はありません。  
  
 詳細については、次を参照してください。 [IOleObject::SetColorScheme](http://msdn.microsoft.com/library/windows/desktop/ms683971)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameonsetdataa--coleserveritemonsetdata"></a><a name="onsetdata"></a>COleServerItem::OnSetData  
 データを指定して OLE アイテムのデータを置き換えるために、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnSetData(
    LPFORMATETC lpFormatEtc,  
    LPSTGMEDIUM lpStgMedium,  
    BOOL bRelease);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)データの形式を指定します。  
  
 `lpStgMedium`  
 ポインター、 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)データが存在する構造体します。  
  
 `bRelease`  
 関数呼び出しの完了後、ストレージ メディアの所有権を持つことを示します。 呼び出し元では、ストレージ メディアの代わりに割り当てられているリソースを解放する担当者を決定します。 呼び出し元がこれを設定してで`bRelease`します。 場合`bRelease`は&0; 以外の値、サーバーの項目は所有権を取得、使用が完了すると、メディアを解放することです。 `bRelease` 0 は、呼び出し元が所有権を保持およびサーバーの項目は、呼び出しの間でのみストレージ メディアを使用できます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 正常に取得するまで、サーバー項目によるデータの所有権はなりません。 その所有権を持ちません場合は 0 を返します。 呼び出してストレージ メディアを解放してデータ ソースに所有権がある場合は、パラメーター、 [ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491)関数です。  
  
 既定の実装では、何も行われません。 OLE アイテムのデータを指定したデータに置き換えるには、この関数をオーバーライドします。 これは、高度なオーバーライドします。  
  
 詳細については、次を参照してください。 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812)、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)、および[ReleaseStgMedium](http://msdn.microsoft.com/library/windows/desktop/ms693491)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameonsetextenta--coleserveritemonsetextent"></a><a name="onsetextent"></a>COleServerItem::OnSetExtent  
 OLE アイテムには、コンテナー ドキュメント内に利用可能な領域の容量を通知するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnSetExtent(
    DVASPECT nDrawAspect,  
    const CSize& size);
```  
  
### <a name="parameters"></a>パラメーター  
 `nDrawAspect`  
 境界が指定されている OLE アイテムの外観を指定します。 このパラメーターは、次の値のいずれかになります。  
  
- `DVASPECT_CONTENT`項目は、そのコンテナー内の埋め込みオブジェクトとして表示できるように表されます。  
  
- `DVASPECT_THUMBNAIL`閲覧ツールで表示されることができるように、「縮小」表現ではアイテムが表示されます。  
  
- `DVASPECT_ICON`項目がアイコンで表されます。  
  
- `DVASPECT_DOCPRINT`[ファイル] メニューから [印刷] コマンドを使用して印刷した場合のように、項目が表されます。  
  
 `size`  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) OLE アイテムの新しいサイズを指定する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 コンテナー アプリケーションは、Microsoft Foundation Class ライブラリで記述された、この関数が呼び出されますときに、 [SetExtent](../../mfc/reference/coleclientitem-class.md#setextent)対応するメンバー関数`COleClientItem`オブジェクトが呼び出されるとします。 既定の実装設定、[です](#m_sizeextent)メンバーを指定したサイズ場合`nDrawAspect`は`DVASPECT_CONTENT`。 それ以外の場合は 0 を返します。 アイテムのサイズを変更すると、特別な処理を実行するには、この関数をオーバーライドします。  
  
##  <a name="a-nameonshowa--coleserveritemonshow"></a><a name="onshow"></a>COleServerItem::OnShow  
 サーバー アプリケーションで OLE アイテムを表示するように指示するために、フレームワークによって呼び出されます。  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>コメント  
 表示される項目を必要とするコンテナー アプリケーションのユーザーがアイテムの作成や編集などの動詞を実行時に、この関数は通常呼び出されます。 既定の実装では、インプレース アクティブ化しようとします。 失敗したかどうか、関数呼び出し、 `OnOpen` OLE アイテムを別のウィンドウに表示するメンバー関数。  
  
 OLE アイテムを表示するときに、特別な処理を実行する場合は、この関数をオーバーライドします。  
  
##  <a name="a-nameonupdatea--coleserveritemonupdate"></a><a name="onupdate"></a>COleServerItem::OnUpdate  
 項目が変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnUpdate(
    COleServerItem* pSender,  
    LPARAM lHint,  
    CObject* pHint,  
    DVASPECT nDrawAspect);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSender`  
 ドキュメントを変更する項目へのポインター。 できる**NULL**します。  
  
 `lHint`  
 変更に関する情報が含まれています。  
  
 `pHint`  
 変更に関する情報を格納するオブジェクトへのポインター。  
  
 `nDrawAspect`  
 `DVASPECT` 列挙体の値。 このパラメーターには、次の値のいずれかがあります。  
  
- `DVASPECT_CONTENT`項目は、そのコンテナー内の埋め込みオブジェクトとして表示できるように表されます。  
  
- `DVASPECT_THUMBNAIL`閲覧ツールで表示されることができるように、「縮小」表現ではアイテムが表示されます。  
  
- `DVASPECT_ICON`項目がアイコンで表されます。  
  
- `DVASPECT_DOCPRINT`[ファイル] メニューから [印刷] コマンドを使用して印刷した場合のように、項目が表されます。  
  
### <a name="remarks"></a>コメント  
 既定の実装[NotifyChanged](#notifychanged)ヒントや送信者に関係なく。  
  
##  <a name="a-nameonupdateitemsa--coleserveritemonupdateitems"></a><a name="onupdateitems"></a>COleServerItem::OnUpdateItems  
 サーバー ドキュメントのすべてのアイテムを更新するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnUpdateItems();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装[UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink)すべて`COleClientItem`ドキュメント内のオブジェクト。  
  
##  <a name="a-namesetitemnamea--coleserveritemsetitemname"></a><a name="setitemname"></a>COleServerItem::SetItemName  
 その名前を設定するリンクされた項目を作成するときに、この関数を呼び出します。  
  
```  
void SetItemName(LPCTSTR lpszItemName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszItemName`  
 項目の新しい名前へのポインター。  
  
### <a name="remarks"></a>コメント  
 名前は、ドキュメント内で一意である必要があります。 リンクされた項目を編集するサーバー アプリケーションが呼び出されると、アプリケーションはこの名前を使用して、項目を検索します。 埋め込みアイテムに対してこの関数を呼び出す必要はありません。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [CDocItem クラス](../../mfc/reference/cdocitem-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)   
 [COleServerDoc クラス](../../mfc/reference/coleserverdoc-class.md)   
 [関数のクラス](../../mfc/reference/coletemplateserver-class.md)

