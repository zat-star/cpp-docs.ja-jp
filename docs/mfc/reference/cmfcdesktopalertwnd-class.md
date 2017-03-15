---
title: "CMFCDesktopAlertWnd クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWnd
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWnd class
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
caps.latest.revision: 33
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
ms.openlocfilehash: be9d81ffff003119aa7ff9e0cd100c575bd82d36
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd Class
`CMFCDesktopAlertWnd`クラスは、イベントについてユーザーに通知する画面に表示されるモードレス ダイアログ ボックスの機能を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCDesktopAlertWnd : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCDesktopAlertWnd::Create](#create)|作成して、デスクトップ通知ウィンドウを初期化します。|  
|[CMFCDesktopAlertWnd::GetAnimationSpeed](#getanimationspeed)|アニメーションの速度を返します。|  
|[CMFCDesktopAlertWnd::GetAnimationType](#getanimationtype)|アニメーションの種類を返します。|  
|[CMFCDesktopAlertWnd::GetAutoCloseTime](#getautoclosetime)|自動終了のタイムアウトを取得します。|  
|[CMFCDesktopAlertWnd::GetCaptionHeight](#getcaptionheight)|キャプションの高さを返します。|  
|[CMFCDesktopAlertWnd::GetDialogSize](#getdialogsize)||  
|[CMFCDesktopAlertWnd::GetLastPos](#getlastpos)|画面上のデスクトップ通知ウィンドウの最後の有効な位置を返します。|  
|[CMFCDesktopAlertWnd::GetTransparency](#gettransparency)|透過性レベルを返します。|  
|[CMFCDesktopAlertWnd::HasSmallCaption](#hassmallcaption)|デスクトップ通知ウィンドウが小規模のキャプションで表示されるかどうかを決定します。|  
|[CMFCDesktopAlertWnd::OnBeforeShow](#onbeforeshow)||  
|[CMFCDesktopAlertWnd::OnClickLinkButton](#onclicklinkbutton)|ユーザーがデスクトップの通知 メニューにあるリンク ボタンをクリックしたときに、フレームワークによって呼び出されます。|  
|[CMFCDesktopAlertWnd::OnCommand](#oncommand)|フレームワークは、ユーザーは、子コントロールは、通知メッセージを送信するとき、またはアクセラレータのキーストロークを変換するとき、メニューから項目を選択すると、このメンバー関数を呼び出します。 (上書き[CWnd::OnCommand](../../mfc/reference/cwnd-class.md#oncommand))。|  
|[CMFCDesktopAlertWnd::OnDraw](#ondraw)||  
|[CMFCDesktopAlertWnd::ProcessCommand](#processcommand)||  
|[CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed)|新しいアニメーションの速度を設定します。|  
|[CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype)|アニメーションの種類を設定します。|  
|[CMFCDesktopAlertWnd::SetAutoCloseTime](#setautoclosetime)|自動終了のタイムアウトを設定します。|  
|[CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)|小さく、通常キャプションとを切り替えます。|  
|[CMFCDesktopAlertWnd::SetTransparency](#settransparency)|透過性レベルを設定します。|  
  
## <a name="remarks"></a>コメント  
 デスクトップ通知ウィンドウを透明にすることができます、アニメーション効果が表示されます (指定された時間が経過したらまたは閉じるボタンをクリックして、ユーザーが破棄時に) を非表示にします。  
  
 デスクトップ通知ウィンドウをアイコン、メッセージ テキスト (ラベル)、およびリンクを含む既定のダイアログ ボックスを含めることもできます。 または、デスクトップ通知ウィンドウには、アプリケーションのリソースからのカスタム ダイアログ ボックスを含めることができます。  
  
 デスクトップ通知ウィンドウは、2 つの手順で作成します。 最初に、構築するコンス トラクターを呼び出し、`CMFCDesktopAlertWnd`オブジェクトです。 次を呼び出す、 [CMFCDesktopAlertWnd::Create](#create)ウィンドウを作成し、適用するメンバー関数を`CMFCDesktopAlertWnd`オブジェクトです。  
  
 `CMFCDesktopAlertWnd`オブジェクトがデスクトップ通知ウィンドウのクライアント領域の値を格納する特殊な子のダイアログ ボックスを作成します。 ダイアログ ボックスでは、それに位置しているすべてのコントロールを所有します。  
  
 ポップアップ ウィンドウにカスタム ダイアログ ボックスを表示するのには、次の手順を実行します。  
  
1.  `CMFCDesktopAlertDialog` の派生クラスを作成します。  
  
2.  リソースには、子のダイアログ ボックス テンプレートを作成します。  
  
3.  呼び出す[CMFCDesktopAlertWnd::Create](#create)  ダイアログ ボックスのテンプレートと、派生クラスのランタイム クラス情報へのポインターのリソース ID を使用します。  
  
4.  ホストされるコントロールからすべての通知を処理するカスタム ダイアログ ボックスをプログラムするか、これらの通知を直接処理するホストされるコントロールをプログラムします。  
  
 デスクトップ通知ウィンドウの動作を制御するのにには、次の関数を使用します。  
  
-   アニメーションの種類を呼び出すことによって設定[CMFCDesktopAlertWnd::SetAnimationType](#setanimationtype)します。 有効なオプションは、展開、スライド、およびフェードインします。  
  
-   アニメーション フレームの速度を呼び出すことによって設定[CMFCDesktopAlertWnd::SetAnimationSpeed](#setanimationspeed)します。  
  
-   呼び出すことによって、透過性レベルを設定[CMFCDesktopAlertWnd::SetTransparency](#settransparency)します。  
  
-   呼び出してから小のキャプションのサイズを変更[CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)します。 小さいキャプションは、高さは 7 ピクセルです。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCDesktopAlertWnd`を構成するクラス、`CMFCDesktopAlertWnd`オブジェクトです。 この例では、アニメーションの種類を設定し、ポップアップ ウィンドウの透明度を設定し、通知ウィンドウに表示する小さいキャプション設定通知ウィンドウが自動的に閉じるまでの経過時間を設定する方法を示します。 この例では、作成してデスクトップ通知ウィンドウを初期化する方法も示します。 このコード スニペットの一部である、[デスクトップ アラート デモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo&#1;](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxDesktopAlertWnd.h  
  
##  <a name="a-namecreatea--cmfcdesktopalertwndcreate"></a><a name="create"></a>CMFCDesktopAlertWnd::Create  
 作成して、デスクトップ通知ウィンドウを初期化します。  
  
```  
virtual BOOL Create(
    CWnd* pWndOwner,  
    UINT uiDlgResID,  
    HMENU hMenu = NULL,  
    CPoint ptPos = CPoint(-1,-1),  
    CRuntimeClass* pRTIDlgBar = RUNTIME_CLASS(CMFCDesktopAlertDialog));

 
virtual BOOL Create(
    CWnd* pWndOwner,  
    CMFCDesktopAlertWndInfo& params,  
    HMENU hMenu = NULL,  
    CPoint ptPos = CPoint(-1,-1));
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]`pWndOwner`  
 アラートのウィンドウの所有者を指定します。 その所有者は、デスクトップ通知ウィンドウのすべての通知を送信し、されます。 この値を `NULL` にすることはできません。  
  
 [入力] `uiDlgResID`  
 通知のウィンドウのリソース ID を指定します。  
  
 [入力] `hMenu`  
 ユーザーがメニュー ボタンをクリックすると表示されるメニューを指定します。 場合`NULL`、メニュー ボタンは表示されません。  
  
 [入力] `ptPos`  
 画面座標を使用して、通知ウィンドウが表示される初期位置を指定します。 このパラメーターが (-1,-1) の場合は、通知ウィンドウが画面の右下隅に表示されます。  
  
 [入力] `pRTIDlgBar`  
 アラートのウィンドウのクライアント領域をカバーするカスタム ダイアログ ボックス クラスのランタイム クラス情報。  
  
 [入力] `params`  
 アラートのウィンドウの作成に使用されるパラメーターを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`通知ウィンドウが正常に作成された場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 アラートのウィンドウを作成するには、このメソッドを呼び出します。 アラートのウィンドウのクライアント領域には、ユーザーに表示されるすべてのコントロールをホストしている子 ダイアログ ボックスが含まれています。  
  
 最初のメソッドのオーバー ロードでは、アプリケーションのリソースから読み込まれた子 ダイアログ ボックスを含む通知ウィンドウを作成します。 最初のメソッドのオーバー ロードでは、カスタム ダイアログ ボックス クラスのランタイム クラス情報も指定できます。  
  
 2 番目のメソッドのオーバー ロードでは、既定のコントロールを含む通知ウィンドウを作成します。 変更することで表示するコントロールを指定する、 [CMFCDesktopAlertWndInfo クラス](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)します。  
  
##  <a name="a-namegetanimationspeeda--cmfcdesktopalertwndgetanimationspeed"></a><a name="getanimationspeed"></a>CMFCDesktopAlertWnd::GetAnimationSpeed  
 アニメーションの速度を返します。  
  
```  
UINT GetAnimationSpeed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ミリ秒単位での通知ウィンドウのアニメーションの速度。  
  
### <a name="remarks"></a>コメント  
 アニメーションの速度は、アラートのウィンドウが開き、終了する速度について説明します。  
  
##  <a name="a-namegetanimationtypea--cmfcdesktopalertwndgetanimationtype"></a><a name="getanimationtype"></a>CMFCDesktopAlertWnd::GetAnimationType  
 アニメーションの種類を返します。  
  
```  
CMFCPopupMenu::ANIMATION_TYPE GetAnimationType();
```  
  
### <a name="return-value"></a>戻り値  
 次のアニメーションの種類のいずれかです。  
  
- `NO_ANIMATION`  
  
- `UNFOLD`  
  
- `SLIDE`  
  
- `FADE`  
  
- `SYSTEM_DEFAULT_ANIMATION`  
  
##  <a name="a-namegetautoclosetimea--cmfcdesktopalertwndgetautoclosetime"></a><a name="getautoclosetime"></a>CMFCDesktopAlertWnd::GetAutoCloseTime  
 自動終了のタイムアウトを取得します。  
  
```  
int GetAutoCloseTime() const;  
```  
  
### <a name="return-value"></a>戻り値  
 時間 (ミリ秒)、その後アラート ウィンドウが自動的に閉じます。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、確認通知ウィンドウが自動的に閉じるまでにかかった時間の経過する必要があります。  
  
##  <a name="a-namegetcaptionheighta--cmfcdesktopalertwndgetcaptionheight"></a><a name="getcaptionheight"></a>CMFCDesktopAlertWnd::GetCaptionHeight  
 キャプションの高さを返します。  
  
```  
virtual int GetCaptionHeight();
```  
  
### <a name="return-value"></a>戻り値  
 (ピクセル単位)、キャプションの高さ。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、派生クラスでオーバーライドされることができます。 既定の実装で、いずれか: ポップアップ ウィンドウには、小さいキャプションまたは Windows API 関数から取得した値を表示する場合は、小さいキャプションの高さの値 (7 ピクセル単位) を返す`GetSystemMetrics(SM_CYSMCAPTION)`します。  
  
##  <a name="a-namegetlastposa--cmfcdesktopalertwndgetlastpos"></a><a name="getlastpos"></a>CMFCDesktopAlertWnd::GetLastPos  
 画面上のデスクトップ通知ウィンドウの最後の位置を返します。  
  
```  
CPoint GetLastPos() const;  
```  
  
### <a name="return-value"></a>戻り値  
 画面座標にポイントします。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、画面の通知ウィンドウの最後の有効な位置を返します。  
  
##  <a name="a-namegettransparencya--cmfcdesktopalertwndgettransparency"></a><a name="gettransparency"></a>CMFCDesktopAlertWnd::GetTransparency  
 透過性レベルを返します。  
  
```  
BYTE GetTransparency() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 ~ 255 の間の透明度レベルです。 この値が大きい、不透明度を高くウィンドウです。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、アラートのウィンドウの現在の透明度を取得できます。  
  
##  <a name="a-namehassmallcaptiona--cmfcdesktopalertwndhassmallcaption"></a><a name="hassmallcaption"></a>CMFCDesktopAlertWnd::HasSmallCaption  
 デスクトップ通知ウィンドウが小さいキャプションまたは標準サイズのキャプションにあるかどうかを決定します。  
  
```  
BOOL HasSmallCaption() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`キャプション付きの小さなポップアップ ウィンドウが表示されている場合`FALSE`場合はポップアップ ウィンドウには、通常のサイズのキャプションが表示されます。  
  
### <a name="remarks"></a>コメント  
 小さいキャプションまたは標準サイズのキャプションにポップアップ ウィンドウがあるかどうかを確認するのにには、このメソッドを使用します。 既定では、小さいキャプションは、高い 7 ピクセルです。 標準サイズのキャプションの高さを取得するには、Windows API 関数の呼び出しを`GetSystemMetrics(SM_CYCAPTION)`します。  
  
##  <a name="a-nameonbeforeshowa--cmfcdesktopalertwndonbeforeshow"></a><a name="onbeforeshow"></a>CMFCDesktopAlertWnd::OnBeforeShow  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnBeforeShow(CPoint&);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `CPoint&`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameonclicklinkbuttona--cmfcdesktopalertwndonclicklinkbutton"></a><a name="onclicklinkbutton"></a>CMFCDesktopAlertWnd::OnClickLinkButton  
 ユーザーがデスクトップの通知 メニューにあるリンク ボタンをクリックしたときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdID`  
 このパラメーターは使用されません。  
  
### <a name="return-value"></a>戻り値  
 常に `FALSE`。  
  
### <a name="remarks"></a>コメント  
 ユーザーは、通知ウィンドウのリンクをクリックしたときに通知する場合は、派生クラスでは、このメソッドをオーバーライドします。  
  
##  <a name="a-nameoncommanda--cmfcdesktopalertwndoncommand"></a><a name="oncommand"></a>CMFCDesktopAlertWnd::OnCommand  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnCommand(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `wParam`  
 [入力] `lParam`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameondrawa--cmfcdesktopalertwndondraw"></a><a name="ondraw"></a>CMFCDesktopAlertWnd::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameprocesscommanda--cmfcdesktopalertwndprocesscommand"></a><a name="processcommand"></a>CMFCDesktopAlertWnd::ProcessCommand  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL ProcessCommand(HWND hwnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hwnd`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetanimationspeeda--cmfcdesktopalertwndsetanimationspeed"></a><a name="setanimationspeed"></a>CMFCDesktopAlertWnd::SetAnimationSpeed  
 新しいアニメーションの速度を設定します。  
  
```  
void SetAnimationSpeed(UINT nSpeed);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nSpeed`  
 新しいアニメーションの速度をミリ秒単位で指定します。  
  
### <a name="remarks"></a>コメント  
 アラートのウィンドウのアニメーションの速度を設定するには、このメソッドを呼び出します。 既定のアニメーションの速度は、30 ミリ秒です。  
  
##  <a name="a-namesetanimationtypea--cmfcdesktopalertwndsetanimationtype"></a><a name="setanimationtype"></a>CMFCDesktopAlertWnd::SetAnimationType  
 アニメーションの種類を設定します。  
  
```  
void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `type`  
 アニメーションの種類を指定します。  
  
### <a name="remarks"></a>コメント  
 アニメーションの種類を設定するには、このメソッドを呼び出します。 次のいずれかの値を指定できます。  
  
- `NO_ANIMATION`  
  
- `UNFOLD`  
  
- `SLIDE`  
  
- `FADE`  
  
- `SYSTEM_DEFAULT_ANIMATION`  
  
##  <a name="a-namesetautoclosetimea--cmfcdesktopalertwndsetautoclosetime"></a><a name="setautoclosetime"></a>CMFCDesktopAlertWnd::SetAutoCloseTime  
 自動終了のタイムアウトを設定します。  
  
```  
void SetAutoCloseTime(int nTime);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nTime`  
 通知ウィンドウが自動的に閉じるまでの経過する時間 (ミリ秒単位)。  
  
### <a name="remarks"></a>コメント  
 ウィンドウで、ユーザーが操作できない場合、指定時間後に、[アラート] ウィンドウが自動的に閉じます。  
  
##  <a name="a-namesetsmallcaptiona--cmfcdesktopalertwndsetsmallcaption"></a><a name="setsmallcaption"></a>CMFCDesktopAlertWnd::SetSmallCaption  
 および標準サイズの小さいキャプションを切り替えます。  
  
```  
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSmallCaption`  
 `TRUE`通知ウィンドウが小さいキャプションを表示することを指定するにはそれ以外の場合、`FALSE`通知ウィンドウが標準サイズのキャプションを表示することを指定します。  
  
### <a name="remarks"></a>コメント  
 小規模または標準サイズのキャプションを表示するには、このメソッドを呼び出します。 既定では、小さいキャプションは、高い 7 ピクセルです。 正規のキャプションのサイズを取得するには、Windows API 関数の呼び出しを`GetSystemMetrics(SM_CYCAPTION)`します。  
  
##  <a name="a-namesettransparencya--cmfcdesktopalertwndsettransparency"></a><a name="settransparency"></a>CMFCDesktopAlertWnd::SetTransparency  
 ポップアップ ウィンドウの透明度を設定します。  
  
```  
void SetTransparency(BYTE nTransparency);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nTransparency`  
 透過性レベルを指定します。 この値は、0 から 255 までの間でなければなりません。 この値が大きい、不透明度を高くウィンドウです。  
  
### <a name="remarks"></a>コメント  
 ポップアップ ウィンドウの透明度を設定するには、この関数を呼び出します。  
  
##  <a name="a-namegetdialogsizea--cmfcdesktopalertwndgetdialogsize"></a><a name="getdialogsize"></a>CMFCDesktopAlertWnd::GetDialogSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetDialogSize();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWndInfo クラス](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)   
 [CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)

