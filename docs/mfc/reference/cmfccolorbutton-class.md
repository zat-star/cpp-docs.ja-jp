---
title: "CMFCColorButton クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::CMFCColorButton
- AFXCOLORBUTTON/CMFCColorButton::EnableAutomaticButton
- AFXCOLORBUTTON/CMFCColorButton::EnableOtherButton
- AFXCOLORBUTTON/CMFCColorButton::GetAutomaticColor
- AFXCOLORBUTTON/CMFCColorButton::GetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColor
- AFXCOLORBUTTON/CMFCColorButton::SetColorName
- AFXCOLORBUTTON/CMFCColorButton::SetColumnsNumber
- AFXCOLORBUTTON/CMFCColorButton::SetDocumentColors
- AFXCOLORBUTTON/CMFCColorButton::SetPalette
- AFXCOLORBUTTON/CMFCColorButton::SizeToContent
- AFXCOLORBUTTON/CMFCColorButton::IsDrawXPTheme
- AFXCOLORBUTTON/CMFCColorButton::OnDraw
- AFXCOLORBUTTON/CMFCColorButton::OnDrawBorder
- AFXCOLORBUTTON/CMFCColorButton::OnDrawFocusRect
- AFXCOLORBUTTON/CMFCColorButton::OnShowColorPopup
- AFXCOLORBUTTON/CMFCColorButton::RebuildPalette
- AFXCOLORBUTTON/CMFCColorButton::UpdateColor
- AFXCOLORBUTTON/CMFCColorButton::m_bEnabledInCustomizeMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorButton::m_Color data member
- CMFCColorButton::m_bAutoSetFocus data member
- CMFCColorButton::m_pPopup data member
- CMFCColorButton::m_nColumns data member
- CMFCColorButton class
- CMFCColorButton::m_strAutoColorText data member
- CMFCColorButton::m_bAltColorDlg data member
- CMFCColorButton::m_strDocColorsText data member
- CMFCColorButton::m_strOtherText data member
- CMFCColorButton::m_pPalette data member
- CMFCColorButton::m_lstDocColors data member
- CMFCColorButton::m_ColorAutomatic data member
ms.assetid: 9fdf34ae-4cc5-4c5e-9d89-1c50e8a73699
caps.latest.revision: 34
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
ms.openlocfilehash: 6a9290d396c8ce5ccafa2ae556b21ff89806d830
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolorbutton-class"></a>CMFCColorButton クラス
`CMFCColorButton`と[CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)クラスは、カラー ピッカー コントロールを実装する一緒に使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCColorButton : public CMFCButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorButton::CMFCColorButton](#cmfccolorbutton)|新しい `CMFCColorButton` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)|有効にして標準のカラー ボタンの上に配置する「自動」ボタンが無効になります。 (標準的なシステムの自動ボタンのラベルは**自動**)。|  
|[CMFCColorButton::EnableOtherButton](#enableotherbutton)|有効にして標準のカラー ボタンの下にある、"other"ボタンが無効になります。 ("Other"ボタンのラベルは、標準的なシステム**他の色**.)|  
|[CMFCColorButton::GetAutomaticColor](#getautomaticcolor)|現在の自動色を取得します。|  
|[CMFCColorButton::GetColor](#getcolor)|ボタンの色を取得します。|  
|[CMFCColorButton::SetColor](#setcolor)|ボタンの色を設定します。|  
|[CMFCColorButton::SetColorName](#setcolorname)|色の名前を設定します。|  
|[CMFCColorButton::SetColumnsNumber](#setcolumnsnumber)|カラー ピッカー ダイアログ ボックスの列の数を設定します。|  
|[CMFCColorButton::SetDocumentColors](#setdocumentcolors)|カラー ピッカー ダイアログ ボックスに表示されるドキュメントに固有の色の一覧を指定します。|  
|[CMFCColorButton::SetPalette](#setpalette)|標準的な表示色のパレットを指定します。|  
|[CMFCColorButton::SizeToContent](#sizetocontent)|そのテキストとイメージのサイズによっては、ボタン コントロールのサイズを変更します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorButton::IsDrawXPTheme](#isdrawxptheme)|Windows XP の visual スタイルで現在の色のボタンを表示するかどうかを示します。|  
|[CMFCColorButton::OnDraw](#ondraw)|ボタンのイメージを表示するためにフレームワークによって呼び出されます。|  
|[CMFCColorButton::OnDrawBorder](#ondrawborder)|ボタンの境界線を表示するためにフレームワークによって呼び出されます。|  
|[CMFCColorButton::OnDrawFocusRect](#ondrawfocusrect)|ボタンに重点を置いたときにフォーカス四角形を表示するためにフレームワークによって呼び出されます。|  
|[CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)|カラー ピッカー ダイアログ ボックスの表示時に、フレームワークによって呼び出されます。|  
|[CMFCColorButton::RebuildPalette](#rebuildpalette)|初期化、`m_pPalette`指定のパレットまたはシステムの既定のパレットにデータ メンバーを保護します。|  
|[CMFCColorButton::UpdateColor](#updatecolor)|カラー ピッカー ダイアログ ボックスのパレットから色を選択すると、フレームワークによって呼び出されます。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|`m_bAltColorDlg`|ブール値。 場合`TRUE`、フレームワークによって表示、 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)色のダイアログ ボックス、*他の*ボタンがクリックされた場合、または`FALSE`システムの色 ダイアログ ボックス。 既定値は `TRUE` です。 詳細については、次を参照してください。 [CMFCColorButton::EnableOtherButton](#enableotherbutton)します。|  
|`m_bAutoSetFocus`|ブール値。 場合`TRUE`、フレームワークでは、メニューが表示されている場合、または色のメニューにフォーカスを設定`FALSE`フォーカスは変わりません。 既定値は `TRUE` です。|  
|[CMFCColorButton::m_bEnabledInCustomizeMode](#m_benabledincustomizemode)|色のボタンのカスタマイズ モードが有効になっているかどうかを示します。|  
|`m_Color`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値。 現在選択されている色が含まれています。|  
|`m_ColorAutomatic`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値。 現在選択されている既定の色が含まれています。|  
|`m_Colors`|A [CArray](../../mfc/reference/carray-class.md)の[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値。 現在利用可能な色が含まれています。|  
|`m_lstDocColors`|A [CList](../../mfc/reference/clist-class.md)の[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値。 現在のドキュメントの色が含まれています。|  
|`m_nColumns`|整数。 色の選択 画面の色のグリッドに表示する列の数が含まれています。|  
|`m_pPalette`|ポインター、 [CPalette](../../mfc/reference/cpalette-class.md)します。 現在の色の選択メニューに表示される色が含まれています。|  
|`m_pPopup`|ポインター、 [CMFCColorPopupMenu クラス](../../mfc/reference/cmfccolorpopupmenu-class.md)オブジェクトです。 色のボタンをクリックしたときに表示される色の選択メニュー。|  
|`m_strAutoColorText`|文字列。 色の選択 画面で「自動」のボタンのラベル。|  
|`m_strDocColorsText`|文字列。 ドキュメントの色を表示する色の選択メニューにボタンのラベル。|  
|`m_strOtherText`|文字列。 色の選択 画面で、"other"ボタンのラベルです。|  
  
## <a name="remarks"></a>コメント  
 既定では、`CMFCColorButton`クラスはカラー ピッカー ダイアログ ボックスを開くプッシュ ボタンとして動作します。 カラー ピッカー ダイアログ ボックスには、小さなカラー ボタンと カスタム カラー ピッカーを表示する"other"ボタンの配列が含まれています。 ("Other"ボタンのラベルは、標準的なシステム**他の色**.)ユーザーが新しい色を選択すると、`CMFCColorButton`オブジェクトは変更が反映され、選択した色が表示されます。  
  
 色のボタン コントロールを作成、コード内で直接、またはを使用して、 **ClassWizard**ツールとダイアログ ボックスのテンプレートです。 色のボタン コントロールを直接作成する場合は、追加、`CMFCColorButton`アプリケーション、および、呼び出すコンス トラクターに変数と`Create`のメソッド、`CMFCColorButton`オブジェクトです。 使用する場合、 **ClassWizard**、追加、`CButton`そのため、アプリケーション変数から変数の型を変更して`CButton`に`CMFCColorButton`します。  
  
 カラー ピッカー ダイアログ ボックス ( [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)) によって表示される、 [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)フレームワークが呼び出す場合は、メソッド、`OnLButtonDown`イベント ハンドラーです。 [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)メソッドをオーバーライドしてカスタムの色の選択をサポートします。  
  
 `CMFCColorButton`オブジェクトがその親に送信して、色が変更されていることを通知する`WM_COMMAND | BN_CLICKED`通知します。 親を使用して、 [CMFCColorButton::GetColor](#getcolor)現在の色を取得します。  
  
## <a name="example"></a>例  
 次の例では、多様なメソッドを使用してカラー ボタンを構成する方法、`CMFCColorButton`クラスです。 メソッドは、色のボタンと、列の番号の色を設定し、自動とその他のボタンを有効にします。 この例は、[ステータス バーのデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_StatusBarDemo&#10;](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_1.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo&#11;](../../mfc/reference/codesnippet/cpp/cmfccolorbutton-class_2.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcolorbutton.h  
  
##  <a name="cmfccolorbutton"></a>CMFCColorButton::CMFCColorButton  
 新しい `CMFCColorButton` オブジェクトを構築します。  
  
```  
CMFCColorButton();
```  
  
##  <a name="enableautomaticbutton"></a>CMFCColorButton::EnableAutomaticButton  
 有効にするまたはカラー ピッカー コントロールの「自動」ボタンを無効にし、自動 (既定値) の色を設定します。  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszLabel`  
 自動のボタンのテキストを指定します。  
  
 [入力] `colorAutomatic`  
 自動のボタンの既定の色を指定します RGB 値。  
  
 [入力] `bEnable`  
 自動のボタンが有効になっているか、無効にするかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enableotherbutton"></a>CMFCColorButton::EnableOtherButton  
 有効または標準のカラー ボタンの下に表示される"other"ボタンを無効にします。  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    BOOL bAltColorDlg=TRUE,  
    BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszLabel`  
 ボタンのテキストを指定します。  
  
 [入力] `bAltColorDlg`  
 指定するかどうか、 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  ダイアログ ボックスまたはシステムの色 ダイアログ ボックスを開いたユーザーがボタンをクリックするとします。  
  
 [入力] `bEnable`  
 "Other"ボタンが有効になっているかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 色のダイアログ ボックスを表示する"other"ボタンをクリックします。 場合、 *bAltColorDlg*パラメーターは`TRUE`、 [CMFCColorDialog クラス](../../mfc/reference/cmfccolordialog-class.md)が表示されます。 それ以外の場合、システムの色 ダイアログ ボックスが表示されます。  
  
##  <a name="getautomaticcolor"></a>CMFCColorButton::GetAutomaticColor  
 現在の自動設定 (既定値) の色を取得します。  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の自動色を表す RGB 値。  
  
### <a name="remarks"></a>コメント  
 現在の自動色が設定され、 [CMFCColorButton::EnableAutomaticButton](#enableautomaticbutton)メソッドです。  
  
##  <a name="getcolor"></a>CMFCColorButton::GetColor  
 現在選択されている色を取得します。  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 RGB 値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isdrawxptheme"></a>CMFCColorButton::IsDrawXPTheme  
 Windows XP の visual スタイルで現在の色のボタンを表示するかどうかを示します。  
  
```  
BOOL IsDrawXPTheme() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`visual スタイルがサポートされていて、Windows XP の visual スタイルで現在の色のボタンが表示されます。それ以外の場合、`FALSE`です。  
  
##  <a name="m_benabledincustomizemode"></a>CMFCColorButton::m_bEnabledInCustomizeMode  
 色のボタンをカスタマイズ モードに設定します。  
  
```  
BOOL m_bEnabledInCustomizeMode;  
```  
  
### <a name="remarks"></a>コメント  
 カスタマイズ ダイアログのページに色のボタンを追加 (または、ユーザーが行うカスタマイズ中に別の色の選択を許可) する必要がある場合は、設定して、ボタンを有効に、`m_bEnabledInCustomizeMode`メンバー`TRUE`します。 既定では、このメンバーに設定`FALSE`します。  
  
##  <a name="ondraw"></a>CMFCColorButton::OnDraw  
 ボタンの画像を表示するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    UINT uiState);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 ボタンのイメージをレンダリングするために使用しているデバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 ボタンに外接する四角形。  
  
 [入力] `uiState`  
 ボタンの表示状態を指定します。  
  
### <a name="remarks"></a>コメント  
 表示処理をカスタマイズするには、このメソッドをオーバーライドします。  
  
##  <a name="ondrawborder"></a>CMFCColorButton::OnDrawBorder  
 ボタンの境界線を表示するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect& rectClient,  
    UINT uiState);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 境界線の描画に使用されるデバイス コンテキストへのポインター。  
  
 [入力] `rectClient`  
 指定されているデバイス コンテキスト内の四角形、`pDC`描画されるボタンの境界を定義するパラメーターです。  
  
 [入力] `uiState`  
 ボタンの表示状態を指定します。  
  
### <a name="remarks"></a>コメント  
 色のボタンの境界線の外観をカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="ondrawfocusrect"></a>CMFCColorButton::OnDrawFocusRect  
 ボタンにフォーカスがあるときにフォーカス四角形を表示するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 フォーカスされた四角形を描画に使用されるデバイス コンテキストへのポインター。  
  
 [入力] `rectClient`  
 指定したデバイス コンテキスト内の四角形、`pDC`ボタンの境界を定義するパラメーターです。  
  
### <a name="remarks"></a>コメント  
 フォーカスされた四角形の外観をカスタマイズするには、このメソッドをオーバーライドします。  
  
##  <a name="onshowcolorpopup"></a>CMFCColorButton::OnShowColorPopup  
 ポップアップのカラー バーが表示される前に呼び出されます。  
  
```  
virtual void OnShowColorPopup();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="rebuildpalette"></a>CMFCColorButton::RebuildPalette  
 初期化、`m_pPalette`指定のパレットまたはシステムの既定のパレットにデータ メンバーを保護します。  
  
```  
void RebuildPalette(CPalette* pPal);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pPal`|論理パレットへのポインターまたは`NULL`です。 場合`NULL`システムの既定のパレットを使用します。|  
  
##  <a name="setcolor"></a>CMFCColorButton::SetColor  
 ボタンの色を指定します。  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `color`  
 RGB 値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setcolorname"></a>CMFCColorButton::SetColorName  
 色の名前を指定します。  
  
```  
static void SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `color`  
 色の RGB 値。  
  
 [入力] `strName`  
 色の名前。  
  
### <a name="remarks"></a>コメント  
 色の名前の一覧は、アプリケーションごとにグローバルです。 そのため、このメソッドで転送にパラメーターを[CMFCColorBar::SetColorName](../../mfc/reference/cmfccolorbar-class.md#setcolorname)します。  
  
##  <a name="setcolumnsnumber"></a>CMFCColorButton::SetColumnsNumber  
 ユーザーの色の選択プロセス中に、ユーザーに表示される色の一覧に表示される列の数を定義します。  
  
```  
void SetColumnsNumber(int nColumns);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nColumns`  
 列の数を指定します。  
  
### <a name="remarks"></a>コメント  
 ユーザーは、定義済みの色の一覧が表示されるポップアップ カラー バーから色を選択することができます。 このメソッドを使用すると、テーブルの列の数を定義します。  
  
##  <a name="setdocumentcolors"></a>CMFCColorButton::SetDocumentColors  
 一連の色とセットの名前を指定します。 使用して色のセットを表示、 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)オブジェクトです。  
  
```  
void SetDocumentColors(
    LPCTSTR lpszLabel,  
    CList<COLORREF,COLORREF>& lstColors);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszLabel`  
 ドキュメントの色のセットを表示するラベルを指定します。  
  
 [入力] `lstColors`  
 RGB 値のリストへの参照。  
  
### <a name="remarks"></a>コメント  
 A`CMFCColorButton`オブジェクトに転送する RGB 値のリストを保持する、 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)オブジェクトです。 これらの色がで指定されたラベルを持つ特別なセクションに表示されるカラー バーが表示されるときに、`lpszLabel`パラメーター。  
  
##  <a name="setpalette"></a>CMFCColorButton::SetPalette  
 ポップアップのカラー バーに表示する標準の色を指定します。  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pPalette`  
 カラー パレットへのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="sizetocontent"></a>CMFCColorButton::SizeToContent  
 ボタン コントロールに合わせてそのテキストとイメージのサイズを変更します。  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bCalcOnly`  
 ゼロ以外の場合は、ボタン コントロールの新しいサイズが計算されますが、実際のサイズは変更されません。  
  
### <a name="return-value"></a>戻り値  
 A`CSize`新しいボタン コントロールのサイズを指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="updatecolor"></a>CMFCColorButton::UpdateColor  
 ユーザーが色のボタンをクリックしたときに表示されるカラー バーの色を選択すると、フレームワークによって呼び出されます。  
  
```  
virtual void UpdateColor(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `color`  
 ユーザーが選択した色。  
  
### <a name="remarks"></a>コメント  
 `UpdateColor`関数は、現在選択されているボタンの色を変更し、親に通知を送信して、 `WM_COMMAND` 、メッセージ、`BN_CLICKED`標準的な通知です。 使用して、 [CMFCColorButton::GetColor](#getcolor)選択した色を取得します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)   
 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCColorButton::OnShowColorPopup](#onshowcolorpopup)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [CPalette クラス](../../mfc/reference/cpalette-class.md)   
 [CArray クラス](../../mfc/reference/carray-class.md)   
 [CList クラス](../../mfc/reference/clist-class.md)   
 [CString](../../atl-mfc-shared/reference/cstringt-class.md)

