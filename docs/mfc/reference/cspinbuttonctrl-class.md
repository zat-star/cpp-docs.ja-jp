---
title: "CSpinButtonCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSpinButtonCtrl
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [C++], CSpinButtonCtrl
- CSpinButtonCtrl class
- CSpinButtonCtrl class, common controls
- up-down controls, spin button control
- spin button control
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
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
ms.openlocfilehash: 486a0842ed04f0e760bbb332986a97a35ce9851f
ms.lasthandoff: 02/24/2017

---
# <a name="cspinbuttonctrl-class"></a>CSpinButtonCtrl クラス
Windows コモン スピン ボタン コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CSpinButtonCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSpinButtonCtrl::CSpinButtonCtrl](#cspinbuttonctrl)|`CSpinButtonCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSpinButtonCtrl::Create](#create)|スピン ボタン コントロールを作成し、それをアタッチ、`CSpinButtonCtrl`オブジェクトです。|  
|[CSpinButtonCtrl::CreateEx](#createex)|指定した Windows 拡張スタイルを使用してスピン ボタン コントロールを作成し、それにアタッチ、`CSpinButtonCtrl`オブジェクトです。|  
|[CSpinButtonCtrl::GetAccel](#getaccel)|スピン ボタン コントロールのアクセラレーション情報を取得します。|  
|[CSpinButtonCtrl::GetBase](#getbase)|スピン ボタン コントロールの現在の基数を取得します。|  
|[CSpinButtonCtrl::GetBuddy](#getbuddy)|現在の関連ウィンドウへのポインターを取得します。|  
|[CSpinButtonCtrl::GetPos](#getpos)|スピン ボタン コントロールの現在位置を取得します。|  
|[CSpinButtonCtrl::GetRange](#getrange)|スピン ボタン コントロールの上限と下限制限 (範囲) を取得します。|  
|[CSpinButtonCtrl::SetAccel](#setaccel)|スピン ボタン コントロール用のアクセラレータを設定します。|  
|[CSpinButtonCtrl::SetBase](#setbase)|スピン ボタン コントロールの基本クラスを設定します。|  
|[CSpinButtonCtrl::SetBuddy](#setbuddy)|スピン ボタン コントロールを関連ウィンドウを設定します。|  
|[CSpinButtonCtrl::SetPos](#setpos)|コントロールの現在の位置を設定します。|  
|[上限値と下限](#setrange)|スピン ボタン コントロールの上限と下限制限 (範囲) を設定します。|  
  
## <a name="remarks"></a>コメント  
 「スピン ボタン コントロール」(アップダウン コントロールとも呼ばれます) は、スクロール位置または横にあるコントロールに表示される番号などの値を増減するにはユーザーがクリックされる下矢印ボタンのペアです。 スピン ボタン コントロールに関連付けられている値には、現在の位置が呼び出されます。 スピン ボタン コントロールが「関連ウィンドウ」と呼ばれる、横にあるコントロールで使用されるほとんどの場合  
  
 このコントロール (つまり、`CSpinButtonCtrl`クラス) は以降、Windows 95/98 および Windows NT version 3.51 で実行するプログラムにのみ使用できます。  
  
 スピン ボタン コントロールとその関連ウィンドウは、ユーザーに、多くの場合、1 つのコントロールのようになります。 あるスピン ボタン コントロールを自動的に配置自体の関連ウィンドウの横にあること、および自動的に設定関連ウィンドウのキャプションを現在の位置を指定できます。 エディット コントロールにスピン ボタン コントロールを使用するには、ユーザーに数値の入力を要求します。  
  
 に向かって、最大文字数は現在の位置を移動上矢印をクリックし、最小値には、現在の位置を移動下向きの矢印をクリックします。 既定では、最小値は 100 と最大値は 0 です。 最小値の設定は最大値 (たとえば、ときに、既定の設定が使用されます) を設定し、上向きの矢印がクリックするといつでも位置の値と下向きの矢印をクリックすると増大にします。  
  
 関連ウィンドウを持たないスピン ボタン コントロールは、簡略化されたスクロール バーの一種として機能します。 たとえば、タブ コントロールには、スピン ボタン コントロールを追加のタブをスクロールして表示するユーザーを有効にすることもありますが表示されます。  
  
 使用する方法について`CSpinButtonCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSpinButtonCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="a-namecreatea--cspinbuttonctrlcreate"></a><a name="create"></a>CSpinButtonCtrl::Create  
 スピン ボタン コントロールを作成し、それをアタッチ、`CSpinButtonCtrl`オブジェクト.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 スピン ボタン コントロールのスタイルを指定します。 スピン ボタン コントロールのスタイルの任意の組み合わせをコントロールに適用されます。 これらのスタイルは「[アップ ダウン コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb759885)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `rect`  
 スピン ボタン コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体  
  
 `pParentWnd`  
 スピン ボタン コントロールの親ウィンドウを通常へのポインター、`CDialog`です。 ことはできません**NULL です。**  
  
 `nID`  
 スピン ボタン コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、`CSpinButtonCtrl`まずオブジェクトの&2; つの手順で、コンス トラクターを呼び出して、呼び出す**作成**、スピン ボタン コントロールを作成およびそれにアタッチする、`CSpinButtonCtrl`オブジェクトです。  
  
 拡張ウィンドウ スタイルを使用して、スピン ボタン コントロールを作成するには、呼び出す[CSpinButtonCtrl::CreateEx](#createex)の代わりに**作成**します。  
  
##  <a name="a-namecreateexa--cspinbuttonctrlcreateex"></a><a name="createex"></a>CSpinButtonCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成し、関連付けます、`CSpinButtonCtrl`オブジェクトです。  
  
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
 スピン ボタン コントロールのスタイルを指定します。 スピン ボタン コントロールのスタイルの任意の組み合わせをコントロールに適用されます。 これらのスタイルは「[アップ ダウン コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb759885)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
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
  
##  <a name="a-namecspinbuttonctrla--cspinbuttonctrlcspinbuttonctrl"></a><a name="cspinbuttonctrl"></a>CSpinButtonCtrl::CSpinButtonCtrl  
 `CSpinButtonCtrl` オブジェクトを構築します。  
  
```  
CSpinButtonCtrl();
```  
  
##  <a name="a-namegetaccela--cspinbuttonctrlgetaccel"></a><a name="getaccel"></a>CSpinButtonCtrl::GetAccel  
 スピン ボタン コントロールのアクセラレーション情報を取得します。  
  
```  
UINT GetAccel(
    int nAccel,  
    UDACCEL* pAccel) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nAccel`  
 指定された配列の要素数`pAccel`します。  
  
 `pAccel`  
 配列を指すポインター [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897)アクセラレーション情報を受け取る構造体。  
  
### <a name="return-value"></a>戻り値  
 アクセラレータの構造体の数を取得します。  
  
##  <a name="a-namegetbasea--cspinbuttonctrlgetbase"></a><a name="getbase"></a>CSpinButtonCtrl::GetBase  
 スピン ボタン コントロールの現在の基数を取得します。  
  
```  
UINT GetBase() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の基本値。  
  
##  <a name="a-namegetbuddya--cspinbuttonctrlgetbuddy"></a><a name="getbuddy"></a>CSpinButtonCtrl::GetBuddy  
 現在の関連ウィンドウへのポインターを取得します。  
  
```  
CWnd* GetBuddy() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の関連ウィンドウへのポインター。  
  
##  <a name="a-namegetposa--cspinbuttonctrlgetpos"></a><a name="getpos"></a>CSpinButtonCtrl::GetPos  
 スピン ボタン コントロールの現在位置を取得します。  
  
```  
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;  ```  
  
### Parameters  
 *lpbError*  
 A pointer to a boolean value that is set to zero if the value is successfully retrieved or non-zero if an error occurs. If this parameter is set to **NULL**, errors are not reported.  
  
### Return Value  
 The first version returns the 16-bit current position in the low-order word. The high-order word is nonzero if an error occurred.  
  
 The second version returns the 32-bit position.  
  
### Remarks  
 When it processes the value returned, the control updates its current position based on the caption of the buddy window. The control returns an error if there is no buddy window or if the caption specifies an invalid or out-of-range value.  
  
##  <a name="getrange"></a>  CSpinButtonCtrl::GetRange  
 Retrieves the upper and lower limits (range) for a spin button control.  
  
```  
DWORD GetRange() const です。  
  
(int >/documents/report1.rdl」の下、GetRange を無効にします。  
    int >/documents/report1.rdl」の上限) const です。  
  
GetRange32 を無効にする (int >/documents/report1.rdl」の下で、  
    int >/documents/report1.rdl」の上限) const です。  
```  
  
### Parameters  
 *lower*  
 Reference to an integer that receives the lower limit for the control.  
  
 *upper*  
 Reference to an integer that receives the upper limit for the control.  
  
### Return Value  
 The first version returns a 32-bit value containing the upper and lower limits. The low-order word is the upper limit for the control, and the high-order word is the lower limit.  
  
### Remarks  
 The member function `GetRange32` retrieves the spin button control's range as a 32-bit integer.  
  
##  <a name="setaccel"></a>  CSpinButtonCtrl::SetAccel  
 Sets the acceleration for a spin button control.  
  
```  
BOOL SetAccel (int nAccel、  
    UDACCEL* pAccel) です。
```  
  
### Parameters  
 `nAccel`  
 Number of [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897) structures specified by `pAccel`.  
  
 `pAccel`  
 Pointer to an array of `UDACCEL` structures, which contain acceleration information. Elements should be sorted in ascending order based on the **nSec** member.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
##  <a name="setbase"></a>  CSpinButtonCtrl::SetBase  
 Sets the base for a spin button control.  
  
```  
int SetBase (int nBase) です。
```  
  
### Parameters  
 `nBase`  
 New base value for the control. It can be 10 for decimal or 16 for hexadecimal.  
  
### Return Value  
 The previous base value if successful, or zero if an invalid base is given.  
  
### Remarks  
 The base value determines whether the buddy window displays numbers in decimal or hexadecimal digits. Hexadecimal numbers are always unsigned; decimal numbers are signed.  
  
##  <a name="setbuddy"></a>  CSpinButtonCtrl::SetBuddy  
 Sets the buddy window for a spin button control.  
  
```  
CWnd* SetBuddy (CWnd* pWndBuddy) です。
```  
  
### Parameters  
 `pWndBuddy`  
 Pointer to the new buddy window.  
  
### Return Value  
 A pointer to the previous buddy window.  
  
### Remarks  
 A spin control is almost always associated with another window, such as an edit control, that displays some content. This other window is called the "buddy" of the spin control.  
  
##  <a name="setpos"></a>  CSpinButtonCtrl::SetPos  
 Sets the current position for a spin button control.  
  
```  
int SetPos (int nPos) です。  
int SetPos32(int nPos) です。
```  
  
### Parameters  
 `nPos`  
 New position for the control. This value must be in the range specified by the upper and lower limits for the control.  
  
### Return Value  
 The previous position (16-bit precision for `SetPos`, 32-bit precision for `SetPos32`).  
  
### Remarks  
 `SetPos32` sets the 32-bit position.  
  
##  <a name="setrange"></a>  CSpinButtonCtrl::SetRange  
 Sets the upper and lower limits (range) for a spin button control.  
  
```  
SetRange (短い上限値を無効にします。  
    短い下限) です。

 
SetRange32 を無効にする (int 上限値、  
    int 下限) です。
```  
  
### Parameters  
 `nLower`and `nUpper`  
 Upper and lower limits for the control. For `SetRange`, neither limit can be greater than **UD_MAXVAL** or less than **UD_MINVAL**; in addition, the difference between the two limits cannot exceed **UD_MAXVAL**. `SetRange32` places no restrictions on the limits; use any integers.  
  
### Remarks  
 The member function `SetRange32` sets the 32-bit range for the spin button control.  
  
> [!NOTE]
>  The default range for the spin button has the maximum set to zero (0) and the minimum set to 100. Because the maximum value is less than the minimum value, clicking the up arrow will decrease the position and clicking the down arrow will increase it. Use `CSpinButtonCtrl::SetRange` to adjust these values.  
  
## See Also  
 [MFC Sample CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd Class](../../mfc/reference/cwnd-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [CSliderCtrl Class](../../mfc/reference/csliderctrl-class.md)

