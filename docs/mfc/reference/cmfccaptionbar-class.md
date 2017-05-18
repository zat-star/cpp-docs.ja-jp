---
title: "CMFCCaptionBar クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar::Create
- AFXCAPTIONBAR/CMFCCaptionBar::DoesAllowDynInsertBefore
- AFXCAPTIONBAR/CMFCCaptionBar::EnableButton
- AFXCAPTIONBAR/CMFCCaptionBar::GetAlignment
- AFXCAPTIONBAR/CMFCCaptionBar::GetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::GetButtonRect
- AFXCAPTIONBAR/CMFCCaptionBar::GetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::IsMessageBarMode
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveButton
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveIcon
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveText
- AFXCAPTIONBAR/CMFCCaptionBar::SetBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::SetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::SetButton
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonPressed
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetFlatBorder
- AFXCAPTIONBAR/CMFCCaptionBar::SetIcon
- AFXCAPTIONBAR/CMFCCaptionBar::SetImageToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::SetText
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBackground
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBorder
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawButton
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawImage
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawText
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBackground
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBorder
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarText
dev_langs:
- C++
helpviewer_keywords:
- CMFCCaptionBar class
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
caps.latest.revision: 28
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c9be93449392de9d04e4869db8dcd73e08125c88
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccaptionbar-class"></a>CMFCCaptionBar クラス
A`CMFCCaptionBar`オブジェクトは&3; つの要素を表示できるコントロール バー: ボタン、テキスト ラベル、およびビットマップです。 表示できる各要素の数は&1; つずつです。 各要素は、コントロールの左端、右端、または中央に揃えて配置できます。 また、キャプション バーの上部または下部の境界線にフラット スタイルまたは 3D スタイルを適用することもできます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCCaptionBar : public CPane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCCaptionBar::Create](#create)|キャプション バー コントロールを作成し、それにアタッチ、`CMFCCaptionBar`オブジェクトです。|  
|[CMFCCaptionBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|キャプション バーと親フレームの間での別のウィンドウを動的に挿入するかどうかを示します。 (上書き[CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore))。|  
|[CMFCCaptionBar::EnableButton](#enablebutton)|有効またはキャプション バーにあるボタンを無効にします。|  
|[CMFCCaptionBar::GetAlignment](#getalignment)|指定した要素の配置を返します。|  
|[CMFCCaptionBar::GetBorderSize](#getbordersize)|キャプション バーの境界線のサイズを返します。|  
|[CMFCCaptionBar::GetButtonRect](#getbuttonrect)|キャプション バーのボタンの外接する四角形を取得します。|  
|[CMFCCaptionBar::GetMargin](#getmargin)|キャプション バー要素の端と、キャプション バー コントロールの端との間の距離を返します。|  
|[CMFCCaptionBar::IsMessageBarMode](#ismessagebarmode)|キャプション バーが、メッセージ バー モードにするかどうかを指定します。|  
|[CMFCCaptionBar::RemoveBitmap](#removebitmap)|キャプション バーからビットマップ イメージを削除します。|  
|[CMFCCaptionBar::RemoveButton](#removebutton)|キャプション バーのボタンを削除します。|  
|[CMFCCaptionBar::RemoveIcon](#removeicon)|キャプション バーからアイコンを削除します。|  
|[CMFCCaptionBar::RemoveText](#removetext)|キャプション バーのテキスト ラベルを削除します。|  
|[CMFCCaptionBar::SetBitmap](#setbitmap)|キャプション バーのビットマップ イメージを設定します。|  
|[CMFCCaptionBar::SetBorderSize](#setbordersize)|キャプション バーの境界線のサイズを設定します。|  
|[CMFCCaptionBar::SetButton](#setbutton)|キャプション バーのボタンを設定します。|  
|[CMFCCaptionBar::SetButtonPressed](#setbuttonpressed)|ボタンが押された状態のままになるかどうかを指定します。|  
|[CMFCCaptionBar::SetButtonToolTip](#setbuttontooltip)|ボタンのツールヒントを設定します。|  
|[CMFCCaptionBar::SetFlatBorder](#setflatborder)|タイトル バーの境界線スタイルを設定します。|  
|[CMFCCaptionBar::SetIcon](#seticon)|キャプション バーのアイコンを設定します。|  
|[CMFCCaptionBar::SetImageToolTip](#setimagetooltip)|キャプション バーの画像のツールヒントを設定します。|  
|[CMFCCaptionBar::SetMargin](#setmargin)|キャプション バー要素の端とキャプション バー コントロールの境界線間の距離を設定します。|  
|[CMFCCaptionBar::SetText](#settext)|キャプション バーのテキスト ラベルを設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCCaptionBar::OnDrawBackground](#ondrawbackground)|キャプション バーの背景を塗りつぶすために、フレームワークによって呼び出されます。|  
|[CMFCCaptionBar::OnDrawBorder](#ondrawborder)|キャプション バーの境界線を描画するためにフレームワークによって呼び出されます。|  
|[CMFCCaptionBar::OnDrawButton](#ondrawbutton)|キャプション バーのボタンを描画するためにフレームワークによって呼び出されます。|  
|[CMFCCaptionBar::OnDrawImage](#ondrawimage)|キャプション バー イメージを描画するためにフレームワークによって呼び出されます。|  
|[CMFCCaptionBar::OnDrawText](#ondrawtext)|キャプション バーのテキストを描画するためにフレームワークによって呼び出されます。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground)|キャプション バーの背景色。|  
|[CMFCCaptionBar::m_clrBarBorder](#m_clrbarborder)|タイトル バーの境界線の色。|  
|[CMFCCaptionBar::m_clrBarText](#m_clrbartext)|キャプション バーのテキストの色です。|  
  
## <a name="remarks"></a>コメント  
 キャプション バーを作成するには、次の手順を実行します。  
  
1.  構築、`CMFCCaptionBar`オブジェクトです。 通常、フレーム ウィンドウ クラスに、キャプション バーを追加します。  
  
2.  呼び出す、 [CMFCCaptionBar::Create](#create)コントロールを作成し、キャプション バーにアタッチ メソッド、`CMFCCaptionBar`オブジェクトです。  
  
3.  呼び出す[CMFCCaptionBar::SetButton](#setbutton)、 [CMFCCaptionBar::SetText](#settext)、 [CMFCCaptionBar::SetIcon](#seticon)、および[CMFCCaptionBar::SetBitmap](#setbitmap)キャプション バー要素を設定します。  
  
 Button 要素を設定すると、ボタンをクリックするコマンド ID を割り当てる必要があります。 ユーザーがボタンのキャプション バーのルートをクリックすると、`WM_COMMAND`を親フレーム ウィンドウにこの ID を持つメッセージ。  
  
 キャプション バーは、メッセージ バー モードは、Microsoft Office 2007 アプリケーションに表示されるメッセージ バーをエミュレートでも処理できます。 メッセージ バー モードで、キャプション バーには、ビットマップ、メッセージ、および (通常、ダイアログ ボックスが開きます。) ボタンが表示されます。ビットマップにツールヒントを割り当てることができます。  
  
 メッセージ バー モードを有効にする[CMFCCaptionBar::Create](#create) (bIsMessageBarMode) の&4; 番目のパラメーターを設定および`TRUE`です。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCCaptionBar`クラスです。 例では、キャプション バー コントロールを作成、キャプション バーの 3D 罫線を設定する、キャプション バーの要素の端と、キャプション バー コントロールの端との間のピクセル単位で距離を設定、キャプション バーのボタンを設定、ボタンのツールヒントを設定、キャプション バーのテキスト ラベルを設定、ビットマップ イメージのキャプション バーの設定方法を示しています。、キャプション バーにイメージのツールヒントを設定します。 このコード スニペットの一部である、 [MS Office 2007 デモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#1;](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_1.h)]  
[!code-cpp[NVC_MFC_MSOffice2007Demo&#2;](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcaptionbar.h  
  
##  <a name="create"></a>CMFCCaptionBar::Create  
 キャプション バー コントロールを作成し、それにアタッチ、`CMFCCaptionBar`オブジェクトです。  
  
```  
BOOL Create(
    DWORD dwStyle,  
    CWnd* pParentWnd,  
    UINT uID,  
    int nHeight=-1,  
    BOOL bIsMessageBarMode=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 キャプション バーのスタイルの論理 OR の組み合わせ。  
  
 `pParentWnd`  
 キャプション バー コントロールの親ウィンドウです。  
  
 `uID`  
 キャプション バー コントロールの ID です。  
  
 `nHeight`  
 (ピクセル単位)、キャプション バー コントロールの高さ。 -1 の場合、高さは、アイコン、テキスト、キャプション バー コントロールを表示するボタンの高さに従って計算されます。  
  
 `bIsMessageBarMode`  
 `TRUE`キャプション バーが、メッセージ バー モードである場合`FALSE`それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`キャプション バー コントロールが正常に作成された場合`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CMFCCaptionBar`&2; つのステップ内のオブジェクト。 まず、コンス トラクターを呼び出すを呼び出す、`Create`メソッドでは、Windows コントロールを作成し、それをアタッチ、`CMFCCaptionBar`オブジェクトです。  
  
##  <a name="doesallowdyninsertbefore"></a>CMFCCaptionBar::DoesAllowDynInsertBefore  
 キャプション バーと親フレームの間での別のウィンドウを動的に挿入するかどうかを示します。  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します。`FALSE`オーバーライドされない限り、します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enablebutton"></a>CMFCCaptionBar::EnableButton  
 有効またはキャプション バーにあるボタンを無効にします。  
  
```  
void EnableButton(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`ボタンを有効にする`FALSE`ボタンを無効にします。  
  
##  <a name="getalignment"></a>CMFCCaptionBar::GetAlignment  
 指定した要素の配置を返します。  
  
```  
BarElementAlignment GetAlignment(BarElement elem);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `elem`  
 キャプション バーには、配置を取得するための要素が表示されます。  
  
### <a name="return-value"></a>戻り値  
 ボタン、ビットマップ、テキスト、アイコンなどの要素の配置です。  
  
### <a name="remarks"></a>コメント  
 要素の配置には、次の値のいずれかを指定できます。  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="getbordersize"></a>CMFCCaptionBar::GetBorderSize  
 キャプション バーの境界線のサイズを返します。  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 枠線のピクセル単位のサイズ。  
  
##  <a name="getbuttonrect"></a>CMFCCaptionBar::GetButtonRect  
 キャプション バーのボタンの外接する四角形を取得します。  
  
```  
CRect GetButtonRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`CRect`キャプション バーのボタンの外接する四角形の座標を格納しているオブジェクト。  
  
##  <a name="getmargin"></a>CMFCCaptionBar::GetMargin  
 キャプション バー要素の端と、キャプション バー コントロールの端との間の距離を返します。  
  
```  
int GetMargin() const;  
```  
  
### <a name="return-value"></a>戻り値  
 (ピクセル単位)、キャプション バー要素の端と、キャプション バー コントロールの端との間の距離。  
  
##  <a name="ismessagebarmode"></a>CMFCCaptionBar::IsMessageBarMode  
 キャプション バーが、メッセージ バー モードにするかどうかを指定します。  
  
```  
BOOL IsMessageBarMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`キャプション バーが、メッセージ バー モードである場合`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 メッセージ バー モードでは、キャプション バーには、ツールヒント、メッセージ テキスト、ボタンの画像が表示されます。  
  
##  <a name="m_clrbarbackground"></a>CMFCCaptionBar::m_clrBarBackground  
 キャプション バーの背景色。  
  
```  
COLORREF m_clrBarBackground  
```  
  
##  <a name="m_clrbarborder"></a>CMFCCaptionBar::m_clrBarBorder  
 タイトル バーの境界線の色。  
  
```  
COLORREF m_clrBarBorder  
```  
  
##  <a name="m_clrbartext"></a>CMFCCaptionBar::m_clrBarText  
 キャプション バーのテキストの色です。  
  
```  
COLORREF m_clrBarText  
```  
  
##  <a name="ondrawbackground"></a>CMFCCaptionBar::OnDrawBackground  
 キャプション バーの背景を塗りつぶすために、フレームワークによって呼び出されます。  
  
```  
virtual void OnDrawBackground(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 タイトル バーのデバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 塗りつぶす外接する四角形。  
  
### <a name="remarks"></a>コメント  
 `OnDrawBackground`キャプション バーの背景が入力すると、メソッドが呼び出されます。 既定の実装を使用して背景を塗りつぶす、 [CMFCCaptionBar::m_clrBarBackground](#m_clrbarbackground)色。  
  
 このメソッドをオーバーライドして、`CMFCCaptionBar`キャプション バーの外観をカスタマイズするクラスを派生します。  
  
##  <a name="ondrawborder"></a>CMFCCaptionBar::OnDrawBorder  
 キャプション バーの境界線を描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 境界線の表示に使用されるデバイス コンテキスト。  
  
 [入力] `rect`  
 外接する四角形。  
  
### <a name="remarks"></a>コメント  
 既定では、罫線には、フラット スタイルが設定されています。  
  
 このメソッドをオーバーライドして、`CMFCCaptionBar`キャプション バーの境界線の外観をカスタマイズするクラスを派生します。  
  
##  <a name="ondrawbutton"></a>CMFCCaptionBar::OnDrawButton  
 キャプション バーのボタンを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawButton(
    CDC* pDC,  
    CRect rect,  
    const CString& strButton,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 ボタンを表示するために使用しているデバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 ボタンの外接する四角形。  
  
 [入力] `strButton`  
 ボタンのテキスト ラベル。  
  
 [入力] `bEnabled`  
 `TRUE`ボタンが有効の場合`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドをオーバーライドして、`CMFCCaptionBar`キャプション バーのボタンの外観をカスタマイズするクラスを派生します。  
  
##  <a name="ondrawimage"></a>CMFCCaptionBar::OnDrawImage  
 キャプション バー イメージを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawImage(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 イメージを表示するために使用しているデバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 イメージの外接する四角形を指定します。  
  
### <a name="remarks"></a>コメント  
 このメソッドをオーバーライドして、`CMFCCaptionBar`イメージの外観をカスタマイズするクラスを派生します。  
  
##  <a name="ondrawtext"></a>CMFCCaptionBar::OnDrawText  
 キャプション バーのテキストを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawText(
    CDC* pDC,  
    CRect rect,  
    const CString& strText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 ボタンを表示するために使用しているデバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 テキストの外接する四角形。  
  
 [入力] `strText`  
 表示するテキスト文字列。  
  
### <a name="remarks"></a>コメント  
 既定の実装を使用して、テキストを表示する`CDC::DrawText`と[CMFCCaptionBar::m_clrBarText](#m_clrbartext)色。  
  
 このメソッドをオーバーライドして、`CMFCCaptionBar`キャプション バーのテキストの外観をカスタマイズするクラスを派生します。  
  
##  <a name="removebitmap"></a>CMFCCaptionBar::RemoveBitmap  
 キャプション バーからビットマップ イメージを削除します。  
  
```  
void RemoveBitmap();
```  
  
##  <a name="removebutton"></a>CMFCCaptionBar::RemoveButton  
 キャプション バーのボタンを削除します。  
  
```  
void RemoveButton();
```  
  
### <a name="remarks"></a>コメント  
 キャプション バー要素のレイアウトは自動的に調整されます。  
  
##  <a name="removeicon"></a>CMFCCaptionBar::RemoveIcon  
 キャプション バーからアイコンを削除します。  
  
```  
void RemoveIcon();
```  
  
##  <a name="removetext"></a>CMFCCaptionBar::RemoveText  
 キャプション バーのテキスト ラベルを削除します。  
  
```  
void RemoveText();
```  
  
##  <a name="setbitmap"></a>CMFCCaptionBar::SetBitmap  
 キャプション バーのビットマップ イメージを設定します。  
  
```  
void SetBitmap(
    HBITMAP hBitmap,  
    COLORREF clrTransparent,  
    BOOL bStretch=FALSE,  
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);

 
void SetBitmap(
    UINT uiBmpResID,  
    COLORREF clrTransparent,  
    BOOL bStretch=FALSE,  
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hBitmap`  
 設定するビットマップへのハンドル。  
  
 [入力] `clrTransparent`  
 ビットマップの透明色を指定する RGB 値。  
  
 [入力] `bStretch`  
 場合`TRUE`イメージの外接する四角形に適合しない場合、ビットマップを拡大します。 それ以外の場合、ビットマップは伸縮されません。  
  
 [入力] `bmpAlignment`  
 ビットマップの配置です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、キャプション バーにビットマップを設定できます。  
  
 前のビットマップは自動的に破棄されます。 キャプション バーにアイコンが表示されますが呼び出されるためかどうか、 [CMFCCaptionBar::SetIcon](#seticon)メソッドを呼び出すことによって、アイコンを削除しない限り、ビットマップは表示されません[CMFCCaptionBar::RemoveIcon](#removeicon)します。  
  
 ビットマップの配置に指定されたとおり、`bmpAlignment`パラメーター。  このパラメーターには、次の `BarElementAlignment` 値のいずれかを指定できます。  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="setbordersize"></a>CMFCCaptionBar::SetBorderSize  
 キャプション バーの境界線のサイズを設定します。  
  
```  
void SetBorderSize(int nSize);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nSize`  
 新しいサイズ (ピクセル単位) のキャプション バーの境界線。  
  
##  <a name="setbutton"></a>CMFCCaptionBar::SetButton  
 キャプション バーのボタンを設定します。  
  
```  
void SetButton(
    LPCTSTR lpszLabel,  
    UINT uiCmdUI,  
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,  
    BOOL bHasDropDownArrow=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszLabel`  
 ボタンのコマンドのラベル。  
  
 `uiCmdUI`  
 ボタンのコマンド id。  
  
 `btnAlignmnet`  
 ボタンの配置。  
  
 `bHasDropDownArrow`  
 `TRUE`ボタンは、ドロップダウン矢印を表示する場合`FALSE`それ以外の場合。  
  
##  <a name="setbuttonpressed"></a>CMFCCaptionBar::SetButtonPressed  
 ボタンが押された状態のままになるかどうかを指定します。  
  
```  
void SetButtonPressed(BOOL bPresed=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bPresed`  
 `TRUE`ボタンが押された状態を保持した場合`FALSE`それ以外の場合。  
  
##  <a name="setbuttontooltip"></a>CMFCCaptionBar::SetButtonToolTip  
 ボタンのツールヒントを設定します。  
  
```  
void SetButtonToolTip(
    LPCTSTR lpszToolTip,  
    LPCTSTR lpszDescription=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszToolTip`  
 ツールヒントのキャプション。  
  
 [入力] `lpszDescription`  
 Tooltip の説明。  
  
##  <a name="setflatborder"></a>CMFCCaptionBar::SetFlatBorder  
 タイトル バーの境界線スタイルを設定します。  
  
```  
void SetFlatBorder(BOOL bFlat=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bFlat`  
 `TRUE`キャプション バーの境界線がフラットな場合。 `FALSE`境界線が 3D の場合。  
  
##  <a name="seticon"></a>CMFCCaptionBar::SetIcon  
 キャプション バーのアイコンを設定します。  
  
```  
void SetIcon(
    HICON hIcon,  
    BarElementAlignment iconAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hIcon`  
 設定するには、アイコンのハンドルです。  
  
 [入力] `iconAlignment`  
 アイコンの配置です。  
  
### <a name="remarks"></a>コメント  
 キャプション バーには、アイコンまたはビットマップのいずれかを表示できます。 参照してください[CMFCCaptionBar::SetBitmap](#setbitmap)ビットマップを表示する方法を確認します。 アイコンとビットマップの両方を設定した場合、アイコンが常に表示されます。 呼び出す[CMFCCaptionBar::RemoveIcon](#removeicon)キャプション バーのアイコンを削除します。  
  
 アイコンの配置」の手順に従って、`iconAlignment`パラメーター。 次のいずれか`BarElementAlignment`値。  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
##  <a name="setimagetooltip"></a>CMFCCaptionBar::SetImageToolTip  
 キャプション バーには、イメージのツールヒントを設定します。  
  
```  
void SetImageToolTip(
    LPCTSTR lpszToolTip,  
    LPCTSTR lpszDescription=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszToolTip`  
 ツールヒントのテキストです。  
  
 [入力] `lpszDescription`  
 Tooltip の説明。  
  
##  <a name="setmargin"></a>CMFCCaptionBar::SetMargin  
 キャプション バー要素の端とキャプション バー コントロールの境界線間の距離を設定します。  
  
```  
void SetMargin(int nMargin);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nMargin`  
 (ピクセル単位)、キャプション バー要素の端と、キャプション バー コントロールの端との間の距離。  
  
##  <a name="settext"></a>CMFCCaptionBar::SetText  
 キャプション バーのテキスト ラベルを設定します。  
  
```  
void SetText(
    const CString& strText,  
    BarElementAlignment textAlignment=ALIGN_RIGHT);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `strText`  
 設定するテキスト文字列。  
  
 [入力] `textAlignment`  
 テキストの配置。  
  
### <a name="remarks"></a>コメント  
 テキスト ラベルを配置に指定されたとおり、`textAlignment`パラメーター。 次のいずれか`BarElementAlignment`値。  
  
-   ALIGN_INVALID  
  
-   ALIGN_LEFT  
  
-   ALIGN_RIGHT  
  
-   ALIGN_CENTER  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)

