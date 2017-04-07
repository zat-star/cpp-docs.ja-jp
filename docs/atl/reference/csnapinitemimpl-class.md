---
title: "CSnapInItemImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl::CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl::AddMenuItems
- ATLSNAP/ATL::CSnapInItemImpl::Command
- ATLSNAP/ATL::CSnapInItemImpl::CreatePropertyPages
- ATLSNAP/ATL::CSnapInItemImpl::FillData
- ATLSNAP/ATL::CSnapInItemImpl::GetResultPaneInfo
- ATLSNAP/ATL::CSnapInItemImpl::GetResultViewType
- ATLSNAP/ATL::CSnapInItemImpl::GetScopePaneInfo
- ATLSNAP/ATL::CSnapInItemImpl::Notify
- ATLSNAP/ATL::CSnapInItemImpl::QueryPagesFor
- ATLSNAP/ATL::CSnapInItemImpl::SetMenuInsertionFlags
- ATLSNAP/ATL::CSnapInItemImpl::SetToolbarButtonInfo
- ATLSNAP/ATL::CSnapInItemImpl::UpdateMenuState
- ATLSNAP/ATL::CSnapInItemImpl::UpdateToolbarButton
- ATLSNAP/ATL::CSnapInItemImpl::m_bstrDisplayName
- ATLSNAP/ATL::CSnapInItemImpl::m_resultDataItem
- ATLSNAP/ATL::CSnapInItemImpl::m_scopeDataItem
dev_langs:
- C++
helpviewer_keywords:
- snap-ins, data items
- snap-ins, ATL support for
- CSnapInItemImpl class
- snap-ins
ms.assetid: 52caefbd-9eae-49b0-add2-d55524271aa7
caps.latest.revision: 20
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 9148ee71ba03a1a0492d390378c64f988e6e0f39
ms.lasthandoff: 02/24/2017

