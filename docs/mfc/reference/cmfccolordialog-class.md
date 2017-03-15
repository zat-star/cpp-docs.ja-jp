---
title: "CMFCColorDialog クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorDialog::m_CurrentColor data member
- CMFCColorDialog::m_pPropSheet data member
- CMFCColorDialog::m_btnColorSelect data member
- CMFCColorDialog class
- CMFCColorDialog::m_wndColors data member
- CMFCColorDialog::m_bIsMyPalette data member
- CMFCColorDialog::m_pColourSheetTwo data member
- CMFCColorDialog::m_NewColor data member
- CMFCColorDialog::m_pPalette data member
- CMFCColorDialog::m_wndStaticPlaceHolder data member
- CMFCColorDialog::m_pColourSheetOne data member
- CMFCColorDialog::m_hcurPicker data member
- CMFCColorDialog::PreTranslateMessage method
- CMFCColorDialog::m_bPickerMode data member
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ac621157e0fcb5bcabef2ae8f367a1b141b4ace0
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolordialog-class"></a>CMFCColorDialog クラス
`CMFCColorDialog`クラスは、色を選択 ダイアログ ボックスを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCColorDialog : public CDialogEx  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorDialog::CMFCColorDialog](#cmfccolordialog)|`CMFCColorDialog` オブジェクトを構築します。|  
|`CMFCColorDialog::~CMFCColorDialog`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCColorDialog::GetColor](#getcolor)|現在選択されている色を返します。|  
|[CMFCColorDialog::GetPalette](#getpalette)|色のパレットを返します。|  
|`CMFCColorDialog::PreTranslateMessage`|ウィンドウのメッセージの変換にディスパッチされる前に、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数です。 構文と詳細については、次を参照してください。 [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)します。 (`CDialogEx::PreTranslateMessage` をオーバーライドします)。|  
|[CMFCColorDialog::RebuildPalette](#rebuildpalette)|パレットをシステム パレットから派生しています。|  
|[CMFCColorDialog::SetCurrentColor](#setcurrentcolor)|現在の選択した色を設定します。|  
|[CMFCColorDialog::SetNewColor](#setnewcolor)|指定した RGB 値に最も近い色を設定します。|  
|[CMFCColorDialog::SetPageOne](#setpageone)|最初のプロパティ ページの RGB 値を選択します。|  
|[CMFCColorDialog::SetPageTwo](#setpagetwo)|2 番目のプロパティ ページの RGB 値を選択します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|`m_bIsMyPalette`|`TRUE`色の選択 ダイアログ ボックスで、独自のカラー パレットを使用する場合、または`FALSE` ダイアログ ボックスがで指定されているパレットを使用するかどうか、`CMFCColorDialog`コンス トラクターです。|  
|`m_bPickerMode`|`TRUE`選択 ダイアログ ボックスでは、ユーザーが色をクリックするときにそれ以外の場合、`FALSE`です。|  
|`m_btnColorSelect`|色のボタンをユーザーが選択されます。|  
|`m_CurrentColor`|現在選択されている色です。|  
|`m_hcurPicker`|色の選択に使用するカーソル。|  
|`m_NewColor`|見込み客に対して選択した色、永続的に選択または元の色を元に戻すことができます。|  
|`m_pColourSheetOne`|色の選択のプロパティ シートの最初のプロパティ ページへのポインター。|  
|`m_pColourSheetTwo`|色の選択のプロパティ シートの&2; 番目のプロパティ ページへのポインター。|  
|`m_pPalette`|現在の論理パレット。|  
|`m_pPropSheet`|色の選択 ダイアログ ボックスのプロパティ シートへのポインター。|  
|`m_wndColors`|カラー ピッカー control オブジェクトです。|  
|`m_wndStaticPlaceHolder`|カラー ピッカーのプロパティ シートのプレース ホルダーは、スタティック コントロールです。|  
  
## <a name="remarks"></a>コメント  
 色の選択 ダイアログ ボックスは、2 つのページのプロパティ シートとして表示されます。 最初のページで、システム パレットから標準的な色を選択します。2 番目のページでは、カスタムの色を選択します。  
  
 構築することができます、`CMFCColorDialog`スタック上のオブジェクトし、し、呼び出す`DoModal`、初期の色をパラメーターとして渡すこと、`CMFCColorDialog`コンス トラクターです。 色の選択 ダイアログ ボックスは、いくつか作成[CMFCColorPickerCtrl クラス](../../mfc/reference/cmfccolorpickerctrl-class.md)各カラー パレットを処理するオブジェクト。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  
  
## <a name="example"></a>例  
 次の例では、多様なメソッドを使用してカラー ダイアログ ボックスを構成する方法、`CMFCColorDialog`クラスです。 例では、現在と、ダイアログ ボックスの新しい色を設定する方法および色 ダイアログ ボックスの&2; つのプロパティ ページで選択した色の赤、緑、および青のコンポーネントを設定する方法を示します。 この例は、[新しいコントロールのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls&#3;](../../mfc/reference/codesnippet/cpp/cmfccolordialog-class_1.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcolordialog.h  
  
##  <a name="a-namecmfccolordialoga--cmfccolordialogcmfccolordialog"></a><a name="cmfccolordialog"></a>CMFCColorDialog::CMFCColorDialog  
 `CMFCColorDialog` オブジェクトを構築します。  
  
```  
CMFCColorDialog(
    COLORREF clrInit=0,  
    DWORD dwFlags=0,  
    CWnd* pParentWnd=NULL,  
    HPALETTE hPal=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `clrInit`  
 既定色を選択します。 値が指定されていない場合は、既定値は RGB(0,0,0) (黒) にします。  
  
 [入力] `dwFlags`  
 (予約済み)  
  
 [入力] `pParentWnd`  
 ダイアログ ボックスの親ウィンドウまたはオーナー ウィンドウへのポインター。  
  
 [入力] `hPal`  
 カラー パレットへのハンドル。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetcolora--cmfccolordialoggetcolor"></a><a name="getcolor"></a>CMFCColorDialog::GetColor  
 カラー ダイアログ ボックスで、ユーザーが選択した色を取得します。  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)色 ダイアログ ボックスで選択した色の RGB 情報を含む値。  
  
### <a name="remarks"></a>コメント  
 呼び出した後に、この関数を呼び出して、`DoModal`メソッドです。  
  
##  <a name="a-namegetpalettea--cmfccolordialoggetpalette"></a><a name="getpalette"></a>CMFCColorDialog::GetPalette  
 現在の色のダイアログ ボックスで使用可能なカラー パレットを取得します。  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CPalette`で指定されたオブジェクト、`CMFCColorDialog`コンス トラクターです。  
  
### <a name="remarks"></a>コメント  
 カラー パレットでは、ユーザーが選択できる色を指定します。  
  
##  <a name="a-namerebuildpalettea--cmfccolordialogrebuildpalette"></a><a name="rebuildpalette"></a>CMFCColorDialog::RebuildPalette  
 パレットをシステム パレットから派生しています。  
  
```  
void RebuildPalette();
```  
  
##  <a name="a-namesetcurrentcolora--cmfccolordialogsetcurrentcolor"></a><a name="setcurrentcolor"></a>CMFCColorDialog::SetCurrentColor  
 ダイアログ ボックスの現在の色を設定します。  
  
```  
void SetCurrentColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rgb`  
 RGB カラー値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetnewcolora--cmfccolordialogsetnewcolor"></a><a name="setnewcolor"></a>CMFCColorDialog::SetNewColor  
 現在の色を最も近い現在パレットの色に設定します。  
  
```  
void SetNewColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rgb`  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) RGB 色を指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetpageonea--cmfccolordialogsetpageone"></a><a name="setpageone"></a>CMFCColorDialog::SetPageOne  
 色のダイアログ ボックスの最初のプロパティ ページで選択した色の赤、緑、および青のコンポーネントを明示的に指定します。  
  
```  
void SetPageOne(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `R`  
 RGB 値の赤の要素を指定します。  
  
 [入力] `G`  
 RGB 値の緑の要素を指定します。  
  
 [入力] `B`  
 RGB 値の青の要素を指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetpagetwoa--cmfccolordialogsetpagetwo"></a><a name="setpagetwo"></a>CMFCColorDialog::SetPageTwo  
 カラー ダイアログ ボックスの&2; 番目のプロパティ ページで選択した色の赤、緑、および青のコンポーネントを明示的に指定します。  
  
```  
void SetPageTwo(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `R`  
 RGB 値の赤の要素を指定します。  
  
 [入力] `G`  
 RGB 値の緑の部分を指定します。  
  
 [入力] `B`  
 RGB 値の青色の部分を指定します。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCColorPickerCtrl クラス](../../mfc/reference/cmfccolorpickerctrl-class.md)

