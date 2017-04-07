---
title: "COleClientItem クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleClientItem
- AFXOLE/COleClientItem
- AFXOLE/COleClientItem::COleClientItem
- AFXOLE/COleClientItem::Activate
- AFXOLE/COleClientItem::ActivateAs
- AFXOLE/COleClientItem::AttachDataObject
- AFXOLE/COleClientItem::CanCreateFromData
- AFXOLE/COleClientItem::CanCreateLinkFromData
- AFXOLE/COleClientItem::CanPaste
- AFXOLE/COleClientItem::CanPasteLink
- AFXOLE/COleClientItem::Close
- AFXOLE/COleClientItem::ConvertTo
- AFXOLE/COleClientItem::CopyToClipboard
- AFXOLE/COleClientItem::CreateCloneFrom
- AFXOLE/COleClientItem::CreateFromClipboard
- AFXOLE/COleClientItem::CreateFromData
- AFXOLE/COleClientItem::CreateFromFile
- AFXOLE/COleClientItem::CreateLinkFromClipboard
- AFXOLE/COleClientItem::CreateLinkFromData
- AFXOLE/COleClientItem::CreateLinkFromFile
- AFXOLE/COleClientItem::CreateNewItem
- AFXOLE/COleClientItem::CreateStaticFromClipboard
- AFXOLE/COleClientItem::CreateStaticFromData
- AFXOLE/COleClientItem::Deactivate
- AFXOLE/COleClientItem::DeactivateUI
- AFXOLE/COleClientItem::Delete
- AFXOLE/COleClientItem::DoDragDrop
- AFXOLE/COleClientItem::DoVerb
- AFXOLE/COleClientItem::Draw
- AFXOLE/COleClientItem::GetActiveView
- AFXOLE/COleClientItem::GetCachedExtent
- AFXOLE/COleClientItem::GetClassID
- AFXOLE/COleClientItem::GetClipboardData
- AFXOLE/COleClientItem::GetDocument
- AFXOLE/COleClientItem::GetDrawAspect
- AFXOLE/COleClientItem::GetExtent
- AFXOLE/COleClientItem::GetIconFromRegistry
- AFXOLE/COleClientItem::GetIconicMetafile
- AFXOLE/COleClientItem::GetInPlaceWindow
- AFXOLE/COleClientItem::GetItemState
- AFXOLE/COleClientItem::GetLastStatus
- AFXOLE/COleClientItem::GetLinkUpdateOptions
- AFXOLE/COleClientItem::GetType
- AFXOLE/COleClientItem::GetUserType
- AFXOLE/COleClientItem::IsInPlaceActive
- AFXOLE/COleClientItem::IsLinkUpToDate
- AFXOLE/COleClientItem::IsModified
- AFXOLE/COleClientItem::IsOpen
- AFXOLE/COleClientItem::IsRunning
- AFXOLE/COleClientItem::OnActivate
- AFXOLE/COleClientItem::OnActivateUI
- AFXOLE/COleClientItem::OnChange
- AFXOLE/COleClientItem::OnDeactivate
- AFXOLE/COleClientItem::OnDeactivateUI
- AFXOLE/COleClientItem::OnGetClipboardData
- AFXOLE/COleClientItem::OnInsertMenus
- AFXOLE/COleClientItem::OnRemoveMenus
- AFXOLE/COleClientItem::OnSetMenu
- AFXOLE/COleClientItem::OnShowControlBars
- AFXOLE/COleClientItem::OnUpdateFrameTitle
- AFXOLE/COleClientItem::ReactivateAndUndo
- AFXOLE/COleClientItem::Release
- AFXOLE/COleClientItem::Reload
- AFXOLE/COleClientItem::Run
- AFXOLE/COleClientItem::SetDrawAspect
- AFXOLE/COleClientItem::SetExtent
- AFXOLE/COleClientItem::SetHostNames
- AFXOLE/COleClientItem::SetIconicMetafile
- AFXOLE/COleClientItem::SetItemRects
- AFXOLE/COleClientItem::SetLinkUpdateOptions
- AFXOLE/COleClientItem::SetPrintDevice
- AFXOLE/COleClientItem::UpdateLink
- AFXOLE/COleClientItem::CanActivate
- AFXOLE/COleClientItem::OnChangeItemPosition
- AFXOLE/COleClientItem::OnDeactivateAndUndo
- AFXOLE/COleClientItem::OnDiscardUndoState
- AFXOLE/COleClientItem::OnGetClipRect
- AFXOLE/COleClientItem::OnGetItemPosition
- AFXOLE/COleClientItem::OnGetWindowContext
- AFXOLE/COleClientItem::OnScrollBy
- AFXOLE/COleClientItem::OnShowItem
dev_langs:
- C++
helpviewer_keywords:
- OLE containers, client items
- COleClientItem class
- OLE client item class
- container interface class
- OLE containers, interface class
- client items and OLE containers
ms.assetid: 7f571b7c-2758-4839-847a-0cf1ef643128
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a200da03305c20eaf2d9c1de1ea585c82410c570
ms.lasthandoff: 02/24/2017