---
# <a name="csnapinitemimpl-class"></a>CSnapInItemImpl クラス
このクラスは、スナップイン ノード オブジェクトを実装するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, BOOL bIsExtension = FALSE>  
class ATL_NO_VTABLE CSnapInItemImpl : public CSnapInItem
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`CSnapInItemImpl`です。  
  
 *bIsExtension*  
 **TRUE**オブジェクトがスナップイン拡張機能の場合それ以外の場合**FALSE**します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSnapInItemImpl::CSnapInItemImpl](#csnapinitemimpl)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSnapInItemImpl::AddMenuItems](#addmenuitems)|コンテキスト メニューにメニュー項目を追加します。|  
|[CSnapInItemImpl::Command](#command)|カスタム メニュー項目を選択すると、コンソールを使用して呼び出されます。|  
|[CSnapInItemImpl::CreatePropertyPages](#createpropertypages)|スナップインのプロパティ シートにページを追加します。|  
|[CSnapInItemImpl::FillData](#filldata)|スナップイン オブジェクトの情報を指定したストリームにコピーします。|  
|[CSnapInItemImpl::GetResultPaneInfo](#getresultpaneinfo)|取得、 **RESULTDATAITEM**スナップインの構造です。|  
|[CSnapInItemImpl::GetResultViewType](#getresultviewtype)|結果ウィンドウで使用されるビューの種類を決定します。|  
|[CSnapInItemImpl::GetScopePaneInfo](#getscopepaneinfo)|取得、 **SCOPEDATAITEM**スナップインの構造です。|  
|[CSnapInItemImpl::Notify](#notify)|ユーザーによって実行されたアクションのスナップインに通知するコンソールを使用して呼び出されます。|  
|[CSnapInItemImpl::QueryPagesFor](#querypagesfor)|スナップインのノード プロパティ ページでサポートされているかどうかに呼び出されます。|  
|[CSnapInItemImpl::SetMenuInsertionFlags](#setmenuinsertionflags)|スナップイン オブジェクトに対するメニュー挿入フラグを変更します。|  
|[CSnapInItemImpl::SetToolbarButtonInfo](#settoolbarbuttoninfo)|指定されたツール バー ボタンの情報を設定します。|  
|[CSnapInItemImpl::UpdateMenuState](#updatemenustate)|コンテキスト メニュー項目の状態を更新します。|  
|[CSnapInItemImpl::UpdateToolbarButton](#updatetoolbarbutton)|指定されたツール バー ボタンの状態を更新します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CSnapInItemImpl::m_bstrDisplayName](#m_bstrdisplayname)|スナップインでオブジェクトの名前。|  
|[CSnapInItemImpl::m_resultDataItem](#m_resultdataitem)|Windows **RESULTDATAITEM**によって使用される構造、`CSnapInItemImpl`オブジェクトです。|  
|[CSnapInItemImpl::m_scopeDataItem](#m_scopedataitem)|Windows **SCOPEDATAITEM**によって使用される構造、`CSnapInItemImpl`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `CSnapInItemImpl`メニュー項目とツールバーを追加して、適切なハンドラー関数にスナップイン ノード用のコマンドの転送などのスナップイン ノード オブジェクトの基本実装を提供します。 これらの機能は、複数のインターフェイスを使用して実装し、型をマップします。 既定の実装は、派生クラスの適切なインスタンスを確認し、適切なインスタンスにメッセージを転送し、ノードのオブジェクトに送信する通知を処理します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CSnapInItem`  
  
 `CSnapInItemImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsnap.h  
  
##  <a name="addmenuitems"></a>CSnapInItemImpl::AddMenuItems  
 このメソッドは、Win32 関数を実装します。 [IExtendContextMenu::AddMenuItems](http://msdn.microsoft.com/library/aa814841)します。  
  
```
AddMenuItems(  
    LPCONTEXTMENUCALLBACK piCallback,
    long* pInsertionAllowed,
    DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>パラメーター  
 *piCallback*  
 [in]ポインター、 **IContextMenuCallback**コンテキスト メニューに項目を追加することができます。  
  
 `pInsertionAllowed`  
 [入力、出力]識別する Microsoft 管理コンソール MMC で定義されているメニュー項目挿入ポイントを使用することができます。 次のフラグの組み合わせになります。  
  
- **CCM_INSERTIONALLOWED_TOP**コンテキスト メニューの上部にある項目を挿入することができます。  
  
- **CCM_INSERTIONALLOWED_NEW** [新規作成] サブメニューで項目を挿入することができます。  
  
- **CCM_INSERTIONALLOWED_TASK**タスク サブメニューに項目を挿入することができます。  
  
- **CCM_INSERTIONALLOWED_VIEW**ツールバーの表示 メニューまたは結果のウィンドウのコンテキスト メニューの ビュー サブメニュー項目を挿入することができます。  
  
 `type`  
 [in]オブジェクトの種類を指定します。 次の値のいずれかを取ります。  
  
- **CCT_SCOPE**スコープ ウィンドウのコンテキストのデータ オブジェクト。  
  
- **CCT_RESULT**結果ペインのコンテキストのデータ オブジェクト。  
  
- **CCT_SNAPIN_MANAGER**マネージャー スナップインでコンテキストのデータ オブジェクト。  
  
- **CCT_UNINITIALIZED**データ オブジェクトには型が無効です。  
  
##  <a name="command"></a>CSnapInItemImpl::Command  
 このメソッドは、Win32 関数を実装します。 [IExtendContextMenu::Command](http://msdn.microsoft.com/library/aa814842)します。  
  
```
Command(long lCommandID, DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>パラメーター  
 *lCommandID*  
 [in]メニュー項目のコマンド識別子を指定します。  
  
 `type`  
 [in]オブジェクトの種類を指定します。 次の値のいずれかを取ります。  
  
- **CCT_SCOPE**スコープ ウィンドウのコンテキストのデータ オブジェクト。  
  
- **CCT_RESULT**結果ペインのコンテキストのデータ オブジェクト。  
  
- **CCT_SNAPIN_MANAGER**マネージャー スナップインでコンテキストのデータ オブジェクト。  
  
- **CCT_UNINITIALIZED**データ オブジェクトには型が無効です。  
  
##  <a name="createpropertypages"></a>CSnapInItemImpl::CreatePropertyPages  
 このメソッドは、Win32 関数を実装します。 [IExtendPropertySheet::CreatePropertyPages](http://msdn.microsoft.com/library/aa814846)します。  
  
```
CreatePropertyPages(  
    LPPROPERTYSHEETCALLBACK lpProvider,
    long handle,
    IUnknown* pUnk,
    DATA_OBJECT_TYPES type);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpProvider*  
 [in]ポインター、**プロパティ シート フレーム**インターフェイスです。  
  
 *ハンドル*  
 [in]使用しているハンドルを指定のルートに、 **MMCN_PROPERTY_CHANGE**通知メッセージを適切なデータ クラスにします。  
  
 *pUnk*  
 [in]ポインター、 **IExtendPropertySheet**ノードに関するコンテキスト情報を含むオブジェクトのインターフェイスです。  
  
 `type`  
 [in]オブジェクトの種類を指定します。 次の値のいずれかを取ります。  
  
- **CCT_SCOPE**スコープ ウィンドウのコンテキストのデータ オブジェクト。  
  
- **CCT_RESULT**結果ペインのコンテキストのデータ オブジェクト。  
  
- **CCT_SNAPIN_MANAGER**マネージャー スナップインでコンテキストのデータ オブジェクト。  
  
- **CCT_UNINITIALIZED**データ オブジェクトには型が無効です。  
  
##  <a name="csnapinitemimpl"></a>CSnapInItemImpl::CSnapInItemImpl  
 `CSnapInItemImpl` オブジェクトを構築します。  
  
```
CSnapInItemImpl();
```  
  
##  <a name="filldata"></a>CSnapInItemImpl::FillData  
 この関数は、項目に関する情報を取得します。  
  
```
FillData(CLIPFORMAT cf, LPSTREAM pStream);
```  
  
### <a name="parameters"></a>パラメーター  
 `cf`  
 [in]クリップボードの形式 (テキスト、リッチ テキストまたはリッチ テキスト OLE 項目を含む)。  
  
 `pStream`  
 [in]オブジェクトのデータを格納しているストリームへのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数を正しく実装するのには、ストリームに、正しい情報をコピー ( `pStream`) で示されるクリップボードの形式に応じて、`cf`です。  
  
##  <a name="getresultviewtype"></a>CSnapInItemImpl::GetResultViewType  
 この関数では、スナップイン オブジェクトの結果ペインのビューの種類を取得します。  
  
```
GetResultViewType(
    LPOLESTR* ppViewType,
    long* pViewOptions);
```  
  
### <a name="parameters"></a>パラメーター  
 *取得可能です。*  
 [out]返されるビューの種類のアドレスへのポインター。  
  
 *pViewOptions*  
 [out]ポインター、 **MMC_VIEW_OPTIONS**列挙体は、所有するスナップインによって指定されたオプションをコンソールを提供します。 この値は、次のいずれかになります。  
  
- **MMC_VIEW_OPTIONS_NOLISTVIEWS** = 0x00000001 通知、コンソールで標準のリスト ビューの選択肢を表示しないように、**ビュー**メニュー。 結果ビュー ペインでのみ、独自のカスタム ビューを表示するスナップインにより、できます。 これは、この時点で定義されている唯一のオプション フラグです。  
  
- **MMC_VIEW_OPTIONS_NONE** 0 が既定のビューのオプションを = です。  
  
##  <a name="getscopepaneinfo"></a>CSnapInItemImpl::GetScopePaneInfo  
 取得するには、この関数を呼び出して、 **SCOPEDATAITEM**スナップインの構造です。  
  
```
GetScopePaneInfo (SCOPEDATAITEM* pScopeDataItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *pScopeDataItem*  
 [out]ポインター、 **SCOPEDATAITEM**の構造、`CSnapInItemImpl`オブジェクトです。  
  
##  <a name="getresultpaneinfo"></a>CSnapInItemImpl::GetResultPaneInfo  
 取得するには、この関数を呼び出して、 **RESULTDATAITEM**スナップインの構造です。  
  
```
GetResultPaneInfo (RESULTDATAITEM* pResultDataItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *pResultDataItem*  
 [out]ポインター、 **RESULTDATAITEM**の構造、`CSnapInItemImpl`オブジェクトです。  
  
##  <a name="m_bstrdisplayname"></a>CSnapInItemImpl::m_bstrDisplayName  
 ノードのアイテムの表示される文字列が含まれています。  
  
```
CComBSTR m_bstrDisplayName;
```  
  
##  <a name="m_scopedataitem"></a>CSnapInItemImpl::m_scopeDataItem  
 `SCOPEDATAITEM`スナップイン データ オブジェクトの構造です。  
  
```
SCOPEDATAITEM m_scopeDataItem;
```  
  
##  <a name="m_resultdataitem"></a>CSnapInItemImpl::m_resultDataItem  
 [RESULTDATAITEM](http://msdn.microsoft.com/library/aa815165)スナップイン データ オブジェクトの構造です。  
  
```
RESULTDATAITEM m_resultDataItem;
```  
  
##  <a name="notify"></a>CSnapInItemImpl::Notify  
 スナップイン オブジェクトは、ユーザーが機能と呼び出されます。  
  
```
STDMETHOD(Notify)(
    MMC_NOTIFY_TYPE event,
    long arg,
    long param,
    IComponentData* pComponentData,
    IComponent* pComponent,
    DATA_OBJECT_TYPES type) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `event`  
 [in]ユーザーが実行する操作を識別します。 次の通知が考えられます。  
  
- **MMCN_ACTIVATE**がアクティブ化、非アクティブ化には、ウィンドウの場合に送信します。  
  
- **MMCN_ADD_IMAGES**宛ての結果ウィンドウにイメージを追加します。  
  
- **MMCN_BTN_CLICK**ツール バー ボタンのいずれかのユーザーがクリックしたときに送信します。  
  
- **MMCN_CLICK**ユーザーがリスト ビューの項目上でマウス ボタンをクリックしたときに送信します。  
  
- **MMCN_DBLCLICK**ユーザーは、リスト ビューの項目上でマウス ボタンを含むことがダブルクリックしたときに送信します。  
  
- **MMCN_DELETE**に送信され、オブジェクトをするか、スナップインの報告を削除します。  
  
- **MMCN_EXPAND**フォルダーを展開または縮小する必要があるときに送信します。  
  
- **MMCN_MINIMIZED**最小化または最大化するには時のウィンドウに送信します。  
  
- **MMCN_PROPERTY_CHANGE**スナップイン オブジェクトのビューが変更されようスナップイン オブジェクトに通知されます。  
  
- **MMCN_REMOVE_CHILDREN**スナップインでする必要がありますが、指定したノードの下に追加全体サブツリーの削除時に送信します。  
  
- **MMCN_RENAME**を名前の変更を行うには、名前の変更を照会する最初と&2; 回目を送信します。  
  
- **MMCN_SELECT**スコープまたは結果ビュー ペインでアイテムが選択されているときに送信します。  
  
- **MMCN_SHOW**スコープ項目が選択されているかを初めて選択解除されたときに送信します。  
  
- **MMCN_VIEW_CHANGE**スナップインからすべてのビューを更新、変更が発生したときにときに送信します。  
  
 `arg`  
 [in]通知の種類によって異なります。  
  
 `param`  
 [in]通知の種類によって異なります。  
  
 *pComponentData*  
 [out]実装するオブジェクトへのポインター **IComponentData**します。 このパラメーターは**NULL**通知がから転送されていない場合**IComponentData::Notify**します。  
  
 *pComponent*  
 [out]実装するオブジェクトへのポインター **IComponent**します。 このパラメーターは**NULL**通知がから転送されていない場合**IComponent::Notify**します。  
  
 `type`  
 [in]オブジェクトの種類を指定します。 次の値のいずれかを取ります。  
  
- **CCT_SCOPE**スコープ ウィンドウのコンテキストのデータ オブジェクト。  
  
- **CCT_RESULT**結果ペインのコンテキストのデータ オブジェクト。  
  
- **CCT_SNAPIN_MANAGER**マネージャー スナップインでコンテキストのデータ オブジェクト。  
  
- **CCT_UNINITIALIZED**データ オブジェクトには型が無効です。  
  
##  <a name="querypagesfor"></a>CSnapInItemImpl::QueryPagesFor  
 スナップインのノード プロパティ ページでサポートされているかどうかに呼び出されます。  
  
```
QueryPagesFor(DATA_OBJECT_TYPES type);
```  
  
##  <a name="setmenuinsertionflags"></a>CSnapInItemImpl::SetMenuInsertionFlags  
 指定されたメニュー挿入フラグを変更するには、この関数を呼び出す`pInsertionAllowed`、スナップイン オブジェクトです。  
  
```
void SetMenuInsertionFlags(  
    bool bBeforeInsertion,
    long* pInsertionAllowed);
```  
  
### <a name="parameters"></a>パラメーター  
 *bBeforeInsertion*  
 [in]項目が、コンテキスト メニューに追加する前に、関数を呼び出す必要がある場合は 0 以外それ以外の場合 0 を返します。  
  
 `pInsertionAllowed`  
 [入力、出力]識別する Microsoft 管理コンソール MMC で定義されているメニュー項目挿入ポイントを使用することができます。 次のフラグの組み合わせになります。  
  
- **CCM_INSERTIONALLOWED_TOP**コンテキスト メニューの上部にある項目を挿入することができます。  
  
- **CCM_INSERTIONALLOWED_NEW** [新規作成] サブメニューで項目を挿入することができます。  
  
- **CCM_INSERTIONALLOWED_TASK**タスク サブメニューに項目を挿入することができます。  
  
- **CCM_INSERTIONALLOWED_VIEW**ツールバーの表示 メニューまたは結果のウィンドウのコンテキスト メニューの ビュー サブメニュー項目を挿入することができます。  
  
### <a name="remarks"></a>コメント  
 プライマリのスナップインを開発する場合は、サード パーティ製の拡張機能を追加するメニュー項目の種類を制限する方法として挿入フラグのいずれかをリセットできます。 たとえば、プライマリのスナップインをオフ、 **CCM_INSERTIONALLOWED_NEW**拡張機能が、独自の新規作成メニュー項目を追加するを防ぐためのフラグ。  
  
 ビットを設定しないで`pInsertionAllowed`もともとをクリアします。 MMC の将来のバージョンでは、定義されていない現在のビットが変わらないようにするために定義されていないビットを使用できます。  
  
##  <a name="settoolbarbuttoninfo"></a>CSnapInItemImpl::SetToolbarButtonInfo  
 ツールバーを作成する前に、スナップイン オブジェクトのツール バー ボタンのスタイルを変更するには、この関数を呼び出します。  
  
```
void SetToolbarButtonInfo(  
    UINT id,
    BYTE* fsState,
    BYTE* fsType);
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]設定するツール バー ボタンの ID です。  
  
 `fsState`  
 [in]ボタンの状態フラグ。 次の&1; つ以上を指定できます。  
  
- `TBSTATE_CHECKED`ボタンには、**スタイル**のスタイルを設定して、押されました。  
  
- `TBSTATE_ENABLED`ボタンは、ユーザー入力を受け付けます。 この状態がないボタンは、ユーザー入力が受け付けられません、淡色表示にします。  
  
- `TBSTATE_HIDDEN`ボタンは表示されず、ユーザー入力を受け取ることはできません。  
  
- `TBSTATE_INDETERMINATE`ボタンは淡色表示にします。  
  
- `TBSTATE_PRESSED`ボタンが押されました。  
  
- `TBSTATE_WRAP`行の区切りには、ボタンが次に示します。 ボタンが必要、`TBSTATE_ENABLED`です。  
  
 *すれば*  
 [in]ボタンの状態フラグ。 次の&1; つ以上を指定できます。  
  
- `TBSTYLE_BUTTON`標準プッシュ ボタンを作成します。  
  
- `TBSTYLE_CHECK`ユーザーがクリックするたびに押された状態と not 押された状態の間を切り替えるボタンを作成します。 ボタンには、押された状態にあるときに、別の背景色です。  
  
- `TBSTYLE_CHECKGROUP`グループ内の別のボタンが押されるまで押されたままにするチェック マーク ボタンを作成します。  
  
- `TBSTYLE_GROUP`グループ内の別のボタンが押されるまで押されたままにする ボタンを作成します。  
  
- `TBSTYLE_SEP`小さなボタン グループにギャップを提供する、区切り記号を作成します。 ボタンをクリックし、このスタイルでは、ユーザー入力を受信しません。  
  
##  <a name="updatemenustate"></a>CSnapInItemImpl::UpdateMenuState  
 この関数では、スナップイン オブジェクトのコンテキスト メニューに挿入する前に、メニュー項目を変更します。  
  
```
void UpdateMenuState(  
    UINT id,
    LPTSTR pBuf,
    UINT* flags);
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 [in]設定するメニュー項目の ID です。  
  
 `pBuf`  
 [in]更新するメニュー項目の文字列へのポインター。  
  
 `flags`  
 [in]新しい状態フラグを指定します。 次のフラグの組み合わせになります。  
  
- **ならば**コンテキスト メニューのサブメニューであることを指定します。 このサブメニューを使用するのには、メニュー項目、挿入ポイント、およびさらに、サブメニューを追加することがあります、 **lCommandID**としてその**IInsertionPointID**します。  
  
- **MF_BITMAP**と`MF_OWNERDRAW`これらのフラグが許可されていないの戻り値になります`E_INVALIDARG`します。  
  
- **MF_SEPARATOR**水平分割線を描画します。 のみ**IContextMenuProvider**でメニュー項目の追加が許可された**MF_SEPARATOR**を設定します。  
  
- ****メニュー項目の横にあるチェック マークを挿入します。  
  
- **MF_DISABLED**メニュー項目を無効にして、選択できない場合は、フラグによってグレーしないようにします。  
  
- `MF_ENABLED`メニュー項目は、選択できるように、淡色表示されている状態から復元するために使用できます。  
  
- **MF_GRAYED**ため選択できませんににグレーアウト、メニュー項目を無効にします。  
  
- **MF_MENUBARBREAK**と同様に機能、 **MF_MENUBREAK**メニュー バーのフラグ。 ドロップダウン メニューのサブメニュー、またはショートカット メニューの新しい列は、垂直線で、古い列から区切られます。  
  
- **MF_MENUBREAK** (メニュー バー) の新しい行にアイテムを配置または列を分離することがなく (ドロップダウン メニューのサブメニュー、またはショートカット メニュー) の新しい列にします。  
  
- **MF_UNCHECKED**項目 (既定値) の横にチェック マークは配置されません。  
  
 次のフラグのグループを一緒に使用できません。  
  
- **MF_DISABLED**、 `MF_ENABLED`、および**MF_GRAYED**します。  
  
- **MF_MENUBARBREAK**と**MF_MENUBREAK**します。  
  
- ****と**MF_UNCHECKED**します。  
  
##  <a name="updatetoolbarbutton"></a>CSnapInItemImpl::UpdateToolbarButton  
 表示されるまでに、スナップイン オブジェクトのツール バー ボタンを変更するには、この関数を呼び出します。  
  
```
BOOL UpdateToolbarButton(UINT id, BYTE fsState);
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 更新するツール バー ボタンのボタン ID を指定します。  
  
 `fsState`  
 ツール バー ボタンの状態を指定します。 この状態を設定する場合は、返す**TRUE**します。 次のフラグの組み合わせになります。  
  
- **有効になっている**ユーザー入力を受け付ける、ボタンをクリックします。 この状態がないボタンは、ユーザー入力が受け付けられません、淡色表示にします。  
  
- **オンになって**にこのボタンは、**チェック**のスタイルを設定して、押されました。  
  
- **HIDDEN**ボタンが表示されていないと、ユーザー入力を受け取ることはできません。  
  
- **不確定な**ボタンが淡色表示されます。  
  
- **BUTTONPRESSED**ボタンが押されました。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

