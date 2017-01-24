---
title: "CMFCColorDialog クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCColorDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorDialog クラス"
  - "CMFCColorDialog::m_bIsMyPalette データ メンバー"
  - "CMFCColorDialog::m_bPickerMode データ メンバー"
  - "CMFCColorDialog::m_btnColorSelect データ メンバー"
  - "CMFCColorDialog::m_CurrentColor データ メンバー"
  - "CMFCColorDialog::m_hcurPicker データ メンバー"
  - "CMFCColorDialog::m_NewColor データ メンバー"
  - "CMFCColorDialog::m_pColourSheetOne データ メンバー"
  - "CMFCColorDialog::m_pColourSheetTwo データ メンバー"
  - "CMFCColorDialog::m_pPalette データ メンバー"
  - "CMFCColorDialog::m_pPropSheet データ メンバー"
  - "CMFCColorDialog::m_wndColors データ メンバー"
  - "CMFCColorDialog::m_wndStaticPlaceHolder データ メンバー"
  - "CMFCColorDialog::PreTranslateMessage メソッド"
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCColorDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCColorDialog` クラスは色選択ダイアログ ボックスを表します。  
  
## 構文  
  
```  
class CMFCColorDialog : public CDialogEx  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCColorDialog::CMFCColorDialog](../Topic/CMFCColorDialog::CMFCColorDialog.md)|`CMFCColorDialog` オブジェクトを構築します。|  
|`CMFCColorDialog::~CMFCColorDialog`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCColorDialog::GetColor](../Topic/CMFCColorDialog::GetColor.md)|現在選択されている色を返します。|  
|[CMFCColorDialog::GetPalette](../Topic/CMFCColorDialog::GetPalette.md)|カラー パレットを返します。|  
|`CMFCColorDialog::PreTranslateMessage`|Windows 関数の [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) や [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) にディスパッチする前にウィンドウ メッセージを変換します。  構文および詳細情報については、「[CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md)」を参照してください。  \(`CDialogEx::PreTranslateMessage` をオーバーライドします。\)|  
|[CMFCColorDialog::RebuildPalette](../Topic/CMFCColorDialog::RebuildPalette.md)|システム パレットからパレットを派生させます。|  
|[CMFCColorDialog::SetCurrentColor](../Topic/CMFCColorDialog::SetCurrentColor.md)|現在選択されている色を設定します。|  
|[CMFCColorDialog::SetNewColor](../Topic/CMFCColorDialog::SetNewColor.md)|指定した RGB 値に最も近い色を設定します。|  
|[CMFCColorDialog::SetPageOne](../Topic/CMFCColorDialog::SetPageOne.md)|最初のプロパティ ページの RGB 値を選択します。|  
|[CMFCColorDialog::SetPageTwo](../Topic/CMFCColorDialog::SetPageTwo.md)|2 番目のプロパティ ページの RGB 値を選択します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|`m_bIsMyPalette`|色選択ダイアログ ボックスで独自のカラー パレットを使用する場合は `TRUE`。`CMFCColorDialog` コンストラクターで指定されたパレットを使用する場合は `FALSE`。|  
|`m_bPickerMode`|ユーザーが選択ダイアログ ボックスから色を選択する場合は `TRUE`。それ以外の場合は `FALSE`。|  
|`m_btnColorSelect`|ユーザーが選択したカラー ボタン。|  
|`m_CurrentColor`|現在選択されている色。|  
|`m_hcurPicker`|色の選択に使用するカーソル。|  
|`m_NewColor`|これから選択される色。この色は、永続的に選択することも、元の色に戻すこともできます。|  
|`m_pColourSheetOne`|色選択プロパティ シートの最初のプロパティ ページへのポインター。|  
|`m_pColourSheetTwo`|色選択プロパティ シートの 2 番目のプロパティ ページへのポインター。|  
|`m_pPalette`|現在の論理パレット。|  
|`m_pPropSheet`|色選択ダイアログ ボックスのプロパティ シートへのポインター。|  
|`m_wndColors`|カラー ピッカー コントロール オブジェクト。|  
|`m_wndStaticPlaceHolder`|カラー ピッカー プロパティ シートのプレースホルダーであるスタティック コントロール。|  
  
## 解説  
 色選択ダイアログ ボックスは、2 ページのプロパティ シートとして表示されます。  最初のページでは、システム パレットから標準の色を選択します。2 番目のページでは、カスタム カラーを選択します。  
  
 スタックで `CMFCColorDialog` オブジェクトを作成し、`CMFCColorDialog` コンストラクターにパラメーターとして初期設定色を渡して `DoModal` を呼び出すことができます。  色選択ダイアログ ボックスに、各カラー パレットを処理するいくつかの [CMFCColorPickerCtrl クラス](../../mfc/reference/cmfccolorpickerctrl-class.md) オブジェクトが作成されます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  
  
## 使用例  
 `CMFCColorDialog` クラスのさまざまなメソッドを使用して色のダイアログ ボックスを設定する方法を次の例に示します。  この例では、ダイアログ ボックスの現在の色と新しい色を設定する方法と、色のダイアログ ボックスの 2 つのプロパティ ページで選択された色の赤、緑、青の各要素を設定する方法を示します。  この例では [新しいコントロールのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!CODE [NVC_MFC_NewControls#3](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#3)]  
  
## 必要条件  
 **ヘッダー :** afxcolordialog.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCColorPickerCtrl クラス](../../mfc/reference/cmfccolorpickerctrl-class.md)