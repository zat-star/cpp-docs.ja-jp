---
title: "CReBarCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CReBarCtrl
- AFXCMN/CReBarCtrl
- AFXCMN/CReBarCtrl::CReBarCtrl
- AFXCMN/CReBarCtrl::BeginDrag
- AFXCMN/CReBarCtrl::Create
- AFXCMN/CReBarCtrl::CreateEx
- AFXCMN/CReBarCtrl::DeleteBand
- AFXCMN/CReBarCtrl::DragMove
- AFXCMN/CReBarCtrl::EndDrag
- AFXCMN/CReBarCtrl::GetBandBorders
- AFXCMN/CReBarCtrl::GetBandCount
- AFXCMN/CReBarCtrl::GetBandInfo
- AFXCMN/CReBarCtrl::GetBandMargins
- AFXCMN/CReBarCtrl::GetBarHeight
- AFXCMN/CReBarCtrl::GetBarInfo
- AFXCMN/CReBarCtrl::GetBkColor
- AFXCMN/CReBarCtrl::GetColorScheme
- AFXCMN/CReBarCtrl::GetDropTarget
- AFXCMN/CReBarCtrl::GetExtendedStyle
- AFXCMN/CReBarCtrl::GetImageList
- AFXCMN/CReBarCtrl::GetPalette
- AFXCMN/CReBarCtrl::GetRect
- AFXCMN/CReBarCtrl::GetRowCount
- AFXCMN/CReBarCtrl::GetRowHeight
- AFXCMN/CReBarCtrl::GetTextColor
- AFXCMN/CReBarCtrl::GetToolTips
- AFXCMN/CReBarCtrl::HitTest
- AFXCMN/CReBarCtrl::IDToIndex
- AFXCMN/CReBarCtrl::InsertBand
- AFXCMN/CReBarCtrl::MaximizeBand
- AFXCMN/CReBarCtrl::MinimizeBand
- AFXCMN/CReBarCtrl::MoveBand
- AFXCMN/CReBarCtrl::PushChevron
- AFXCMN/CReBarCtrl::RestoreBand
- AFXCMN/CReBarCtrl::SetBandInfo
- AFXCMN/CReBarCtrl::SetBandWidth
- AFXCMN/CReBarCtrl::SetBarInfo
- AFXCMN/CReBarCtrl::SetBkColor
- AFXCMN/CReBarCtrl::SetColorScheme
- AFXCMN/CReBarCtrl::SetExtendedStyle
- AFXCMN/CReBarCtrl::SetImageList
- AFXCMN/CReBarCtrl::SetOwner
- AFXCMN/CReBarCtrl::SetPalette
- AFXCMN/CReBarCtrl::SetTextColor
- AFXCMN/CReBarCtrl::SetToolTips
- AFXCMN/CReBarCtrl::SetWindowTheme
- AFXCMN/CReBarCtrl::ShowBand
- AFXCMN/CReBarCtrl::SizeToRect
dev_langs:
- C++
helpviewer_keywords:
- rebar controls, control bar
- rebar controls, CReBarCtrl class
- CReBarCtrl class
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
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
ms.openlocfilehash: c1da4de2897c74e9cb25bc060033f4bd43159174
ms.lasthandoff: 02/24/2017

