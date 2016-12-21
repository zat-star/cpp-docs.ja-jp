---
title: "CMFCColorButton クラス | Microsoft Docs"
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
  - "CMFCColorButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorButton クラス"
  - "CMFCColorButton::m_bAltColorDlg データ メンバー"
  - "CMFCColorButton::m_bAutoSetFocus データ メンバー"
  - "CMFCColorButton::m_Color データ メンバー"
  - "CMFCColorButton::m_ColorAutomatic データ メンバー"
  - "CMFCColorButton::m_lstDocColors データ メンバー"
  - "CMFCColorButton::m_nColumns データ メンバー"
  - "CMFCColorButton::m_pPalette データ メンバー"
  - "CMFCColorButton::m_pPopup データ メンバー"
  - "CMFCColorButton::m_strAutoColorText データ メンバー"
  - "CMFCColorButton::m_strDocColorsText データ メンバー"
  - "CMFCColorButton::m_strOtherText データ メンバー"
ms.assetid: 9fdf34ae-4cc5-4c5e-9d89-1c50e8a73699
caps.latest.revision: 34
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCColorButton クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCColorButton` クラスと [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md) クラスを組み合わせて使用して、カラー ピッカー コントロールを実装します。  
  
## 構文  
  
```  
class CMFCColorButton : public CMFCButton  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCColorButton::CMFCColorButton](../Topic/CMFCColorButton::CMFCColorButton.md)|新しい `CMFCColorButton` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCColorButton::EnableAutomaticButton](../Topic/CMFCColorButton::EnableAutomaticButton.md)|標準のカラー ボタンの上にある "自動" ボタンを有効または無効にします   \(標準システムの自動ボタンのラベルは **\[自動\]** です\)。|  
|[CMFCColorButton::EnableOtherButton](../Topic/CMFCColorButton::EnableOtherButton.md)|標準のカラー ボタンの下にある "その他" ボタンを有効または無効にします   \(標準的なシステムの "その他" ボタンのラベルは **\[More Colors\]** です\)。|  
|[CMFCColorButton::GetAutomaticColor](../Topic/CMFCColorButton::GetAutomaticColor.md)|現在の自動設定の色を取得します。|  
|[CMFCColorButton::GetColor](../Topic/CMFCColorButton::GetColor.md)|ボタンの色を取得します。|  
|[CMFCColorButton::SetColor](../Topic/CMFCColorButton::SetColor.md)|ボタンの色を設定します。|  
|[CMFCColorButton::SetColorName](../Topic/CMFCColorButton::SetColorName.md)|色の名前を設定します。|  
|[CMFCColorButton::SetColumnsNumber](../Topic/CMFCColorButton::SetColumnsNumber.md)|カラー ピッカー ダイアログ ボックスの列の数を設定します。|  
|[CMFCColorButton::SetDocumentColors](../Topic/CMFCColorButton::SetDocumentColors.md)|カラー ピッカー ダイアログ ボックスに表示されるドキュメント固有の色のリストを指定します。|  
|[CMFCColorButton::SetPalette](../Topic/CMFCColorButton::SetPalette.md)|標準表示色のパレットを指定します。|  
|[CMFCColorButton::SizeToContent](../Topic/CMFCColorButton::SizeToContent.md)|ボタンのテキスト サイズとイメージ サイズに合わせてボタン コントロールのサイズを変更します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCColorButton::IsDrawXPTheme](../Topic/CMFCColorButton::IsDrawXPTheme.md)|現在のカラー ボタンが Windows XP の visual スタイルで表示されるかどうかを示します。|  
|[CMFCColorButton::OnDraw](../Topic/CMFCColorButton::OnDraw.md)|ボタンのイメージを表示するために、フレームワークによって呼び出されます。|  
|[CMFCColorButton::OnDrawBorder](../Topic/CMFCColorButton::OnDrawBorder.md)|ボタンの境界線を表示するために、フレームワークによって呼び出されます。|  
|[CMFCColorButton::OnDrawFocusRect](../Topic/CMFCColorButton::OnDrawFocusRect.md)|ボタンにフォーカスがあるときに、フォーカスを示す四角形を表示するために、フレームワークによって呼び出されます。|  
|[CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md)|カラー ピッカー ダイアログ ボックスが表示される直前に、フレームワークによって呼び出されます。|  
|[CMFCColorButton::RebuildPalette](../Topic/CMFCColorButton::RebuildPalette.md)|`m_pPalette` プロテクト データ メンバーを初期化して、指定されたパレットまたは既定のシステム パレットを生成します。|  
|[CMFCColorButton::UpdateColor](../Topic/CMFCColorButton::UpdateColor.md)|ユーザーが、カラー ピッカー ダイアログ ボックスのパレットから色を選択すると、フレームワークによって呼び出されます。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|`m_bAltColorDlg`|ブール値。  `TRUE` の場合は、*他*のボタンがクリックされると、フレームワークが[CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) カラー ダイアログ ボックスを表示します。`FALSE` の場合は、システム カラー ダイアログ ボックスを表示します。  既定値 `TRUE` です。  詳細については、「[CMFCColorButton::EnableOtherButton](../Topic/CMFCColorButton::EnableOtherButton.md)」を参照してください。|  
|`m_bAutoSetFocus`|ブール値。  `TRUE` の場合は、カラー メニューが表示されると、フレームワークがそのメニューにフォーカスを設定し、`FALSE` の場合はフォーカスを変更しません。  既定値 `TRUE` です。|  
|[CMFCColorButton::m\_bEnabledInCustomizeMode](../Topic/CMFCColorButton::m_bEnabledInCustomizeMode.md)|カラー ボタンのカスタマイズ モードが有効かどうかを示します。|  
|`m_Color`|[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 値。  現在選択されている色が含まれます。|  
|`m_ColorAutomatic`|[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 値。  現在選択されている既定色が含まれます。|  
|`m_Colors`|[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 値の [CArray](../../mfc/reference/carray-class.md)。  現在使用できる色が含まれます。|  
|`m_lstDocColors`|[COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 値の  [CList](../../mfc/reference/clist-class.md)。  現在のドキュメントの色が含まれます。|  
|`m_nColumns`|整数。  色の選択メニューの色のグリッドに表示する列の数が含まれます。|  
|`m_pPalette`|[CPalette](../../mfc/reference/cpalette-class.md) へのポインター。  現在の色の選択メニューで使用できる色が含まれます。|  
|`m_pPopup`|[CMFCColorPopupMenu クラス](../Topic/CMFCColorPopupMenu%20Class.md) オブジェクトへのポインター。  カラー ボタンをクリックすると表示される色の選択メニュー。|  
|`m_strAutoColorText`|文字列  色の選択メニューの "自動" ボタンのラベル。|  
|`m_strDocColorsText`|文字列  ドキュメントの色を表示する色の選択メニューに含まれるボタンのラベル。|  
|`m_strOtherText`|文字列  色の選択メニューの "その他" ボタンのラベル。|  
  
## 解説  
 既定では、`CMFCColorButton` クラスは、カラー ピッカー ダイアログ ボックスを開くプッシュ ボタンとして動作します。  カラー ピッカー ダイアログ ボックスには、小さいカラー ボタンとカスタム カラー ピッカーを表示する "その他" ボタンの配列が含まれます。  \(標準的なシステムの "その他" ボタンのラベルは **\[More Colors\]** です\)。ユーザーが新しい色を選択すると、`CMFCColorButton` オブジェクトはその変更を反映し、選択された色を表示します。  
  
 カラー ボタン コントロールを、コードに直接作成するか、**ClassWizard** ツールとダイアログ ボックス テンプレートを使用して作成します。  カラー ボタン コントロールを直接作成する場合は、アプリケーションに `CMFCColorButton` 変数を追加し、構造体と `CMFCColorButton` オブジェクトの `Create` メソッドを呼び出します。  **ClassWizard** を使用する場合は、アプリケーションに `CButton` 変数を追加し、変数のタイプを `CButton` から `CMFCColorButton` に変更します。  
  
 カラー ピッカー ダイアログ ボックス \([CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)\) は、フレームワークが `OnLButtonDown` イベント ハンドラーを呼び出すときに [CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md) メソッドによって表示されます。  カスタム カラーの選択をサポートするには、[CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md) メソッドをオーバーライドします。  
  
 `CMFCColorButton` オブジェクトは、`WM_COMMAND | BN_CLICKED` 通知を送信することで、その親に色の変更を知らせます。  親は、[CMFCColorButton::GetColor](../Topic/CMFCColorButton::GetColor.md) メソッドを使用して現在の色を取得します。  
  
## 使用例  
 `CMFCColorButton` クラスのさまざまなメソッドを使用してカラー ボタンを設定する方法を次の例に示します。  メソッドは、カラー ボタンの色と列の数を設定し、自動ボタンとその他ボタンを有効にします。  この例では [ステータス バーのデモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_StatusBarDemo#10](../../mfc/reference/codesnippet/CPP/cmfccolorbutton-class_1.h)]  
[!code-cpp[NVC_MFC_StatusBarDemo#11](../../mfc/reference/codesnippet/CPP/cmfccolorbutton-class_2.cpp)]  
  
## 必要条件  
 **ヘッダー :** afxcolorbutton.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)   
 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCColorButton::OnShowColorPopup](../Topic/CMFCColorButton::OnShowColorPopup.md)   
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)   
 [CPalette クラス](../../mfc/reference/cpalette-class.md)   
 [CArray クラス](../../mfc/reference/carray-class.md)   
 [CList クラス](../../mfc/reference/clist-class.md)   
 [CString](../../atl-mfc-shared/reference/cstringt-class.md)