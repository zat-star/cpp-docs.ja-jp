---
title: "CMFCDropDownToolbarButton クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CopyFrom
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::DropDownToolbar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::ExportToMenuButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::GetDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsDropDown
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsExtraSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCalculateSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnChangeParentWnd
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClick
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClickUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnContextHelp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCustomizeMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDraw
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDrawOnCustomizeList
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::Serialize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::SetDefaultCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::m_uiShowBarDelay
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownToolbarButton class
- OnCancelMode method
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
caps.latest.revision: 31
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
ms.openlocfilehash: 24398ddb605489bf9677bd493a1bc1f490d583b9
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdropdowntoolbarbutton-class"></a>CMFCDropDownToolbarButton クラス
ツール バー ボタンの一種で、クリックされたときは標準ボタンと同じように動作します。 ただし、ドロップダウン ツールバーを開きます ( [CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)押すし、ツール バー ボタンを押したかどうか。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCDropDownToolbarButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](#cmfcdropdowntoolbarbutton)|`CMFCDropDownToolbarButton` オブジェクトを構築します。|  
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::CopyFrom](#copyfrom)|現在のボタンに別のツール バー ボタンのプロパティをコピーします。 (上書き[CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom))。|  
|`CMFCDropDownToolbarButton::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)|ドロップダウン ツールバーを開きます。|  
|[CMFCDropDownToolbarButton::ExportToMenuButton](#exporttomenubutton)|ツール バー ボタンからメニューにテキストをコピーします。 (上書き[CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton))。|  
|[CMFCDropDownToolbarButton::GetDropDownToolBar](#getdropdowntoolbar)|ボタンに関連付けられているドロップダウン ツールバーを取得します。|  
|`CMFCDropDownToolbarButton::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCDropDownToolbarButton::IsDropDown](#isdropdown)|ドロップダウン ツールバーが現在開いているかどうかを決定します。|  
|[CMFCDropDownToolbarButton::IsExtraSize](#isextrasize)|拡張された境界で、ボタンを表示できるかどうかを決定します。 (上書き[CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize))。|  
|[CMFCDropDownToolbarButton::OnCalculateSize](#oncalculatesize)|指定したデバイス コンテキストとドッキングの状態のボタンのサイズを計算するためにフレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize))。|  
|`CMFCDropDownToolbarButton::OnCancelMode`|処理するためにフレームワークによって呼び出される、 [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615)メッセージです。 (`CMCToolBarButton::OnCancelMode` をオーバーライドします)。|  
|[CMFCDropDownToolbarButton::OnChangeParentWnd](#onchangeparentwnd)|新しいツールバーにボタンが挿入されたときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd))。|  
|[CMFCDropDownToolbarButton::OnClick](#onclick)|ユーザーがマウス ボタンをクリックすると、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick))。|  
|[CMFCDropDownToolbarButton::OnClickUp](#onclickup)|マウス ボタンを離したときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup))。|  
|[CMFCDropDownToolbarButton::OnContextHelp](#oncontexthelp)|親ツールバーが処理されるときに、フレームワークによって呼び出され、`WM_HELPHITTEST`メッセージです。 (上書き[CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp))。|  
|[CMFCDropDownToolbarButton::OnCustomizeMenu](#oncustomizemenu)|アプリケーションでは、親ツールバーにショートカット メニューを表示するときは、指定されたメニューを変更します。 (上書き[CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu))。|  
|[CMFCDropDownToolbarButton::OnDraw](#ondraw)|指定したスタイルとオプションを使用して、ボタンを描画するためにフレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw))。|  
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|ボタンを描画するためにフレームワークによって呼び出される、**コマンド**のウィンドウ、**カスタマイズ** ダイアログ ボックス。 (上書き[CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist))。|  
|[CMFCDropDownToolbarButton::Serialize](#serialize)|アーカイブからこのオブジェクトを読み取りまたはアーカイブを書き込みます。 (上書き[CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize))。|  
|[CMFCDropDownToolbarButton::SetDefaultCommand](#setdefaultcommand)|ユーザーがボタンをクリックしたときにフレームワークによって使用される既定のコマンドを設定します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay)|ユーザーを押し、マウスのボタン ドロップダウン ツールバーが表示されるまでの時間の長さを指定します。|  
  
## <a name="remarks"></a>コメント  
 A`CMFCDropDownToolBarButton`ボタンの右下隅にある小さな矢印がある点で通常のボタンは異なります。 ドロップダウン ツールバーにユーザーがボタンを選択すると、フレームワークは、トップレベルのツール バー ボタン (右下隅にある小さな矢印の付いたボタン) 上のアイコンを表示します。  
  
 ドロップダウン ツールバーを実装する方法については、次を参照してください。 [CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)します。  
  
 `CMFCDropDownToolBarButton`にオブジェクトをエクスポートできる、 [CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)オブジェクトし、ポップアップ メニューをメニュー ボタンとして表示されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdropdowntoolbar.h  
  
##  <a name="copyfrom"></a>CMFCDropDownToolbarButton::CopyFrom  
 現在のボタンに別のツール バー ボタンのプロパティをコピーします。  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `src`  
 コピー元のソース ボタンへの参照。  
  
### <a name="remarks"></a>コメント  
 このツール バー ボタンに別のツール バー ボタンをコピーするには、このメソッドを呼び出します。 `src`型でなければなりません`CMFCDropDownToolbarButton`します。  
  
##  <a name="cmfcdropdowntoolbarbutton"></a>CMFCDropDownToolbarButton::CMFCDropDownToolbarButton  
 `CMFCDropDownToolbarButton` オブジェクトを構築します。  
  
```  
CMFCDropDownToolbarButton();

 
CMFCDropDownToolbarButton(
    LPCTSTR lpszName,  
    CMFCDropDownToolBar* pToolBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszName`  
 ボタンの既定のテキスト。  
  
 [入力] `pToolBar`  
 ポインター、`CMFCDropDownToolBar`ユーザーがボタンを押したときに表示されるオブジェクト。  
  
### <a name="remarks"></a>コメント  
 コンス トラクターの&2; 番目のオーバー ロード コピー ドロップダウン ボタンを&1; 番目のボタンのツールバーからを`pToolBar`を指定します。  
  
 通常、ドロップダウン ツールバー ボタンがツールバーに、最近使用したボタンのテキストを使用する`pToolBar`を指定します。 指定したテキストを使用して`lpszName`ボタンがメニュー ボタンに変換またはに表示される、**コマンド**のタブ、**カスタマイズ** ダイアログ ボックス。 詳細については、**カスタマイズ**ダイアログ ボックスを参照してください[CMFCToolBarsCustomizeDialog クラス](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)します。  
  
### <a name="example"></a>例  
 次の例のオブジェクトを構築する方法、`CMFCDropDownToolbarButton`クラスです。 このコード スニペットの一部である、 [Visual Studio のデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&31;](../../mfc/codesnippet/cpp/cmfcdropdowntoolbarbutton-class_1.cpp)]  
  
##  <a name="dropdowntoolbar"></a>CMFCDropDownToolbarButton::DropDownToolbar  
 ドロップダウン ツールバーを開きます。  
  
```  
BOOL DropDownToolbar(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 ドロップダウン フレームの親ウィンドウまたは`NULL`ドロップダウン ツールバー ボタンの親ウィンドウを使用します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 [CMFCDropDownToolbarButton::OnClick](#onclick)メソッドを押すし、ツール バー ボタンを押したときに、ドロップダウン ツールバーを開くには、このメソッドを呼び出します。  
  
 このメソッドを使用して、ドロップダウン ツールバーを作成する、 [CMFCDropDownFrame::Create](../../mfc/reference/cmfcdropdownframe-class.md#create)メソッドです。 親ツールバーが垂直方向にドッキングされている場合このメソッドは配置ドロップダウン ツールバーに収まるようによっては、親ツールバーの左側または右側の側のいずれかです。 それ以外の場合、このメソッドは、親ツールバーの下にあるドロップダウン ツールバーを配置します。  
  
 このメソッドは失敗`pWnd`は`NULL`ドロップダウン ツールバー ボタンに親ウィンドウがないとします。  
  
##  <a name="exporttomenubutton"></a>CMFCDropDownToolbarButton::ExportToMenuButton  
 ツール バー ボタンからメニューにテキストをコピーします。  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `menuButton`  
 ターゲットのメニュー ボタンへの参照。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合は 0。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、基本クラスの実装を呼び出します ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) し、各ツールバーのメニュー項目では、このボタンを含むポップアップ メニューにターゲット メニュー ボタンを追加します。 このメソッドでは、ポップアップ メニューのサブメニューは追加されません。  
  
 このメソッドは失敗親ツールバー`m_pToolBar`は`NULL`または基本クラスの実装を返す`FALSE`します。  
  
##  <a name="getdropdowntoolbar"></a>CMFCDropDownToolbarButton::GetDropDownToolBar  
 ボタンに関連付けられているドロップダウン ツールバーを取得します。  
  
```  
CMFCToolBar* GetDropDownToolBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタンに関連付けられているドロップダウン ツールバーです。  
  
### <a name="remarks"></a>コメント  
 このメソッドが戻る、`m_pToolBar`データ メンバーです。  
  
##  <a name="isdropdown"></a>CMFCDropDownToolbarButton::IsDropDown  
 ドロップダウン ツールバーが現在開いているかどうかを決定します。  
  
```  
BOOL IsDropDown() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドロップダウン ツールバーが現在開いている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 フレームワークを使用して、ドロップダウン ツールバーを開き、 [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)メソッドです。 フレームワークは、ユーザーがドロップダウン ツールバーの非クライアント領域でマウスの左ボタンを押したときにドロップダウン ツールバーを閉じます。  
  
##  <a name="isextrasize"></a>CMFCDropDownToolbarButton::IsExtraSize  
 拡張された境界で、ボタンを表示できるかどうかを決定します。  
  
```  
virtual BOOL IsExtraSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 拡張境界で、ツール バー ボタンを表示できる場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 拡張の罫線の詳細については、次を参照してください。 [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize)します。  
  
##  <a name="m_uishowbardelay"></a>CMFCDropDownToolbarButton::m_uiShowBarDelay  
 ユーザーを押し、マウスのボタン ドロップダウン ツールバーが表示されるまでの時間の長さを指定します。  
  
```  
static UINT m_uiShowBarDelay;  
```  
  
### <a name="remarks"></a>コメント  
 遅延時間はミリ秒単位で測定されます。 既定値は 500 です。 別の遅延を設定するには、この共有データ メンバーの値を変更します。  
  
##  <a name="oncalculatesize"></a>CMFCDropDownToolbarButton::OnCalculateSize  
 指定したデバイス コンテキストとドッキングの状態のボタンのサイズを計算するためにフレームワークによって呼び出されます。  
  
```  
virtual SIZE OnCalculateSize(
    CDC* pDC,  
    const CSize& sizeDefault,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 ボタンを表示するデバイス コンテキスト。  
  
 [入力] `sizeDefault`  
 ボタンの既定のサイズ。  
  
 [入力] `bHorz`  
 親ツールバーのドッキング状態です。 このパラメーターは`TRUE`場合は、ツールバーが水平方向にドッキングされているか、浮動小数点型、または`FALSE`ツールバーが垂直方向にドッキングされている場合。  
  
### <a name="return-value"></a>戻り値  
 A `SIZE` (ピクセル単位)、ボタンの大きさを格納する構造体。  
  
### <a name="remarks"></a>コメント  
 このメソッドによって拡張基本クラスの実装 ( [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize))、ボタンのサイズの横幅に下向きの矢印の幅を追加しています。  
  
##  <a name="onchangeparentwnd"></a>CMFCDropDownToolbarButton::OnChangeParentWnd  
 新しいツールバーにボタンが挿入されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndParent`  
 新しい親ウィンドウです。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、基本クラスの実装 ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) をテキスト ラベルをオフにして ( [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)) と設定、 [CMFCToolBarButton::m_bText](../../mfc/reference/cmfctoolbarbutton-class.md#m_btext)と[CMFCToolBarButton::m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_buserbutton)データ メンバーに`FALSE`します。  
  
##  <a name="onclick"></a>CMFCDropDownToolbarButton::OnClick  
 ユーザーがマウス ボタンをクリックすると、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 ツール バー ボタンの親ウィンドウです。  
  
 [入力] `bDelay`  
 `TRUE`場合は、メッセージは、遅延時間で処理する必要があります。  
  
### <a name="return-value"></a>戻り値  
 ボタンをクリックしてメッセージを処理する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドが基本クラスの実装を拡張[CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)、ドロップダウン ツールバーの状態を更新しています。  
  
 このメソッドが指定した時間の長さが待機するタイマーを作成するユーザーには、ツールバーのボタンがクリックすると、 [CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay)データ メンバーとし、開くドロップダウン ツールバーを使用して、 [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)メソッドです。 このメソッドは、ツールバーのボタンをクリックして&2; 回目にドロップダウン ツールバーを閉じます。  
  
##  <a name="onclickup"></a>CMFCDropDownToolbarButton::OnClickUp  
 マウス ボタンを離したときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnClickUp();
```  
  
### <a name="return-value"></a>戻り値  
 ボタンをクリックしてメッセージを処理する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドが基本クラスの実装を拡張[CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup)、ドロップダウン ツールバーの状態を更新しています。  
  
 このメソッドは、アクティブな場合、ドロップダウン ツールバー タイマーを停止します。 開いている場合は、ドロップダウン ツールバーを閉じます。  
  
 ドロップダウン ツールバーおよびドロップダウン ツールバー タイマーの詳細については、次を参照してください。 [CMFCDropDownToolbarButton::OnClick](#onclick)します。  
  
##  <a name="oncontexthelp"></a>CMFCDropDownToolbarButton::OnContextHelp  
 親ツールバーが処理されるときに、フレームワークによって呼び出され、`WM_HELPHITTEST`メッセージです。  
  
```  
virtual BOOL OnContextHelp(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 ツール バー ボタンの親ウィンドウです。  
  
### <a name="return-value"></a>戻り値  
 ボタンは、ヘルプ メッセージを処理する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドによって拡張基本クラスの実装 ( [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)) を呼び出して、 [CMFCDropDownToolbarButton::OnClick](#onclick)メソッドを`bDelay`設定`FALSE`します。 このメソッドによって返される値を返します[CMFCDropDownToolbarButton::OnClick](#onclick)します。  
  
 詳細については、 `WM_HELPHITTEST message, see` [TN028: 状況依存ヘルプ サポート](../../mfc/tn028-context-sensitive-help-support.md)します。  
  
##  <a name="oncustomizemenu"></a>CMFCDropDownToolbarButton::OnCustomizeMenu  
 アプリケーションでは、親ツールバーにショートカット メニューを表示するときは、指定されたメニューを変更します。  
  
```  
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMenu`  
 カスタマイズするメニュー。  
  
### <a name="return-value"></a>戻り値  
 このメソッドは `TRUE` を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドによって拡張基本クラスの実装 ( [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)) を次のメニュー項目を無効にします。  
  
- **ボタン イメージのコピー**  
  
- **ボタンの外観**  
  
- **イメージ**  
  
- **テキスト**  
  
- **画像とテキスト**  
  
 カスタマイズ モードに、フレームワークによって表示されるショートカット メニューを変更するには、このメソッドをオーバーライドします。  
  
##  <a name="ondraw"></a>CMFCDropDownToolbarButton::OnDraw  
 指定したスタイルとオプションを使用して、ボタンを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    CMFCToolBarImages* pImages,  
    BOOL bHorz = TRUE,  
    BOOL bCustomizeMode = FALSE,  
    BOOL bHighlight = FALSE,  
    BOOL bDrawBorder = TRUE,  
    BOOL bGrayDisabledButtons = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 ボタンを表示するデバイス コンテキスト。  
  
 [入力] `rect`  
 ボタンの外接する四角形。  
  
 [入力] `pImages`  
 ボタンに関連付けられているツール バー イメージのコレクション。  
  
 [入力] `bHorz`  
 親ツールバーのドッキング状態です。 このパラメーターは`TRUE`ボタンが水平方向にドッキングされている場合と`FALSE`ボタンが垂直方向にドッキングされています。  
  
 [入力] `bCustomizeMode`  
 ツールバーがカスタマイズ モードになっているかどうかを指定します。 このパラメーターは`TRUE`ツールバーはカスタマイズ モードのときと`FALSE`カスタマイズ モードでツールバーがありませんが。  
  
 [入力] `bHighlight`  
 ボタンが強調表示されているかどうかを指定します。 このパラメーターは`TRUE`ボタンが強調表示されていると`FALSE`ボタンが強調表示されない場合。  
  
 [入力] `bDrawBorder`  
 ボタンの境界線を表示する必要があるかどうかを指定します。 このパラメーターは`TRUE`ボタンが、枠線を表示する場合と`FALSE`ときに、ボタンを表示しないで、枠線。  
  
 [入力] `bGrayDisabledButtons`  
 無効なボタンに影を付けるか、無効なイメージのコレクションを使用するかどうかを指定します。 このパラメーターは`TRUE`無効なボタンが淡色表示されている場合、`FALSE`このメソッドが、無効なイメージのコレクションを使用するとします。  
  
### <a name="remarks"></a>コメント  
 ツールバーのボタンの描画をカスタマイズするには、このメソッドをオーバーライドします。  
  
##  <a name="ondrawoncustomizelist"></a>CMFCDropDownToolbarButton::OnDrawOnCustomizeList  
 ボタンを描画するためにフレームワークによって呼び出される、**コマンド**のウィンドウ、**カスタマイズ** ダイアログ ボックス。  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 ボタンを表示するデバイス コンテキスト。  
  
 [入力] `rect`  
 ボタンの外接する四角形。  
  
 [入力] `bSelected`  
 ボタンが選択されているかどうか。 このパラメーターは、する場合`TRUE`ボタンを選択します。 このパラメーターは場合`FALSE`ボタンが選択されていません。  
  
### <a name="return-value"></a>戻り値  
 指定したデバイス コンテキストにあるボタンのピクセル単位の幅。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、カスタマイズ ダイアログ ボックス (**コマンド** タブ)、ボタンがオーナー描画のリスト ボックスに表示するために必要な場合です。  
  
 このメソッドが基本クラスの実装を拡張 ( [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)) ボタンのテキスト ラベルをボタンの名前に変更することで (つまりの値に、`lpszName`コンス トラクターに渡されたパラメーター)。  
  
##  <a name="serialize"></a>CMFCDropDownToolbarButton::Serialize  
 アーカイブからこのオブジェクトを読み取りまたはアーカイブを書き込みます。  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ar`  
 `CArchive`元またはシリアル化するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメソッドによって拡張基本クラスの実装 ( [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)) の親ツールバー リソース ID をシリアル化しています。 アーカイブの読み込み時 ([とき](../../mfc/reference/carchive-class.md#isloading)値を返します)、このメソッドは、設定、`m_pToolBar`データ メンバーをシリアル化されたリソース ID を含むツールバー  
  
##  <a name="setdefaultcommand"></a>CMFCDropDownToolbarButton::SetDefaultCommand  
 ユーザーがボタンをクリックしたときにフレームワークによって使用される既定のコマンドを設定します。  
  
```  
void SetDefaultCommand(UINT uiCmd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmd`  
 既定のコマンドの ID です。  
  
### <a name="remarks"></a>コメント  
 ユーザーがボタンをクリックしたときに、フレームワークが実行される既定のコマンドを指定するには、このメソッドを呼び出します。 指定されたコマンド ID を持つ項目`uiCmd`親ドロップダウン ツールバーに配置する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)   
 [チュートリアル: ツールバーへのコントロールを配置します。](../../mfc/walkthrough-putting-controls-on-toolbars.md)