---
# <a name="crebarctrl-class"></a>CReBarCtrl クラス
Rebar コントロールの機能がカプセル化されています。Rebar コントロールは、子ウィンドウを含むコンテナーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CReBarCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CReBarCtrl::CReBarCtrl](#crebarctrl)|`CReBarCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CReBarCtrl::BeginDrag](#begindrag)|Rebar コントロールをドラッグ アンド ドロップ モードに配置します。|  
|[CReBarCtrl::Create](#create)|Rebar コントロールを作成し、それをアタッチ、`CReBarCtrl`オブジェクトです。|  
|[CReBarCtrl::CreateEx](#createex)|指定した Windows 拡張スタイルを使用 rebar コントロールを作成し、それにアタッチ、`CReBarCtrl`オブジェクトです。|  
|[CReBarCtrl::DeleteBand](#deleteband)|Rebar コントロールのバンドを削除します。|  
|[CReBarCtrl::DragMove](#dragmove)|呼び出した後、rebar コントロールでドラッグの位置を更新`BeginDrag`します。|  
|[CReBarCtrl::EndDrag](#enddrag)|Rebar コントロールのドラッグ アンド ドロップ操作を終了します。|  
|[CReBarCtrl::GetBandBorders](#getbandborders)|バンドの境界線を取得します。|  
|[CReBarCtrl::GetBandCount](#getbandcount)|Rebar コントロールの現在のバンドの数を取得します。|  
|[CReBarCtrl::GetBandInfo](#getbandinfo)|Rebar コントロールで指定されたバンドに関する情報を取得します。|  
|[CReBarCtrl::GetBandMargins](#getbandmargins)|バンドのマージンを取得します。|  
|[CReBarCtrl::GetBarHeight](#getbarheight)|Rebar コントロールの高さを取得します。|  
|[CReBarCtrl::GetBarInfo](#getbarinfo)|Rebar コントロールおよびそれを使用してイメージ リストに関する情報を取得します。|  
|[CReBarCtrl::GetBkColor](#getbkcolor)|Rebar コントロールの既定の背景色を取得します。|  
|[CReBarCtrl::GetColorScheme](#getcolorscheme)|取得、 [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) rebar コントロールに関連付けられている構造体。|  
|[CReBarCtrl::GetDropTarget](#getdroptarget)|Rebar コントロールの取得`IDropTarget`インターフェイス ポインター。|  
|[CReBarCtrl::GetExtendedStyle](#getextendedstyle)|現在の rebar コントロールの拡張スタイルを取得します。|  
|[CReBarCtrl::GetImageList](#getimagelist)|Rebar コントロールに関連付けられているイメージ リストを取得します。|  
|[CReBarCtrl::GetPalette](#getpalette)|Rebar コントロールの現在のパレットを取得します。|  
|[CReBarCtrl::GetRect](#getrect)|Rebar コントロールの特定のバンドの外接する四角形を取得します。|  
|[CReBarCtrl::GetRowCount](#getrowcount)|Rebar コントロールでの帯域外行の数を取得します。|  
|[CReBarCtrl::GetRowHeight](#getrowheight)|Rebar コントロールで指定された行の高さを取得します。|  
|[CReBarCtrl::GetTextColor](#gettextcolor)|Rebar コントロールの既定のテキスト色を取得します。|  
|[CReBarCtrl::GetToolTips](#gettooltips)|Rebar コントロールに関連付けられているすべてのツール ヒント コントロールのハンドルを取得します。|  
|[CReBarCtrl::HitTest](#hittest)|Rebar バンドがその時点で存在する場合に、rebar バンドのどの部分が画面で、特定の時点が判断します。|  
|[CReBarCtrl::IDToIndex](#idtoindex)|帯域外識別子 (ID) を rebar コントロールのバンドのインデックスに変換します。|  
|[CReBarCtrl::InsertBand](#insertband)|Rebar コントロールで新しいバンドを挿入します。|  
|[CReBarCtrl::MaximizeBand](#maximizeband)|最大サイズに rebar コントロールのバンドのサイズを変更します。|  
|[CReBarCtrl::MinimizeBand](#minimizeband)|最小サイズに rebar コントロールのバンドのサイズを変更します。|  
|[CReBarCtrl::MoveBand](#moveband)|バンドを別の&1; つのインデックスに移動します。|  
|[CReBarCtrl::PushChevron](#pushchevron)|プログラムを使用して、シェブロンをプッシュします。|  
|[CReBarCtrl::RestoreBand](#restoreband)|適切なサイズに rebar コントロールのバンドのサイズを変更します。|  
|[CReBarCtrl::SetBandInfo](#setbandinfo)|Rebar コントロールでは、既存のバンドの特性を設定します。|  
|[CReBarCtrl::SetBandWidth](#setbandwidth)|現在の rebar コントロールでは、指定したドッキング バンドの幅を設定します。|  
|[CReBarCtrl::SetBarInfo](#setbarinfo)|Rebar コントロールの特性を設定します。|  
|[CReBarCtrl::SetBkColor](#setbkcolor)|Rebar コントロールの既定の背景色を設定します。|  
|[CReBarCtrl::SetColorScheme](#setcolorscheme)|Rebar コントロールのボタンの画面の配色を設定します。|  
|[CReBarCtrl::SetExtendedStyle](#setextendedstyle)|現在の rebar コントロールの拡張スタイルを設定します。|  
|[CReBarCtrl::SetImageList](#setimagelist)|Rebar コントロールのイメージ リストを設定します。|  
|[CReBarCtrl::SetOwner](#setowner)|Rebar コントロールのオーナー ウィンドウを設定します。|  
|[CReBarCtrl::SetPalette](#setpalette)|Rebar コントロールの現在のパレットを設定します。|  
|[CReBarCtrl::SetTextColor](#settextcolor)|Rebar コントロールの既定のテキスト色を設定します。|  
|[CReBarCtrl::SetToolTips](#settooltips)|Rebar コントロールとツール ヒント コントロールを関連付けます。|  
|[CReBarCtrl::SetWindowTheme](#setwindowtheme)|Rebar コントロールの表示スタイルを設定します。|  
|[CReBarCtrl::ShowBand](#showband)|Rebar コントロールの特定のバンドの表示と非表示を切り替えます。|  
|[CReBarCtrl::SizeToRect](#sizetorect)|Rebar コントロールを指定した四角形に収まるようにします。|  
  
## <a name="remarks"></a>コメント  
 Rebar コントロールが配置されているアプリケーションは、rebar バンド rebar コントロールに含まれる子ウィンドウを割り当てます。 子ウィンドウは、通常他の一般的なコントロールです。  
  
 Rebar コントロールには、1 つまたは複数のバンドが含まれています。 各バンド グリッパー バー、ビットマップ、テキスト ラベル、および子ウィンドウの組み合わせを含めることができます。 バンドは、これらの各項目の&1; つだけを含めることができます。  
  
 Rebar コントロールでは、指定した背景ビットマップを子ウィンドウを表示できます。 Rebar コントロールのすべてのバンド サイズを変更できる、使用するものを除く、 **RBBS_FIXEDSIZE**スタイル。 位置を変更または rebar コントロールのバンドのサイズを変更すると、rebar コントロールは、サイズとそのバンドに割り当てられている子ウィンドウの位置を管理します。 サイズを変更したり、コントロール内のバンドの順序を変更したり、をクリックし、バンドのグリッパー バーをドラッグします。  
  
 次の図は、次の&3; つのバンドを持つ rebar コントロールを示しています。  
  
-   帯域外 0 には、フラットで透明なツール バー コントロールが含まれています。  
  
-   帯域外 1 には、両方の透過的な標準および透過的なドロップダウン ボタンが含まれています。  
  
-   帯域外 2 には、コンボ ボックスと 4 つの標準ボタンが含まれています。  
  
     ![Rebar メニューの例](../../mfc/reference/media/vc4scc1.gif "vc4scc1")  
  
## <a name="rebar-control"></a>Rebar コントロール  
 コントロールのサポートを rebar:  
  
-   イメージが一覧表示します。  
  
-   メッセージ処理します。  
  
-   カスタム描画機能。  
  
-   さまざまな標準のウィンドウ スタイルだけでなく、コントロールのスタイル。 これらのスタイルの一覧は、次を参照してください。 [Rebar コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb774377)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 詳細については、次を参照してください。[を使用して CReBarCtrl](../../mfc/using-crebarctrl.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CReBarCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="begindrag"></a>CReBarCtrl::BeginDrag  
 Win32 メッセージの動作を実装[RB_BEGINDRAG](http://msdn.microsoft.com/library/windows/desktop/bb774429)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
void BeginDrag(
    UINT uBand,  
    DWORD dwPos = (DWORD)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 `uBand`  
 ドラッグ アンド ドロップ操作に影響を与えるバンドの&0; から始まるインデックス。  
  
 `dwPos`  
 A`DWORD`開始マウス座標を表す値。 水平方向の座標は、LOWORD に含まれ、HIWORD に垂直方向の座標が含まれています。 渡した場合`(DWORD)-1`、rebar コントロールが最後に、コントロールのスレッドと呼ばれるマウスの位置を使用して**GetMessage**または**PeekMessage**します。  
  
##  <a name="create"></a>CReBarCtrl::Create  
 Rebar コントロールを作成し、それをアタッチ、`CReBarCtrl`オブジェクトです。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 Rebar コントロールのスタイルがコントロールに適用の組み合わせを指定します。 参照してください[Rebar コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb774377)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]サポートされているスタイルの一覧にします。  
  
 `rect`  
 参照、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造 rebar コントロールのサイズと位置です。  
  
 `pParentWnd`  
 ポインター、 [CWnd](../../mfc/reference/cwnd-class.md) rebar コントロールの親ウィンドウであるオブジェクト。 ことはできません**NULL**します。  
  
 `nID`  
 Rebar コントロールのコントロール ID を指定します  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが正常に作成された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 Rebar コントロールは、2 つの手順で作成します。  
  
1.  呼び出す[CReBarCtrl](#crebarctrl)を構築する、`CReBarCtrl`オブジェクトです。  
  
2.  このメンバー関数は、Windows rebar コントロールを作成し、それにアタッチするを呼び出す、`CReBarCtrl`オブジェクトです。  
  
 呼び出すと**作成**、一般的なコントロールが初期化されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CReBarCtrl&#3;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]  
  
##  <a name="createex"></a>CReBarCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成し、関連付けます、`CReBarCtrl`オブジェクトです。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExStyle`  
 作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、`dwExStyle`パラメーター [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `dwStyle`  
 Rebar コントロールのスタイルがコントロールに適用の組み合わせを指定します。 サポートされているスタイルの一覧は、次を参照してください。 [Rebar コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb774377)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体のサイズとのクライアント座標で、作成するウィンドウの位置を表す`pParentWnd`します。  
  
 `pParentWnd`  
 コントロールの親ウィンドウへのポインター。  
  
 `nID`  
 コントロールの子ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用`CreateEx`の代わりに[作成](#create)、Windows 拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。  
  
##  <a name="crebarctrl"></a>CReBarCtrl::CReBarCtrl  
 
          `CReBarCtrl` オブジェクトを作成します。  
  
```  
CReBarCtrl();
```  
  
### <a name="example"></a>例  
  例を参照してください[CReBarCtrl::Create](#create)します。  
  
##  <a name="deleteband"></a>CReBarCtrl::DeleteBand  
 Win32 メッセージの動作を実装[RB_DELETEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774431)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
BOOL DeleteBand(UINT uBand);
```  
  
### <a name="parameters"></a>パラメーター  
 `uBand`  
 削除するバンドの&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 バンドが正常に削除された場合は&0; 以外。それ以外の場合&0; を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CReBarCtrl&4;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]  
  
##  <a name="dragmove"></a>CReBarCtrl::DragMove  
 Win32 メッセージの動作を実装[RB_DRAGMOVE](https://msdn.microsoft.com/library/bb774433.aspx)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
void DragMove(DWORD dwPos = (DWORD)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwPos`  
 A`DWORD`新しいマウス座標を表す値。 水平方向の座標は、LOWORD に含まれ、HIWORD に垂直方向の座標が含まれています。 渡した場合`(DWORD)-1`、rebar コントロールが最後に、コントロールのスレッドと呼ばれるマウスの位置を使用して**GetMessage**または**PeekMessage**します。  
  
##  <a name="enddrag"></a>CReBarCtrl::EndDrag  
 Win32 メッセージの動作を実装[RB_ENDDRAG](http://msdn.microsoft.com/library/windows/desktop/bb774435)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
void EndDrag();
```  
  
##  <a name="getbandborders"></a>CReBarCtrl::GetBandBorders  
 Win32 メッセージの動作を実装[RB_GETBANDBORDERS](http://msdn.microsoft.com/library/windows/desktop/bb774437)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
void GetBandBorders(
    UINT uBand,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `uBand`  
 境界線を取得するバンドの&0; から始まるインデックス。  
  
 `prc`  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)バンド境界線を受け取る。 Rebar コントロールがある場合、 **RBS_BANDBORDERS**スタイルでは、この構造体の各メンバーには、境界を構成する、バンドの対応する側のピクセル数が表示されます。 Rebar コントロールがない場合、 **RBS_BANDBORDERS**スタイルをこの構造体の左のメンバーが有効な情報を受け取るだけです。 Rebar コントロールのスタイルについては、次を参照してください。 [Rebar コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb774377)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getbandcount"></a>CReBarCtrl::GetBandCount  
 Win32 メッセージの動作を実装[RB_GETBANDCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb774439)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
UINT GetBandCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロールに割り当てられているバンドの数。  
  
##  <a name="getbandinfo"></a>CReBarCtrl::GetBandInfo  
 Win32 メッセージの動作を実装[RB_GETBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774451) 」の説明に従って、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
BOOL GetBandInfo(
    UINT uBand,  
    REBARBANDINFO* prbbi) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `uBand`  
 情報の取得されるバンドの&0; から始まるインデックス。  
  
 `prbbi`  
 ポインター、 [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393)帯域外情報を受け取る構造です。 設定する必要があります、`cbSize`この構造体のメンバー`sizeof(REBARBANDINFO)`し、設定、 **fMask**メンバーをこのメッセージを送信する前に取得する項目にします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
##  <a name="getbandmargins"></a>CReBarCtrl::GetBandMargins  
 バンドのマージンを取得します。  
  
```  
void GetBandMargins(PMARGINS pMargins);
```  
  
### <a name="parameters"></a>パラメーター  
 *pMargins*  
 ポインター、[余白](http://msdn.microsoft.com/library/windows/desktop/bb773244)は情報を受信する構造体。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [RB_GETBANDMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb774453) 」の説明に従って、メッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getbarheight"></a>CReBarCtrl::GetBarHeight  
 Rebar バーの高さを取得します。  
  
```  
UINT GetBarHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロールのピクセル単位の高さを表す値です。  
  
##  <a name="getbarinfo"></a>CReBarCtrl::GetBarInfo  
 Win32 メッセージの動作を実装[RB_GETBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774457)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
BOOL GetBarInfo(REBARINFO* prbi) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `prbi`  
 ポインター、 [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) rebar コントロールの情報を受け取る。 設定する必要があります、`cbSize`この構造体のメンバー`sizeof(REBARINFO)`このメッセージを送信する前にします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
##  <a name="getbkcolor"></a>CReBarCtrl::GetBkColor  
 Win32 メッセージの動作を実装[RB_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774459)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A **COLORREF**を現在の既定の背景色を表す値。  
  
##  <a name="getcolorscheme"></a>CReBarCtrl::GetColorScheme  
 取得、 [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) rebar コントロールの構造です。  
  
```  
BOOL GetColorScheme(COLORSCHEME* lpcs);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpcs`  
 ポインター、 [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502)構造、」の説明に従って、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 **COLORSCHEME**構造体には、ボタンの強調表示色とボタンの影の色が含まれています。  
  
##  <a name="getdroptarget"></a>CReBarCtrl::GetDropTarget  
 Win32 メッセージの動作を実装[RB_GETDROPTARGET](http://msdn.microsoft.com/library/windows/desktop/bb774463)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
IDropTarget* GetDropTarget() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)インターフェイスです。  
  
##  <a name="getextendedstyle"></a>CReBarCtrl::GetExtendedStyle  
 現在の rebar コントロールの拡張スタイルを取得します。  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 拡張スタイルを示すフラグのビットごとの組み合わせ (OR)。 可能なフラグは`RBS_EX_SPLITTER`と`RBS_EX_TRANSPARENT`です。 詳細については、次を参照してください。、`dwMask`のパラメーター、 [CReBarCtrl::SetExtendedStyle](#setextendedstyle)メソッドです。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [RB_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb774433)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getimagelist"></a>CReBarCtrl::GetImageList  
 取得、 `CImageList` rebar コントロールに関連付けられているオブジェクト。  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)オブジェクトです。 返します。 **NULL**コントロールのイメージ リストが設定されていない場合。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数に格納されているサイズとマスクの情報を使用して、 [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395)構造、」の説明に従って、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getpalette"></a>CReBarCtrl::GetPalette  
 Rebar コントロールの現在のパレットを取得します。  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CPalette](../../mfc/reference/cpalette-class.md) rebar コントロールの現在のパレットを指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用している、 `CPalette` 、戻り値としてオブジェクトではなく、`HPALETTE`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CReBarCtrl&#5;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]  
  
##  <a name="getrect"></a>CReBarCtrl::GetRect  
 Win32 メッセージの動作を実装[RB_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb774469)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
BOOL GetRect(
    UINT uBand,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `uBand`  
 Rebar コントロールのバンドの&0; から始まるインデックス。  
  
 `prc`  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) rebar バンドの境界を受け取る。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CReBarCtrl&6;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]  
  
##  <a name="getrowcount"></a>CReBarCtrl::GetRowCount  
 Win32 メッセージの動作を実装[RB_GETROWCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb774471)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
UINT GetRowCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A **UINT**コントロールでの帯域外行の数を表す値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CReBarCtrl&#7;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]  
  
##  <a name="getrowheight"></a>CReBarCtrl::GetRowHeight  
 Win32 メッセージの動作を実装[RB_GETROWHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb774473)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
UINT GetRowHeight(UINT uRow) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *uRow*  
 高さを取得するバンドの&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 A **UINT**をピクセル単位での行の高さを表す値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CReBarCtrl&#8;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]  
  
##  <a name="gettextcolor"></a>CReBarCtrl::GetTextColor  
 Win32 メッセージの動作を実装[RB_GETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774475)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A **COLORREF**を現在の既定のテキスト色を表す値。  
  
##  <a name="gettooltips"></a>CReBarCtrl::GetToolTips  
 Win32 メッセージの動作を実装[RB_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb774477)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 注意 MFC 実装の`GetToolTips`へのポインターを返す、`CToolTipCtrl`ではなく、`HWND`です。  
  
##  <a name="hittest"></a>CReBarCtrl::HitTest  
 Win32 メッセージの動作を実装[RB_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb774494)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
int HitTest(RBHITTESTINFO* prbht);
```  
  
### <a name="parameters"></a>パラメーター  
 *prbht*  
 ポインター、 [RBHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb774391)構造体。 メッセージを送信する前に、 **pt**この構造体のメンバーは、クライアント座標で、テスト ポイントに初期化する必要があります。  
  
### <a name="return-value"></a>戻り値  
 指定したポイントまたは時点 rebar バンドがなかった場合は-1 にバンドの&0; から始まるインデックス。  
  
##  <a name="idtoindex"></a>CReBarCtrl::IDToIndex  
 Win32 メッセージの動作を実装[RB_IDTOINDEX](http://msdn.microsoft.com/library/windows/desktop/bb774496)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
int IDToIndex(UINT uBandID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *uBandID*  
 指定されたバンドのアプリケーション定義の識別子が渡された、 **wID**のメンバー、 [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393)バンドが挿入されたときに構造化します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、帯域外の&0; から始まるインデックス、または-1 のそれ以外の場合。 重複している帯域外インデックスが存在する場合は、1 つ目が返されます。  
  
##  <a name="insertband"></a>CReBarCtrl::InsertBand  
 Win32 メッセージの動作を実装[RB_INSERTBAND](http://msdn.microsoft.com/library/windows/desktop/bb774498)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
BOOL InsertBand(
    UINT uIndex,  
    REBARBANDINFO* prbbi);
```  
  
### <a name="parameters"></a>パラメーター  
 *uIndex*  
 バンドを挿入する位置の&0; から始まるインデックス。 このパラメーターを-1 に設定すると、コントロールは最後の位置で新しいバンドを追加します。  
  
 `prbbi`  
 ポインター、 [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393)を挿入するバンドを定義します。 設定する必要があります、`cbSize`この構造体のメンバー`sizeof(REBARBANDINFO)`この関数を呼び出す前にします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CReBarCtrl&#9;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]  
  
##  <a name="maximizeband"></a>CReBarCtrl::MaximizeBand  
 最大サイズに rebar コントロールのバンドのサイズを変更します。  
  
```  
void MaximizeBand(UINT uBand);
```  
  
### <a name="parameters"></a>パラメーター  
 `uBand`  
 最大化するバンドの&0; から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 Win32 メッセージの動作を実装[RB_MAXIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774500)と`fIdeal`」の説明に従って、0 に設定、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CReBarCtrl&#10;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]  
  
##  <a name="minimizeband"></a>CReBarCtrl::MinimizeBand  
 最小サイズに rebar コントロールのバンドのサイズを変更します。  
  
```  
void MinimizeBand(UINT uBand);
```  
  
### <a name="parameters"></a>パラメーター  
 `uBand`  
 最小化するバンドの&0; から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 Win32 メッセージの動作を実装[RB_MINIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774502)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CReBarCtrl&#11;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]  
  
##  <a name="moveband"></a>CReBarCtrl::MoveBand  
 Win32 メッセージの動作を実装[RB_MOVEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774504)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
BOOL MoveBand(
    UINT uFrom,  
    UINT uTo);
```  
  
### <a name="parameters"></a>パラメーター  
 *uFrom*  
 移動するバンドの&0; から始まるインデックス。  
  
 *不在*  
 新しいバンド位置の&0; から始まるインデックス。 このパラメーターの値は、バンドから&1; を引いた数より大きいしない場合があります。 バンドの数を取得する呼び出し[GetBandCount](#getbandcount)します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
##  <a name="pushchevron"></a>CReBarCtrl::PushChevron  
 Win32 メッセージの動作を実装[RB_PUSHCHEVRON](http://msdn.microsoft.com/library/windows/desktop/bb774506)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
void PushChevron(
    UINT uBand,  
    LPARAM lAppValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `uBand`  
 シェブロンをプッシュするのには帯域外の&0; から始まるインデックス。  
  
 `lAppValue`  
 アプリケーションでは、32 ビット値を定義します。 参照してください`lAppValue`で[RB_PUSHCHEVRON](http://msdn.microsoft.com/library/windows/desktop/bb774506)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="restoreband"></a>CReBarCtrl::RestoreBand  
 適切なサイズに rebar コントロールのバンドのサイズを変更します。  
  
```  
void RestoreBand(UINT uBand);
```  
  
### <a name="parameters"></a>パラメーター  
 `uBand`  
 最大化するバンドの&0; から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 Win32 メッセージの動作を実装[RB_MAXIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774500)と`fIdeal`」の説明に従って、1 に設定、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CReBarCtrl&#12;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]  
  
##  <a name="setbandinfo"></a>CReBarCtrl::SetBandInfo  
 Win32 メッセージの動作を実装[RB_SETBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774508)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
BOOL SetBandInfo(
    UINT uBand,  
    REBARBANDINFO* prbbi);
```  
  
### <a name="parameters"></a>パラメーター  
 `uBand`  
 新しい設定を受信するバンドの&0; から始まるインデックス。  
  
 `prbbi`  
 ポインター、 [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393)を挿入するバンドを定義します。 設定する必要があります、`cbSize`この構造体のメンバー`sizeof(REBARBANDINFO)`このメッセージを送信する前にします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CReBarCtrl&#13;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]  
  
##  <a name="setbandwidth"></a>CReBarCtrl::SetBandWidth  
 現在の rebar コントロールでは、指定したドッキング バンドの幅を設定します。  
  
```  
BOOL SetBandWidth(
    UINT uBand,   
    int cxWidth);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `uBand`|Rebar バンドの&0; から始まるインデックス。|  
|[入力] `cxWidth`|(ピクセル単位)、rebar バンドの幅。|  
  
### <a name="return-value"></a>戻り値  
 このメソッドが成功した場合は `true`。それ以外の場合は `false`。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [RB_SETBANDWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb774511)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_rebar`つまり、現在の rebar コントロールのアクセスに使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CReBarCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]  
  
### <a name="example"></a>例  
 次のコード例では、同じ幅にするには、各 rebar バンドを設定します。  
  
 [!code-cpp[NVC_MFC_CReBarCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]  
  
##  <a name="setbarinfo"></a>CReBarCtrl::SetBarInfo  
 Win32 メッセージの動作を実装[RB_SETBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774513)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
BOOL SetBarInfo(REBARINFO* prbi);
```  
  
### <a name="parameters"></a>パラメーター  
 `prbi`  
 ポインター、 [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395)を設定する情報を含む構造体。 設定する必要があります、`cbSize`この構造体のメンバー`sizeof(REBARINFO)`このメッセージを送信する前に  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CReBarCtrl&#14;](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]  
  
##  <a name="setbkcolor"></a>CReBarCtrl::SetBkColor  
 Win32 メッセージの動作を実装[RB_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774515)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
COLORREF SetBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>パラメーター  
 `clr`  
 **COLORREF**を新しい既定の背景色を表す値。  
  
### <a name="return-value"></a>戻り値  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)を前の既定の背景色を表す値。  
  
### <a name="remarks"></a>コメント  
 背景色を設定して、既定値を設定する方法の詳細については、このトピックを参照してください。  
  
##  <a name="setcolorscheme"></a>CReBarCtrl::SetColorScheme  
 Rebar コントロールのボタンの画面の配色を設定します。  
  
```  
void SetColorScheme(const COLORSCHEME* lpcs);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpcs`  
 ポインター、 [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502)構造、」の説明に従って、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 **COLORSCHEME**構造体には、ボタンの強調表示色とボタンの影の色の両方が含まれています。  
  
##  <a name="setextendedstyle"></a>CReBarCtrl::SetExtendedStyle  
 現在の rebar コントロールの拡張スタイルを設定します。  
  
```  
DWORD SetExtendedStyle(
    DWORD dwMask,   
    DWORD dwStyleEx);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `dwMask`|どのフラグを指定するフラグのビットごとの組み合わせ (OR)、`dwStyleEx`パラメーターを適用します。 次の値の&1; つ以上を使用します。<br /><br /> RBS_EX_SPLITTER: 既定では、分割ウィンドウ下部にある水平モードの場合と右側のモードで表示垂直方向です。<br /><br /> RBS_EX_TRANSPARENT: 転送、 [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055)メッセージを親ウィンドウにします。|  
|[入力] `dwStyleEx`|適用するスタイルを指定するフラグのビットごとの組み合わせ (OR)。 スタイルを設定するで使用されている同じフラグを指定、`dwMask`パラメーター。 スタイルをリセットするには、バイナリのゼロを指定します。|  
  
### <a name="return-value"></a>戻り値  
 以前の拡張スタイル。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [RB_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb774519)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="setimagelist"></a>CReBarCtrl::SetImageList  
 Rebar コントロールには、イメージ リストを割り当てます。  
  
```  
BOOL SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>パラメーター  
 `pImageList`  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md) rebar コントロールに割り当てられるイメージ リストを格納するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
##  <a name="setowner"></a>CReBarCtrl::SetOwner  
 Win32 メッセージの動作を実装[RB_SETPARENT](http://msdn.microsoft.com/library/windows/desktop/bb774522)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
CWnd* SetOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 ポインター、 `CWnd` rebar コントロールの所有者として設定するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CWnd](../../mfc/reference/cwnd-class.md) rebar コントロールの現在の所有者であるオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数へのポインターを使用して`CWnd`ウィンドウへのハンドルのではなく、rebar コントロールの現在および選択された所有者の両方のオブジェクトします。  
  
> [!NOTE]
>  このメンバー関数には、コントロールが作成されたときに設定した実際の親は変わりません。はなく、指定したウィンドウに通知メッセージを送信します。  
  
##  <a name="setpalette"></a>CReBarCtrl::SetPalette  
 Win32 メッセージの動作を実装[RB_SETPALETTE](http://msdn.microsoft.com/library/windows/desktop/bb774520)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
CPalette* SetPalette(HPALETTE hPal);
```  
  
### <a name="parameters"></a>パラメーター  
 *hPal*  
 `HPALETTE` Rebar コントロールで使用する新しいパレットを指定します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CPalette](../../mfc/reference/cpalette-class.md) rebar コントロールの前のパレットを指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用している、 `CPalette` 、戻り値としてオブジェクトではなく、`HPALETTE`です。  
  
##  <a name="settextcolor"></a>CReBarCtrl::SetTextColor  
 Win32 メッセージの動作を実装[RB_SETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774524)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
COLORREF SetTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>パラメーター  
 `clr`  
 A **COLORREF**を新しいテキストを表す値の色を`CReBarCtrl`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)前のテキストの色を表す値に関連付けられている、`CReBarCtrl`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 Rebar コントロールでテキストの色の柔軟性をサポートするために提供されます。  
  
##  <a name="settooltips"></a>CReBarCtrl::SetToolTips  
 Rebar コントロールでは、ツール ヒント コントロールを関連付けます。  
  
```  
void SetToolTips(CToolTipCtrl* pToolTip);
```  
  
### <a name="parameters"></a>パラメーター  
 *pToolTip*  
 ポインター、 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)オブジェクト  
  
### <a name="remarks"></a>コメント  
 破棄する必要があります、`CToolTipCtrl`オブジェクトの操作が終了します。  
  
##  <a name="setwindowtheme"></a>CReBarCtrl::SetWindowTheme  
 Rebar コントロールの表示スタイルを設定します。  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszSubAppName`  
 設定する rebar visual スタイルを含む Unicode 文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 戻り値は使用されません。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [RB_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb774530) 」の説明に従って、メッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="showband"></a>CReBarCtrl::ShowBand  
 Win32 メッセージの動作を実装[RB_SHOWBAND](http://msdn.microsoft.com/library/windows/desktop/bb774532)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
BOOL ShowBand(
    UINT uBand,  
    BOOL fShow = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `uBand`  
 Rebar コントロールのバンドの&0; から始まるインデックス。  
  
 *fShow*  
 バンドを表示するか非表示を示します。 この値は、する場合**TRUE**バンドが表示されます。 それ以外の場合は、帯域外は表示されません。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
##  <a name="sizetorect"></a>CReBarCtrl::SizeToRect  
 Win32 メッセージの動作を実装[RB_SIZETORECT](http://msdn.microsoft.com/library/windows/desktop/bb774534)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
```  
BOOL SizeToRect(CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 参照、 [CRect](../../atl-mfc-shared/reference/crect-class.md) rebar コントロールのサイズの四角形を指定するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用している、`CRect`オブジェクトをパラメーターとしてではなく、`RECT`構造体。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