---
# <a name="coleclientitem-class"></a>COleClientItem クラス
OLE アイテムへのコンテナー インターフェイスを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleClientItem : public CDocItem  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleClientItem::COleClientItem](#coleclientitem)|`COleClientItem` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleClientItem::Activate](#activate)|操作の OLE アイテムを開き、指定した動詞を実行します。|  
|[COleClientItem::ActivateAs](#activateas)|別の種類としては、アイテムをアクティブになります。|  
|[COleClientItem::AttachDataObject](#attachdataobject)|OLE オブジェクトのデータにアクセスします。|  
|[COleClientItem::CanCreateFromData](#cancreatefromdata)|コンテナー アプリケーションが、埋め込みオブジェクトを作成できるかどうかを示します。|  
|[COleClientItem::CanCreateLinkFromData](#cancreatelinkfromdata)|コンテナー アプリケーションがリンクされているオブジェクトを作成できるかどうかを示します。|  
|[置き換えるには](#canpaste)|クリップボードに組み込み可能なまたは静的な OLE アイテムが含まれているかどうかを示します。|  
|[置き換えるには](#canpastelink)|クリップボードにリンク可能な OLE アイテムが含まれているかどうかを示します。|  
|[COleClientItem::Close](#close)|サーバーへのリンクを閉じますが、OLE アイテムは破棄しません。|  
|[COleClientItem::ConvertTo](#convertto)|アイテムを別の型に変換します。|  
|[COleClientItem::CopyToClipboard](#copytoclipboard)|OLE アイテムをクリップボードにコピーします。|  
|[COleClientItem::CreateCloneFrom](#createclonefrom)|既存の項目の複製を作成します。|  
|[COleClientItem::CreateFromClipboard](#createfromclipboard)|クリップボードから埋め込みアイテムを作成します。|  
|[COleClientItem::CreateFromData](#createfromdata)|データ オブジェクトから埋め込みアイテムを作成します。|  
|[COleClientItem::CreateFromFile](#createfromfile)|ファイルから埋め込みアイテムを作成します。|  
|[リンク](#createlinkfromclipboard)|クリップボードからリンクされた項目を作成します。|  
|[COleClientItem::CreateLinkFromData](#createlinkfromdata)|データ オブジェクトからリンクされた項目を作成します。|  
|[COleClientItem::CreateLinkFromFile](#createlinkfromfile)|ファイルからリンクされた項目を作成します。|  
|[COleClientItem::CreateNewItem](#createnewitem)|サーバー アプリケーションを起動して新しい埋め込みアイテムを作成します。|  
|[COleClientItem::CreateStaticFromClipboard](#createstaticfromclipboard)|クリップボードの静的な項目を作成します。|  
|[COleClientItem::CreateStaticFromData](#createstaticfromdata)|データ オブジェクトから、静的な項目を作成します。|  
|[COleClientItem::Deactivate](#deactivate)|アイテムを非アクティブにします。|  
|[COleClientItem::DeactivateUI](#deactivateui)|コンテナー アプリケーションのユーザー インターフェイスを元の状態に復元します。|  
|[COleClientItem::Delete](#delete)|削除するか、リンクされた項目があった場合は、OLE アイテムを閉じます。|  
|[クラス](#dodragdrop)|ドラッグ アンド ドロップ操作を実行します。|  
|[COleClientItem::DoVerb](#doverb)|指定した動詞を実行します。|  
|[値](#draw)|OLE アイテムを描画します。|  
|[COleClientItem::GetActiveView](#getactiveview)|場所に項目がアクティブにビューを取得します。|  
|[COleClientItem::GetCachedExtent](#getcachedextent)|OLE アイテムの四角形の境界を返します。|  
|[COleClientItem::GetClassID](#getclassid)|現在のアイテムのクラス ID を取得します|  
|[COleClientItem::GetClipboardData](#getclipboarddata)|呼び出して、クリップボードに配置すると、データの取得、`CopyToClipboard`メンバー関数。|  
|[COleClientItem::GetDocument](#getdocument)|返します。、`COleDocument`を現在のアイテムを含むオブジェクト。|  
|[COleClientItem::GetDrawAspect](#getdrawaspect)|表示のアイテムの現在のビューを取得します。|  
|[COleClientItem::GetExtent](#getextent)|OLE アイテムの四角形の境界を返します。|  
|[COleClientItem::GetIconFromRegistry](#geticonfromregistry)|特定の CLSID のサーバーに関連付けられているアイコンへのハンドルを取得します。|  
|[COleClientItem::GetIconicMetafile](#geticonicmetafile)|項目のアイコンを描画するために使われるメタファイルを取得します。|  
|[COleClientItem::GetInPlaceWindow](#getinplacewindow)|項目の一括編集ウィンドウへのポインターを返します。|  
|[COleClientItem::GetItemState](#getitemstate)|アイテムの現在の状態を取得します。|  
|[COleClientItem::GetLastStatus](#getlaststatus)|最後の OLE 操作のステータスを返します。|  
|[COleClientItem::GetLinkUpdateOptions](#getlinkupdateoptions)|リンクされた項目 (高度な機能) の更新モードを返します。|  
|[COleClientItem::GetType](#gettype)|OLE アイテムの種類 (埋め込まれた、リンク、または静的) を返します。|  
|[COleClientItem::GetUserType](#getusertype)|項目の型を記述する文字列を取得します。|  
|[COleClientItem::IsInPlaceActive](#isinplaceactive)|返します。`TRUE`アイテムがアクティブである場合。|  
|[COleClientItem::IsLinkUpToDate](#islinkuptodate)|返します。 **TRUE**場合は、リンクされた項目がソース ドキュメント内で最新の状態。|  
|[COleClientItem::IsModified](#ismodified)|返します。`TRUE`項目が最後に保存されてから変更された場合。|  
|[COleClientItem::IsOpen](#isopen)|返します。`TRUE`項目が、サーバー アプリケーションで現在開いている場合。|  
|[COleClientItem::IsRunning](#isrunning)|返します。`TRUE`アイテムのサーバー アプリケーションが実行されている場合。|  
|[COleClientItem::OnActivate](#onactivate)|アクティブ化されるアイテムを通知するためにフレームワークによって呼び出されます。|  
|[COleClientItem::OnActivateUI](#onactivateui)|アクティブになり、そのユーザー インターフェイスを表示する必要がありますが、アイテムを通知するためにフレームワークによって呼び出されます。|  
|[として](#onchange)|サーバーに OLE アイテムが変更されたときに呼び出されます。 必要な実装です。|  
|[COleClientItem::OnDeactivate](#ondeactivate)|項目が非アクティブ化されたときに、フレームワークによって呼び出されます。|  
|[COleClientItem::OnDeactivateUI](#ondeactivateui)|サーバーに、埋め込み先ユーザー インターフェイスが削除されることがある場合に、フレームワークによって呼び出されます。|  
|[COleClientItem::OnGetClipboardData](#ongetclipboarddata)|クリップボードにコピーするデータを取得するためにフレームワークによって呼び出されます。|  
|[COleClientItem::OnInsertMenus](#oninsertmenus)|複合メニューを作成するために、フレームワークによって呼び出されます。|  
|[COleClientItem::OnRemoveMenus](#onremovemenus)|複合のメニューから、コンテナーのメニューを削除するために、フレームワークによって呼び出されます。|  
|[COleClientItem::OnSetMenu](#onsetmenu)|インストールおよびコンポジット メニューを削除するために、フレームワークによって呼び出されます。|  
|[COleClientItem::OnShowControlBars](#onshowcontrolbars)|コントロール バーを非表示にしたりするためにフレームワークによって呼び出されます。|  
|[COleClientItem::OnUpdateFrameTitle](#onupdateframetitle)|フレーム ウィンドウのタイトル バーを更新するためにフレームワークによって呼び出されます。|  
|[COleClientItem::ReactivateAndUndo](#reactivateandundo)|アイテムを再アクティブ化し、最後のインプレース編集操作を元に戻します。|  
|[COleClientItem::Release](#release)|OLE リンク アイテムへの接続を解放しが開いていた場合に終了します。 クライアント アイテムは破棄されません。|  
|[COleClientItem::Reload](#reload)|呼び出した後、項目を再読み込み`ActivateAs`します。|  
|[COleClientItem::Run](#run)|アイテムに関連付けられているアプリケーションを実行します。|  
|[COleClientItem::SetDrawAspect](#setdrawaspect)|表示するため、項目の現在のビューを設定します。|  
|[COleClientItem::SetExtent](#setextent)|OLE 項目の外接する四角形を設定します。|  
|[COleClientItem::SetHostNames](#sethostnames)|OLE アイテムを編集するときに、サーバーが表示名を設定します。|  
|[COleClientItem::SetIconicMetafile](#seticonicmetafile)|項目のアイコンを描画するために使われるメタファイルをキャッシュします。|  
|[COleClientItem::SetItemRects](#setitemrects)|項目の外接する四角形を設定します。|  
|[COleClientItem::SetLinkUpdateOptions](#setlinkupdateoptions)|リンクされた項目 (高度な機能) の更新モードを設定します。|  
|[COleClientItem::SetPrintDevice](#setprintdevice)|このクライアント アイテムの出力先のデバイスを設定します。|  
|[COleClientItem::UpdateLink](#updatelink)|アイテムのプレゼンテーションのキャッシュを更新します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleClientItem::CanActivate](#canactivate)|インプレース アクティブ化が使用できるかどうかを判断するためにフレームワークによって呼び出されます。|  
|[に](#onchangeitemposition)|アイテムの位置が変更されたときに、フレームワークによって呼び出されます。|  
|[COleClientItem::OnDeactivateAndUndo](#ondeactivateandundo)|アクティブ化の後に元に戻すために、フレームワークによって呼び出されます。|  
|[COleClientItem::OnDiscardUndoState](#ondiscardundostate)|アイテムの元に戻す状態情報を破棄するためにフレームワークによって呼び出されます。|  
|[COleClientItem::OnGetClipRect](#ongetcliprect)|アイテムのクリッピング四角形の座標を取得するためにフレームワークによって呼び出されます。|  
|[状態](#ongetitemposition)|ビューに、項目の位置を取得するために、フレームワークによって呼び出されます。|  
|[COleClientItem::OnGetWindowContext](#ongetwindowcontext)|アイテムは場所にアクティブになったときに、フレームワークによって呼び出されます。|  
|[COleClientItem::OnScrollBy](#onscrollby)|アイテムをスクロールして表示するためにフレームワークによって呼び出されます。|  
|[COleClientItem::OnShowItem](#onshowitem)|OLE アイテムを表示するためにフレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 OLE アイテムでは、データを作成して保守する「シームレス」に組み込むことがドキュメントを&1; つのドキュメントをユーザーに表示されるように、サーバーのアプリケーションを表します。 OLE アイテムとを含むドキュメントから成ります「複合ドキュメント」になります。  
  
 OLE アイテムでは、する、埋め込まれているか、またはリンクできます。 埋め込まれている場合、複合ドキュメントの一部として、データが格納されます。 リンクされている場合は、サーバー アプリケーションで作成された別のファイルの一部として、データが保存され、複合ドキュメントにそのファイルへのリンクのみが格納されています。 すべての OLE アイテムには、編集するサーバー アプリケーションを指定する情報が含まれます。  
  
 `COleClientItem`サーバー アプリケーションからの要求に応答と呼ばれるいくつかのオーバーライド可能な関数を定義します。これらのオーバーライド可能な関数は、通常、通知として機能します。 これにより、サーバー アプリケーションは OLE アイテムを編集するときに、ユーザーが行った変更のコンテナーに通知する、または編集するときに必要な情報を取得します。  
  
 `COleClientItem`いずれかと併用して、 [COleDocument](../../mfc/reference/coledocument-class.md)、[直接](../../mfc/reference/colelinkingdoc-class.md)、または[COleServerDoc](../../mfc/reference/coleserverdoc-class.md)クラスです。 使用する`COleClientItem`、クラスの派生、および実装、 [OnChange](#onchange)メンバー関数は、コンテナーをアイテムに加えられた変更に応答する方法を定義します。 インプレース アクティブ化をサポートするためにオーバーライド、[埋め込み](#ongetitemposition)メンバー関数。 この関数は、OLE アイテムの表示位置に関する情報を提供します。  
  
 詳細については、コンテナー インターフェイスを使用して、記事を参照してください。[コンテナー: コンテナーの実装](../../mfc/containers-implementing-a-container.md)と[アクティベーション](../../mfc/activation-cpp.md)します。  
  
> [!NOTE]
>  [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 「オブジェクト」としての埋め込みとリンク アイテムには、「クラス」と項目の種類を指して このリファレンスでは、"item"という用語を使用して、OLE のエンティティを対応する C++ オブジェクトや C++ クラス OLE カテゴリを区別するためには、"type"という用語と区別します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleClientItem`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="activate"></a>COleClientItem::Activate  
 代わりに、指定した動詞を実行するには、この関数を呼び出す[DoVerb](#doverb)できるように、例外がスローされたときに、独自の処理を行うことができます。  
  
```  
void Activate(
    LONG nVerb,  
    CView* pView,  
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nVerb`  
 実行する動詞を指定します。 次のいずれかを指定できます。  
  
|値|説明|シンボル|  
|-----------|-------------|------------|  
|– 0|主動詞|`OLEIVERB_PRIMARY`|  
|– 1|セカンダリ動詞|(なし)|  
|– 1|編集するための表示項目|`OLEIVERB_SHOW`|  
|– 2|別のウィンドウで項目を編集します。|`OLEIVERB_OPEN`|  
|– 3|アイテムを非表示します。|`OLEIVERB_HIDE`|  
  
 –&1; の値は、通常、他の動詞のエイリアスです。 編集のオープンがサポートされていない場合、–&2; は-1 と同じ効果を持ちます。 その他の値を参照してください。 [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `pView`  
 OLE アイテムを保持するコンテナーの表示ウィンドウへのポインターインプレースでライセンス認証のため、サーバー アプリケーションによって使用されます。 このパラメーターを指定する必要があります**NULL**コンテナーは、インプレース アクティブ化をサポートしていない場合。  
  
 `lpMsg`  
 アクティブ化する項目を原因となったメッセージへのポインター。  
  
### <a name="remarks"></a>コメント  
 サーバー アプリケーションは、Microsoft Foundation Class ライブラリを使用して記述された、この関数を実行すると、 [OnDoVerb](../../mfc/reference/coleserveritem-class.md#ondoverb)対応するメンバー関数`COleServerItem`実行されるオブジェクト。  
  
 主動詞がおよびで&0; が指定されているかどうか、 `nVerb` OLE アイテムを編集することを許可するようにパラメーター、サーバー アプリケーションを起動します。 コンテナー アプリケーションでは、インプレース アクティブ化をサポートする場合に編集を実行できます。 コンテナーは、インプレース アクティブ化 (または Open 動詞が指定されているかどうか) をサポートしていない、独立したウィンドウで、サーバーが起動し、編集行われます。 通常は、コンテナー アプリケーションのユーザーがプライマリ動詞の値である OLE アイテムをダブルクリックすると、`nVerb`パラメーターは、ユーザーが実行できるアクションを決定します。 ただし、サーバーは、1 つだけの操作をサポートする場合は、その操作で指定された値に関係なく、`nVerb`パラメーター。  
  
 詳細については、次を参照してください。 [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="activateas"></a>COleClientItem::ActivateAs  
 OLE のオブジェクトの変換機能を使用して、指定された型の項目と同様に、項目をアクティブに`clsidNew`します。  
  
```  
virtual BOOL ActivateAs(
    LPCTSTR lpszUserType,  
    REFCLSID clsidOld,  
    REFCLSID clsidNew);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszUserType*  
 「Word 文書」などのターゲット ユーザーの種類を表す文字列へのポインター  
  
 *clsidOld*  
 アイテムの現在のクラスへの参照の id。 クラス ID にリンクがある場合を除いては、格納されている実際のオブジェクトの種類を表す必要があります。 その場合は、リンクが参照する項目の CLSID ができます。 [メンバー](../../mfc/reference/coleconvertdialog-class.md)項目の適切なクラス ID を自動的に提供します。  
  
 `clsidNew`  
 対象のクラス ID への参照  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 これはによって自動的に呼び出されます[COleConvertDialog::DoConvert](../../mfc/reference/coleconvertdialog-class.md#doconvert)します。 これは通常呼び出されません直接。  
  
##  <a name="attachdataobject"></a>COleClientItem::AttachDataObject  
 初期化するには、この関数を呼び出して、 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE アイテム内のデータにアクセスするためです。  
  
```  
void AttachDataObject(COleDataObject& rDataObject) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *rDataObject*  
 参照、 `COleDataObject` OLE アイテムのデータへのアクセスを許可するように初期化されるオブジェクト。  
  
##  <a name="canactivate"></a>COleClientItem::CanActivate  
 OLE アイテムのインプレース アクティブ化を要求すると、フレームワークによって呼び出されますこの関数の戻り値は、インプレース アクティブ化が許可されているかどうかを決定します。  
  
```  
virtual BOOL CanActivate();
```  
  
### <a name="return-value"></a>戻り値  
 インプレース アクティブ化が使用できる場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装は、コンテナーに有効なウィンドウがある場合、インプレース アクティブ化を使用します。 受け入れるか、またはアクティブ化要求を拒否の特別なロジックを実装するには、この関数をオーバーライドします。 たとえば、OLE アイテムが小さすぎるか、現在表示されていない場合は、ライセンス認証要求を拒否する可能性がします。  
  
 詳細については、次を参照してください。 [IOleInPlaceSite::CanInPlaceActivate](http://msdn.microsoft.com/library/windows/desktop/ms691236)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="cancreatefromdata"></a>COleClientItem::CanCreateFromData  
 コンテナー アプリケーションの埋め込みオブジェクトを作成できるかどうかを調べます、指定された`COleDataObject`オブジェクトです。  
  
```  
static BOOL PASCAL CanCreateFromData(const COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 ポインター、 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE アイテムを作成する元となるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 コンテナーは、埋め込みオブジェクトを作成できる場合は 0 以外、`COleDataObject`オブジェクト。 それ以外の場合、0 です。  
  
### <a name="remarks"></a>コメント  
 `COleDataObject`クラスは、ドラッグ アンド ドロップをクリップボードや OLE 埋め込みアイテムからさまざまな形式でデータを取得するためのデータ転送に使用します。  
  
 コンテナーは、この関数を使用して、有効にするか、貼り付け、編集貼り付けコマンドを無効にすることです。  
  
 詳細については、記事を参照してください。[データ オブジェクトとデータ ソース (OLE)](../../mfc/data-objects-and-data-sources-ole.md)します。  
  
##  <a name="cancreatelinkfromdata"></a>COleClientItem::CanCreateLinkFromData  
 コンテナー アプリケーションからのリンクされたオブジェクトを作成できるかどうかを調べます、指定された`COleDataObject`オブジェクトです。  
  
```  
static BOOL PASCAL CanCreateLinkFromData(const COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 ポインター、 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE アイテムを作成する元となるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 コンテナーからのリンクされたオブジェクトを作成できる場合は&0; 以外、`COleDataObject`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 `COleDataObject`クラスは、ドラッグ アンド ドロップをクリップボードや OLE 埋め込みアイテムからさまざまな形式でデータを取得するためのデータ転送に使用します。  
  
 コンテナーは、この関数を使用して、有効またはそれを編集して貼り付け、リンクの編集コマンドを無効にすることできます。  
  
 詳細については、記事を参照してください。[データ オブジェクトとデータ ソース (OLE)](../../mfc/data-objects-and-data-sources-ole.md)します。  
  
##  <a name="canpaste"></a>置き換えるには  
 この関数では、OLE 埋め込みアイテムをクリップボードから貼り付けできるかどうかを参照してください。  
  
```  
static BOOL PASCAL CanPaste();
```  
  
### <a name="return-value"></a>戻り値  
 OLE 埋め込みアイテムをクリップボードから貼り付けできる場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [OleGetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms692778)と[OleQueryCreateFromData](http://msdn.microsoft.com/library/windows/desktop/ms683739)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="canpastelink"></a>置き換えるには  
 この関数では、リンクされている OLE アイテムをクリップボードから貼り付けできるかどうかを参照してください。  
  
```  
static BOOL PASCAL CanPasteLink();
```  
  
### <a name="return-value"></a>戻り値  
 OLE のリンク アイテムをクリップボードから貼り付けできる場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [OleGetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms692778)と[OleQueryLinkFromData](http://msdn.microsoft.com/library/windows/desktop/ms690244)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="close"></a>COleClientItem::Close  
 メモリ内には、そのハンドラーが実行されていないサーバーをロードは、読み込まれた状態に、実行中の状態から OLE アイテムの状態を変更するには、この関数を呼び出します。  
  
```  
void Close(OLECLOSE dwCloseOption = OLECLOSE_SAVEIFDIRTY);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCloseOption`  
 読み込み済み状態に戻すときに保存する OLE アイテムどのような状況を指定するフラグを設定します。 次の値のいずれかを取ります。  
  
- `OLECLOSE_SAVEIFDIRTY`OLE アイテムを保存します。  
  
- `OLECLOSE_NOSAVE`OLE アイテムを保存しません。  
  
- `OLECLOSE_PROMPTSAVE`OLE アイテムを保存するかどうかをユーザーに問い合わせます。  
  
### <a name="remarks"></a>コメント  
 OLE アイテムが実行されていない場合は、この関数を指定しても効果はありません。  
  
 詳細については、次を参照してください。 [IOleObject::Close](http://msdn.microsoft.com/library/windows/desktop/ms683922)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="coleclientitem"></a>COleClientItem::COleClientItem  
 構築、`COleClientItem`オブジェクトし、C++ オブジェクトのみを構築し、OLE の初期化は行われませんドキュメント アイテムのコンテナー ドキュメントのコレクションに追加します。  
  
```  
COleClientItem(COleDocument* pContainerDoc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pContainerDoc`  
 この項目を格納するコンテナー ドキュメントへのポインター。 [COleDocument](../../mfc/reference/coledocument-class.md)から派生します。  
  
### <a name="remarks"></a>コメント  
 渡した場合、 **NULL**ポインターの追加は行いませんコンテナー ドキュメントです。 明示的に呼び出す必要があります[COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem)します。  
  
 OLE アイテムを使用する前に、次の作成のメンバー関数のいずれかを呼び出す必要があります。  
  
- [一般的に](#createfromclipboard)  
  
- [CreateFromData](#createfromdata)  
  
- [CreateFromFile](#createfromfile)  
  
- [関数](#createstaticfromclipboard)  
  
- [CreateStaticFromData](#createstaticfromdata)  
  
- [CreateLinkFromClipboard](#createlinkfromclipboard)  
  
- [CreateLinkFromData](#createlinkfromdata)  
  
- [CreateLinkFromFile](#createlinkfromfile)  
  
- [CreateNewItem](#createnewitem)  
  
- [CreateCloneFrom](#createclonefrom)  
  
##  <a name="convertto"></a>COleClientItem::ConvertTo  
 このメンバー関数を呼び出して指定された型に変換してから`clsidNew`します。  
  
```  
virtual BOOL ConvertTo(REFCLSID clsidNew);
```  
  
### <a name="parameters"></a>パラメーター  
 `clsidNew`  
 対象の型のクラス ID。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 これはによって自動的に呼び出されます[メンバー](../../mfc/reference/coleconvertdialog-class.md)します。 メソッドを直接呼び出す必要はありません。  
  
##  <a name="copytoclipboard"></a>COleClientItem::CopyToClipboard  
 OLE アイテムをクリップボードにコピーするには、この関数を呼び出します。  
  
```  
void CopyToClipboard(BOOL bIncludeLink = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bIncludeLink`  
 **TRUE**リンク情報をクリップボードにコピーする場合は、貼り付けられた、それ以外のリンクされた項目を許可する**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 通常、[編集] メニューからコピーまたは切り取りコマンドは、メッセージのハンドラーを記述するときは、この関数を呼び出します。 コピーまたは切り取りコマンドを実装する場合は、コンテナー アプリケーションで項目の選択を実装する必要があります。  
  
 詳細については、次を参照してください。 [OleSetClipboard](http://msdn.microsoft.com/library/windows/desktop/ms686623)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="createclonefrom"></a>COleClientItem::CreateCloneFrom  
 指定した OLE アイテムのコピーを作成するには、この関数を呼び出します。  
  
```  
BOOL CreateCloneFrom(const COleClientItem* pSrcItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *pSrcItem*  
 重複する OLE アイテムへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 コピーは、元の項目と同じです。 この関数は、元に戻す操作をサポートするために使用できます。  
  
##  <a name="createfromclipboard"></a>COleClientItem::CreateFromClipboard  
 クリップボードの内容から埋め込みアイテムを作成するには、この関数を呼び出します。  
  
```  
BOOL CreateFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *レンダリング*  
 サーバーが OLE アイテムを表示する方法を指定するフラグ。 有効な値を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `cfFormat`  
 OLE アイテムの作成時にキャッシュされるクリップボード データ形式を指定します。  
  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)場合に使用される構造体*レンダリング*は**OLERENDER_FORMAT**または**OLERENDER_DRAW**します。 クリップボードの形式で指定した以外の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`します。 このパラメーターを省略した場合、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 通常の編集 メニューの 貼り付け コマンド メッセージ ハンドラーからこの関数を呼び出します。 (場合に、フレームワークによって [貼り付け] コマンドが有効になって、 [CanPaste](#canpaste)メンバー関数は&0; 以外を返します)。  
  
 詳細については、次を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="createfromdata"></a>COleClientItem::CreateFromData  
 埋め込みアイテムを作成するには、この関数を呼び出して、`COleDataObject`オブジェクトです。  
  
```  
BOOL CreateFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 ポインター、 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE アイテムを作成する元となるオブジェクト。  
  
 *レンダリング*  
 サーバーが OLE アイテムを表示する方法を指定するフラグ。 有効な値を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `cfFormat`  
 OLE アイテムの作成時にキャッシュされるクリップボード データ形式を指定します。  
  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)場合に使用される構造体*レンダリング*は**OLERENDER_FORMAT**または**OLERENDER_DRAW**します。 クリップボードの形式で指定した以外の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`します。 このパラメーターを省略した場合、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 貼り付け、クリップボード操作やドラッグ アンド ドロップ操作のなどのデータ転送操作を提供`COleDataObject`サーバー アプリケーションによって提供される情報を含むオブジェクトします。 通常は、オーバーライド、使用[この関数](../../mfc/reference/cview-class.md#ondrop)します。  
  
 詳細については、次を参照してください。 [OleCreateFromData](http://msdn.microsoft.com/library/windows/desktop/ms691211)、 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)、および[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="createfromfile"></a>COleClientItem::CreateFromFile  
 ファイルから埋め込み OLE アイテムを作成するには、この関数を呼び出します。  
  
```  
BOOL CreateFromFile(
    LPCTSTR lpszFileName,  
    REFCLSID clsid = CLSID_NULL,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFileName`  
 OLE アイテムを作成する元となるファイルの名前へのポインター。  
  
 `clsid`  
 将来使用するために予約されています。  
  
 *レンダリング*  
 サーバーが OLE アイテムを表示する方法を指定するフラグ。 有効な値を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `cfFormat`  
 OLE アイテムの作成時にキャッシュされるクリップボード データ形式を指定します。  
  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)場合に使用される構造体*レンダリング*は**OLERENDER_FORMAT**または**OLERENDER_DRAW**します。 クリップボードの形式で指定した以外の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`します。 このパラメーターを省略した場合、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、この関数から[クリック](../../mfc/reference/coleinsertdialog-class.md#createitem)場合は、ファイルから作成を選択すると、ユーザーがオブジェクトの挿入ダイアログ ボックスから [ok] を選択します。  
  
 詳細については、次を参照してください。 [OleCreateFromFile](http://msdn.microsoft.com/library/windows/desktop/ms690116)、 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)、および[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="createlinkfromclipboard"></a>リンク  
 クリップボードの内容からリンクされた項目を作成するには、この関数を呼び出します。  
  
```  
BOOL CreateLinkFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *レンダリング*  
 サーバーが OLE アイテムを表示する方法を指定するフラグ。 有効な値を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `cfFormat`  
 OLE アイテムの作成時にキャッシュされるクリップボード データ形式を指定します。  
  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)場合に使用される構造体*レンダリング*は**OLERENDER_FORMAT**または**OLERENDER_DRAW**します。 クリップボードの形式で指定した以外の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`します。 このパラメーターを省略した場合、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 通常の編集] メニューの [リンク貼り付けコマンド メッセージ ハンドラーからこの関数を呼び出します。 (の既定の実装でリンク貼り付け コマンドが有効になっている[COleDocument](../../mfc/reference/coledocument-class.md)クリップボードに OLE アイテムにリンクが含まれている場合)。  
  
 詳細については、次を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="createlinkfromdata"></a>COleClientItem::CreateLinkFromData  
 リンクされた項目を作成するには、この関数を呼び出して、`COleDataObject`オブジェクトです。  
  
```  
BOOL CreateLinkFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 ポインター、 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE アイテムを作成する元となるオブジェクト。  
  
 *レンダリング*  
 サーバーが OLE アイテムを表示する方法を指定するフラグ。 有効な値を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `cfFormat`  
 OLE アイテムの作成時にキャッシュされるクリップボード データ形式を指定します。  
  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)場合に使用される構造体*レンダリング*は**OLERENDER_FORMAT**または**OLERENDER_DRAW**します。 クリップボードの形式で指定した以外の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`します。 このパラメーターを省略した場合、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出しがこのユーザーには、リンクが示されている場合は、ドロップ操作中に作成する必要があります。 貼り付けコマンドを処理することにも使用できます。 内で、フレームワークによって呼び出される`COleClientItem::CreateLinkFromClipboard`し、[静的オブジェクト](../../mfc/reference/colepastespecialdialog-class.md#createitem)リンク オプションが選択されたとき。  
  
 詳細については、次を参照してください。 [OleCreateLinkFromData](http://msdn.microsoft.com/library/windows/desktop/ms680731)、 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)、および[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="createlinkfromfile"></a>COleClientItem::CreateLinkFromFile  
 ファイルからリンクされている OLE アイテムを作成するには、この関数を呼び出します。  
  
```  
BOOL CreateLinkFromFile(
    LPCTSTR lpszFileName,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFileName`  
 OLE アイテムを作成する元となるファイルの名前へのポインター。  
  
 *レンダリング*  
 サーバーが OLE アイテムを表示する方法を指定するフラグ。 有効な値を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `cfFormat`  
 OLE アイテムの作成時にキャッシュされるクリップボード データ形式を指定します。  
  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)場合に使用される構造体*レンダリング*は**OLERENDER_FORMAT**または**OLERENDER_DRAW**します。 クリップボードの形式で指定した以外の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`します。 このパラメーターを省略した場合、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ユーザーが、ファイルから作成 が選択されているし、リンクのチェック ボックスをオンに、オブジェクトの挿入 ダイアログ ボックスから ok を選択する場合、この関数を呼び出します。 呼び出される[クリック](../../mfc/reference/coleinsertdialog-class.md#createitem)します。  
  
 詳細については、次を参照してください。 [OleCreateLinkToFile](http://msdn.microsoft.com/library/windows/desktop/ms678434)、 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)、および[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="createnewitem"></a>COleClientItem::CreateNewItem  
 埋め込みアイテム; を作成するには、この関数を呼び出すこの関数は、OLE アイテムの作成をユーザーには、サーバー アプリケーションを起動します。  
  
```  
BOOL CreateNewItem(
    REFCLSID clsid,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 作成する OLE アイテムの種類を一意に識別する ID です。  
  
 *レンダリング*  
 サーバーが OLE アイテムを表示する方法を指定するフラグ。 有効な値を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `cfFormat`  
 OLE アイテムの作成時にキャッシュされるクリップボード データ形式を指定します。  
  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)場合に使用される構造体*レンダリング*は**OLERENDER_FORMAT**または**OLERENDER_DRAW**します。 クリップボードの形式で指定した以外の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`します。 このパラメーターを省略した場合、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、新規作成 ボタンを選択すると、ユーザーがオブジェクトの挿入 ダイアログ ボックスから ok を選択する場合に、この関数を呼び出します。  
  
 詳細については、次を参照してください。 [OleCreate](http://msdn.microsoft.com/library/windows/desktop/ms678409)、 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)、および[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="createstaticfromclipboard"></a>COleClientItem::CreateStaticFromClipboard  
 クリップボードの内容から、静的な項目を作成するには、この関数を呼び出します。  
  
```  
BOOL CreateStaticFromClipboard(
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *レンダリング*  
 サーバーが OLE アイテムを表示する方法を指定するフラグ。 有効な値を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `cfFormat`  
 OLE アイテムの作成時にキャッシュされるクリップボード データ形式を指定します。  
  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)場合に使用される構造体*レンダリング*は**OLERENDER_FORMAT**または**OLERENDER_DRAW**します。 クリップボードの形式で指定した以外の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`します。 このパラメーターを省略した場合、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プレゼンテーション データはネイティブのデータではなく、静的な項目が含まれますそのため編集できません。 通常この関数を呼び出す場合、[一般的に](#createfromclipboard)メンバー関数は失敗します。  
  
 詳細については、次を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)と[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="createstaticfromdata"></a>COleClientItem::CreateStaticFromData  
 静的な項目を作成するには、この関数を呼び出して、`COleDataObject`オブジェクトです。  
  
```  
BOOL CreateStaticFromData(
    COleDataObject* pDataObject,  
    OLERENDER render = OLERENDER_DRAW,  
    CLIPFORMAT cfFormat = 0,  
    LPFORMATETC lpFormatEtc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 ポインター、 [COleDataObject](../../mfc/reference/coledataobject-class.md) OLE アイテムを作成する元となるオブジェクト。  
  
 *レンダリング*  
 サーバーが OLE アイテムを表示する方法を指定するフラグ。 有効な値を参照してください。 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `cfFormat`  
 OLE アイテムの作成時にキャッシュされるクリップボード データ形式を指定します。  
  
 `lpFormatEtc`  
 ポインター、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)場合に使用される構造体*レンダリング*は**OLERENDER_FORMAT**または**OLERENDER_DRAW**します。 クリップボードの形式で指定した以外の追加の書式情報を指定する場合にのみ、このパラメーターの値を指定`cfFormat`します。 このパラメーターを省略した場合、既定値は、の他のフィールドの使用は、 **FORMATETC**構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 プレゼンテーション データはネイティブのデータではなく、静的な項目が含まれますそのため、編集できません。 これは、基本的に同じ[関数](#createstaticfromclipboard)任意の静的な項目を作成できる点を除いて`COleDataObject`クリップボードからだけでなく、します。  
  
 使用される[静的オブジェクト](../../mfc/reference/colepastespecialdialog-class.md#createitem)静的が選択されている場合。  
  
 詳細については、次を参照してください。 [OleCreateStaticFromData](http://msdn.microsoft.com/library/windows/desktop/ms687290)、 [OLERENDER](http://msdn.microsoft.com/library/windows/desktop/ms691507)、および[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="deactivate"></a>COleClientItem::Deactivate  
 OLE アイテムを非アクティブにして、関連付けられているリソースを解放するには、この関数を呼び出します。  
  
```  
void Deactivate();
```  
  
### <a name="remarks"></a>コメント  
 インプレース アクティブ OLE アイテムは、ユーザー項目の範囲外のクライアント領域上にマウス ポインターをクリックしたときにアクティブです。 OLE アイテムを非アクティブ化と呼び出すことができないの元に戻す状態が破棄されることに注意してください、[ので](#reactivateandundo)メンバー関数。  
  
 アプリケーションでは、元に戻すをサポートする場合は呼び出す必要はありません`Deactivate`。 代わりに、呼び出す[DeactivateUI](#deactivateui)します。  
  
 詳細については、次を参照してください。 [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="deactivateui"></a>COleClientItem::DeactivateUI  
 ユーザーには、インプレース アクティブなアイテムが非アクティブ化時に、この関数を呼び出します。  
  
```  
void DeactivateUI();
```  
  
### <a name="remarks"></a>コメント  
 この関数は、コンテナー アプリケーションのユーザー インターフェイスを任意のメニューおよびインプレース アクティブ化用に作成されたその他のコントロールを非表示の元の状態に復元します。  
  
 この関数は、アイテムの元に戻す状態情報をフラッシュしません。 情報を保持するように[ので](#reactivateandundo)アイテムを非アクティブの直後に、コンテナーの元に戻すコマンドを選択した場合に後で、サーバー アプリケーションで元に戻すコマンドを実行するに使用できます。  
  
 詳細については、次を参照してください。 [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="delete"></a>COleClientItem::Delete  
 OLE 項目コンテナー ドキュメントから削除するには、この関数を呼び出します。  
  
```  
void Delete(BOOL bAutoDelete = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bAutoDelete`  
 アイテムをドキュメントから削除するかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 この関数は、[リリース](#release)メンバー関数は、さらに、項目、永続的に項目を削除して、OLE ドキュメントからの C++ オブジェクトを削除します。 OLE アイテムが埋め込まれている場合、項目のネイティブのデータが削除されます。 実行中のサーバーを常に閉じるそのため、項目がリンクを開く場合、それを閉じます。  
  
##  <a name="dodragdrop"></a>クラス  
 呼び出す、`DoDragDrop`ドラッグ アンド ドロップ操作を実行するメンバー関数。  
  
```  
DROPEFFECT DoDragDrop(
    LPCRECT lpItemRect,  
    CPoint ptOffset,  
    BOOL bIncludeLink = FALSE,  
    DWORD dwEffects = DROPEFFECT_COPY | DROPEFFECT_MOVE,  
    LPCRECT lpRectStartDrag = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpItemRect`  
 クライアント座標 (ピクセル単位) での画面で、項目の四角形。  
  
 `ptOffset`  
 オフセット`lpItemRect`がドラッグ時に、マウスの位置であります。  
  
 `bIncludeLink`  
 これを設定**TRUE**場合は、データのリンクをクリップボードにコピーする必要があります。 設定**FALSE**サーバー アプリケーションでは、リンクをサポートしていない場合。  
  
 `dwEffects`  
 ドラッグ ソースがドラッグ操作で許可する効果を決定します。  
  
 `lpRectStartDrag`  
 実際には、ドラッグの開始位置を定義する四角形へのポインター。 詳細については、「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 `DROPEFFECT` 値。 ある場合`DROPEFFECT_MOVE`、元のデータを削除する必要があります。  
  
### <a name="remarks"></a>コメント  
 ドラッグ アンド ドロップ操作はすぐに開始されません。 マウス カーソルが指定された四角形のままになるまで待機している`lpRectStartDrag`または指定したミリ秒数が経過するまでです。 場合`lpRectStartDrag`は**NULL**、四角形のサイズは&1; ピクセルです。  
  
 遅延時間は、レジストリ キーの設定によって指定されます。 遅延時間を変更するにを呼び出して[CWinApp::WriteProfileString](../../mfc/reference/cwinapp-class.md#writeprofilestring)または[cwinapp::writeprofileint](../../mfc/reference/cwinapp-class.md#writeprofileint)します。 遅延時間を指定しない場合は、200 ミリ秒の既定値が使用されます。 ドラッグ遅延時間は、次のように格納されます。  
  
-   Windows NT ドラッグ遅延時間は、HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\NT\CurrentVersion\IniFileMapping\win.ini\Windows\DragDelay に格納されます。  
  
-   Windows 3.x ドラッグ遅延時間は、WIN に格納されます。INI ファイルの [Windows} セクション。  
  
-   Windows 95/98 ドラッグ遅延時間は、WIN のキャッシュされたバージョンに格納されます。INI します。  
  
 遅延の情報は、レジストリに格納されている方法の詳細についてはドラッグのか。INI ファイルを参照してください[WriteProfileString](http://msdn.microsoft.com/library/windows/desktop/ms725504)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="doverb"></a>COleClientItem::DoVerb  
 呼び出す`DoVerb`を指定した動詞を実行します。  
  
```  
virtual BOOL DoVerb(
    LONG nVerb,  
    CView* pView,
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nVerb`  
 実行する動詞を指定します。 次のいずれかを指定できます。  
  
|値|説明|シンボル|  
|-----------|-------------|------------|  
|– 0|主動詞|`OLEIVERB_PRIMARY`|  
|– 1|セカンダリ動詞|(なし)|  
|– 1|編集するための表示項目|`OLEIVERB_SHOW`|  
|– 2|別のウィンドウで項目を編集します。|`OLEIVERB_OPEN`|  
|– 3|アイテムを非表示します。|`OLEIVERB_HIDE`|  
  
 –&1; の値は、通常、他の動詞のエイリアスです。 編集のオープンがサポートされていない場合、–&2; は-1 と同じ効果を持ちます。 その他の値を参照してください。 [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `pView`  
 表示ウィンドウへのポインターこれについては、インプレース アクティブ化のため、サーバーによって使用されます。 このパラメーターを指定する必要があります**NULL**コンテナー アプリケーションは、インプレース アクティブ化を許可していない場合。  
  
 `lpMsg`  
 アクティブ化する項目を原因となったメッセージへのポインター。  
  
### <a name="return-value"></a>戻り値  
 動詞が正常に実行された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、 [Activate](#activate)動詞を実行するメンバー関数。 例外をキャッチし、いずれかがスローされた場合、ユーザーにメッセージ ボックスを表示します。  
  
 主動詞がおよびで&0; が指定されているかどうか、 `nVerb` OLE アイテムを編集することを許可するようにパラメーター、サーバー アプリケーションを起動します。 コンテナー アプリケーションでは、インプレース アクティブ化をサポートする場合に編集を実行できます。 コンテナーは、インプレース アクティブ化 (または Open 動詞が指定されているかどうか) をサポートしていない、独立したウィンドウで、サーバーが起動し、編集行われます。 通常は、コンテナー アプリケーションのユーザーがプライマリ動詞の値である OLE アイテムをダブルクリックすると、`nVerb`パラメーターは、ユーザーが実行できるアクションを決定します。 ただし、サーバーは、1 つだけの操作をサポートする場合は、その操作で指定された値に関係なく、`nVerb`パラメーター。  
  
##  <a name="draw"></a>値  
 指定したデバイス コンテキストを使用して、指定された外接する四角形に OLE アイテムを描画するには、この関数を呼び出します。  
  
```  
BOOL Draw(
    CDC* pDC,  
    LPCRECT lpBounds,  
    DVASPECT nDrawAspect = (DVASPECT)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 ポインター、 [CDC](../../mfc/reference/cdc-class.md) OLE アイテムの描画に使用するオブジェクト。  
  
 `lpBounds`  
 ポインター、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは`RECT`を (論理単位でデバイス コンテキストから判別した OLE アイテムを描画するための外接する四角形を定義します。  
  
 `nDrawAspect`  
 OLE の縦横比項目は、表示方法を指定します。 場合`nDrawAspect`-1 で、最後の側面を使用して設定[外観](#setdrawaspect)を使用します。 このフラグを指定する値の詳細については、次を参照してください。[外観](#setdrawaspect)します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 関数が表現を使用して、メタファイルによって作成された OLE アイテムの[OnDraw](../../mfc/reference/coleserveritem-class.md#ondraw)のメンバー関数`COleServerItem`します。  
  
 通常使用して、**描画**画面表示のためには、として画面デバイス コンテキストを渡して`pDC`します。 この場合、最初の&2; つのパラメーターのみを指定する必要があります。  
  
 `lpBounds`パラメーターでターゲットのデバイス コンテキスト (現在のマップ モード) の相対で四角形を識別します。 レンダリングでは、図のスケーリングを含んでされ、表示されているビューと最終的な印刷されたイメージのサイズを変更するビューを設定するコンテナー アプリケーションで使用できます。  
  
 詳細については、次を参照してください。 [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getactiveview"></a>COleClientItem::GetActiveView  
 アイテムがインプレースでアクティブ化されるビューを返します。  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ビューへのポインターそれ以外の場合**NULL**場合は、アイテムはインプレース アクティブ化ではありません。  
  
##  <a name="getcachedextent"></a>COleClientItem::GetCachedExtent  
 OLE アイテムのサイズを取得するには、この関数を呼び出します。  
  
```  
BOOL GetCachedExtent(
    LPSIZE lpSize,  
    DVASPECT nDrawAspect = (DVASPECT)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpSize`  
 ポインター、**サイズ**構造体、または[CSize](../../atl-mfc-shared/reference/csize-class.md)サイズ情報を受け取るオブジェクト。  
  
 `nDrawAspect`  
 境界を取得する OLE アイテムの外観を指定します。 指定できる値は、次を参照してください。[外観](#setdrawaspect)します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。OLE アイテムが空白の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数と同じ情報を提供する[GetExtent](#getextent)します。 ただし、呼び出す`GetCachedExtent`エクステントの情報を取得、処理中に他の OLE ハンドラーなど[OnChange](#onchange)します。 ディメンションは`MM_HIMETRIC`単位です。  
  
 これは、可能なため`GetCachedExtent`を使用して、 [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318)を使用するのではなく、インターフェイス、 [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709)この項目の範囲を取得するインターフェイスです。 **IViewObject2** COM オブジェクトには、前の呼び出しで使用範囲情報がキャッシュされ[IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655)します。  
  
 詳細については、次を参照してください。 [IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getclassid"></a>COleClientItem::GetClassID  
 指すメモリにアイテムのクラス ID を返す`pClassID`します。  
  
```  
void GetClassID(CLSID* pClassID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pClassID`  
 種類の id へのポインター [CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424)クラス ID を取得するには 詳細について**CLSID**を参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 クラス ID は、項目を編集するアプリケーションを一意に識別する 128 ビットの数値です。  
  
 詳細については、次を参照してください。 [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getclipboarddata"></a>COleClientItem::GetClipboardData  
 取得するには、この関数を呼び出す、`COleDataSource`オブジェクトへの呼び出しによって、クリップボードに配置するとすべてのデータを含む、 [CopyToClipboard](#copytoclipboard)メンバー関数。  
  
```  
void GetClipboardData(
    COleDataSource* pDataSource,  
    BOOL bIncludeLink = FALSE,  
    LPPOINT lpOffset = NULL,  
    LPSIZE lpSize = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataSource`  
 ポインター、 [COleDataSource](../../mfc/reference/coledatasource-class.md) OLE アイテムに含まれているデータを受け取るオブジェクト。  
  
 `bIncludeLink`  
 **TRUE**リンク データが含まれています。 それ以外の場合必要がある場合**FALSE**します。  
  
 `lpOffset`  
 マウス ポインターのピクセル単位でオブジェクトの原点からのオフセット。  
  
 `lpSize`  
 ピクセル単位でオブジェクトのサイズ。  
  
### <a name="remarks"></a>コメント  
 `GetClipboardData`既定の実装として呼び出される[OnGetClipboardData](#ongetclipboarddata)します。 オーバーライド`OnGetClipboardData`により提供されるだけでなく、データ形式を提供する場合にのみ`CopyToClipboard`します。 配置済みの形式で、`COleDataSource`オブジェクト呼び出しの前後に`CopyToClipboard`、し、渡します、`COleDataSource`オブジェクトを[COleDataSource::SetClipboard](../../mfc/reference/coledatasource-class.md#setclipboard)関数です。 たとえば、OLE アイテムの位置にクリップボードに付属するコンテナー ドキュメントの場合はその情報を渡すための独自の書式を定義するして配置、`COleDataSource`呼び出す前に`CopyToClipboard`します。  
  
##  <a name="getdocument"></a>COleClientItem::GetDocument  
 OLE アイテムを含むドキュメントへのポインターを取得するには、この関数を呼び出します。  
  
```  
COleDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 OLE アイテムを含むドキュメントへのポインター。 **NULL**場合は、項目は、ドキュメントの一部ではありません。  
  
### <a name="remarks"></a>コメント  
 このポインターにアクセスできるように、`COleDocument`への引数として渡されたオブジェクト、`COleClientItem`コンス トラクターです。  
  
##  <a name="getdrawaspect"></a>COleClientItem::GetDrawAspect  
 呼び出す、`GetDrawAspect`を現在の「外観」または項目のビューを調べます。  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 値、`DVASPECT`のリファレンスについての値が表示されている列挙[外観](#setdrawaspect)します。  
  
### <a name="remarks"></a>コメント  
 縦横比は、アイテムがレンダリングされる方法を指定します。  
  
##  <a name="getextent"></a>COleClientItem::GetExtent  
 OLE アイテムのサイズを取得するには、この関数を呼び出します。  
  
```  
BOOL GetExtent(
    LPSIZE lpSize,  
    DVASPECT nDrawAspect = (DVASPECT)- 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpSize`  
 ポインター、**サイズ**構造体、または`CSize`サイズ情報を受け取るオブジェクト。  
  
 `nDrawAspect`  
 境界を取得する OLE アイテムの外観を指定します。 指定できる値は、次を参照してください。[外観](#setdrawaspect)します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。OLE アイテムが空白の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 サーバー アプリケーションは、Microsoft Foundation Class ライブラリを使用して記述された、この関数を実行すると、 [OnGetExtent](../../mfc/reference/coleserveritem-class.md#ongetextent)対応するメンバー関数`COleServerItem`に呼び出されるオブジェクト。 最後に設定されているサイズから取得したサイズが変わる可能性がある注意してください、 [SetExtent](#setextent)メンバー関数; で指定されたサイズ`SetExtent`修正案として扱われます。 ディメンションは`MM_HIMETRIC`単位です。  
  
> [!NOTE]
>  呼び出す必要はありません`GetExtent`OLE ハンドラーの処理中になど[OnChange](#onchange)します。 呼び出す[GetCachedExtent](#getcachedextent)代わりにします。  
  
 詳細については、次を参照してください。 [IOleObject::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms692325)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="geticonfromregistry"></a>COleClientItem::GetIconFromRegistry  
 特定の CLSID のサーバーに関連付けられているアイコン リソースを識別するハンドルを取得するには、このメンバー関数を呼び出します。  
  
```  
HICON GetIconFromRegistry() const;  
  
static HICON GetIconFromRegistry(CLSID& clsid);
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 アイコンに関連付けられているサーバーの CLSID への参照。  
  
### <a name="return-value"></a>戻り値  
 アイコン リソースへの有効なハンドルまたは**NULL**サーバーのアイコン、または既定のアイコンが見つからない場合。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、サーバーを起動したり、サーバーが既に実行されている場合であっても、アイコンを動的に取得。 代わりに、このメンバー関数は、サーバーの実行可能イメージを開き、が登録されたサーバーに関連付けられている静的なアイコンを取得します。  
  
##  <a name="geticonicmetafile"></a>COleClientItem::GetIconicMetafile  
 項目のアイコンを描画するために使われるメタファイルを取得します。  
  
```  
HGLOBAL GetIconicMetafile();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、メタファイルを識別するハンドルそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 現在のアイコンがない場合、既定のアイコンが返されます。 これは、MFC/OLE ダイアログによって自動的に呼び出され、通常直接呼び出されることです。  
  
 この関数を呼び出しても[SetIconicMetafile](#seticonicmetafile)を後で使用できるメタファイルをキャッシュします。  
  
##  <a name="getinplacewindow"></a>COleClientItem::GetInPlaceWindow  
 呼び出す、`GetInPlaceWindow`で埋め込み先編集のアイテムが開かれたウィンドウへのポインターを取得します。  
  
```  
CWnd* GetInPlaceWindow();
```  
  
### <a name="return-value"></a>戻り値  
 項目の一括編集ウィンドウへのポインター**NULL**アイテムがアクティブでない場合、またはそのサーバーが利用できない場合。  
  
### <a name="remarks"></a>コメント  
 この関数は、インプレース アクティブにある項目に対してのみ呼び出す必要があります。  
  
##  <a name="getitemstate"></a>COleClientItem::GetItemState  
 OLE アイテムの現在の状態を取得するには、この関数を呼び出します。  
  
```  
UINT GetItemState() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A **COleClientItem::ItemState**列挙値で、次のいずれかになります: `emptyState`、 **loadedState**、 `openState`、 `activeState`、`activeUIState`です。 これらの状態については、記事を参照してください。[コンテナー: クライアント アイテムの状態](../../mfc/containers-client-item-states.md)します。  
  
### <a name="remarks"></a>コメント  
 OLE アイテムの状態が変更されたときに通知を受け取るを使用して、 [OnChange](#onchange)メンバー関数。  
  
 詳細については、記事を参照してください。[コンテナー: クライアント アイテムの状態](../../mfc/containers-client-item-states.md)します。  
  
##  <a name="getlaststatus"></a>COleClientItem::GetLastStatus  
 OLE の最後の操作のステータス コードを返します。  
  
```  
SCODE GetLastStatus() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `SCODE` 値。  
  
### <a name="remarks"></a>コメント  
 メンバー関数を返す、 **BOOL**の値**FALSE**、またはその他のメンバー関数を返します。 **NULL**、`GetLastStatus`より詳細なエラー情報を返します。 ほとんどの OLE メンバー関数がより重大なエラーに対して例外をスローすることに注意してください。 特定の解釈について、`SCODE`は最後に返されたを基になる OLE 呼び出しに依存します、`SCODE`値。  
  
 詳細については`SCODE`を参照してください[COM エラー コードの構造体](http://msdn.microsoft.com/library/windows/desktop/ms690088)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]ドキュメントです。  
  
##  <a name="getlinkupdateoptions"></a>COleClientItem::GetLinkUpdateOptions  
 OLE アイテムのリンクの更新オプションの現在の値を取得するには、この関数を呼び出します。  
  
```  
OLEUPDATE GetLinkUpdateOptions();
```  
  
### <a name="return-value"></a>戻り値  
 次のいずれかの値です。  
  
- `OLEUPDATE_ALWAYS`可能な場合は、リンクされた項目を更新します。 このオプションは、リンク ダイアログ ボックスで、リンクの自動更新オプション ボタンをサポートします。  
  
- `OLEUPDATE_ONCALL`コンテナー アプリケーションからの要求にのみリンク アイテムを更新 (ときに、 [UpdateLink](#updatelink)メンバー関数が呼び出されます)。 このオプションは、リンク ダイアログ ボックスで、リンクの手動更新オプション ボタンをサポートします。  
  
### <a name="remarks"></a>コメント  
 これは、高度な操作です。  
  
 この関数の[関数](../../mfc/reference/colelinksdialog-class.md)クラスです。  
  
 詳細については、次を参照してください。 [IOleLink::GetUpdateOptions](http://msdn.microsoft.com/library/windows/desktop/ms680100)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="gettype"></a>COleClientItem::GetType  
 この関数では、OLE アイテムが埋め込まれているか、リンクされたかどうか、または静的を判断します。  
  
```  
OLE_OBJTYPE GetType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 次の値のいずれかで符号なし整数。  
  
- `OT_LINK`OLE アイテムは、リンクです。  
  
- `OT_EMBEDDED`OLE アイテムが埋め込まれます。  
  
- `OT_STATIC`OLE アイテムが静的は、ネイティブではないデータは、プレゼンテーション データが含まれていて、そのため、編集することはできません。  
  
##  <a name="getusertype"></a>COleClientItem::GetUserType  
 「Word 文書」などの OLE アイテムの型を記述するユーザーに表示される文字列を取得するには、この関数を呼び出す  
  
```  
void GetUserType(
    USERCLASSTYPE nUserClassType,  
    CString& rString);
```  
  
### <a name="parameters"></a>パラメーター  
 *nUserClassType*  
 OLE アイテムの型を記述する文字列の目的のバリエーションを示す値。 次の値の&1; つとります。  
  
- `USERCLASSTYPE_FULL`完全な型名をユーザーに表示します。  
  
- `USERCLASSTYPE_SHORT`ポップアップ メニューやリンクの編集 ダイアログ ボックスで短い名前 (最大で&15; 文字以内)。  
  
- `USERCLASSTYPE_APPNAME`クラスを処理するアプリケーションの名前。  
  
 `rString`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md) OLE アイテムの型を記述する文字列が返されるオブジェクト。  
  
### <a name="remarks"></a>コメント  
 これは、システムの登録情報データベース内のエントリでは多くの場合です。  
  
 完全な型名が要求されましたが、使用できない場合は、短い名前が代わりに使用します。 Registration データベースに OLE アイテムの種類のエントリが見つからないか、ユーザーの種類が OLE アイテムの種類に登録されていない場合、ユーザーの種類に格納されている場合は、OLE アイテムが使用されます。 そのユーザーの種類名が空の文字列の場合は、「不明なオブジェクト」が使用されます。  
  
 詳細については、次を参照してください。 [IOleObject::GetUserType](http://msdn.microsoft.com/library/windows/desktop/ms688643)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="isinplaceactive"></a>COleClientItem::IsInPlaceActive  
 OLE アイテムがアクティブであるかどうかを確認するには、この関数を呼び出します。  
  
```  
BOOL IsInPlaceActive() const;  
```  
  
### <a name="return-value"></a>戻り値  
 OLE アイテムが、インプレースが有効である場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 一般的に、項目を編集するかどうかに応じて異なるロジックを実行します。 関数は、現在の項目の状態がいずれかに等しいかどうかを確認、`activeState`または`activeUIState`です。  
  
##  <a name="islinkuptodate"></a>COleClientItem::IsLinkUpToDate  
 OLE アイテムが最新かどうかを表示するには、この関数を呼び出します。  
  
```  
BOOL IsLinkUpToDate() const;  
```  
  
### <a name="return-value"></a>戻り値  
 OLE 項目が最新の状態の場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 リンクの項目は、古いは元のドキュメントが更新されている場合があります。 内のリンクを含む埋め込みアイテム同様になります。 期限が切れています。 関数は、OLE アイテムのチェックを再帰的です。 OLE アイテムが期限切れかどうかを決定できる更新を実際に実行するコストがかかるに注意してください。  
  
 これはによって自動的に呼び出されます、[関数](../../mfc/reference/colelinksdialog-class.md)実装します。  
  
 詳細については、次を参照してください。 [:isuptodate](http://msdn.microsoft.com/library/windows/desktop/ms686624)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="ismodified"></a>COleClientItem::IsModified  
 この関数を呼び出しているかどうか OLE アイテムがダーティ (最後に保存された以降に変更) を参照してください。  
  
```  
BOOL IsModified() const;  
```  
  
### <a name="return-value"></a>戻り値  
 OLE 項目がダーティの場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [IPersistStorage::IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="isopen"></a>COleClientItem::IsOpen  
 OLE アイテムが開かれているかどうかを表示するには、この関数を呼び出すつまり、別のウィンドウで実行されているサーバー アプリケーションのインスタンスで開かれます。  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 OLE アイテムが開いている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 () の陰影パターンを持つオブジェクトを描画するかを判断に使用されます。 開いているオブジェクト、オブジェクトの上に描画ハッチ パターンが必要です。 使用することができます、 [CRectTracker](../../mfc/reference/crecttracker-class.md)これを実現するオブジェクト。  
  
##  <a name="isrunning"></a>COleClientItem::IsRunning  
 OLE アイテムが実行中かどうかを表示するには、この関数を呼び出すつまり、かどうか、項目が読み込まれ、サーバー アプリケーションの実行中です。  
  
```  
BOOL IsRunning() const;  
```  
  
### <a name="return-value"></a>戻り値  
 OLE アイテムを実行している場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [OleIsRunning](http://msdn.microsoft.com/library/windows/desktop/ms688705)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="onactivate"></a>COleClientItem::OnActivate  
 インプレース アクティブされただけのアイテムを通知するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnActivate();
```  
  
### <a name="remarks"></a>コメント  
 この関数が、ユーザー インターフェイスがコンテナー アプリケーションにインストールされたことを示すためにない、サーバーを実行することを示すためと呼ばれることに注意してください。 この時点で、オブジェクトには、アクティブなユーザー インターフェイスはありません (は`activeUIState`)。 メニューまたはツールバーがされています。 [入った](#onactivateui)その場合、メンバー関数が呼び出されます。  
  
 既定の実装、 [OnChange](#onchange)メンバー関数を**OLE_CHANGEDSTATE**をパラメーターとして。 項目がアクティブになったときに、カスタム処理を実行するには、この関数をオーバーライドします。  
  
##  <a name="onactivateui"></a>COleClientItem::OnActivateUI  
 Framework 呼び出し`OnActivateUI`オブジェクトがアクティブの UI の状態になったとします。  
  
```  
virtual void OnActivateUI();
```  
  
### <a name="remarks"></a>コメント  
 ツールバーとメニューのオブジェクトがインストールされました。  
  
 既定の実装は、サーバーを記憶`HWND`後に**で**呼び出しです。  
  
##  <a name="onchange"></a>として  
 ユーザーは、変更したり、保存すると、OLE アイテムを閉じたりするときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnChange(
    OLE_NOTIFICATION nCode,  
    DWORD dwParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCode`  
 理由は、サーバーは、この項目を変更します。 次の値のいずれかを取ります。  
  
- `OLE_CHANGED`OLE アイテムの外観が変更されました。  
  
- `OLE_SAVED`OLE アイテムが保存されました。  
  
- `OLE_CLOSED`OLE アイテムが閉じられています。  
  
- `OLE_CHANGED_STATE`OLE アイテムは、別の&1; つの状態から変更されました。  
  
 `dwParam`  
 場合`nCode`は`OLE_SAVED`または`OLE_CLOSED`、このパラメーターは使用されません。 場合`nCode`は`OLE_CHANGED`、このパラメーターが変更された OLE アイテムの外観を指定します。 指定できる値は、次を参照してください。、`dwParam`のパラメーター[値](#draw)です。 場合`nCode`は`OLE_CHANGED_STATE`、このパラメーターは、 **COleClientItem::ItemState**値が列挙され、入力されている状態を説明します。 次の値の&1; つ持つことができます: `emptyState`、 **loadedState**、 `openState`、 `activeState`、または`activeUIState`です。  
  
### <a name="remarks"></a>コメント  
 (Microsoft Foundation Class ライブラリを使用して、サーバー アプリケーションを記述すると、この関数はへの応答に呼び出されます、`Notify`のメンバー関数`COleServerDoc`または`COleServerItem`。)。既定の実装が場合は、変更として、コンテナー ドキュメントをマーク`nCode`は`OLE_CHANGED`または`OLE_SAVED`です。  
  
 `OLE_CHANGED_STATE`、現在の状態から返された[GetItemState](#getitemstate)以前の状態、つまり、この状態の変更前に現在の状態ができます。  
  
 OLE アイテムの状態の変化に対応するには、この関数をオーバーライドします。 通常、項目が表示される領域を無効にして項目の外観を更新します。 オーバーライドした関数の先頭には、基本クラス実装を呼び出します。  
  
##  <a name="onchangeitemposition"></a>に  
 コンテナーにインプレース アクティブ化時に OLE アイテムの範囲が変更されたことを通知するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnChangeItemPosition(const CRect& rectPos);
```  
  
### <a name="parameters"></a>パラメーター  
 *rectPos*  
 コンテナー アプリケーションのクライアント領域を基準と、項目の位置を示します。  
  
### <a name="return-value"></a>戻り値  
 アイテムの位置が正常に変更された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 OLE アイテムと呼び出しの新しい表示される四角形を決定する既定の実装[SetItemRects](#setitemrects)に新しい値。 既定の実装では、アイテムの表示される四角形を計算し、その情報をサーバーに渡します。  
  
 サイズ変更/移動操作には特別な規則を適用するには、この関数をオーバーライドします。 この呼び出しの結果、サーバーが呼び出されるため、アプリケーションが MFC で記述されている場合[から](../../mfc/reference/coleserverdoc-class.md#requestpositionchange)します。  
  
##  <a name="ondeactivate"></a>COleClientItem::OnDeactivate  
 OLE アイテムは、インプレース アクティブ状態から移行する際に、フレームワークによって呼び出されます ( `activeState`) 読み込み済みの状態、つまり、インプレース アクティブ化の後に非アクティブにします。  
  
```  
virtual void OnDeactivate();
```  
  
### <a name="remarks"></a>コメント  
 OLE アイテムが閉じているしないコンテナー アプリケーションから削除されたユーザー インターフェイスを示すためにこの関数と呼ばれることに注意してください。 その場合、 [OnDeactivateUI](#ondeactivateui)メンバー関数が呼び出されます。  
  
 既定の実装、 [OnChange](#onchange)メンバー関数を**OLE_CHANGEDSTATE**をパラメーターとして。 インプレースでアクティブなアイテムが非アクティブになるカスタム処理を実行するには、この関数をオーバーライドします。 たとえば、コンテナー アプリケーションで元に戻すコマンドをサポートする場合できます関数をオーバーライドするこの元に戻す状態を破棄するアイテムが非アクティブ化に OLE アイテムに対して実行された最後の操作を元に戻すことはできませんすることを示します。  
  
##  <a name="ondeactivateandundo"></a>COleClientItem::OnDeactivateAndUndo  
 ユーザーは、OLE アイテムの配置をアクティブ化した後、元に戻すコマンドを呼び出したときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnDeactivateAndUndo();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装[DeactivateUI](#deactivateui)サーバーのユーザー インターフェイスを非アクティブ化します。 コンテナー アプリケーションで元に戻すコマンドを実装している場合は、この関数をオーバーライドします。 オーバーライドの中では、関数の基底クラスのバージョンを呼び出し、最後のコマンドは、アプリケーションの実行を元に戻します。  
  
 詳細については、次を参照してください。 [IOleInPlaceSite::DeactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms683743)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="ondeactivateui"></a>COleClientItem::OnDeactivateUI  
 アクティブなアイテムを非アクティブにすると呼び出されます。  
  
```  
virtual void OnDeactivateUI(BOOL bUndoable);
```  
  
### <a name="parameters"></a>パラメーター  
 `bUndoable`  
 編集の変更が元に戻せるがないかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 この関数は、コンテナー アプリケーションのユーザー インターフェイスを任意のメニューおよびインプレース アクティブ化用に作成されたその他のコントロールを非表示の元の状態に復元します。  
  
 場合`bUndoable`は**FALSE**取り消し可能なは破棄することで、コンテナーの元に戻す状態、サーバーが最後の操作が実行を示すため、コンテナーには、元に戻すコマンドが無効にする必要があります。  
  
##  <a name="ondiscardundostate"></a>COleClientItem::OnDiscardUndoState  
 ユーザーは、OLE アイテムを編集するときに元に戻す状態を破棄する操作を実行したときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnDiscardUndoState();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も行われません。 コンテナー アプリケーションで元に戻すコマンドを実装している場合は、この関数をオーバーライドします。 オーバーライドの中では、コンテナー アプリケーションの元に戻す状態を破棄します。  
  
 Microsoft Foundation Class ライブラリに、サーバーを作成した場合、サーバーは、この呼び出される関数を呼び出すことによってを引き起こすこと[COleServerDoc::DiscardUndoState](../../mfc/reference/coleserverdoc-class.md#discardundostate)します。  
  
 詳細については、次を参照してください。 [IOleInPlaceSite::DiscardUndoState](http://msdn.microsoft.com/library/windows/desktop/ms688642)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="ongetclipboarddata"></a>COleClientItem::OnGetClipboardData  
 取得するためにフレームワークによって呼び出されます、`COleDataSource`オブジェクトのいずれかへの呼び出しでクリップボードに配置するとすべてのデータを含む、 [CopyToClipboard](#copytoclipboard)または[(dodragdrop を)](#dodragdrop)メンバー関数。  
  
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
 ピクセル単位でオブジェクトの元のマウス カーソルのオフセットへのポインター。  
  
 `lpSize`  
 ピクセル単位でオブジェクトのサイズへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [COleDataSource](../../mfc/reference/coledatasource-class.md)クリップボードのデータを格納するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装を呼び出す[GetClipboardData](#getclipboarddata)します。  
  
##  <a name="ongetcliprect"></a>COleClientItem::OnGetClipRect  
 フレームワークによって、`OnGetClipRect`インプレース編集されているアイテムのクリッピング四角形の座標を取得します。  
  
```  
virtual void OnGetClipRect(CRect& rClipRect);
```  
  
### <a name="parameters"></a>パラメーター  
 *rClipRect*  
 クラスのオブジェクトへのポインター [CRect](../../atl-mfc-shared/reference/crect-class.md)アイテムのクリッピング四角形の座標を保持します。  
  
### <a name="remarks"></a>コメント  
 座標は、コンテナー アプリケーション ウィンドウのクライアント領域を基準と (ピクセル単位)。  
  
 既定の実装は、単純に、項目が、インプレース アクティブなビューのクライアントの四角形を返します。  
  
##  <a name="ongetitemposition"></a>状態  
 フレームワークによって、`OnGetItemPosition`インプレース編集されているアイテムの座標を取得します。  
  
```  
virtual void OnGetItemPosition(CRect& rPosition);
```  
  
### <a name="parameters"></a>パラメーター  
 `rPosition`  
 参照、 [CRect](../../atl-mfc-shared/reference/crect-class.md)アイテムの位置座標を格納するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 座標は、コンテナー アプリケーション ウィンドウのクライアント領域を基準と (ピクセル単位)。  
  
 この関数の既定の実装は、何も行いません。 埋め込み先編集をサポートするアプリケーションでは、その実装が必要です。  
  
##  <a name="ongetwindowcontext"></a>COleClientItem::OnGetWindowContext  
 アイテムは場所にアクティブになったときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnGetWindowContext(
    CFrameWnd** ppMainFrame,  
    CFrameWnd** ppDocFrame,  
    LPOLEINPLACEFRAMEINFO lpFrameInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppMainFrame`  
 メイン フレーム ウィンドウへのポインターへのポインター。  
  
 `ppDocFrame`  
 ドキュメント フレーム ウィンドウへのポインターへのポインター。  
  
 `lpFrameInfo`  
 ポインター、[受け取る](http://msdn.microsoft.com/library/windows/desktop/ms693737)フレーム ウィンドウの情報を受け取る。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数を使用して、OLE アイテムの親ウィンドウに関する情報を取得します。  
  
 既定の実装がへのポインターを返すコンテナーがサポートする MDI アプリケーションの場合は、 [CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)オブジェクト`ppMainFrame`と、アクティブなへのポインター [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)内のオブジェクト`ppDocFrame`します。 既定の実装がへのポインターを返す場合は、SDI アプリケーションは、コンテナーは、 [CFrameWnd](../../mfc/reference/cframewnd-class.md)オブジェクト`ppMainFrame`し、返します**NULL**で`ppDocFrame`します。 メンバーでも、既定の実装を格納`lpFrameInfo`します。  
  
 既定の実装で、アプリケーションが適していない場合にのみ、この関数をオーバーライドします。たとえば、次のように、アプリケーションがあるユーザー インターフェイスのパラダイム SDI または MDI とは異なる場合。 これは、高度なオーバーライドします。  
  
 詳細については、次を参照してください。 [IOleInPlaceSite::GetWindowContext](http://msdn.microsoft.com/library/windows/desktop/ms694366)と[受け取る](http://msdn.microsoft.com/library/windows/desktop/ms693737)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="oninsertmenus"></a>COleClientItem::OnInsertMenus  
 空のメニューに、コンテナー アプリケーションのメニューを挿入するインプレース アクティブ化時にフレームワークによって呼び出されます。  
  
```  
virtual void OnInsertMenus(
    CMenu* pMenuShared,  
    LPOLEMENUGROUPWIDTHS lpMenuWidths);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMenuShared`  
 空のメニューへのポインター。  
  
 `lpMenuWidths`  
 6 文字の配列を指す**長い**次のメニュー グループの各メニューの数を示す値: ファイル、編集、コンテナー オブジェクト ウィンドウのヘルプ。 コンテナー アプリケーションは、ファイル、コンテナー、およびウィンドウ] メニューの [グループの 0、2、およびこの配列の 4 要素に対応します。  
  
### <a name="remarks"></a>コメント  
 このメニューは複合メニューを作成する独自のメニューを挿入すると、サーバーに渡されます。 この関数は、いくつかの複合メニューを構築する繰り返し呼び出すことができます。  
  
 既定の実装を挿入`pMenuShared`インプレース コンテナーのメニューです。 つまり、ファイル、コンテナー、およびウィンドウのメニュー グループです。 [CDocTemplate::SetContainerInfo](../../mfc/reference/cdoctemplate-class.md#setcontainerinfo) ] メニューの [このリソースを設定するために使用します。 また、既定の実装は要素 0、2、および 4 に適切な値を割り当てます`lpMenuWidths`メニュー リソースによって異なります。 既定の実装がアプリケーションに適切でない場合は、この関数をオーバーライドします。たとえば、次のように、アプリケーションがリソースをドキュメントの種類に関連付けるためのドキュメント テンプレートを使用しない場合。 この関数をオーバーライドする場合をオーバーライドも[とき](#onsetmenu)と[OnRemoveMenus](#onremovemenus)します。 これは、高度なオーバーライドします。  
  
 詳細については、次を参照してください。 [IOleInPlaceFrame::InsertMenus](http://msdn.microsoft.com/library/windows/desktop/ms683987)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="onremovemenus"></a>COleClientItem::OnRemoveMenus  
 インプレース アクティブ化が終了すると、指定した複合メニューからコンテナーのメニューを削除するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnRemoveMenus(CMenu* pMenuShared);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMenuShared`  
 呼び出しによって構築された複合メニューが指す、[とき](#oninsertmenus)メンバー関数。  
  
### <a name="remarks"></a>コメント  
 既定の実装を解除`pMenuShared`インプレース コンテナーのメニューは、ファイル、コンテナー、およびウィンドウのメニュー グループです。 既定の実装がアプリケーションに適切でない場合は、この関数をオーバーライドします。たとえば、次のように、アプリケーションがリソースをドキュメントの種類に関連付けるためのドキュメント テンプレートを使用しない場合。 この関数をオーバーライドする場合はおそらくをオーバーライドする[とき](#oninsertmenus)と[とき](#onsetmenu)もします。 これは、高度なオーバーライドします。  
  
 サブメニュー `pMenuShared` 、サーバーが繰り返し呼び出されている場合に、複合 メニューの&1; つ以上が共有可能`OnInsertMenus`します。 そのため削除しないで、サブメニューのオーバーライドで`OnRemoveMenus`; のみ切断する必要があります。  
  
 詳細については、次を参照してください。 [IOleInPlaceFrame::RemoveMenus](http://msdn.microsoft.com/library/windows/desktop/ms688685)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="onscrollby"></a>COleClientItem::OnScrollBy  
 サーバーからの要求に応えて OLE アイテムをスクロールするためのフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnScrollBy(CSize sizeExtent);
```  
  
### <a name="parameters"></a>パラメーター  
 *sizeExtent*  
 X および y 方向にスクロールするためのピクセルで、距離を指定します。  
  
### <a name="return-value"></a>戻り値  
 アイテムがスクロールされた場合は 0 以外アイテムがスクロールできない場合は 0。  
  
### <a name="remarks"></a>コメント  
 たとえば、OLE アイテムが部分的に表示されると、ユーザーが表示領域外で埋め込み先編集の実行中に移動、この関数は、カーソルを表示したままに呼び出されます。 既定の実装では、何も行われません。 指定した量によって、アイテムをスクロールするには、この関数をオーバーライドします。 スクロールなどの結果として OLE アイテムの表示部分を変更できることに注意してください。 呼び出す[SetItemRects](#setitemrects)をアイテムの表示される四角形を更新します。  
  
 詳細については、次を参照してください。 [IOleInPlaceSite::Scroll](http://msdn.microsoft.com/library/windows/desktop/ms690291)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="onsetmenu"></a>COleClientItem::OnSetMenu  
 呼ばれるフレームワークによって&2; 回インプレース アクティブ化が開始され、終了するか。複合メニューと&2; 回目をインストールする最初の時間 (と`holemenu`に等しい**NULL**) を削除します。  
  
```  
virtual void OnSetMenu(
    CMenu* pMenuShared,  
    HOLEMENU holemenu,  
    HWND hwndActiveObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMenuShared`  
 呼び出しによって構築された複合メニューへのポインター、[とき](#oninsertmenus)メンバー関数と`InsertMenu`関数です。  
  
 `holemenu`  
 によって返されるメニュー記述子へのハンドル、 **OleCreateMenuDescriptor**関数、または**NULL**ディスパッチのコードを削除する場合。  
  
 *hwndActiveObject*  
 OLE アイテムの編集ウィンドウへのハンドルします。 これは、OLE から編集コマンドを受信するウィンドウです。  
  
### <a name="remarks"></a>コメント  
 既定の実装は、インストールまたは複合のメニューを削除しを呼び出して、[その](http://msdn.microsoft.com/library/windows/desktop/ms692831)関数をインストールまたはディスパッチのコードを削除します。 既定の実装がアプリケーションに対して適切でない場合は、この関数をオーバーライドします。 この関数をオーバーライドする場合はおそらくをオーバーライドする[とき](#oninsertmenus)と[OnRemoveMenus](#onremovemenus)もします。 これは、高度なオーバーライドします。  
  
 詳細については、次を参照してください。 [OleCreateMenuDescriptor](http://msdn.microsoft.com/library/windows/desktop/ms691415)、[その](http://msdn.microsoft.com/library/windows/desktop/ms692831)、および[IOleInPlaceFrame::SetMenu](http://msdn.microsoft.com/library/windows/desktop/ms693713)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="onshowcontrolbars"></a>COleClientItem::OnShowControlBars  
 コンテナー アプリケーションのコントロール バーを非表示にしたりするためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnShowControlBars(
    CFrameWnd* pFrameWnd,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFrameWnd`  
 コンテナー アプリケーションのフレーム ウィンドウへのポインター。 メイン フレーム ウィンドウまたは MDI 子ウィンドウのいずれかを指定できます。  
  
 `bShow`  
 コントロール バーを表示するか非表示になっているかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 関数呼び出しの変化によって、コントロール バーの状態である場合は 0 以外0 呼び出すには、変更がない場合、または`pFrameWnd`がコンテナーのフレーム ウィンドウを指していません。  
  
### <a name="remarks"></a>コメント  
 この関数は、コントロール バーは、既にで指定された状態である場合に 0 を返します*bShow します。* これは、処理は発生、たとえば、コントロール バーが表示されていない場合、`bShow`は**FALSE**します。  
  
 既定の実装では、最上位のフレーム ウィンドウから、ツールバーを削除します。  
  
##  <a name="onshowitem"></a>COleClientItem::OnShowItem  
 編集中に完全に認識させる OLE アイテムを表示するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnShowItem();
```  
  
### <a name="remarks"></a>コメント  
 コンテナー アプリケーションは、埋め込みアイテムへのリンクをサポートしている場合に使用されます (からドキュメント クラスを派生する場合は、[直接](../../mfc/reference/colelinkingdoc-class.md))。 この関数は、インプレース アクティブ化または OLE アイテムは、リンク元と、ユーザーがそれを編集する時に呼び出されます。 既定の実装には、コンテナー ドキュメントの最初のビューがアクティブになります。 OLE アイテムが表示されるように、ドキュメントをスクロールするには、この関数をオーバーライドします。  
  
##  <a name="onupdateframetitle"></a>COleClientItem::OnUpdateFrameTitle  
 フレーム ウィンドウのタイトル バーを更新するインプレース アクティブ化時にフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnUpdateFrameTitle();
```  
  
### <a name="return-value"></a>戻り値  
 この場合は&0; 以外の関数は、フレームのタイトルを正常に更新されました、それ以外の場合は&0; です。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、フレーム ウィンドウのタイトルは変更されません。 たとえば、アプリケーションの別のフレームのタイトルを必要する場合は、この関数をオーバーライド" *server アプリ* - *項目*で*docname*"(つまり、"Microsoft Excel のレポートでのスプレッドシートです。DOC") です。 これは、高度なオーバーライドします。  
  
##  <a name="reactivateandundo"></a>COleClientItem::ReactivateAndUndo  
 OLE アイテムを再アクティブ化して、埋め込み先編集中に、ユーザーによって実行される最後の操作を元に戻すには、この関数を呼び出します。  
  
```  
BOOL ReactivateAndUndo();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 コンテナー アプリケーションでは、元に戻すコマンドをサポートする場合は、ユーザーは、OLE アイテムを非アクティブ化した直後に元に戻すコマンドを選択した場合、この関数を呼び出します。  
  
 Microsoft Foundation Class ライブラリとサーバー アプリケーションが書き込まれると、この関数を実行すると、サーバーを呼び出す[されて](../../mfc/reference/coleserverdoc-class.md#onreactivateandundo)します。  
  
 詳細については、次を参照してください。 [IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="release"></a>COleClientItem::Release  
 OLE アイテムによって使用されているリソースをクリーンアップするには、この関数を呼び出します。  
  
```  
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwCloseOption`  
 読み込み済み状態に戻すときに保存する OLE アイテムどのような状況を指定するフラグを設定します。 使用可能な値の一覧は、次を参照してください。 [COleClientItem::Close](#close)します。  
  
### <a name="remarks"></a>コメント  
 **リリース**によって呼び出される、`COleClientItem`デストラクターです。  
  
 詳細については、次を参照してください。 [:release](http://msdn.microsoft.com/library/windows/desktop/ms682317)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="reload"></a>COleClientItem::Reload  
 閉じ、項目を再読み込みします。  
  
```  
BOOL Reload();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出す、`Reload`関数への呼び出しによって別の型の項目として項目をアクティブ化したら[ActivateAs](#activateas)します。  
  
##  <a name="run"></a>COleClientItem::Run  
 この項目に関連付けられているアプリケーションを実行します。  
  
```  
void Run();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す、**実行**メンバー関数、項目をアクティブ化する前にサーバー アプリケーションを起動します。 によって自動的にこれは、 [Activate](#activate)と[DoVerb](#doverb)のためこの関数を呼び出すために必要なことは通常、します。 項目属性を設定するためにサーバーを実行する必要がある場合は、この関数を呼び出す[SetExtent](#setextent)、実行する前に[DoVerb](#doverb)します。  
  
##  <a name="setdrawaspect"></a>COleClientItem::SetDrawAspect  
 呼び出す、 `SetDrawAspect` 「外観」、または項目のビューを設定します。  
  
```  
virtual void SetDrawAspect(DVASPECT nDrawAspect);
```  
  
### <a name="parameters"></a>パラメーター  
 `nDrawAspect`  
 `DVASPECT` 列挙体の値。 このパラメーターには、次のいずれかの値を指定できます。  
  
- `DVASPECT_CONTENT`項目は、そのコンテナー内の埋め込みオブジェクトとして表示できるように表されます。  
  
- `DVASPECT_THUMBNAIL`閲覧ツールで表示されることができるように、「縮小」表現ではアイテムが表示されます。  
  
- `DVASPECT_ICON`項目がアイコンで表されます。  
  
- `DVASPECT_DOCPRINT`[ファイル] メニューから [印刷] コマンドを使用して印刷した場合のように、項目が表されます。  
  
### <a name="remarks"></a>コメント  
 アスペクト項目を指定する方法によって表示される[描画](#draw)とき、既定値を関数の`nDrawAspect`引数を使用します。  
  
 この関数はアイコンの変更 (およびその他のダイアログ ボックスのアイコンの変更 ダイアログ ボックスを直接呼び出す) によって自動的に呼び出されます。 ユーザーが要求されたときに、アイコンの表示アスペクトを有効にします。  
  
##  <a name="setextent"></a>COleClientItem::SetExtent  
 OLE アイテムに使用可能な領域の量を指定するには、この関数を呼び出します。  
  
```  
void SetExtent(
    const CSize& size,  
    DVASPECT nDrawAspect = DVASPECT_CONTENT);
```  
  
### <a name="parameters"></a>パラメーター  
 `size`  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md)サイズ情報を含むオブジェクト。  
  
 `nDrawAspect`  
 境界を設定する OLE アイテムの外観を指定します。 指定できる値は、次を参照してください。[外観](#setdrawaspect)します。  
  
### <a name="remarks"></a>コメント  
 サーバー アプリケーションは、Microsoft Foundation Class ライブラリを使用して記述されました、これを実行すると、 [OnSetExtent](../../mfc/reference/coleserveritem-class.md#onsetextent)対応するメンバー関数`COleServerItem`に呼び出されるオブジェクト。 OLE アイテムは、表示を適宜調整し、できます。 ディメンションがである必要があります`MM_HIMETRIC`単位です。 OLE アイテムが変わると、または何らかの形式のレイアウトのネゴシエーションをサポートする場合は、この関数を呼び出します。  
  
 詳細については、次を参照してください。 [IOleObject::SetExtent](http://msdn.microsoft.com/library/windows/desktop/ms694330)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="sethostnames"></a>COleClientItem::SetHostNames  
 コンテナー アプリケーションの名前と OLE 埋め込みアイテムのコンテナーの名前を指定するには、この関数を呼び出します。  
  
```  
void SetHostNames(
    LPCTSTR lpszHost,  
    LPCTSTR lpszHostObj);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszHost`  
 コンテナー アプリケーションのユーザーに表示される名前へのポインター。  
  
 `lpszHostObj`  
 OLE アイテムを保持するコンテナーの識別文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出す場合は、サーバー アプリケーションは、Microsoft Foundation Class ライブラリを使用して記述されました、[されていると](../../mfc/reference/coleserverdoc-class.md#onsethostnames)のメンバー関数、 `COleServerDoc` OLE アイテムを含むドキュメントです。 この情報は、OLE アイテムを編集するときに、ウィンドウ タイトルに使用されます。 コンテナー ドキュメントが読み込まれるたびに、フレームワークでは、ドキュメント内のすべての OLE アイテムに対してこの関数を呼び出します。 `SetHostNames`埋め込みアイテムにのみ適用されます。 この関数に編集するための OLE 埋め込みアイテムがアクティブ化されるたびを呼び出す必要はありません。  
  
 これとも呼ばれます自動的にアプリケーション名、ドキュメントの名前と、オブジェクトが読み込まれるときに、または別の名前でファイルを保存します。 したがって、この関数を直接呼び出すには通常必要はありません。  
  
 詳細については、次を参照してください。 [IOleObject::SetHostNames](http://msdn.microsoft.com/library/windows/desktop/ms680642)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="seticonicmetafile"></a>COleClientItem::SetIconicMetafile  
 項目のアイコンを描画するために使われるメタファイルをキャッシュします。  
  
```  
BOOL SetIconicMetafile(HGLOBAL hMetaPict);
```  
  
### <a name="parameters"></a>パラメーター  
 `hMetaPict`  
 項目のアイコンを描画するために使われるメタファイルへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用[GetIconicMetafile](#geticonicmetafile)メタファイルを取得します。  
  
 `hMetaPict`アイテムにパラメーターがコピーされるため、`hMetaPict`呼び出し元によって解放する必要があります。  
  
##  <a name="setitemrects"></a>COleClientItem::SetItemRects  
 外接する四角形または OLE アイテムの表示される四角形を設定するには、この関数を呼び出します。  
  
```  
BOOL SetItemRects(
    LPCRECT lpPosRect = NULL,  
    LPCRECT lpClipRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lprcPosRect*  
 クライアント座標で、親ウィンドウの相対 OLE アイテムの境界を保持する四角形へのポインター。  
  
 *lprcClipRect*  
 クライアント座標で、親ウィンドウの相対 OLE アイテムの表示部分の境界を保持する四角形へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装によって、 [OnChangeItemPosition](#onchangeitemposition)メンバー関数。 位置または OLE の表示部分の項目の変更されるたびに、この関数を呼び出す必要があります。 つまり、ビューから呼び出す[OnSize](../../mfc/reference/cwnd-class.md#onsize)と[OnScrollBy](../../mfc/reference/cview-class.md#onscrollby)メンバー関数。  
  
 詳細については、次を参照してください。 [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="setlinkupdateoptions"></a>COleClientItem::SetLinkUpdateOptions  
 指定したリンク アイテムの表示のリンクの更新オプションを設定するには、この関数を呼び出します。  
  
```  
void SetLinkUpdateOptions(OLEUPDATE dwUpdateOpt);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwUpdateOpt*  
 この項目に対するリンクの更新オプションの値。 この値は、次のいずれかを指定する必要があります。  
  
- `OLEUPDATE_ALWAYS`可能な場合は、リンクされた項目を更新します。 このオプションは、リンク ダイアログ ボックスで、リンクの自動更新オプション ボタンをサポートします。  
  
- `OLEUPDATE_ONCALL`コンテナー アプリケーションからの要求にのみリンク アイテムを更新 (ときに、 [UpdateLink](#updatelink)メンバー関数が呼び出されます)。 このオプションは、リンク ダイアログ ボックスで、リンクの手動更新オプション ボタンをサポートします。  
  
### <a name="remarks"></a>コメント  
 通常、リンク ダイアログ ボックスでユーザーが選択した更新プログラムのオプションを変更する必要がありません。  
  
 詳細については、次を参照してください。 [IOleLink::SetUpdateOptions](http://msdn.microsoft.com/library/windows/desktop/ms680120)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="setprintdevice"></a>COleClientItem::SetPrintDevice  
 この項目の出力先のデバイスを変更するには、この関数を呼び出します。  
  
```  
BOOL SetPrintDevice(const DVTARGETDEVICE* ptd);  
BOOL SetPrintDevice(const PRINTDLG* ppd);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptd`  
 ポインター、 [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613)データ構造は、新しい出力先のデバイスに関する情報が含まれています。 できる**NULL**します。  
  
 `ppd`  
 ポインター、 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646940)新しい出力先のデバイスに関する情報を含むデータ構造体。 できる**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、項目の出力先のデバイスの更新が、プレゼンテーションのキャッシュは更新しません。 アイテムのプレゼンテーションのキャッシュを更新するには、呼び出す[UpdateLink](#updatelink)します。  
  
 この関数に対する引数には、ターゲット デバイスを識別する OLE システムを使用して情報が含まれます。 **PRINTDLG**構造体には、Windows に共通の印刷 ダイアログ ボックスを初期化するために使用する情報が含まれています。 ユーザーがダイアログ ボックスを閉じた後、Windows は、この構造体でユーザーの選択に関する情報を返します。 `m_pd`のメンバー、 [CPrintDialog](../../mfc/reference/cprintdialog-class.md)オブジェクトが、 **PRINTDLG**構造体。  
  
 この構造体の詳細については、次を参照してください。 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 詳細については、次を参照してください。 [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="updatelink"></a>COleClientItem::UpdateLink  
 OLE アイテムのプレゼンテーションのデータを直ちに更新するには、この関数を呼び出します。  
  
```  
BOOL UpdateLink();
```  
  
### <a name="return-value"></a>戻り値  
 正常に完了した場合はゼロ以外、それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 リンクされた項目は、関数は、OLE アイテムの新しいプレゼンテーションを取得するリンクのソースを検索します。 このプロセスは、時間がかかる場合も、1 つまたは複数のサーバー アプリケーションを実行する必要があります。 埋め込みアイテムの関数の動作を再帰的に、埋め込みアイテムが古い可能性のあるリンクを含めるかどうかをチェックし、それらを更新します。 ユーザーは、リンク ダイアログ ボックスを使用して個々 のリンクを手動で更新できます。  
  
 詳細については、次を参照してください。 [IOleLink::Update](http://msdn.microsoft.com/library/windows/desktop/ms692660)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MFCBIND](../../visual-cpp-samples.md)   
 [MFC サンプルの OCLIENT](../../visual-cpp-samples.md)   
 [CDocItem クラス](../../mfc/reference/cdocitem-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [実際のクラス](../../mfc/reference/coleserveritem-class.md)

