---
title: "CToolTipCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CToolTipCtrl
- AFXCMN/CToolTipCtrl
- AFXCMN/CToolTipCtrl::CToolTipCtrl
- AFXCMN/CToolTipCtrl::Activate
- AFXCMN/CToolTipCtrl::AddTool
- AFXCMN/CToolTipCtrl::AdjustRect
- AFXCMN/CToolTipCtrl::Create
- AFXCMN/CToolTipCtrl::CreateEx
- AFXCMN/CToolTipCtrl::DelTool
- AFXCMN/CToolTipCtrl::GetBubbleSize
- AFXCMN/CToolTipCtrl::GetCurrentTool
- AFXCMN/CToolTipCtrl::GetDelayTime
- AFXCMN/CToolTipCtrl::GetMargin
- AFXCMN/CToolTipCtrl::GetMaxTipWidth
- AFXCMN/CToolTipCtrl::GetText
- AFXCMN/CToolTipCtrl::GetTipBkColor
- AFXCMN/CToolTipCtrl::GetTipTextColor
- AFXCMN/CToolTipCtrl::GetTitle
- AFXCMN/CToolTipCtrl::GetToolCount
- AFXCMN/CToolTipCtrl::GetToolInfo
- AFXCMN/CToolTipCtrl::HitTest
- AFXCMN/CToolTipCtrl::Pop
- AFXCMN/CToolTipCtrl::Popup
- AFXCMN/CToolTipCtrl::RelayEvent
- AFXCMN/CToolTipCtrl::SetDelayTime
- AFXCMN/CToolTipCtrl::SetMargin
- AFXCMN/CToolTipCtrl::SetMaxTipWidth
- AFXCMN/CToolTipCtrl::SetTipBkColor
- AFXCMN/CToolTipCtrl::SetTipTextColor
- AFXCMN/CToolTipCtrl::SetTitle
- AFXCMN/CToolTipCtrl::SetToolInfo
- AFXCMN/CToolTipCtrl::SetToolRect
- AFXCMN/CToolTipCtrl::SetWindowTheme
- AFXCMN/CToolTipCtrl::Update
- AFXCMN/CToolTipCtrl::UpdateTipText
dev_langs:
- C++
helpviewer_keywords:
- tool tips [C++], tool tip controls
- data tips [C++]
- CToolTipCtrl class
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 982aae01dc1308896e9c625e2c2e118b65ec2e64
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ctooltipctrl-class"></a>CToolTipCtrl Class
"ツールヒント コントロール" の機能をカプセル化しています。このコンロトールは、アプリケーションでツールの目的を説明する&1; 行のテキストを表示する小さなポップアップ ウィンドウです。  
  
## <a name="syntax"></a>構文  
  
