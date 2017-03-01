---
title: "CControlBar クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CControlBar
dev_langs:
- C++
helpviewer_keywords:
- CControlBar class
- OLE resize bars
- OLE resize bars, base class
- dialog bars, base class
- toolbars [C++], base class
- control bars [C++], base class
- status bars, base class
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
caps.latest.revision: 22
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
ms.openlocfilehash: 9720c4c11656834923c0e42a2017d51543c08f53
ms.lasthandoff: 02/24/2017

---
# <a name="ccontrolbar-class"></a>CControlBar Class
コントロール バー クラスの基本クラス[CStatusBar](../../mfc/reference/cstatusbar-class.md)、 [CToolBar](../../mfc/reference/ctoolbar-class.md)、 [CDialogBar](../../mfc/reference/cdialogbar-class.md)、 [CReBar](../../mfc/reference/crebar-class.md)、および[COleResizeBar](../../mfc/reference/coleresizebar-class.md)します。  
  
## <a name="syntax"></a>構文  
  
```  
class CControlBar : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CControlBar::CControlBar](#ccontrolbar)|`CControlBar` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CControlBar::CalcDynamicLayout](#calcdynamiclayout)|としてダイナミック コントロール バーのサイズを返す、 [CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトです。|  
|[CControlBar::CalcFixedLayout](#calcfixedlayout)|としてコントロール バーのサイズを返す、 [CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトです。|  
|[CControlBar::CalcInsideRect](#calcinsiderect)|境界線を含むコントロール バー領域の現在のディメンションを返します。|  
|[CControlBar::DoPaint](#dopaint)|コントロール バーの境界線およびグリップをレンダリングします。|  
|[CControlBar::DrawBorders](#drawborders)|コントロール バーの境界線をレンダリングします。|  
|[CControlBar::DrawGripper](#drawgripper)|コントロール バーのグリップをレンダリングします。|  
|[CControlBar::EnableDocking](#enabledocking)|コントロール バーをドッキングまたはフローティングできるようにします。|  
|[したとき](#getbarstyle)|コントロール バーのスタイル設定を取得します。|  
|[CControlBar::GetBorders](#getborders)|コントロール バーの境界線の値を取得します。|  
|[CControlBar::GetCount](#getcount)|非数を返す`HWND`コントロール バー内の要素。|  
|[CControlBar::GetDockingFrame](#getdockingframe)|コントロール バーがドッキングされるフレームへのポインターを返します。|  
|[CControlBar::IsFloating](#isfloating)|対象のコントロール バーがフローティング コントロール バーである場合に、ゼロ以外の値を返します。|  
|[CControlBar::OnUpdateCmdUI](#onupdatecmdui)|コマンド UI ハンドラーを呼び出します。|  
|[CControlBar::SetBarStyle](#setbarstyle)|コントロール バーのスタイル設定を変更します。|  
|[CControlBar::SetBorders](#setborders)|コントロール バーの境界線の値を設定します。|  
|[CControlBar::SetInPlaceOwner](#setinplaceowner)|コントロール バーのインプレース所有者を変更します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CControlBar::m_bAutoDelete](#m_bautodelete)|ゼロ以外の場合は、Windows のコントロール バーが破棄されると、`CControlBar` オブジェクトが削除されます。|  
|[CControlBar::m_pInPlaceOwner](#m_pinplaceowner)|コントロール バーのインプレース所有者です。|  
  
## <a name="remarks"></a>コメント  
 通常、コントロール バーは、フレーム ウィンドウの左側または右側にアラインされるウィンドウです。 いずれかである子項目を含めることが`HWND`ベースされる生成し、Windows メッセージまたは非対応であるコントロールの使用方法 - `HWND`-ベースで、windows ではなく、アプリケーション コードまたはフレームワーク コードにより管理されるアイテムです。 リスト ボックスやエディット コントロールの例を`HWND`- ベースのコントロールは、ステータス バー ペインやビットマップ ボタンが以外の - `HWND`-ベースのコントロールです。  
  
 通常、コントロール バーのウィンドウは親フレーム ウィンドウの子ウィンドウであり、通常はクライアント ビューまたはフレーム ウィンドウの MDI クライアントの兄弟です。 `CControlBar` オブジェクトは、親ウィンドウのクライアント領域の四角形に関する情報を使用して、それ自体を配置します。 次に、親ウィンドウのクライアント領域においてどの程度の未割り当て領域が残っているかについて、親ウィンドウに通知します。  
  
 `CControlBar` の詳細については、次を参照してください。  
  
- [コントロール バー](../../mfc/control-bars.md)  
  
- [テクニカル ノート 31: コントロール バー](../../mfc/tn031-control-bars.md)します。  
  
-   サポート技術情報の文書 Q242577「PRB: Update Command UI Handlers Do Not Work for Menu Attached to a Dialog Box」  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CControlBar`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="a-namecalcdynamiclayouta--ccontrolbarcalcdynamiclayout"></a><a name="calcdynamiclayout"></a>CControlBar::CalcDynamicLayout  
 フレームワークでは、動的なツールバーのサイズを計算するには、このメンバー関数を呼び出します。  
  
