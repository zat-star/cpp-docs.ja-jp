---
title: "CMFCColorPickerCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCColorPickerCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorPickerCtrl クラス"
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CMFCColorPickerCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCColorPickerCtrl` クラスは、色の選択に使用するコントロールの機能を提供します。  
  
## 構文  
  
```  
class CMFCColorPickerCtrl : public CButton  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCColorPickerCtrl::CMFCColorPickerCtrl](../Topic/CMFCColorPickerCtrl::CMFCColorPickerCtrl.md)|`CMFCColorPickerCtrl` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCColorPickerCtrl::GetColor](../Topic/CMFCColorPickerCtrl::GetColor.md)|ユーザーが選択した色を取得します。|  
|[CMFCColorPickerCtrl::GetHLS](../Topic/CMFCColorPickerCtrl::GetHLS.md)|ユーザーが選択した色の色合い、輝度、および彩度の値を取得します。|  
|[CMFCColorPickerCtrl::GetHue](../Topic/CMFCColorPickerCtrl::GetHue.md)|ユーザーが選択した色の、色合いコンポーネントを取得します。|  
|[CMFCColorPickerCtrl::GetLuminance](../Topic/CMFCColorPickerCtrl::GetLuminance.md)|ユーザーが選択した色の輝度コンポーネントを取得します。|  
|[CMFCColorPickerCtrl::GetSaturation](../Topic/CMFCColorPickerCtrl::GetSaturation.md)|ユーザーが選択した色の彩度コンポーネントを取得します。|  
|[CMFCColorPickerCtrl::SelectCellHexagon](../Topic/CMFCColorPickerCtrl::SelectCellHexagon.md)|現在の色を、指定した RGB 色要素または指定したセル六角形で定義された色に設定します。|  
|[CMFCColorPickerCtrl::SetColor](../Topic/CMFCColorPickerCtrl::SetColor.md)|現在の色を、指定した RGB カラー値に設定します。|  
|[CMFCColorPickerCtrl::SetHLS](../Topic/CMFCColorPickerCtrl::SetHLS.md)|現在の色を、指定した HLS カラー値に設定します。|  
|[CMFCColorPickerCtrl::SetHue](../Topic/CMFCColorPickerCtrl::SetHue.md)|現在選択されている色の色合いコンポーネントを変更します。|  
|[CMFCColorPickerCtrl::SetLuminance](../Topic/CMFCColorPickerCtrl::SetLuminance.md)|現在選択されている色の輝度コンポーネントを変更します。|  
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](../Topic/CMFCColorPickerCtrl::SetLuminanceBarWidth.md)|カラー ピッカー コントロールの輝度バーの幅を設定します。|  
|[CMFCColorPickerCtrl::SetOriginalColor](../Topic/CMFCColorPickerCtrl::SetOriginalColor.md)|最初に選択する色を設定します。|  
|[CMFCColorPickerCtrl::SetPalette](../Topic/CMFCColorPickerCtrl::SetPalette.md)|現在のカラー パレットを設定します。|  
|[CMFCColorPickerCtrl::SetSaturation](../Topic/CMFCColorPickerCtrl::SetSaturation.md)|現在選択されている色の彩度コンポーネントを変更します。|  
|[CMFCColorPickerCtrl::SetType](../Topic/CMFCColorPickerCtrl::SetType.md)|表示するカラー ピッカー コントロールの種類を設定します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCColorPickerCtrl::DrawCursor](../Topic/CMFCColorPickerCtrl::DrawCursor.md)|選択した色をポイントするカーソルを表示する前に、フレームワークによって呼び出されます。|  
  
## 解説  
 標準色は六角形カラー パレットから選択され、カスタム色は輝度バーから選択されます。輝度バーでは、色を赤\/緑\/青または色合い\/彩度\/輝度で指定します。  
  
 次の図に `CMFCColorPickerCtrl` オブジェクトをいくつか示します。  
  
 ![CMFCColorPickerCtrl ダイアログ ボックス](../../mfc/reference/media/colorpicker.png "ColorPicker")  
  
 `CMFCColorPickerCtrl` はスタイルのペアを 2 組サポートします。  標準色の選択には HEX スタイルと HEX\_GREYSCALE スタイルが適しています。  カスタム色の選択には、PICKER スタイルと LUMINANCE スタイルが適しています。  
  
 `CMFCColorPickerCtrl` コントロールをダイアログ ボックスに組み込むには、次の手順に従います。  
  
1.  **ClassWizard** を使用する場合は、新しいボタン コントロールをダイアログ ボックス テンプレートに挿入します \(`CMFCColorPickerCtrl` クラスが `CButton` クラスを継承しているため\)。  
  
2.  新しいボタン コントロールに関連付けられているメンバー変数をダイアログ ボックス クラスに挿入します。  次に、変数の型を `CButton` から `CMFCColorPickerCtrl` に変更します。  
  
3.  ダイアログ ボックス クラスの `WM_INITDIALOG` メッセージ ハンドラーを挿入します。  ハンドラーで、`CMFCColorPickerCtrl` コントロールの種類、パレット、および初期選択色を設定します。  
  
## 使用例  
 次の例は、`CMFCColorPickerCtrl` クラスのさまざまなメソッドを使用して `CMFCColorPickerCtrl` オブジェクトを構成する方法について説明しています。  具体的には、ピッカー コントロールの種類の設定方法と、その色、色合い、輝度、および彩度の設定方法を示しています。  この例では [新しいコントロールのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!CODE [NVC_MFC_NewControls#4](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#4)]  
[!CODE [NVC_MFC_NewControls#5](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#5)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)  
  
## 必要条件  
 **ヘッダー :** afxcolorpickerctrl.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCColorDialog クラス](../../mfc/reference/cmfccolordialog-class.md)