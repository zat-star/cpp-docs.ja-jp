---
title: "メンバー クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleControlContainer
- AFXOCC/COleControlContainer
- AFXOCC/COleControlContainer::COleControlContainer
- AFXOCC/COleControlContainer::AttachControlSite
- AFXOCC/COleControlContainer::BroadcastAmbientPropertyChange
- AFXOCC/COleControlContainer::CheckDlgButton
- AFXOCC/COleControlContainer::CheckRadioButton
- AFXOCC/COleControlContainer::CreateControl
- AFXOCC/COleControlContainer::CreateOleFont
- AFXOCC/COleControlContainer::FindItem
- AFXOCC/COleControlContainer::FreezeAllEvents
- AFXOCC/COleControlContainer::GetAmbientProp
- AFXOCC/COleControlContainer::GetDlgItem
- AFXOCC/COleControlContainer::GetDlgItemInt
- AFXOCC/COleControlContainer::GetDlgItemText
- AFXOCC/COleControlContainer::HandleSetFocus
- AFXOCC/COleControlContainer::HandleWindowlessMessage
- AFXOCC/COleControlContainer::IsDlgButtonChecked
- AFXOCC/COleControlContainer::OnPaint
- AFXOCC/COleControlContainer::OnUIActivate
- AFXOCC/COleControlContainer::OnUIDeactivate
- AFXOCC/COleControlContainer::ScrollChildren
- AFXOCC/COleControlContainer::SendDlgItemMessage
- AFXOCC/COleControlContainer::SetDlgItemInt
- AFXOCC/COleControlContainer::SetDlgItemText
- AFXOCC/COleControlContainer::m_crBack
- AFXOCC/COleControlContainer::m_crFore
- AFXOCC/COleControlContainer::m_listSitesOrWnds
- AFXOCC/COleControlContainer::m_nWindowlessControls
- AFXOCC/COleControlContainer::m_pOleFont
- AFXOCC/COleControlContainer::m_pSiteCapture
- AFXOCC/COleControlContainer::m_pSiteFocus
- AFXOCC/COleControlContainer::m_pSiteUIActive
- AFXOCC/COleControlContainer::m_pWnd
- AFXOCC/COleControlContainer::m_siteMap
dev_langs:
- C++
helpviewer_keywords:
- custom controls [MFC], sites
- COleControlContainer class
- ActiveX control containers [C++], control site
ms.assetid: f7ce9246-0fb7-4f07-a83a-6c2390d0fdf8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 764583d28bf71319eac5b7e51e0915ae786261a7
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="colecontrolcontainer-class"></a>メンバー クラス
ActiveX コントロールのコントロール コンテナーとして機能します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleControlContainer : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleControlContainer::COleControlContainer](#colecontrolcontainer)|`COleControlContainer` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleControlContainer::AttachControlSite](#attachcontrolsite)|コンテナーによってホストされるコントロール サイトを作成します。|  
|[COleControlContainer::BroadcastAmbientPropertyChange](#broadcastambientpropertychange)|アンビエント プロパティが変更されたホストされるすべてのコントロールに通知します。|  
|[COleControlContainer::CheckDlgButton](#checkdlgbutton)|指定されたボタン コントロールを変更します。|  
|[COleControlContainer::CheckRadioButton](#checkradiobutton)|グループの指定されたオプション ボタンを選択します。|  
|[COleControlContainer::CreateControl](#createcontrol)|ホストされている ActiveX コントロールを作成します。|  
|[COleControlContainer::CreateOleFont](#createolefont)|OLE フォントを作成します。|  
|[COleControlContainer::FindItem](#finditem)|指定されたコントロールのカスタムのサイトを返します。|  
|[COleControlContainer::FreezeAllEvents](#freezeallevents)|コントロール サイトがイベントを受け入れるかどうかを判断します。|  
|[COleControlContainer::GetAmbientProp](#getambientprop)|指定されたアンビエント プロパティを取得します。|  
|[COleControlContainer::GetDlgItem](#getdlgitem)|指定されたダイアログ コントロールを取得します。|  
|[COleControlContainer::GetDlgItemInt](#getdlgitemint)|指定したダイアログ コントロールの値を取得します。|  
|[COleControlContainer::GetDlgItemText](#getdlgitemtext)|指定したダイアログ コントロールのキャプションを取得します。|  
|[COleControlContainer::HandleSetFocus](#handlesetfocus)|コンテナーが処理を決定`WM_SETFOCUS`メッセージです。|  
|[COleControlContainer::HandleWindowlessMessage](#handlewindowlessmessage)|ウィンドウなしのコントロールに送信されたメッセージを処理します。|  
|[COleControlContainer::IsDlgButtonChecked](#isdlgbuttonchecked)|指定したボタンの状態を判断します。|  
|[COleControlContainer::OnPaint](#onpaint)|コンテナーの一部を再描画と呼ばれます。|  
|[COleControlContainer::OnUIActivate](#onuiactivate)|コントロールが埋め込みでアクティブ化されると呼び出されます。|  
|[COleControlContainer::OnUIDeactivate](#onuideactivate)|コントロールが非アクティブにすると呼び出されます。|  
|[COleControlContainer::ScrollChildren](#scrollchildren)|子ウィンドウからスクロール メッセージを受信するときに、フレームワークによって呼び出されます。|  
|[COleControlContainer::SendDlgItemMessage](#senddlgitemmessage)|指定されたコントロールにメッセージを送信します。|  
|[COleControlContainer::SetDlgItemInt](#setdlgitemint)|指定したコントロールの値を設定します。|  
|[COleControlContainer::SetDlgItemText](#setdlgitemtext)|指定したコントロールのテキストを設定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleControlContainer::m_crBack](#m_crback)|コンテナーの背景色。|  
|[COleControlContainer::m_crFore](#m_crfore)|コンテナーの前景色。|  
|[COleControlContainer::m_listSitesOrWnds](#m_listsitesorwnds)|サポートされているコントロールのサイトの一覧。|  
|[COleControlContainer::m_nWindowlessControls](#m_nwindowlesscontrols)|ホストされたウィンドウなしのコントロールの数。|  
|[COleControlContainer::m_pOleFont](#m_polefont)|OLE フォントのカスタム コントロール サイトへのポインター。|  
|[COleControlContainer::m_pSiteCapture](#m_psitecapture)|キャプチャ コントロール サイトへのポインター。|  
|[COleControlContainer::m_pSiteFocus](#m_psitefocus)|現在入力フォーカス コントロールへのポインター。|  
|[COleControlContainer::m_pSiteUIActive](#m_psiteuiactive)|インプレースでアクティブになっているコントロールへのポインター。|  
|[COleControlContainer::m_pWnd](#m_pwnd)|コントロールのコンテナーを実装するウィンドウへのポインター。|  
|[COleControlContainer::m_siteMap](#m_sitemap)|サイト マップします。|  
  
## <a name="remarks"></a>コメント  
 これは、1 つまたは複数の ActiveX コントロール サイトをサポートすることで (によって実装される`COleControlSite`)。 `COleControlContainer`完全に実装する、 [IOleInPlaceFrame](http://msdn.microsoft.com/library/windows/desktop/ms692770)と[IOleContainer](http://msdn.microsoft.com/library/windows/desktop/ms690103)インターフェイス、埋め込み先アイテムとして、必要条件を満たすために格納されている ActiveX コントロールを許可します。  
  
 一般的には、このクラスと組み合わせて使用`COccManager`と`COleControlSite`を&1; つまたは複数の ActiveX コントロールのカスタムのサイトとカスタム ActiveX コントロール コンテナーを実装します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlContainer`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxocc.h  
  
##  <a name="attachcontrolsite"></a>COleControlContainer::AttachControlSite  
 作成し、コントロールのサイトに接続するためにフレームワークによって呼び出されます。  
  
```  
virtual void AttachControlSite(
    CWnd* pWnd,  
    UINT nIDC = 0);

 
void AttachControlSite(
    CWnd* pWnd,  
    UINT nIDC = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 ポインター、`CWnd`オブジェクトです。  
  
 `nIDC`  
 接続する、コントロールの ID。  
  
### <a name="remarks"></a>コメント  
 このプロセスをカスタマイズする場合は、この関数をオーバーライドします。  
  
> [!NOTE]
>  MFC ライブラリに静的にリンクしている場合は、この関数の最初の形式を使用します。 MFC ライブラリに動的にリンクしている場合は、2 番目の形式を使用します。  
  
##  <a name="broadcastambientpropertychange"></a>COleControlContainer::BroadcastAmbientPropertyChange  
 アンビエント プロパティが変更されたホストされるすべてのコントロールに通知します。  
  
```  
virtual void BroadcastAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 変更されたアンビエント プロパティのディスパッチの ID。  
  
### <a name="remarks"></a>コメント  
 アンビエント プロパティの値が変更されたときに、この関数は、フレームワークによって呼び出されます。 この動作をカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="checkdlgbutton"></a>COleControlContainer::CheckDlgButton  
 ボタンの現在の状態を変更します。  
  
```  
virtual void CheckDlgButton(
    int nIDButton,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDButton`  
 変更するボタンの ID。  
  
 `nCheck`  
 ボタンの状態を指定します。 次のいずれかの値を指定します。  
  
- **BST_CHECKED**ボタンの状態をオフに設定します。  
  
- **BST_INDETERMINATE**淡色表示されている、不確定な状態を示すボタンの状態を設定します。 この値を使用して、ボタンがある場合のみ、 **BS_3STATE**または**BS_AUTO3STATE**スタイル。  
  
- **設定されている**ボタンの状態をオフに設定します。  
  
##  <a name="checkradiobutton"></a>COleControlContainer::CheckRadioButton  
 グループ内の指定されたオプション ボタンを選択し、グループ内の残りのボタンをクリアします。  
  
```  
virtual void CheckRadioButton(
    int nIDFirstButton,  
    int nIDLastButton,  
    int nIDCheckButton);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDFirstButton`  
 グループ内の最初のオプション ボタンの識別子を指定します。  
  
 `nIDLastButton`  
 グループ内の最後のオプション ボタンの識別子を指定します。  
  
 `nIDCheckButton`  
 チェックするオプション ボタンの識別子を指定します。  
  
##  <a name="colecontrolcontainer"></a>COleControlContainer::COleControlContainer  
 `COleControlContainer` オブジェクトを構築します。  
  
```  
explicit COleControlContainer(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 コントロールのコンテナーの親ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 オブジェクトが正常に作成される追加のカスタム コントロール サイトへの呼び出しを`AttachControlSite`します。  
  
##  <a name="createcontrol"></a>COleControlContainer::CreateControl  
 指定したホストされている、ActiveX コントロールを作成`COleControlSite`オブジェクトです。  
  
```  
BOOL CreateControl(
    CWnd* pWndCtrl,  
    REFCLSID clsid,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    UINT nID,  
    CFile* pPersist =NULL,  
    BOOL bStorage =FALSE,  
    BSTR bstrLicKey =NULL,  
    COleControlSite** ppNewSite =NULL);

 
BOOL CreateControl(
    CWnd* pWndCtrl,  
    REFCLSID clsid,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const POINT* ppt,  
    const SIZE* psize,  
    UINT nID,  
    CFile* pPersist =NULL,  
    BOOL bStorage =FALSE,  
    BSTR bstrLicKey =NULL,  
    COleControlSite** ppNewSite =NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWndCtrl`  
 コントロールを表すウィンドウ オブジェクトへのポインター。  
  
 `clsid`  
 コントロールの一意のクラス ID。  
  
 `lpszWindowName`  
 コントロールに表示されるテキストへのポインター。 (もしあれば) は、コントロールのキャプションまたはテキストのプロパティの値を設定します。 場合**NULL**コントロールのキャプションまたはテキストのプロパティは変更されません。  
  
 `dwStyle`  
 ウィンドウ スタイル。 使用できるスタイルについては、「、**解説**セクションです。  
  
 `rect`  
 コントロールのサイズと位置を指定します。 いずれかになります、`CRect`オブジェクトまたは`RECT`構造体。  
  
 `nID`  
 コントロールの子ウィンドウの ID を指定します  
  
 `pPersist`  
 ポインター、`CFile`コントロールの永続的な状態を格納します。 既定値は**NULL**、このコントロール自体の初期化を任意の永続的なストレージからの状態を復元しないことを示します。 ない場合**NULL**へのポインターである必要があります、 `CFile`-ストリームまたはストレージのいずれかの形式でのコントロールの永続的なデータを含むオブジェクトを派生します。 クライアントの以前の操作でこのデータが保存された可能性があります。 `CFile`その他のデータを含めることができますが、読み取り/書き込みを指すポインターへの呼び出しの時に永続的なデータの最初のバイトに設定する必要がありますが、`CreateControl`です。  
  
 `bStorage`  
 示すかどうかのデータ`pPersist`として解釈する必要があります`IStorage`または`IStream`データ。 場合にデータ`pPersist`、記憶域は、`bStorage`する必要があります**TRUE**します。 場合にデータ`pPersist`、ストリームは、`bStorage`する必要があります**FALSE**します。 既定値は**FALSE**します。  
  
 `bstrLicKey`  
 省略可能なライセンス キーのデータ。 このデータは、実行時ライセンス キーが必要なコントロールを作成するときだけ必要です。 コントロールは、ライセンスをサポートする場合を成功させるのにコントロールを作成するためのライセンス キーを提供する必要があります。 既定値は**NULL**します。  
  
 *ppNewSite*  
 作成されるコントロールをホストする既存のコントロール サイトへのポインター。 既定値は**NULL**、新しいコントロールのサイトが自動的に作成され、新しいコントロールにアタッチされていることを示します。  
  
 `ppt`  
 ポインター、**ポイント**コントロールの左上隅を格納する構造体。 コントロールのサイズの値によって決まります*psize*します。 `ppt`と*psize*値は、サイズと、コントロールの位置を指定するオプションのメソッドです。  
  
 *psize*  
 ポインター、**サイズ**コントロールのサイズを格納する構造体。 左上隅の値によって決まります`ppt`します。 `ppt`と*psize*値は、サイズと、コントロールの位置を指定するオプションのメソッドです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 Windows のサブセットのみ`dwStyle`でフラグがサポートされている`CreateControl`:  
  
- **WS_VISIBLE**が最初に表示されるウィンドウを作成します。 通常のウィンドウと同様に、すぐに表示されるようにコントロールするかどうかに必要です。  
  
- **WS_DISABLED**最初に無効になっているウィンドウを作成します。 無効になっているウィンドウは、ユーザーからの入力を受け取ることはできません。 コントロールは、Enabled プロパティに設定できます。  
  
- `WS_BORDER`ウィンドウは、細い罫線を作成します。 コントロールの境界線スタイルのプロパティの場合、設定できます。  
  
- **WS_GROUP**コントロールのグループの最初のコントロールを指定します。 ユーザーを変更できますキーボード フォーカス、グループ内の&1; つのコントロールから次の方向キーを使用しています。 定義されたすべてのコントロール、 **WS_GROUP**後、同じグループに属している最初のコントロールのスタイルを設定します。 次のコントロールで、 **WS_GROUP**スタイルは、グループを終了し、次のグループを開始します。  
  
- **WS_TABSTOP**ユーザーが TAB キーを押したときにキーボード フォーカスが受信可能なコントロールを指定します。 次のコントロールにキーボード フォーカスを移した TAB キーを押すと、 **WS_TABSTOP**スタイル。  
  
 2 番目のオーバー ロードを使用すると、既定のサイズのコントロールを作成できます。  
  
##  <a name="createolefont"></a>COleControlContainer::CreateOleFont  
 OLE フォントを作成します。  
  
```  
void CreateOleFont(CFont* pFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFont`  
 コントロール コンテナーで使用するフォントへのポインター。  
  
##  <a name="finditem"></a>COleControlContainer::FindItem  
 指定した項目をホストするカスタムのサイトを検索します。  
  
```  
virtual COleControlSite* FindItem(UINT nID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 検索するアイテムの識別子。  
  
### <a name="return-value"></a>戻り値  
 指定した項目のカスタムのサイトへのポインター。  
  
##  <a name="freezeallevents"></a>COleControlContainer::FreezeAllEvents  
 かどうかは、コンテナーは関連付けられたコントロールのサイトからのイベントを無視するか、ライセンス条項に同意を決定します。  
  
```  
void FreezeAllEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>パラメーター  
 `bFreeze`  
 イベントが処理される場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロールは、コントロール コンテナーによって要求された場合のイベントの発生を停止する必要はありません。 起動処理を続行できますが、コントロール コンテナーで後続のすべてのイベントは無視されます。  
  
##  <a name="getambientprop"></a>COleControlContainer::GetAmbientProp  
 指定されたアンビエント プロパティの値を取得します。  
  
```  
virtual BOOL GetAmbientProp(
    COleControlSite* pSite,  
    DISPID dispid,  
    VARIANT* pvarResult);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSite`  
 アンビエント プロパティの取得元となるコントロール サイトへのポインター。  
  
 `dispid`  
 目的のアンビエント プロパティのディスパッチの ID。  
  
 *pVarResult*  
 アンビエント プロパティの値へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="getdlgitem"></a>COleControlContainer::GetDlgItem  
 ダイアログ ボックスで指定されたコントロールまたは子ウィンドウまたはその他のウィンドウへのポインターを取得します。  
  
```  
virtual CWnd* GetDlgItem(int nID) const;  
  
virtual void GetDlgItem(
    int nID,  
    HWND* phWnd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 取得する ダイアログの項目の識別子です。  
  
 `phWnd`  
 指定したダイアログ アイテムのウィンドウ オブジェクトのハンドルへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ダイアログのアイテムのウィンドウへのポインター。  
  
##  <a name="getdlgitemint"></a>COleControlContainer::GetDlgItemInt  
 指定されたコントロールの翻訳されたテキストの値を取得します。  
  
```  
virtual UINT GetDlgItemInt(
    int nID,  
    BOOL* lpTrans,  
    BOOL bSigned) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 コントロールの識別子です。  
  
 `lpTrans`  
 関数の成功/失敗の値を受け取ってブール変数を指すポインター ( **TRUE**は成功を示し**FALSE**失敗を示します)。  
  
 `bSigned`  
 関数が先頭にマイナス記号のテキストを調べるしが見つかった場合は、符号付き整数値を返すかどうか指定します。 場合、`bSigned`パラメーターは**TRUE**、戻り値を取得する値を符号付き整数の値に指定するキャスト、`int`型です。 拡張エラー情報を取得する[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)します。  
  
### <a name="return-value"></a>戻り値  
 かどうかは成功すると、変数が指す`lpTrans`に設定されている**TRUE**、戻り値は、コントロール テキストの翻訳済みの値とします。  
  
 関数が失敗した場合は、変数が指す`lpTrans`に設定されている**FALSE**、戻り値は&0; です。 0 が使用可能な変換された値であるため、戻り値が&0; は単独で障害を示していないことを注意してください。  
  
 場合`lpTrans`は**NULL**関数を使用しないため、成功または失敗に関する情報を返します。  
  
### <a name="remarks"></a>コメント  
 関数は、テキストの先頭にある余分なスペースを削除し、10 進数字に変換して取得したテキストを変換します。 関数は、文字列の終端に達したまたは数値以外の文字を検出したときの変換を停止します。  
  
 変換された値がより大きい場合、この関数は&0; を返します**INT_MAX**の符号付き数値または**UINT_MAX** (の符号なしの数値)。  
  
##  <a name="getdlgitemtext"></a>COleControlContainer::GetDlgItemText  
 指定されたコントロールのテキストを取得します。  
  
```  
virtual int GetDlgItemText(
    int nID,  
    LPTSTR lpStr,  
    int nMaxCount) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 コントロールの識別子です。  
  
 `lpStr`  
 コントロールのテキストへのポインター。  
  
 `nMaxCount`  
 指すバッファーにコピーする文字列の文字の最大長の指定`lpStr`します。 文字列の長さが、制限を超える場合、文字列は切り捨てられます。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、戻り値は、終端の null 文字を含まない、バッファーにコピーされた文字数を指定します。  
  
 関数が失敗した場合は、0 を返します。 拡張エラー情報を取得する[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)します。  
  
##  <a name="handlesetfocus"></a>COleControlContainer::HandleSetFocus  
 コンテナーが処理を決定`WM_SETFOCUS`メッセージです。  
  
```  
virtual BOOL HandleSetFocus();
```  
  
### <a name="return-value"></a>戻り値  
 コンテナーが処理する場合は&0; 以外。`WM_SETFOCUS`メッセージ。 それ以外の場合&0; です。  
  
##  <a name="handlewindowlessmessage"></a>COleControlContainer::HandleWindowlessMessage  
 ウィンドウなしのコントロールのウィンドウ メッセージを処理します。  
  
```  
virtual BOOL HandleWindowlessMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* plResult);
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 Windows によって提供される、ウィンドウ メッセージの識別子。  
  
 `wParam`  
 メッセージのパラメーターWindows によって提供されます。 その他のメッセージに固有の情報を指定します。 このパラメーターの内容の値に依存、`message`パラメーター。  
  
 `lParam`  
 メッセージのパラメーターWindows によって提供されます。 その他のメッセージに固有の情報を指定します。 このパラメーターの内容の値に依存、`message`パラメーター。  
  
 *plResult*  
 Windows の結果コード。 メッセージの処理の結果を指定し、送信メッセージに依存します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウなしのコントロール メッセージの処理をカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="isdlgbuttonchecked"></a>COleControlContainer::IsDlgButtonChecked  
 指定したボタンの状態を判断します。  
  
```  
virtual UINT IsDlgButtonChecked(int nIDButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDButton`  
 ボタン コントロールの識別子です。  
  
### <a name="return-value"></a>戻り値  
 作成したボタンからの戻り値、 **BS_AUTOCHECKBOX**、 **BS_AUTORADIOBUTTON**、 **BS_AUTO3STATE**、 **BS_CHECKBOX**、 **BS_RADIOBUTTON**、または**BS_3STATE**スタイル。 次のいずれかの値を指定します。  
  
- **BST_CHECKED**ボタンがオンになっています。  
  
- **BST_INDETERMINATE**ボタンは淡色表示、不確定な状態を示す (ボタンには、場合にのみ、 **BS_3STATE**または**BS_AUTO3STATE**スタイル)。  
  
- **設定されている**ボタンは無効です。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、決定するかどうか、淡色表示をオンになっているボタンが&3; つの状態のコントロールの場合は、どちらかです。  
  
##  <a name="m_crback"></a>COleControlContainer::m_crBack  
 コンテナーの背景色。  
  
```  
COLORREF m_crBack;  
```  
  
##  <a name="m_crfore"></a>COleControlContainer::m_crFore  
 コンテナーの前景色。  
  
```  
COLORREF m_crFore;  
```  
  
##  <a name="m_listsitesorwnds"></a>COleControlContainer::m_listSitesOrWnds  
 コンテナーによってホストされるコントロールのサイトの一覧。  
  
```  
CTypedPtrList<CPtrList, COleControlSiteOrWnd*> m_listSitesOrWnds;  
```  
  
##  <a name="m_nwindowlesscontrols"></a>COleControlContainer::m_nWindowlessControls  
 コントロール コンテナーでホストされているウィンドウなしのコントロールの数。  
  
```  
int m_nWindowlessControls;  
```  
  
##  <a name="m_polefont"></a>COleControlContainer::m_pOleFont  
 OLE フォントのカスタム コントロール サイトへのポインター。  
  
```  
LPFONTDISP m_pOleFont;  
```  
  
##  <a name="m_psitecapture"></a>COleControlContainer::m_pSiteCapture  
 キャプチャ コントロール サイトへのポインター。  
  
```  
COleControlSite* m_pSiteCapture;  
```  
  
##  <a name="m_psitefocus"></a>COleControlContainer::m_pSiteFocus  
 現在入力フォーカス コントロール サイトへのポインター。  
  
```  
COleControlSite* m_pSiteFocus;  
```  
  
##  <a name="m_psiteuiactive"></a>COleControlContainer::m_pSiteUIActive  
 インプレース アクティブ化は、コントロール サイトへのポインター。  
  
```  
COleControlSite* m_pSiteUIActive;  
```  
  
##  <a name="m_pwnd"></a>COleControlContainer::m_pWnd  
 コンテナーに関連付けられたウィンドウ オブジェクトへのポインター。  
  
```  
CWnd* m_pWnd;  
```  
  
##  <a name="m_sitemap"></a>COleControlContainer::m_siteMap  
 サイト マップします。  
  
```  
CMapPtrToPtr m_siteMap;  
```  
  
##  <a name="onpaint"></a>COleControlContainer::OnPaint  
 処理するためにフレームワークによって呼び出される`WM_PAINT`要求します。  
  
```  
virtual BOOL OnPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 コンテナーで使用されるデバイス コンテキストへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メッセージが処理された場合は&0; 以外。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 描画プロセスをカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="onuiactivate"></a>COleControlContainer::OnUIActivate  
 フレームワークによって呼び出されますとコントロール サイトが指す`pSite`、しようインプレース アクティブ化します。  
  
```  
virtual void OnUIActivate(COleControlSite* pSite);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSite`  
 インプレース アクティブ化しようとしてコントロール サイトへのポインター。  
  
### <a name="remarks"></a>コメント  
 インプレース アクティブ化では、コンテナーのメイン メニューがインプレースで複合メニューに置き換えられることを意味します。  
  
##  <a name="onuideactivate"></a>COleControlContainer::OnUIDeactivate  
 フレームワークによって呼び出されるとコントロール サイトが指す`pSite`が非アクティブ化しようとしています。  
  
```  
virtual void OnUIDeactivate(COleControlSite* pSite);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSite`  
 非アクティブ化するには、約コントロール サイトへのポインター。  
  
### <a name="remarks"></a>コメント  
 この通知を受信すると、コンテナーは、ユーザー インターフェイスを再インストールし、フォーカスを取得する必要があります。  
  
##  <a name="scrollchildren"></a>COleControlContainer::ScrollChildren  
 子ウィンドウからスクロール メッセージを受信するときに、フレームワークによって呼び出されます。  
  
```  
virtual void ScrollChildren(
    int dx,  
    int dy);
```  
  
### <a name="parameters"></a>パラメーター  
 `dx`  
 X 軸方向のスクロールの (ピクセル単位) の量。  
  
 *dy*  
 Y 軸方向のスクロールの (ピクセル単位) の量。  
  
##  <a name="senddlgitemmessage"></a>COleControlContainer::SendDlgItemMessage  
 指定されたコントロールにメッセージを送信します。  
  
```  
virtual LRESULT SendDlgItemMessage(
    int nID,  
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 メッセージを受信するコントロールの識別子を指定します。  
  
 `message`  
 送信するメッセージを指定します。  
  
 `wParam`  
 その他のメッセージに固有の情報を指定します。  
  
 `lParam`  
 その他のメッセージに固有の情報を指定します。  
  
##  <a name="setdlgitemint"></a>COleControlContainer::SetDlgItemInt  
 指定した整数値の文字列形式にダイアログ ボックスで、コントロールのテキストを設定します。  
  
```  
virtual void SetDlgItemInt(
    int nID,  
    UINT nValue,  
    BOOL bSigned);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 コントロールの識別子です。  
  
 `nValue`  
 表示される整数値。  
  
 `bSigned`  
 指定するかどうか、`nValue`パラメーターの符号付きまたは符号なし。 このパラメーターがある場合**TRUE**、`nValue`が署名されています。 このパラメーターがある場合**TRUE**と`nValue`は&0; より小さく、マイナス記号は、文字列の最初の桁の前に置かれます。 このパラメーターは、する場合**FALSE**、`nValue`が署名されていません。  
  
##  <a name="setdlgitemtext"></a>COleControlContainer::SetDlgItemText  
 含まれているテキストを使用して、指定したコントロールのテキストを設定`lpszString`します。  
  
```  
virtual void SetDlgItemText(
    int nID,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 コントロールの識別子です。  
  
 `lpszString`  
 コントロールのテキストへのポインター。  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [メンバー クラス](../../mfc/reference/colecontrolsite-class.md)   
 [関数のクラス](../../mfc/reference/coccmanager-class.md)