```  
virtual CSize CalcDynamicLayout(
    int nLength,  
    DWORD nMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nLength`  
 コントロール バー、に応じて、縦線または横線の要求されたディメンション`dwMode`します。  
  
 `nMode`  
 次の定義済みフラグを使用して、ダイナミック コントロール バーの幅と高さを決定します。 ビットごとの OR (|) 演算子を使用して、フラグを結合します。  
  
|レイアウト モード フラグ|その意味|  
|-----------------------|-------------------|  
|`LM_STRETCH`|コントロール バーをフレームのサイズを拡大するかどうかを示します。 バーがドッキング バー (ドッキングは使用できません) ではない場合に設定します。 設定されていない、バーがドッキングまたはフローティング (ドッキングの使用可能)。 場合設定すると、`LM_STRETCH`は無視されます`nLength`に基づいてディメンションを取得し、`LM_HORZ`状態です。 `LM_STRETCH`同じように動作、`bStretch`で使用されるパラメーター [CalcFixedLayout](#calcfixedlayout); 伸縮と方向のリレーションシップの詳細については、メンバー関数を参照してください。|  
|`LM_HORZ`|バーが水平方向または垂直方向であることを示します。 バーが水平方向および垂直方向に配置している場合が設定されていない場合に設定します。 `LM_HORZ`同じように動作、`bHorz`で使用されるパラメーター [CalcFixedLayout](#calcfixedlayout); 伸縮と方向のリレーションシップの詳細については、メンバー関数を参照してください。|  
|**LM_MRUWIDTH**|最近使った動的の幅。 無視`nLength`幅が最近使ったパラメーターと、記憶されている使用します。|  
|`LM_HORZDOCK`|水平方向には、ディメンションがドッキングされています。 無視`nLength`パラメーターを最大幅で動的なサイズを返します。|  
|`LM_VERTDOCK`|垂直方向には、ディメンションがドッキングされています。 無視`nLength`パラメーターと高さの最大値と動的なサイズを返します。|  
|`LM_LENGTHY`|場合は、設定`nLength`幅ではなく高さ (Y 方向) を示します。|  
|`LM_COMMIT`|リセット**LM_MRUWIDTH**フローティング コントロール バーの現在の幅にします。|  
  
### <a name="return-value"></a>戻り値  
 コントロール バーのサイズをピクセル単位での[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 派生したクラスで、独自の動的なレイアウトを提供するには、この関数をオーバーライド`CControlBar`します。 派生した MFC クラス`CControlBar`など[CToolbar](../../mfc/reference/ctoolbar-class.md)、このメンバー関数をオーバーライドし、独自の実装を提供します。  
  
##  <a name="a-namecalcfixedlayouta--ccontrolbarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CControlBar::CalcFixedLayout  
 コントロール バーの水平方向のサイズを計算するには、このメンバー関数を呼び出します。  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>パラメーター  
 `bStretch`  
 フレームのサイズをバーを拡大するかどうかを示します。 `bStretch`パラメーターは 0 以外のバー ドッキング バー (ドッキングは使用できません) ではないありが 0 ドッキングまたはフローティングにあるとき (ドッキングの使用可能)。  
  
 `bHorz`  
 バーが水平方向または垂直方向であることを示します。 `bHorz`場合は、バーが水平方向および垂直方向である場合は 0、パラメーターが 0 以外の値。  
  
### <a name="return-value"></a>戻り値  
 コントロール バーのサイズをピクセル単位での`CSize`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 ツールバーなどのコントロール バーが水平方向に拡張するか、垂直方向にボタンに合わせて、コントロール バーに含まれています。  
  
 場合`bStretch`は**TRUE**、に沿って、印刷の向きによって提供されるディメンションをストレッチ`bHorz`します。 つまり場合、`bHorz`は**FALSE**、コントロール バーは垂直方向に拡大されます。 場合`bStretch`は**FALSE**stretch が行われません。 次の表は、の可能な順列と結果のコントロール バー スタイルを示しています。`bStretch`と`bHorz`です。  
  
|bStretch|bHorz|拡大|[方向]|ドッキング/未ドッキング|  
|--------------|-----------|----------------|-----------------|--------------------------|  
|**TRUE**|**TRUE**|水平方向の拡大|横方向に配置|非ドッキング|  
|**TRUE**|**FALSE**|垂直方向の拡大|垂直方向|非ドッキング|  
|**FALSE**|**TRUE**|伸縮しません。|横方向に配置|ドッキング|  
|**FALSE**|**FALSE**|伸縮しません。|垂直方向|ドッキング|  
  
##  <a name="a-namecalcinsiderecta--ccontrolbarcalcinsiderect"></a><a name="calcinsiderect"></a>CControlBar::CalcInsideRect  
 フレームワークでは、コントロール バーのクライアント領域を計算するには、この関数を呼び出します。  
  
```  
virtual void CalcInsideRect(
    CRect& rect,  
    BOOL bHorz) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 コントロール バーの現在のディメンションが含まれています罫線を含みます。  
  
 `bHorz`  
 バーが水平方向または垂直方向であることを示します。 `bHorz`場合は、バーが水平方向および垂直方向である場合は 0、パラメーターが 0 以外の値。  
  
### <a name="remarks"></a>コメント  
 コントロール バーが描画前に、この関数が呼び出されます。  
  
 コントロール バーのグリッパー バー、罫線の描画をカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="a-nameccontrolbara--ccontrolbarccontrolbar"></a><a name="ccontrolbar"></a>CControlBar::CControlBar  
 `CControlBar` オブジェクトを構築します。  
  
```  
CControlBar();
```  
  
##  <a name="a-namedopainta--ccontrolbardopaint"></a><a name="dopaint"></a>CControlBar::DoPaint  
 枠線とコントロール バーのグリッパー バーを表示するためにフレームワークによって呼び出されます。  
  
```  
virtual void DoPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 境界線およびコントロール バーのグリップを表示するために使用するデバイス コンテキストへのポインター。  
  
### <a name="remarks"></a>コメント  
 コントロール バーの描画の動作をカスタマイズするには、この関数をオーバーライドします。  
  
 他のカスタマイズ方法は、オーバーライドする、`DrawBorders`と`DrawGripper`機能し、境界線およびグリップのカスタムの描画コードを追加します。 既定では、これらのメソッドが呼び出されるため`DoPaint`メソッドをオーバーライドした関数`DoPaint`は必要ありません。  
  
##  <a name="a-namedrawbordersa--ccontrolbardrawborders"></a><a name="drawborders"></a>CControlBar::DrawBorders  
 コントロール バーの境界線をレンダリングするためにフレームワークによって呼び出されます。  
  
```  
virtual void DrawBorders(
    CDC* pDC,  
    CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 コントロール バーの境界線の描画に使用されるデバイス コンテキストへのポインター。  
  
 `rect`  
 A`CRect`コントロール バーのサイズを格納するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 コントロール バーの境界線の外観をカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="a-namedrawgrippera--ccontrolbardrawgripper"></a><a name="drawgripper"></a>CControlBar::DrawGripper  
 コントロール バーのグリップをレンダリングするためにフレームワークによって呼び出されます。  
  
```  
virtual void DrawGripper(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 コントロール バーのグリップを表示するために使用されるデバイス コンテキストへのポインター。  
  
 `rect`  
 A`CRect`コントロール バーのグリップのディメンションを含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 コントロール バーのグリップの外観をカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="a-nameenabledockinga--ccontrolbarenabledocking"></a><a name="enabledocking"></a>CControlBar::EnableDocking  
 ドッキング コントロール バーを有効にするには、この関数を呼び出します。  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDockStyle`  
 サポートされている場合は、コントロール バーがドッキングをサポートするかどうかとするコントロール バーをドッキングできる、親ウィンドウの辺を指定します。 次の&1; つ以上を指定できます。  
  
- `CBRS_ALIGN_TOP`により、クライアント領域の上部にドッキングできます。  
  
- `CBRS_ALIGN_BOTTOM`により、クライアント領域の下部にドッキングできます。  
  
- `CBRS_ALIGN_LEFT`により、クライアント領域の左側にドッキングできます。  
  
- `CBRS_ALIGN_RIGHT`により、クライアント領域の右側にドッキングできます。  
  
- `CBRS_ALIGN_ANY`により、クライアント領域の任意の辺にドッキングできます。  
  
- `CBRS_FLOAT_MULTI`複数のコントロール バーを配置できる単一のミニフレーム ウィンドウを使用します。  
  
 0 の場合 (つまり、いないことを示すフラグ)、コントロール バーがドッキングされません。  
  
### <a name="remarks"></a>コメント  
 指定した辺で、移行先のフレーム ウィンドウにドッキングできる辺の&1; つと一致する必要がありますかそのフレーム ウィンドウに、コントロール バーを固定できません。  
  
##  <a name="a-namegetbarstylea--ccontrolbargetbarstyle"></a><a name="getbarstyle"></a>したとき  
 決定するためには、この関数を呼び出す**cbrs _** (コントロール バーのスタイル) の設定は、コントロール バーに現在設定されています。  
  
```  
DWORD GetBarStyle();
```  
  
### <a name="return-value"></a>戻り値  
 現在**cbrs _**コントロール バーの (コントロール バーのスタイル) 設定します。 参照してください[CControlBar::SetBarStyle](#setbarstyle)利用可能なスタイルの完全な一覧です。  
  
### <a name="remarks"></a>コメント  
 処理されない**ws _** (ウィンドウ スタイル) のスタイル。  
  
##  <a name="a-namegetbordersa--ccontrolbargetborders"></a><a name="getborders"></a>CControlBar::GetBorders  
 コントロール バーの現在の境界線の値を返します。  
  
```  
CRect GetBorders() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`CRect`コントロール バー オブジェクトの各辺のピクセル単位で現在の幅を格納しているオブジェクト。 値など、 `left` 、メンバーの[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクト、左の境界線の幅は、です。  
  
##  <a name="a-namegetcounta--ccontrolbargetcount"></a><a name="getcount"></a>CControlBar::GetCount  
 以外の数を返します`HWND`上のアイコン、`CControlBar`オブジェクトです。  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 非数`HWND`上のアイコン、`CControlBar`オブジェクトです。 この関数に 0 を返します、 [CDialogBar](../../mfc/reference/cdialogbar-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 項目の種類は、派生オブジェクトによって異なります。 ペインについて[CStatusBar](../../mfc/reference/cstatusbar-class.md)オブジェクト、およびボタンおよび区切り記号の[CToolBar](../../mfc/reference/ctoolbar-class.md)オブジェクトです。  
  
##  <a name="a-namegetdockingframea--ccontrolbargetdockingframe"></a><a name="getdockingframe"></a>CControlBar::GetDockingFrame  
 このメンバー関数を呼び出して、コントロール バーがドッキングされている現在のフレーム ウィンドウへのポインターを取得します。  
  
```  
CFrameWnd* GetDockingFrame() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、フレーム ウィンドウへのポインターそれ以外の場合**NULL**します。  
  
 場合 (つまり、コントロール バーが固定されていない) 場合、コントロール バーは、フレーム ウィンドウにドッキングされず、この関数は、親へのポインターを返します[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)します。  
  
### <a name="remarks"></a>コメント  
 ドッキング可能なコントロール バーの詳細については、次を参照してください。 [CControlBar::EnableDocking](#enabledocking)と[CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar)します。  
  
##  <a name="a-nameisfloatinga--ccontrolbarisfloating"></a><a name="isfloating"></a>CControlBar::IsFloating  
 このメンバー関数を呼び出して、コントロール バーがフローティングかドッキングかどうかを確認します。  
  
```  
BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロール バーが固定されていない場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 浮動小数点へのドッキング コントロール バーの状態を変更するを呼び出す[切り離すには](../../mfc/reference/cframewnd-class.md#floatcontrolbar)です。  
  
##  <a name="a-namembautodeletea--ccontrolbarmbautodelete"></a><a name="m_bautodelete"></a>CControlBar::m_bAutoDelete  
 ゼロ以外の場合は、Windows のコントロール バーが破棄されると、`CControlBar` オブジェクトが削除されます。  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>コメント  
 `m_bAutoDelete`型のパブリック変数**BOOL**します。  
  
 コントロール バー オブジェクトは通常、フレーム ウィンドウ オブジェクトに埋め込まれます。 この場合、 `m_bAutoDelete` 0 は、フレーム ウィンドウが破棄されるときに、埋め込まれたコントロール バー オブジェクトが破棄されるためです。  
  
 割り当てる場合、この変数を&0; 以外の値に設定、`CControlBar`ヒープでオブジェクトを呼び出すしない**削除**します。  
  
##  <a name="a-namempinplaceownera--ccontrolbarmpinplaceowner"></a><a name="m_pinplaceowner"></a>CControlBar::m_pInPlaceOwner  
 コントロール バーのインプレース所有者です。  
  
```  
CWnd* m_pInPlaceOwner;  
```  
  
##  <a name="a-nameonupdatecmduia--ccontrolbaronupdatecmdui"></a><a name="onupdatecmdui"></a>CControlBar::OnUpdateCmdUI  
 このメンバー関数は、ツールバーやステータス バーの状態を更新するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pTarget`  
 アプリケーションのメイン フレーム ウィンドウへのポインター。 このポインターは、更新プログラムのメッセージのルーティングに使用されます。  
  
 `bDisableIfNoHndler`  
 更新ハンドラーを持たないコントロールが無効として自動的に表示されるかどうかを示すフラグです。  
  
### <a name="remarks"></a>コメント  
 更新するには、各ボタンまたはペインを使用して、`ON_UPDATE_COMMAND_UI`更新ハンドラーを適切に設定する、メッセージ マップにマクロです。 参照してください[ON_UPDATE_COMMAND_UI](http://msdn.microsoft.com/library/c4de3c21-2d2e-4b89-a4ce-d0c0e2d9edc4)詳細については、このマクロを使用します。  
  
 `OnUpdateCmdUI`アプリケーションがアイドル状態のときに、フレームワークによって呼び出されます。 フレーム ウィンドウを更新する必要がありますできない子ウィンドウでは、直接には、少なくとも、表示されるフレーム ウィンドウの。 `OnUpdateCmdUI`高度なオーバーライドします。  
  
##  <a name="a-namesetbarstylea--ccontrolbarsetbarstyle"></a><a name="setbarstyle"></a>CControlBar::SetBarStyle  
 この関数を呼び出して、必要な設定**cbrs _**コントロール バーのスタイル。  
  
```  
void SetBarStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 コントロール バーのスタイルを指定します。 次の&1; つ以上を指定できます。  
  
- `CBRS_ALIGN_TOP`フレーム ウィンドウのクライアント領域の上部にドッキングするコントロール バーをできるようにします。  
  
- `CBRS_ALIGN_BOTTOM`フレーム ウィンドウのクライアント領域の下部にドッキング コントロール バーを使用します。  
  
- `CBRS_ALIGN_LEFT`フレーム ウィンドウのクライアント領域の左側にドッキング コントロール バーを使用します。  
  
- `CBRS_ALIGN_RIGHT`フレーム ウィンドウのクライアント領域の右側にドッキング コントロール バーを使用します。  
  
- `CBRS_ALIGN_ANY`フレーム ウィンドウのクライアント領域の任意の辺にドッキング コントロール バーを使用します。  
  
- `CBRS_BORDER_TOP`表示されるときに、コントロール バーの上端に描画される境界線をさせます。  
  
- `CBRS_BORDER_BOTTOM`表示されるときに、コントロール バーの一番下に描画される境界線をさせます。  
  
- `CBRS_BORDER_LEFT`表示されるときに、コントロール バーの左端に描画される境界線をさせます。  
  
- `CBRS_BORDER_RIGHT`表示されるときに、コントロール バーの右端に描画される境界線をさせます。  
  
- `CBRS_FLOAT_MULTI`複数のコントロール バーを配置できる単一のミニフレーム ウィンドウを使用します。  
  
- `CBRS_TOOLTIPS`コントロール バーに表示されるツール ヒントが発生します。  
  
- `CBRS_FLYBY`ツール ヒントと同時に更新するメッセージ テキスト。  
  
- **CBRS_GRIPPER**グリッパー、バンドで使用されるような原因、 **CReBar**オブジェクトのいずれかを描画する`CControlBar`-クラスを派生します。  
  
### <a name="remarks"></a>コメント  
 影響しません、 **ws _** (ウィンドウ スタイル) 設定します。  
  
##  <a name="a-namesetbordersa--ccontrolbarsetborders"></a><a name="setborders"></a>CControlBar::SetBorders  
 コントロール バーの境界線のサイズを設定するには、この関数を呼び出します。  
  
```  
void SetBorders(
    int cxLeft = 0,  
    int cyTop = 0,  
    int cxRight = 0,  
    int cyBottom = 0);  
  
void SetBorders(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 *cxLeft*  
 コントロール バーの左罫線の幅をピクセル単位で。  
  
 *cyTop*  
 コントロール バーの上枠線の高さをピクセル単位で。  
  
 *cxRight*  
 コントロール バーの右罫線の幅をピクセル単位で。  
  
 *cyBottom*  
 コントロール バーの下の境界線の高さをピクセル単位で。  
  
 `lpRect`  
 ポインター、 [CRect](../../atl-mfc-shared/reference/crect-class.md)各オブジェクトの枠線、コントロール バーの現在の幅をピクセル単位で格納しているオブジェクト。  
  
### <a name="example"></a>例  
 次のコード例は、2 ピクセルを 5 ピクセルにコントロール バーの上端と下端の枠線と左と右の枠線を設定します。  
  
 [!code-cpp[NVC_MFCControlLadenDialog&#61;](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]  
  
##  <a name="a-namesetinplaceownera--ccontrolbarsetinplaceowner"></a><a name="setinplaceowner"></a>CControlBar::SetInPlaceOwner  
 コントロール バーのインプレース所有者を変更します。  
  
```  
void SetInPlaceOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 ポインター、`CWnd`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CTRLBARS](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CToolBar クラス](../../mfc/reference/ctoolbar-class.md)   
 [CDialogBar クラス](../../mfc/reference/cdialogbar-class.md)   
 [CStatusBar クラス](../../mfc/reference/cstatusbar-class.md)   
 [CReBar クラス](../../mfc/reference/crebar-class.md)

