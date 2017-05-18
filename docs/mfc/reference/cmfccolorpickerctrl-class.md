---
title: "CMFCColorPickerCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SelectCellHexagon
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminanceBarWidth
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetOriginalColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetPalette
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetType
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::DrawCursor
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorPickerCtrl class
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0a819d04535ba965e2c1a10f3761c442c9840538
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolorpickerctrl-class"></a>CMFCColorPickerCtrl クラス
`CMFCColorPickerCtrl`クラスには、色の選択に使用されるコントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCColorPickerCtrl : public CButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::CMFCColorPickerCtrl](#cmfccolorpickerctrl)|`CMFCColorPickerCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::GetColor](#getcolor)|ユーザーが選択した色を取得します。|  
|[CMFCColorPickerCtrl::GetHLS](#gethls)|ユーザーが選択した色の色合い、明るさ、および彩度の値を取得します。|  
|[CMFCColorPickerCtrl::GetHue](#gethue)|ユーザーが選択した色の色合いを取得します。|  
|[CMFCColorPickerCtrl::GetLuminance](#getluminance)|ユーザーが選択した色の明るさのコンポーネントを取得します。|  
|[CMFCColorPickerCtrl::GetSaturation](#getsaturation)|ユーザーが選択した色の彩度を取得します。|  
|[CMFCColorPickerCtrl::SelectCellHexagon](#selectcellhexagon)|現在の色を RGB 色の指定された要素または指定したセル六角形によって定義されている色に設定します。|  
|[CMFCColorPickerCtrl::SetColor](#setcolor)|現在の色を RGB 色の指定した値に設定します。|  
|[CMFCColorPickerCtrl::SetHLS](#sethls)|現在の色を指定した HLS カラー値に設定します。|  
|[CMFCColorPickerCtrl::SetHue](#sethue)|現在選択されている色の色合いを変更します。|  
|[CMFCColorPickerCtrl::SetLuminance](#setluminance)|現在選択されている色の明るさのコンポーネントを変更します。|  
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](#setluminancebarwidth)|カラー ピッカー コントロールの輝度バーの幅を設定します。|  
|[CMFCColorPickerCtrl::SetOriginalColor](#setoriginalcolor)|初期の選択した色を設定します。|  
|[CMFCColorPickerCtrl::SetPalette](#setpalette)|現在のカラー パレットを設定します。|  
|[CMFCColorPickerCtrl::SetSaturation](#setsaturation)|現在選択されている色の彩度を変更します。|  
|[CMFCColorPickerCtrl::SetType](#settype)|表示するカラー ピッカー コントロールの種類を設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::DrawCursor](#drawcursor)|選択した色をポイントするカーソルが表示されるまでに、フレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 標準の色は、六角形カラー パレットから選択し、輝度バーから作成した色が選択されている色が赤/緑/青表記または色合い/satuaration/輝度表記を使用して指定されています。  
  
 いくつかを以下に示す`CMFCColorPickerCtrl`オブジェクトです。  
  
 ![CMFCColorPickerCtrl ダイアログ ボックス](../../mfc/reference/media/colorpicker.png "colorpicker")  
  
 `CMFCColorPickerCtrl`スタイルの&2; つのペアをサポートします。 16 進数と HEX_GREYSCALE のスタイルは、標準的な色の選択に適しています。 選択と輝度のスタイルは、カスタムの色の選択に適しています。  
  
 組み込むように、次の手順を実行、 `CMFCColorPickerCtrl`  ダイアログ ボックスに管理します。  
  
1.  使用する場合、 **ClassWizard**、ダイアログ ボックス テンプレートに新しいボタン コントロールを挿入 (ため、`CMFCColorPickerCtrl`から継承されたクラス、`CButton`クラス)。  
  
2.  ダイアログ ボックス クラスに新しいボタン コントロールに関連付けられているメンバー変数を挿入します。 変数の型を変更し、`CButton`に`CMFCColorPickerCtrl`します。  
  
3.  挿入、 `WM_INITDIALOG`  ダイアログ ボックス クラス用のメッセージ ハンドラーです。 ハンドラーに、種類、パレット、およびの初期の選択した色を設定、`CMFCColorPickerCtrl`コントロールです。  
  
## <a name="example"></a>例  
 次の例では、構成、`CMFCColorPickerCtrl`オブジェクトのさまざまなメソッドを使用して、`CMFCColorPickerCtrl`クラスです。 例では、その色、色合い、明るさ、および鮮やかさを設定する方法とピッカー コントロールの種類を設定する方法を示します。 この例は、[新しいコントロールのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls&4;](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#5;](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcolorpickerctrl.h  
  
##  <a name="cmfccolorpickerctrl"></a>CMFCColorPickerCtrl::CMFCColorPickerCtrl  
 `CMFCColorPickerCtrl` オブジェクトを構築します。  
  
```  
CMFCColorPickerCtrl();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="drawcursor"></a>CMFCColorPickerCtrl::DrawCursor  
 選択した色をポイントするカーソルが表示されるまでに、フレームワークによって呼び出されます。  
  
```  
virtual void DrawCursor(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 選択した色の周りの四角形の領域を指定します。  
  
### <a name="remarks"></a>コメント  
 選択した色をポイントするカーソルの形状を変更する必要がある場合は、このメソッドをオーバーライドします。  
  
##  <a name="getcolor"></a>CMFCColorPickerCtrl::GetColor  
 ユーザーが選択した色を取得します。  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択した色の RGB 値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gethls"></a>CMFCColorPickerCtrl::GetHLS  
 ユーザーが選択した色の色合い、明るさ、および彩度の値を取得します。  
  
```  
void GetHLS(
    double* hue,  
    double* luminance,  
    double* saturation);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `hue`  
 色合い情報を受け取る double 型の変数へのポインター。  
  
 [出力] `luminance`  
 輝度情報を受け取る double 型の変数へのポインター。  
  
 [出力] `saturation`  
 飽和状態情報を受け取る double 型の変数へのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gethue"></a>CMFCColorPickerCtrl::GetHue  
 ユーザーが選択した色の色合いを取得します。  
  
```  
double GetHue() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択した色の色合いコンポーネント。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getluminance"></a>CMFCColorPickerCtrl::GetLuminance  
 ユーザーが選択した色の明るさのコンポーネントを取得します。  
  
```  
double GetLuminance() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択された色の明るさのコンポーネントです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getsaturation"></a>CMFCColorPickerCtrl::GetSaturation  
 ユーザーが選択した色の鮮やかさの値を取得します。  
  
```  
double GetSaturation() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択された色の彩度。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="selectcellhexagon"></a>CMFCColorPickerCtrl::SelectCellHexagon  
 現在の色を RGB 色の指定された要素または指定したセル六角形によって定義されている色に設定します。  
  
```  
void SelectCellHexagon(
    BYTE R,  
    BYTE G,  
    BYTE B);

 
BOOL SelectCellHexagon(
    int x,  
    int y);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `R`  
 色の赤のコンポーネント。  
  
 [入力] `G`  
 緑色のコンポーネント。  
  
 [入力] `B`  
 青の色のコンポーネント。  
  
 [入力] `x`  
 セル六角形を指すと、カーソルの x 座標。  
  
 [入力] `y`  
 セル六角形を指すと、カーソルの y 座標。  
  
### <a name="return-value"></a>戻り値  
 このメソッドの&2; 番目のオーバー ロードを常に返します`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、現在の色の選択コントロールに対応する色に色を設定の最初のオーバー ロードには、赤、緑、および青の色の要素が指定しました。  
  
 このメソッドの&2; 番目のオーバー ロードは、指定したカーソル位置によってポイントされているセル六角形の色に現在の色を設定します。  
  
##  <a name="setcolor"></a>CMFCColorPickerCtrl::SetColor  
 現在の色を RGB 色の指定した値に設定します。  
  
```  
void SetColor(COLORREF Color);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `Color`  
 RGB 色の値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="sethls"></a>CMFCColorPickerCtrl::SetHLS  
 現在の色を指定した HLS カラー値に設定します。  
  
```  
void SetHLS(
    double hue,  
    double luminance,  
    double saturation,  
    BOOL bInvalidate=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hue`  
 色合いの値。  
  
 [入力] `luminance`  
 輝度の値。  
  
 [入力] `saturation`  
 鮮やかさの値。  
  
 [入力] `bInvalidate`  
 `TRUE`ウィンドウが強制的に新しい色を直ちに更新するにはそれ以外の場合、`FALSE`です。 既定値は、`TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="sethue"></a>CMFCColorPickerCtrl::SetHue  
 現在選択されている色の色合いを変更します。  
  
```  
void SetHue(double Hue);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `Hue`  
 色合いの値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setluminance"></a>CMFCColorPickerCtrl::SetLuminance  
 現在選択されている色の明るさを変更します。  
  
```  
void SetLuminance(double Luminance);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `Luminance`  
 輝度の値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setluminancebarwidth"></a>CMFCColorPickerCtrl::SetLuminanceBarWidth  
 カラー ピッカー コントロールの輝度バーの幅を設定します。  
  
```  
void SetLuminanceBarWidth(int w);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `w`  
 輝度バーの幅はピクセル単位で測定されます。  
  
### <a name="remarks"></a>コメント  
 有効になって輝度バーのサイズを変更するには、このメソッドを使用して、**カスタム**カラー ピッカー コントロールのタブをクリックします。 `w`輝度バーの幅を指定します。 幅の値には、クライアント領域の幅の&4; 分の&3; を超えている場合は無視されます。  
  
##  <a name="setoriginalcolor"></a>CMFCColorPickerCtrl::SetOriginalColor  
 初期の選択した色を設定します。  
  
```  
void SetOriginalColor(COLORREF ref);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ref`  
 RGB 色の値。  
  
### <a name="remarks"></a>コメント  
 カラー ピッカー コントロールが初期化されたときに、このメソッドを呼び出します。  
  
##  <a name="setpalette"></a>CMFCColorPickerCtrl::SetPalette  
 現在のカラー パレットを設定します。  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pPalette`  
 カラー パレットへのポインター。  
  
### <a name="remarks"></a>コメント  
 カラー パレットは、カラー ピッカー コントロールで表示される色の配列を定義します。  
  
##  <a name="setsaturation"></a>CMFCColorPickerCtrl::SetSaturation  
 現在選択されている色の彩度を変更します。  
  
```  
void SetSaturation(double Saturation);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `Saturation`  
 鮮やかさの値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="settype"></a>CMFCColorPickerCtrl::SetType  
 表示するカラー ピッカー コントロールの種類を設定します。  
  
```  
void SetType(COLORTYPE colorType);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `colorType`  
 カラー ピッカー コントロールの種類。  
  
 によって、型が定義されて、`CMFCColorPickerCtrl::COLORTYPE`列挙します。 可能な型は`LUMINANCE`、 `PICKER`、`HEX`と`HEX_GREYSCALE`です。 既定の型は `PICKER` です。  
  
### <a name="remarks"></a>コメント  
 カラー ピッカー コントロールの種類を指定するには、Windows のコントロールが作成される前に、このメソッドを呼び出します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog クラス](../../mfc/reference/cmfccolordialog-class.md)

