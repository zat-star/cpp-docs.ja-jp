---
title: "CMFCToolBarDateTimeCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CanBeStretched
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CopyFrom
- AFXTOOLBARDATETIMECTRL/CMFCToolBarButton::ExportToMenuButton
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetByCmd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetHwnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTimeAll
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::HaveHotBorder
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::NotifyCommand
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnAddToCustomizePage
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnChangeParentWnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnClick
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnCtlColor
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnMove
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnShow
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnUpdateToolTip
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTimeAll
dev_langs:
- C++
helpviewer_keywords:
- SetStyle method
- OnCalculateSize method
- OnDraw method
- OnDrawOnCustomizeList method
- CMFCToolBarDateTimeCtrl class
- Serialize method
- OnSize method
ms.assetid: a3853cb9-8ebc-444f-a1e4-9cf905e24c18
caps.latest.revision: 30
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
ms.openlocfilehash: 9558d62710c7be571d6aefab2c44fe504ca56d60
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbardatetimectrl-class"></a>CMFCToolBarDateTimeCtrl クラス
日付と時刻のピッカー コントロールを含むツール バー ボタンです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCToolBarDateTimeCtrl : public CMFCToolBarButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl](#cmfctoolbardatetimectrl)|`CMFCToolBarDateTimeCtrl` オブジェクトを構築します。|  
|`CMFCToolBarDateTimeCtrl::~CMFCToolBarDateTimeCtrl`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarDateTimeCtrl::CanBeStretched](#canbestretched)|ユーザーがカスタマイズするときに、ボタンを拡張するかどうかを指定します。 (上書き[CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched))。|  
|[CMFCToolBarDateTimeCtrl::CopyFrom](#copyfrom)|現在のボタンに別のツール バー ボタンのプロパティをコピーします。 (上書き[CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom))。|  
|`CMFCToolBarDateTimeCtrl::DuplicateData`|将来使用するために予約されています。|  
|[CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|ツール バー ボタンからメニューにテキストをコピーします。|  
|`CMFCToolBarDateTimeCtrl::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMFCToolBarDateTimeCtrl::GetByCmd](#getbycmd)|最初の取得`CMFCToolBarDateTimeCtrl`指定されたコマンド ID を持つアプリケーション内のオブジェクト|  
|[CMFCToolBarDateTimeCtrl::GetDateTimeCtrl](#getdatetimectrl)|日時指定コントロールへのポインターを返します。|  
|[CMFCToolBarDateTimeCtrl::GetHwnd](#gethwnd)|ツール バー ボタンに関連付けられているウィンドウ ハンドルを取得します。 (上書き[CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd))。|  
|`CMFCToolBarDateTimeCtrl::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCToolBarDateTimeCtrl::GetTime](#gettime)|日付と時刻の選択コントロールから選択した時間を取得し、指定した配置[SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)構造体。|  
|[CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall)|指定されたコマンド ID を持つ日時指定コントロールのボタンから選択した日時を返します。|  
|[CMFCToolBarDateTimeCtrl::HaveHotBorder](#havehotborder)|ユーザーがボタンを選択したときに、ボタンの境界線を表示するかどうかを決定します。 (上書き[CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder))。|  
|[CMFCToolBarDateTimeCtrl::NotifyCommand](#notifycommand)|ボタンを処理するかどうかを示す、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)メッセージです。 (上書き[CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand))。|  
|[CMFCToolBarDateTimeCtrl::OnAddToCustomizePage](#onaddtocustomizepage)|ボタンを追加するときに、フレームワークによって呼び出されます、**カスタマイズ** ダイアログ ボックス。 (上書き[CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage))。|  
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|指定したデバイス コンテキストとドッキングの状態のボタンのサイズを計算するためにフレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize))。|  
|[CMFCToolBarDateTimeCtrl::OnChangeParentWnd](#onchangeparentwnd)|新しいツールバーにボタンが挿入されたときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd))。|  
|[CMFCToolBarDateTimeCtrl::OnClick](#onclick)|ユーザー コントロールをクリックしたときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick))。|  
|[CMFCToolBarDateTimeCtrl::OnCtlColor](#onctlcolor)|親ツールバーが処理されるときに、フレームワークによって呼び出され、`WM_CTLCOLOR`メッセージです。 (上書き[CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor))。|  
|`CMFCToolBarDateTimeCtrl::OnDraw`|指定したスタイルとオプションを使用して、ボタンを描画するためにフレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw))。|  
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|ボタンを描画するためにフレームワークによって呼び出される、**コマンド**のウィンドウ、**カスタマイズ** ダイアログ ボックス。 (上書き[CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist))。|  
|[CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged](#onglobalfontschanged)|グローバルのフォントが変更されたときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged))。|  
|[CMFCToolBarDateTimeCtrl::OnMove](#onmove)|親ツールバーに移動したときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove))。|  
|[CMFCToolBarDateTimeCtrl::OnShow](#onshow)|フレームワークによって呼び出さ になったら表示と非表示です。 (上書き[CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow))。|  
|`CMFCToolBarDateTimeCtrl::OnSize`|親ツールバーのサイズまたは位置が変更されに伴ってボタンのサイズを変更するときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize))。|  
|[CMFCToolBarDateTimeCtrl::OnUpdateToolTip](#onupdatetooltip)|親ツールバーは、そのツールヒント テキストを更新するときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip))。|  
|`CMFCToolBarDateTimeCtrl::Serialize`|アーカイブからこのオブジェクトを読み取るか、アーカイブを書き込みます (オーバーライド[CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize))。|  
|`CMFCToolBarDateTimeCtrl::SetStyle`|ツール バー ボタンのスタイルを設定します。 (上書き[CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle))。|  
|[CMFCToolBarDateTimeCtrl::SetTime](#settime)|日時指定コントロールの日付と時刻を設定します。|  
|[CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall)|日時指定コントロールの指定されたコマンド ID を持つすべてのインスタンスでの日付と時刻を設定します。|  
  
## <a name="remarks"></a>コメント  
 日付と時刻のピッカー コントロールを使用する方法の例は、ToolbarDateTimePicker サンプル プロジェクトを参照してください。 コントロールのボタンをツールバーに追加する方法については、次を参照してください。[チュートリアル: ツールバーにコントロールを配置する](../../mfc/walkthrough-putting-controls-on-toolbars.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtoolbardatetimectrl.h  
  
##  <a name="canbestretched"></a>CMFCToolBarDateTimeCtrl::CanBeStretched  
 ユーザーがカスタマイズするときに、ボタンを拡張するかどうかを指定します。  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このメソッドは `TRUE` を返します。  
  
### <a name="remarks"></a>コメント  
 既定では、フレームワークは、ユーザーにカスタマイズするときに拡張できるツール バー ボタンをできません。 このメソッドによって拡張基本クラスの実装 ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)) され、ユーザーをカスタマイズするときに日付と時刻のツール バー ボタンを拡大しています。  
  
##  <a name="cmfctoolbardatetimectrl"></a>CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl  
 作成して初期化、 [CMFCToolBarDateTimeCtrl](../../mfc/reference/cmfctoolbardatetimectrl-class.md)オブジェクトです。  
  
```  
CMFCToolBarDateTimeCtrl(
    UINT uiID,  
    int iImage,  
    DWORD dwStyle=0,  
    int iWidth=0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiID`  
 コントロールの id。  
  
 [入力] `iImage`  
 ツールバーの イメージのインデックス`CMFCToolBarImages`オブジェクトです。  
  
 [入力] `dwStyle`  
 スタイル、`CMFCToolBarDateTimeCtrlImpl`ユーザーがボタンをクリックしたときに作成されるウィンドウです。  
  
 [入力] `iWidth`  
 コントロールの幅 (ピクセル単位)。  
  
### <a name="remarks"></a>コメント  
 このオブジェクトは、システムの日付と時刻に初期化されます。 内部のウィンドウ スタイル`CMFCToolBarDateTimeCtrlImpl`オブジェクトが含まれています、`dwStyle`パラメーターおよび`WS_CHILD`と`WS_VISIBLE`スタイル。 使用してこれらのスタイルを変更することはできません`CMFCToolBarDateTimeCtrl::SetStyle`します。 使用`SetStyle`のスタイルを変更する、`CMFCToolBarDateTimeCtrl`コントロールです。  
  
### <a name="example"></a>例  
 次の例のオブジェクトを構築する方法、`CMFCToolBarDateTimeCtrl`クラスです。 このコード スニペットの一部である、[ツールバー日時指定コントロールのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_ToolbarDateTimePicker&#1;](../../mfc/reference/codesnippet/cpp/cmfctoolbardatetimectrl-class_1.cpp)]  
  
##  <a name="copyfrom"></a>CMFCToolBarDateTimeCtrl::CopyFrom  
 現在のボタンに別のツール バー ボタンのプロパティをコピーします。  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `src`  
 コピー元のソース ボタンへの参照。  
  
### <a name="remarks"></a>コメント  
 このツール バー ボタンに別のツール バー ボタンをコピーするには、このメソッドを呼び出します。 `src`型でなければなりません`CMFCToolBarDateTimeCtrl`します。  
  
##  <a name="exporttomenubutton"></a>CMFCToolBarDateTimeCtrl::ExportToMenuButton  
 ツール バー ボタンからメニューにテキストをコピーします。  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `menuButton`  
 ターゲットのメニュー ボタンへの参照。  
  
### <a name="return-value"></a>戻り値  
 このメソッドは `TRUE` を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、基本クラスの実装 ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) によって、コントロールのコマンド ID に関連付けられている文字列リソースを読み込みます。 文字列リソースの詳細については、次を参照してください。 [CStringT::LoadString](../../atl-mfc-shared/reference/cstringt-class.md#loadstring)します。  
  
##  <a name="getbycmd"></a>CMFCToolBarDateTimeCtrl::GetByCmd  
 最初の取得`CMFCToolBarDateTimeCtrl`指定されたコマンド ID を持つアプリケーション内のオブジェクト  
  
```  
static CMFCToolBarDateTimeCtrl* __stdcall GetByCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmd`  
 取得する、ボタンのコマンド ID。  
  
### <a name="return-value"></a>戻り値  
 最初の`CMFCToolBarDateTimeCtrl`指定されたコマンド ID を持つアプリケーション内のオブジェクトまたは`NULL`いない場合`CMFCToolBarDateTimeCtrl`オブジェクトは、指定されたコマンド ID を持ちます。  
  
### <a name="remarks"></a>コメント  
 など、この共有ユーティリティ メソッドがメソッドで使用される[CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall)と[CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall)を設定または指定されたコマンド ID を持つ日時指定コントロールのすべてのインスタンスの日付と時刻の取得  
  
##  <a name="getdatetimectrl"></a>CMFCToolBarDateTimeCtrl::GetDateTimeCtrl  
 日時指定コントロールへのポインターを返します。  
  
```  
CDateTimeCtrl* GetDateTimeCtrl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 日付と時刻の選択コントロールへのポインターまたは`NULL`コントロールが存在しない場合。  
  
### <a name="remarks"></a>コメント  
 `CMFCToolBarDateTimeCtrl`クラスの初期化、`m_pWndDateTime`データ メンバーを挿入すると、`CMFCToolBarDateTimeCtrl`ツールバーにオブジェクトです。  
  
##  <a name="gethwnd"></a>CMFCToolBarDateTimeCtrl::GetHwnd  
 ツール バー ボタンに関連付けられているウィンドウ ハンドルを取得します。  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>戻り値  
 日付と時刻のツール バー ボタンに関連付けられているウィンドウ ハンドル。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、 [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd)メソッドです。  
  
##  <a name="gettime"></a>CMFCToolBarDateTimeCtrl::GetTime  
 関連する日付と日時選択コントロールから選択した時刻を取得し、指定した配置[SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)構造体  
  
```  
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `[out] timeDest`  
 最初のオーバー ロードで、[時刻クラス](../../atl-mfc-shared/reference/coledatetime-class.md)システム時刻の情報を受け取るオブジェクト。 2 番目のオーバー ロードでは、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)システム時刻の情報を受け取るオブジェクト。  
  
 `[out] pTimeDest`  
 ポインター、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)システム時刻の情報を受け取る構造体。 `NULL` にすることはできません。  
  
### <a name="return-value"></a>戻り値  
 最初のオーバー ロードで、時間が正常に書き込まれた場合は 0 以外、[時刻クラス](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクト。 それ以外の場合、0 です。 2 番目と&3; 番目のオーバー ロードで戻り値は、`DWORD`で設定された dwFlag メンバーへの値が、[戻り](http://msdn.microsoft.com/library/windows/desktop/bb761730)構造体。  
  
### <a name="remarks"></a>コメント  
 メソッドのセット、[戻り](http://msdn.microsoft.com/library/windows/desktop/bb761730)形式、日付と時刻の選択が日付と時刻に設定されているかどうかを示すためにします。 コントロールに設定されている値と等しい場合 GDT_NONE、`no date`状態、DTS_SHOWNONE スタイルを使用しています。 返される値と等しい場合戻り、移行先の場所にシステム時刻が正常に保存します。  
  
##  <a name="gettimeall"></a>CMFCToolBarDateTimeCtrl::GetTimeAll  
 ユーザーが指定されたコマンド ID を持つ日時指定コントロールのボタンが選択した時刻を返します。  
  
```  
static BOOL GetTimeAll(
    UINT uiCmd,  
    COleDateTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,  
    CTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,  
    LPSYSTEMTIME pTimeDest);
```  
  
### <a name="parameters"></a>パラメーター  
 `[in] uiCmd`  
 ツール バー ボタンのコマンド ID を指定します  
  
 `[out] timeDest`  
 最初のオーバー ロードで、[時刻クラス](../../atl-mfc-shared/reference/coledatetime-class.md)システム時刻の情報を受け取るオブジェクト。 2 番目のオーバー ロードでは、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)システム時刻の情報を受け取るオブジェクト。  
  
 `[out] pTimeDest`  
 ポインター、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)システム時刻の情報を受け取る構造体。 `NULL` にすることはできません。  
  
### <a name="return-value"></a>戻り値  
 コマンド ID と一致するツールバー ボタンをフレームワークが見つからないかどうかは`uiCmd`、戻り値は最初のオーバー ロードでは、0 から他のオーバー ロードで GDT_NONE します。 ツール バー ボタンが見つかった場合、戻り値への呼び出しからの戻り値と同じ[CMFCToolBarDateTimeCtrl::GetTime](#gettime)その ボタンをクリックします。 ゼロまたは GDT_NONE 値は、ボタンが見つかったことを示すときに発生する可能性が戻り値への呼び出し`GetTime`何らかの理由で有効な日付が返されませんでした。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出し、指定されたコマンド ID を持つツール バー ボタンを探します[CMFCToolBarDateTimeCtrl::GetTime](#gettime)メソッドをそのボタンをクリックします。  
  
##  <a name="havehotborder"></a>CMFCToolBarDateTimeCtrl::HaveHotBorder  
 ユーザーがボタンを選択したときに、ボタンの境界線を表示するかどうかを決定します。  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタンが選択されている場合、境界線を表示する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、コントロールが表示されている場合は、0 以外の値を返します。  
  
##  <a name="notifycommand"></a>CMFCToolBarDateTimeCtrl::NotifyCommand  
 ボタンを処理するかどうかを示す、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)メッセージです。  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iNotifyCode`  
 コマンドに関連付けられている通知メッセージです。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ボタンを処理する場合、`WM_COMMAND`メッセージ、または`FALSE`を親ツールバーで、メッセージを処理することを示します。  
  
### <a name="remarks"></a>コメント  
 フレームワークが送信しようとしているときに、このメソッドを呼び出して、 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)メッセージを親ウィンドウにします。  
  
 このメソッドによって拡張基本クラスの実装 ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) 処理することで、 [DTN_DATETIMECHANGE](http://msdn.microsoft.com/library/windows/desktop/bb761737)通知します。 内部の時間のステータスを更新し、すべての時刻のプロパティが更新`CMFCToolBarDateTimeCtrl`オブジェクトでは、同じコマンド ID  
  
##  <a name="onaddtocustomizepage"></a>CMFCToolBarDateTimeCtrl::OnAddToCustomizePage  
 ボタンを追加するときに、フレームワークによって呼び出されます、**カスタマイズ** ダイアログ ボックス。  
  
```  
virtual void OnAddToCustomizePage();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドが基本クラスの実装を拡張[CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)で最初の日付から、プロパティのコピーと時刻をこのオブジェクトと同じコマンド ID を持つ任意のツールバーで制御します。 日付と時刻のコントロールで、このオブジェクトと同じコマンド ID を持つツールバーがない場合、このメソッドは何もはしません。  
  
 詳細については、**カスタマイズ**ダイアログ ボックスを参照してください[CMFCToolBarsCustomizeDialog クラス](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)します。  
  
##  <a name="onchangeparentwnd"></a>CMFCToolBarDateTimeCtrl::OnChangeParentWnd  
 新しいツールバーにボタンが挿入されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndParent`  
 新しい親ウィンドウです。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、基本クラスの実装 ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) 内部の再作成して`CMFCToolBarDateTimeCtrlImpl`オブジェクトです。  
  
##  <a name="onclick"></a>CMFCToolBarDateTimeCtrl::OnClick  
 ユーザー コントロールをクリックしたときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 使用されません。  
  
 [入力] `bDelay`  
 使用されません。  
  
### <a name="return-value"></a>戻り値  
 ボタンをクリックしてメッセージを処理する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、基本クラスの実装では、 [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)場合に、0 以外の値を返すことによって、内部`CMFCToolBarDateTimeCtrlImpl`オブジェクトを表示します。  
  
##  <a name="onctlcolor"></a>CMFCToolBarDateTimeCtrl::OnCtlColor  
 親ツールバーが処理されるときに、フレームワークによって呼び出され、`WM_CTLCOLOR`メッセージです。  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 ボタンを表示するデバイス コンテキスト。  
  
 [入力] `nCtlColor`  
 使用されません。  
  
### <a name="return-value"></a>戻り値  
 フレームワークがボタンの背景の描画に使用するグローバル ブラシへのハンドル。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、基本クラスの実装では、 [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)でテキストを設定およびグローバルのテキストに指定したデバイス コンテキストの色と背景の色をそれぞれバック グラウンドです。  
  
 詳細については、アプリケーションで使用できるグローバル オプションは、次を参照してください。 [AFX_GLOBAL_DATA 構造体](../../mfc/reference/afx-global-data-structure.md)します。  
  
##  <a name="onglobalfontschanged"></a>CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged  
 グローバルのフォントが変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドによって拡張基本クラスの実装 ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) グローバル フォントのコントロールのフォントを変更しています。  
  
 詳細については、アプリケーションで使用できるグローバル オプションは、次を参照してください。 [AFX_GLOBAL_DATA 構造体](../../mfc/reference/afx-global-data-structure.md)します。  
  
##  <a name="onmove"></a>CMFCToolBarDateTimeCtrl::OnMove  
 親ツールバーに移動したときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnMove();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、既定のクラスの実装 ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) 内部の位置を更新することによって`CMFCToolBarDateTimeCtrlImpl`オブジェクトです。  
  
##  <a name="onshow"></a>CMFCToolBarDateTimeCtrl::OnShow  
 フレームワークによって呼び出さ になったら表示と非表示です。  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bShow`  
 ボタンが表示されているかどうかを指定します。 このパラメーターは場合`TRUE`、ボタンを表示します。 それ以外の場合、ボタンは表示されません。  
  
### <a name="remarks"></a>コメント  
 このメソッドによって拡張基本クラスの実装 ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) 場合、ボタンを表示することによって`bShow`は`TRUE`です。 それ以外の場合、このメソッドでは、ボタンを非表示にします。  
  
##  <a name="onsize"></a>CMFCToolBarDateTimeCtrl::OnSize  
 親ツールバーのサイズまたは位置が変更されに伴ってボタンのサイズを変更するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iSize`  
 ピクセル単位で、ボタンの新しい幅。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、既定のクラスの実装 ( [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)) サイズと、内部の位置を更新することによって`CMFCToolBarDateTimeCtrlImpl`オブジェクトです。  
  
##  <a name="onupdatetooltip"></a>CMFCToolBarDateTimeCtrl::OnUpdateToolTip  
 親ツールバーは、そのツールヒント テキストを更新するときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndParent`  
 親ウィンドウです。  
  
 [入力] `iButtonIndex`  
 親ボタン コレクション内のボタンの&0; から始まるインデックス。  
  
 [入力] `wndToolTip`  
 ツールヒント テキストを表示するコントロール。  
  
 [出力] `str`  
 A`CString`更新済みのツールヒント テキストを受け取るオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 メソッドは、ツールヒントのテキストを更新する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドによって拡張基本クラスの実装 ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip))、ボタンに関連付けられているツールヒント テキストを表示しています。 このメソッドは何も実行し、返しますボタンが水平方向にドッキングされていない場合`FALSE`します。  
  
##  <a name="settime"></a>CMFCToolBarDateTimeCtrl::SetTime  
 日時指定コントロールの日付と時刻を設定します。  
  
```  
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* timeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `[in] timeNew`  
 最初の形式への参照では、[時刻クラス](../../atl-mfc-shared/reference/coledatetime-class.md)コントロールを設定する時刻を含むオブジェクト。 2 番目のバージョンへのポインターで、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)コントロールを設定する時刻を含むオブジェクト。  
  
 `[in] pTimeNew`  
 ポインター、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)コントロールを設定する時刻を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 日付と時刻の選択コントロールを呼び出して時刻を設定[CDateTimeCtrl::SetTime](../../mfc/reference/cdatetimectrl-class.md#settime)します。  
  
##  <a name="settimeall"></a>CMFCToolBarDateTimeCtrl::SetTimeAll  
 日時指定コントロールの指定されたコマンド ID を持つすべてのインスタンスでの日付と時刻を設定します。  
  
```  
static BOOL SetTimeAll(
    UINT uiCmd,  
    const COleDateTime& timeNew);

static BOOL SetTimeAll(
    UINT uiCmd,  
    const CTime* pTimeNew);

static BOOL SetTimeAll(
    UINT uiCmd,  
    LPSYSTEMTIME pTimeNew=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `[in] uiCmd`  
 ツール バー ボタンのコマンド ID を指定します  
  
 `[in] timeNew`  
 最初のバージョンで、[時刻クラス](../../atl-mfc-shared/reference/coledatetime-class.md)コントロールを設定する時刻を含むオブジェクト。 2 番目のバージョンへのポインターで、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)コントロールを設定する時刻を含むオブジェクト。  
  
 `[in] pTimeNew`  
 ポインター、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)コントロールを設定する時刻を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定されたコマンド ID を持つツール バー ボタンを検索し、日付と時刻の選択コントロールを呼び出して時刻を設定[CMFCToolBarDateTimeCtrl::SetTime](#settime)します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [チュートリアル: ツールバーへのコントロールを配置します。](../../mfc/walkthrough-putting-controls-on-toolbars.md)