```  
class CToolTipCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CToolTipCtrl::CToolTipCtrl](#ctooltipctrl)|`CToolTipCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CToolTipCtrl::Activate](#activate)|アクティブにし、ツール ヒント コントロールを非アクティブにします。|  
|[CToolTipCtrl::AddTool](#addtool)|ツール ヒント コントロールのツールを登録します。|  
|[CToolTipCtrl::AdjustRect](#adjustrect)|ツール ヒント コントロールのテキストの間の変換は、四角形とそのウィンドウの四角形を表示します。|  
|[CToolTipCtrl::Create](#create)|ツール ヒント コントロールを作成し、それをアタッチ、`CToolTipCtrl`オブジェクトです。|  
|[CToolTipCtrl::CreateEx](#createex)|指定した Windows 拡張スタイルを使用してツール ヒント コントロールを作成し、それにアタッチ、`CToolTipCtrl`オブジェクトです。|  
|[CToolTipCtrl::DelTool](#deltool)|ツール ヒント コントロールからツールを削除します。|  
|[CToolTipCtrl::GetBubbleSize](#getbubblesize)|ツール ヒントのサイズを取得します。|  
|[CToolTipCtrl::GetCurrentTool](#getcurrenttool)|サイズ、位置、および現在のツール ヒント コントロールを表示するツールヒント ウィンドウのテキストなどの情報を取得します。|  
|[については](#getdelaytime)|最初、ポップアップ、および再表示必要時間を取得ヒント コントロールの現在のツールは、設定されている期間。|  
|[CToolTipCtrl::GetMargin](#getmargin)|上、左、下、およびツール ヒントのウィンドウに設定されている右の余白を取得します。|  
|[CToolTipCtrl::GetMaxTipWidth](#getmaxtipwidth)|ツール ヒントのウィンドウの最大幅を取得します。|  
|[CToolTipCtrl::GetText](#gettext)|ツールは、ツール ヒント コントロールを保持するテキストを取得します。|  
|[CToolTipCtrl::GetTipBkColor](#gettipbkcolor)|ツール ヒントのウィンドウの背景色を取得します。|  
|[CToolTipCtrl::GetTipTextColor](#gettiptextcolor)|ツール ヒントのウィンドウのテキストの色を取得します。|  
|[CToolTipCtrl::GetTitle](#gettitle)|現在のツール ヒント コントロールのタイトルを取得します。|  
|[CToolTipCtrl::GetToolCount](#gettoolcount)|ツール ヒント コントロールで管理されているツールの数を取得します。|  
|[CToolTipCtrl::GetToolInfo](#gettoolinfo)|ツールのツール ヒント コントロールを保持する情報を取得します。|  
|[CToolTipCtrl::HitTest](#hittest)|指定したツールの外接する四角形内にあるかどうかを確認する点をテストします。 必要な場合は、ツールについての情報を取得します。|  
|[CToolTipCtrl::Pop](#pop)|ビューから表示されているツール ヒントのウィンドウを削除します。|  
|[CToolTipCtrl::Popup](#popup)|現在のツール ヒント コントロールの最後のマウス メッセージの座標にある表示させます。|  
|[CToolTipCtrl::RelayEvent](#relayevent)|マウス メッセージを処理するためのツール ヒント コントロールに渡します。|  
|[CToolTipCtrl::SetDelayTime](#setdelaytime)|最初のポップアップを設定し、ツール ヒント コントロールの期間を表示します。|  
|[CToolTipCtrl::SetMargin](#setmargin)|上、左、下、およびツール ヒントのウィンドウの右の余白を設定します。|  
|[CToolTipCtrl::SetMaxTipWidth](#setmaxtipwidth)|ツール ヒントのウィンドウの最大幅を設定します。|  
|[CToolTipCtrl::SetTipBkColor](#settipbkcolor)|ツール ヒント ウィンドウの背景色を設定します。|  
|[CToolTipCtrl::SetTipTextColor](#settiptextcolor)|ツール ヒントのウィンドウのテキストの色を設定します。|  
|[CToolTipCtrl::SetTitle](#settitle)|ツール ヒントには、標準的なアイコンとタイトルの文字列を追加します。|  
|[CToolTipCtrl::SetToolInfo](#settoolinfo)|ツール ヒントが保持するツールの情報を設定します。|  
|[CToolTipCtrl::SetToolRect](#settoolrect)|ツールの新しい外接する四角形を設定します。|  
|[CToolTipCtrl::SetWindowTheme](#setwindowtheme)|ツール ヒントのウィンドウの表示スタイルを設定します。|  
|[CToolTipCtrl::Update](#update)|現在のツールを再描画を強制します。|  
|[CToolTipCtrl::UpdateTipText](#updatetiptext)|ツールは、ツールヒントのテキストを設定します。|  
  
## <a name="remarks"></a>コメント  
 「ツール」は、子ウィンドウや、コントロールまたはウィンドウのクライアント領域内でアプリケーションで定義された四角形領域など、いずれかのウィンドウです。 ツール ヒントには、ほとんどのされ場合にのみ、ユーザー ツールの上にカーソルを置きます約半分のままに&2; つ目に表示されない場合は表示されません。 ツール ヒントは、カーソルの近くが表示され、ユーザーがマウス ボタンをクリックし、ツールからカーソルを移動したりすると消えます。  
  
 `CToolTipCtrl`ツールヒントのテキスト、自体には、ツール ヒントのウィンドウの幅、およびツールヒントの背景色とテキストの色を囲む余白の幅、開始時刻とツール ヒントの期間を制御する機能を提供します。 1 つのツール ヒント コントロールは、1 つ以上のツールに関する情報を提供できます。  
  
 `CToolTipCtrl`クラスには、Windows の一般的なツール ヒント コントロールの機能が用意されています。 このコントロール (つまり、`CToolTipCtrl`クラス) は以降 Windows 95/98 および Windows NT version 3.51 の下で実行されているプログラムにのみ使用できます。  
  
 ツール ヒントを有効にする方法の詳細については、次を参照してください。[ウィンドウのツール ヒントは CFrameWnd から派生しない](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)します。  
  
 使用する方法について`CToolTipCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CToolTipCtrl](../../mfc/using-ctooltipctrl.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CToolTipCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="activate"></a>CToolTipCtrl::Activate  
 この関数では、ツール ヒント コントロールをアクティブまたは非アクティブにします。  
  
```  
void Activate(BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 `bActivate`  
 ツール ヒント コントロールをアクティブ化または非アクティブにするかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 場合`bActivate`は**TRUE**、コントロールがアクティブにされた場合は**FALSE**が非アクティブ化します。  
  
 コントロールに登録されているツールのカーソルが置かれてツール ヒント コントロールがアクティブである場合、ツール ヒントの情報が表示されます。アクティブな場合は、ツール ヒントの情報が表示されないもツールのカーソルがあるときです。  
  
### <a name="example"></a>例  
  例を参照してください[CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)します。  
  
##  <a name="addtool"></a>CToolTipCtrl::AddTool  
 ツール ヒント コントロールのツールを登録します。  
  
```  
BOOL AddTool(
    CWnd* pWnd,  
    UINT nIDText,  
    LPCRECT lpRectTool = NULL,  
    UINT_PTR nIDTool = 0);

 
BOOL AddTool(
    CWnd* pWnd,  
    LPCTSTR lpszText = LPSTR_TEXTCALLBACK,  
    LPCRECT lpRectTool = NULL,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 このツールが含まれるウィンドウへのポインター。  
  
 `nIDText`  
 このツールのテキストを含んでいる文字列リソースの ID。  
  
 *lpRectTool*  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)ツールの座標を含む構造体の外接する四角形。 識別されるウィンドウのクライアント領域の左上隅に対する相対座標は、`pWnd`です。  
  
 `nIDTool`  
 このツールの ID です。  
  
 `lpszText`  
 このツールのテキストへのポインター。 このパラメーターに値が含まれている場合**保持するようにする**、 **TTN_NEEDTEXT**通知メッセージがウィンドウの親に移動する`pWnd`をポイントします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 **LpRectTool**と**nIDTool**パラメーターなければなりません。 どちらも有効ですが、または**lpRectTool**が NULL の場合、 **nIDTool** 0 でなければなりません。  
  
 ツール ヒント コントロールは、1 つ以上のツールを関連付けることができます。 ツールのカーソルが置かれてツール ヒントに格納されている情報が表示されるように、ツール ヒント コントロールとツールを登録するには、この関数を呼び出します。  
  
> [!NOTE]
>  静的コントロールを使用して、ツール ヒントを設定できません`AddTool`します。  
  
### <a name="example"></a>例  
  例を参照してください[CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)します。  
  
##  <a name="adjustrect"></a>CToolTipCtrl::AdjustRect  
 ツール ヒント コントロールのテキストの間の変換は、四角形とそのウィンドウの四角形を表示します。  
  
```  
BOOL AdjustRect(
    LPRECT lprc,  
    BOOL bLarger = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lprc`  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)ツール ヒントのウィンドウの四角形、またはテキストの表示の四角形を保持する構造体。  
  
 `bLarger`  
 場合**TRUE**、`lprc`表示テキストの四角形を指定するために使用され、対応するウィンドウの四角形を受け取ります。 場合**FALSE**、`lprc`ウィンドウの四角形を指定するために使用され、対応するテキスト表示する四角形を受け取ります。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、四角形は正常に調整されました。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、ツール ヒント コントロールのテキスト表示する四角形のウィンドウの四角形の指定したテキストの表示の四角形を表示するために必要なツール ヒント ウィンドウ四角形を計算します。  
  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_ADJUSTRECT](http://msdn.microsoft.com/library/windows/desktop/bb760352)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="create"></a>CToolTipCtrl::Create  
 ツール ヒント コントロールを作成し、それをアタッチ、`CToolTipCtrl`オブジェクトです。  
  
```  
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 ツール ヒント コントロールの親ウィンドウを通常指定する`CDialog`です。 ことはできません**NULL**します。  
  
 `dwStyle`  
 ツール ヒント コントロールのスタイルを指定します。 参照してください、**解説**の詳細セクションです。  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、`CToolTipCtrl`オブジェクトが正常に作成された、それ以外には 0 です。  
  
### <a name="remarks"></a>コメント  
 構築する、`CToolTipCtrl`で&2; つの手順を実行します。 最初に、構築するコンス トラクターを呼び出す、`CToolTipCtrl`オブジェクト、し、呼び出す**作成**をツール ヒント コントロールを作成してアタッチする、`CToolTipCtrl`オブジェクトです。  
  
 `dwStyle`パラメーターの任意の組み合わせを指定できます[ウィンドウ スタイル](../../mfc/reference/window-styles.md)します。 さらに、ツール ヒント コントロールには&2; つのクラスに固有のスタイル: **TTS_ALWAYSTIP**と**TTS_NOPREFIX**します。  
  
|スタイル|説明|  
|-----------|-------------|  
|**TTS_ALWAYSTIP**|ツール ヒント コントロールのオーナー ウィンドウは、アクティブまたは非アクティブかどうかに関係なく、ツールの上にカーソルがある場合、ツール ヒントが表示されることを指定します。 このスタイルがアクティブでないときではなく、ツールのオーナー ウィンドウがアクティブの場合にツール ヒント コントロールが表示されます。|  
|**TTS_NOPREFIX**|このスタイルでは、システムが、文字列からアンパサンド (&) 文字を削除できなくなります。 ツール ヒント コントロールがない場合、 **TTS_NOPREFIX**スタイル、システムは自動的にアンパサンド文字をアプリケーションおよびツール ヒント コントロールのテキストをメニュー項目としては、同じ文字列を使用することにより削除されます。|  
  
 ツール ヒント コントロールは、`WS_POPUP`と**WS_EX_TOOLWINDOW**かどうかを指定すること、コントロールを作成するときに関係なく、ウィンドウ スタイル。  
  
 拡張ウィンドウ スタイルを使用してツール ヒント コントロールを作成するには、呼び出す[CToolTipCtrl::CreateEx](#createex)の代わりに**作成**します。  
  
### <a name="example"></a>例  
  例を参照してください[CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)します。  
  
##  <a name="createex"></a>CToolTipCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成し、関連付けること、`CToolTipCtrl`オブジェクトです。  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwStyle = 0,  
    DWORD dwStyleEx = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 コントロールの親ウィンドウへのポインター。  
  
 `dwStyle`  
 ツール ヒント コントロールのスタイルを指定します。 参照してください、**解説**の[作成](#create)の詳細。  
  
 *dwStyleEx*  
 作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、`dwExStyle`パラメーター [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外。 それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用`CreateEx`の代わりに**作成**、Windows 拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。  
  
##  <a name="ctooltipctrl"></a>CToolTipCtrl::CToolTipCtrl  
 `CToolTipCtrl` オブジェクトを構築します。  
  
```  
CToolTipCtrl();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります**作成**後、オブジェクトを構築します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog #&74;](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]  
  
##  <a name="deltool"></a>CToolTipCtrl::DelTool  
 指定されたツールを削除`pWnd`と`nIDTool`ツール ヒント コントロールがサポートするツールのコレクションからです。  
  
```  
void DelTool(
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 このツールが含まれるウィンドウへのポインター。  
  
 `nIDTool`  
 このツールの ID です。  
  
##  <a name="getbubblesize"></a>CToolTipCtrl::GetBubbleSize  
 ツール ヒントのサイズを取得します。  
  
```  
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpToolInfo`  
 ツール ヒントへのポインター [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256)構造体。  
  
### <a name="return-value"></a>戻り値  
 ツール ヒントのサイズ。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_GETBUBBLESIZE](http://msdn.microsoft.com/library/windows/desktop/bb760387)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getcurrenttool"></a>CToolTipCtrl::GetCurrentTool  
 サイズ、位置、および現在のツール ヒント コントロールによって表示されるツールヒント ウィンドウのテキストなどの情報を取得します。  
  
```  
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[出力] `lpToolInfo`|ポインター、 [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256)現在のツールヒント ウィンドウに関する情報を受け取る構造体。|  
  
### <a name="return-value"></a>戻り値  
 `true`情報が正常に取得される場合それ以外の場合、`false.`  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TTM_GETCURRENTTOOL](http://msdn.microsoft.com/library/windows/desktop/bb760389)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例では、現在のツールヒント ウィンドウに関する情報を取得します。  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s1&6;](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]  
  
##  <a name="getdelaytime"></a>については  
 最初のポップアップを取得し、ツール ヒント コントロールに現在設定されて表示されます。  
  
```  
int GetDelayTime(DWORD dwDuration) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDuration`  
 遅延値を指定するフラグが取得されます。 このパラメーターは、次の値のいずれかになります。  
  
- `TTDT_AUTOPOP`ツール ヒントのウィンドウが表示されるは、場合は、ポインターが静止しているツールの外接する四角形内で時間の長さを取得します。  
  
- `TTDT_INITIAL`ツール ヒントのウィンドウが表示されるまで、ポインターが静止しているツールの外接する四角形内でいなければならない時間の長さを取得します。  
  
- `TTDT_RESHOW`ツールの&1; つの間、ポインターを移動するように表示する次のツール ヒントのウィンドウにかかる時間の長さを取得します。  
  
### <a name="return-value"></a>戻り値  
 指定遅延時間 (ミリ秒)  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_GETDELAYTIME](http://msdn.microsoft.com/library/windows/desktop/bb760390)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getmargin"></a>CToolTipCtrl::GetMargin  
 上、左、下、および右余白のツール ヒントのウィンドウの設定を取得します。  
  
```  
void GetMargin(LPRECT lprc) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lprc`  
 アドレス、`RECT`余白情報を受け取る。 メンバー、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造が外接する四角形を定義しています。 このメッセージの目的では構造体のメンバーはように解釈されます。  
  
|メンバー|表現|  
|------------|--------------------|  
|**top**|上罫線とツールヒントのテキスト、(ピクセル単位) の一番上の距離。|  
|**left**|左罫線と (ピクセル単位) のツールヒントのテキストの左端の間の距離。|  
|**下部にあります。**|下罫線と (ピクセル単位) のツールヒントのテキストの下部にある間の距離。|  
|**right**|右罫線と右端の位置 (ピクセル単位) のツールヒントのテキストの間の距離。|  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_GETMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb760391)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getmaxtipwidth"></a>CToolTipCtrl::GetMaxTipWidth  
 ツール ヒントのウィンドウの最大幅を取得します。  
  
```  
int GetMaxTipWidth() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ツール ヒントのウィンドウの最大幅。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_GETMAXTIPWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760392)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="gettext"></a>CToolTipCtrl::GetText  
 ツールは、ツール ヒント コントロールを保持するテキストを取得します。  
  
```  
void GetText(
    CString& str,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `str`  
 参照、`CString`ツールのテキストを受け取るオブジェクト。  
  
 `pWnd`  
 このツールが含まれるウィンドウへのポインター。  
  
 `nIDTool`  
 このツールの ID です。  
  
### <a name="remarks"></a>コメント  
 `pWnd`と`nIDTool`パラメーターは、ツールを指定します。 そのツールは以前を前回呼び出したとき、ツール ヒント コントロールに登録されている場合**CToolTipCtrl::AddTool**、によって参照されるオブジェクト、`str`パラメーターには、ツールのテキストが割り当てられます。  
  
##  <a name="gettipbkcolor"></a>CToolTipCtrl::GetTipBkColor  
 ツール ヒントのウィンドウの背景色を取得します。  
  
```  
COLORREF GetTipBkColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)背景色を表す値。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_GETTIPBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760394)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="gettiptextcolor"></a>CToolTipCtrl::GetTipTextColor  
 ツール ヒントのウィンドウのテキストの色を取得します。  
  
```  
COLORREF GetTipTextColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)テキストの色を表す値。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_GETTIPTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760395)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="gettitle"></a>CToolTipCtrl::GetTitle  
 現在のツール ヒント コントロールのタイトルを取得します。  
  
```  
void GetTitle(PTTGETTITLE pttgt) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[出力] `pttgt`|ポインター、 [TTGETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760260) ToolTip コントロールに関する情報を格納する構造体。 このメソッドが戻るとき、`pszTitle`のメンバー、 [TTGETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760260)タイトルのテキストへのポインターを構成します。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TTM_GETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760396)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="gettoolcount"></a>CToolTipCtrl::GetToolCount  
 ツール ヒント コントロールに登録されているツールの数を取得します。  
  
```  
int GetToolCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ツールの数は、ツール ヒント コントロールに登録されます。  
  
##  <a name="gettoolinfo"></a>CToolTipCtrl::GetToolInfo  
 ツールのツール ヒント コントロールを保持する情報を取得します。  
  
```  
BOOL GetToolInfo(
    CToolInfo& ToolInfo,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *ToolInfo*  
 参照、`TOOLINFO`ツールのテキストを受け取るオブジェクト。  
  
 `pWnd`  
 このツールが含まれるウィンドウへのポインター。  
  
 `nIDTool`  
 このツールの ID です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 **Hwnd**と**uId**のメンバー、 [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256)によって参照される構造*CToolInfo*ツールを識別します。 前回の呼び出しに使用してツール ヒント コントロールのツールが登録されている場合`AddTool`、`TOOLINFO`構造は、ツールに関する情報を入力します。  
  
##  <a name="hittest"></a>CToolTipCtrl::HitTest  
 指定したツールの外接する四角形内にあるかどうかを確認し場合は、このツールに関する情報を取得する点をテストします。  
  
```  
BOOL HitTest(
    CWnd* pWnd,  
    CPoint pt,  
    LPTOOLINFO lpToolInfo) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 このツールが含まれるウィンドウへのポインター。  
  
 `pt`  
 ポインター、`CPoint`をテストする点の座標を格納するオブジェクト。  
  
 `lpToolInfo`  
 ポインター [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256)ツールについての情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 ヒット テスト情報で指定されたポイントが、ツールの外接する四角形内にある場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は&0; 以外の値を返す場合、構造体を指す`lpToolInfo`点が含む四角形内にあるツールに関する情報を入力します。  
  
 `TTHITTESTINFO`構造は次のように定義されます。  
  
 `typedef struct _TT_HITTESTINFO { // tthti`  
  
 `HWND hwnd;   // handle of tool or window with tool`  
  
 `POINT pt;    // client coordinates of point to test`  
  
 `TOOLINFO ti; // receives information about the tool`  
  
 `} TTHITTESTINFO, FAR * LPHITTESTINFO;`  
  
 **hwnd の分離**  
 ツールのハンドルを指定します。  
  
 **pt**  
 ポイントは、ツールの外接する四角形の場合は、点の座標を指定します。  
  
 **ti**  
 このツールに関する情報。 詳細については、`TOOLINFO`構造体は、「 [CToolTipCtrl::GetToolInfo](#gettoolinfo)します。  
  
##  <a name="pop"></a>CToolTipCtrl::Pop  
 ビューから表示されているツール ヒントのウィンドウを削除します。  
  
```  
void Pop();
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_POP](http://msdn.microsoft.com/library/windows/desktop/bb760401)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="popup"></a>CToolTipCtrl::Popup  
 現在のツール ヒント コントロールの最後のマウス メッセージの座標にある表示させます。  
  
```  
void Popup();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [TTM_POPUP](http://msdn.microsoft.com/library/windows/desktop/bb760402)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例では、ツールヒント ウィンドウが表示されます。  
  
 [!code-cpp[NVC_MFC_CToolBarCtrl_s&#1;7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]  
  
##  <a name="relayevent"></a>CToolTipCtrl::RelayEvent  
 マウス メッセージを処理するためのツール ヒント コントロールに渡します。  
  
```  
void RelayEvent(LPMSG lpMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpMsg`  
 ポインター、 [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958)リレーにメッセージを格納する構造体。  
  
### <a name="remarks"></a>コメント  
 ツール ヒント コントロールのみ、次メッセージを処理してに送信される`RelayEvent`:  
  
|WM_LBUTTONDOWN|WM_MOUSEMOVE|  
|---------------------|-------------------|  
|`WM_LBUTTONUP`|`WM_RBUTTONDOWN`|  
|`WM_MBUTTONDOWN`|`WM_RBUTTONUP`|  
|`WM_MBUTTONUP`||  
  
### <a name="example"></a>例  
  例を参照してください[CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)します。  
  
##  <a name="setdelaytime"></a>CToolTipCtrl::SetDelayTime  
 ツール ヒント コントロールの時刻の遅延を設定します。  
  
```  
void SetDelayTime(UINT nDelay);

 
void SetDelayTime(
    DWORD dwDuration,  
    int iTime);
```  
  
### <a name="parameters"></a>パラメーター  
 *nDelay*  
 新しい時刻の遅延をミリ秒単位で指定します。  
  
 `dwDuration`  
 遅延値を指定するフラグが取得されます。 参照してください[については](#getdelaytime)有効な値の詳細についてです。  
  
 *iTime*  
 指定遅延時間 (ミリ秒)。  
  
### <a name="remarks"></a>コメント  
 遅延時間は、ツール ヒントのウィンドウが表示される前に、ツールのカーソルを維持する必要があります。 既定の遅延時間は、500 ミリ秒です。  
  
##  <a name="setmargin"></a>CToolTipCtrl::SetMargin  
 上、左、下、およびツール ヒントのウィンドウの右の余白を設定します。  
  
```  
void SetMargin(LPRECT lprc);
```  
  
### <a name="parameters"></a>パラメーター  
 `lprc`  
 アドレス、`RECT`を設定する余白の情報を格納する構造体。 メンバー、`RECT`構造が外接する四角形を定義しています。 参照してください[CToolTipCtrl::GetMargin](#getmargin)余白情報の詳細についてです。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_SETMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb760406)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="setmaxtipwidth"></a>CToolTipCtrl::SetMaxTipWidth  
 ツール ヒントのウィンドウの最大幅を設定します。  
  
```  
int SetMaxTipWidth(int iWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 *iWidth*  
 設定する最大のツール ヒント ウィンドウの幅。  
  
### <a name="return-value"></a>戻り値  
 前のヒントの最大の幅。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_SETMAXTIPWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760408)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="settipbkcolor"></a>CToolTipCtrl::SetTipBkColor  
 ツール ヒント ウィンドウの背景色を設定します。  
  
```  
void SetTipBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>パラメーター  
 `clr`  
 新しい背景色。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_SETTIPBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760411)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="settiptextcolor"></a>CToolTipCtrl::SetTipTextColor  
 ツール ヒントのウィンドウのテキストの色を設定します。  
  
```  
void SetTipTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>パラメーター  
 `clr`  
 新しいテキストの色。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_SETTIPTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760413)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="settitle"></a>CToolTipCtrl::SetTitle  
 ツール ヒントには、標準的なアイコンとタイトルの文字列を追加します。  
  
```  
BOOL SetTitle(
    UINT uIcon,  
    LPCTSTR lpstrTitle);
```  
  
### <a name="parameters"></a>パラメーター  
 *uIcon*  
 参照してください*アイコン*で[TTM_SETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760414)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 *キャプションを表示*  
 タイトル文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[TTM_SETTITLE](http://msdn.microsoft.com/library/windows/desktop/bb760414)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="settoolinfo"></a>CToolTipCtrl::SetToolInfo  
 ツール ヒントが保持するツールの情報を設定します。  
  
```  
void SetToolInfo(LPTOOLINFO lpToolInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpToolInfo`  
 ポインター、 [TOOLINFO](http://msdn.microsoft.com/library/windows/desktop/bb760256)を設定するには、情報を指定します。  
  
##  <a name="settoolrect"></a>CToolTipCtrl::SetToolRect  
 ツールの新しい外接する四角形を設定します。  
  
```  
void SetToolRect(
    CWnd* pWnd,  
    UINT_PTR nIDTool,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 このツールが含まれるウィンドウへのポインター。  
  
 `nIDTool`  
 このツールの ID です。  
  
 `lpRect`  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体の新しい外接する四角形を指定します。  
  
##  <a name="setwindowtheme"></a>CToolTipCtrl::SetWindowTheme  
 ツール ヒントのウィンドウの表示スタイルを設定します。  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszSubAppName`  
 設定する visual スタイルを含む Unicode 文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 戻り値は使用されません。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [TTM_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb760418) 」の説明に従って、メッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="update"></a>CToolTipCtrl::Update  
 現在のツールを再描画を強制します。  
  
```  
void Update();
```  
  
##  <a name="updatetiptext"></a>CToolTipCtrl::UpdateTipText  
 このコントロールのツールのツールヒントのテキストを更新します。  
  
```  
void UpdateTipText(
    LPCTSTR lpszText,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);

 
void UpdateTipText(
    UINT nIDText,  
    CWnd* pWnd,  
    UINT_PTR nIDTool = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszText`  
 このツールのテキストへのポインター。  
  
 `pWnd`  
 このツールが含まれるウィンドウへのポインター。  
  
 `nIDTool`  
 このツールの ID です。  
  
 `nIDText`  
 このツールのテキストを含んでいる文字列リソースの ID。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CToolBar クラス](../../mfc/reference/ctoolbar-class.md)

