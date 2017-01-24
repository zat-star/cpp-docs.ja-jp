---
title: "CMFCColorBar クラス | Microsoft Docs"
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
  - "CMFCColorBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCColorBar クラス"
  - "CMFCColorBar::m_bInternal データ メンバー"
  - "CMFCColorBar::m_bIsEnabled データ メンバー"
  - "CMFCColorBar::m_bIsTearOff データ メンバー"
  - "CMFCColorBar::m_BoxSize データ メンバー"
  - "CMFCColorBar::m_bShowDocColorsWhenDocked データ メンバー"
  - "CMFCColorBar::m_bStdColorDlg データ メンバー"
  - "CMFCColorBar::m_ColorAutomatic データ メンバー"
  - "CMFCColorBar::m_ColorNames データ メンバー"
  - "CMFCColorBar::m_colors データ メンバー"
  - "CMFCColorBar::m_ColorSelected データ メンバー"
  - "CMFCColorBar::m_lstDocColors データ メンバー"
  - "CMFCColorBar::m_nCommandID データ メンバー"
  - "CMFCColorBar::m_nHorzMargin データ メンバー"
  - "CMFCColorBar::m_nHorzOffset データ メンバー"
  - "CMFCColorBar::m_nNumColumns データ メンバー"
  - "CMFCColorBar::m_nNumColumnsVert データ メンバー"
  - "CMFCColorBar::m_nNumRowsHorz データ メンバー"
  - "CMFCColorBar::m_nRowHeight データ メンバー"
  - "CMFCColorBar::m_nVertMargin データ メンバー"
  - "CMFCColorBar::m_nVertOffset データ メンバー"
  - "CMFCColorBar::m_Palette データ メンバー"
  - "CMFCColorBar::m_pParentBtn データ メンバー"
  - "CMFCColorBar::m_pParentRibbonBtn データ メンバー"
  - "CMFCColorBar::m_pWndPropList データ メンバー"
  - "CMFCColorBar::m_strAutoColor データ メンバー"
  - "CMFCColorBar::m_strDocColors データ メンバー"
  - "CMFCColorBar::m_strOtherColor データ メンバー"
ms.assetid: 4756ee40-25a5-4cee-af7f-acab7993d1c7
caps.latest.revision: 35
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCColorBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCColorBar` クラスは、ドキュメントまたはアプリケーションで色を選択できるドッキング コントロール バーを表します。  
  
## 構文  
  
```  
class CMFCColorBar : public CMFCPopupMenuBar  
```  
  
## メンバー  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCColorBar::CMFCColorBar](../Topic/CMFCColorBar::CMFCColorBar.md)|`CMFCColorBar` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCColorBar::ContextToSize](../Topic/CMFCColorBar::ContextToSize.md)|カラー バー コントロールのボタンを格納するために必要な垂直方向と水平方向のマージンを計算し、そのボタンの位置を調整します。|  
|[CMFCColorBar::CreateControl](../Topic/CMFCColorBar::CreateControl.md)|カラー バー コントロール ウィンドウを作成し、`CMFCColorBar` オブジェクトに結び付け、指定されたカラー パレットが格納されるようにコントロールのサイズを変更します。|  
|[CMFCColorBar::Create](../Topic/CMFCColorBar::Create.md)|カラー バー コントロール ウィンドウを作成し、`CMFCColorBar` オブジェクトに結び付けます。|  
|[CMFCColorBar::EnableAutomaticButton](../Topic/CMFCColorBar::EnableAutomaticButton.md)|自動ボタンの表示、非表示を切り替えます。|  
|[CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md)|ユーザーがより多くの色を選択できるダイアログ ボックスの表示を有効または無効にします。|  
|[CMFCColorBar::GetColor](../Topic/CMFCColorBar::GetColor.md)|現在選択されている色を取得します。|  
|[CMFCColorBar::GetCommandID](../Topic/CMFCColorBar::GetCommandID.md)|現在のカラー バー コントロールのコマンド ID を取得します。|  
|[CMFCColorBar::GetHighlightedColor](../Topic/CMFCColorBar::GetHighlightedColor.md)|カラー ボタンにフォーカスがある、つまり、ボタンが*ホット*であることを示す色を取得します。|  
|[CMFCColorBar::GetHorzMargin](../Topic/CMFCColorBar::GetHorzMargin.md)|水平方向のマージンを取得します。水平方向のマージンは、左右の色セルとクライアント領域の境界の間の領域です。|  
|[CMFCColorBar::GetVertMargin](../Topic/CMFCColorBar::GetVertMargin.md)|縦方向のマージンを取得します。縦方向のマージンは、上部または下部の色セルとクライアント領域の境界の間の領域です。|  
|[CMFCColorBar::IsTearOff](../Topic/CMFCColorBar::IsTearOff.md)|現在のカラー バーがドッキング可能であるかどうかを示します。|  
|[CMFCColorBar::SetColor](../Topic/CMFCColorBar::SetColor.md)|現在選択されている色を設定します。|  
|[CMFCColorBar::SetColorName](../Topic/CMFCColorBar::SetColorName.md)|指定した色の新しい名前を設定します。|  
|[CMFCColorBar::SetCommandID](../Topic/CMFCColorBar::SetCommandID.md)|カラー バー コントロールの新しいコマンド ID を設定します。|  
|[CMFCColorBar::SetDocumentColors](../Topic/CMFCColorBar::SetDocumentColors.md)|現在のドキュメントで使用する色のリストを設定します。|  
|[CMFCColorBar::SetHorzMargin](../Topic/CMFCColorBar::SetHorzMargin.md)|水平方向のマージンを設定します。水平方向のマージンは、左右の色セルとクライアント領域の境界の間の領域です。|  
|[CMFCColorBar::SetVertMargin](../Topic/CMFCColorBar::SetVertMargin.md)|縦方向のマージンを設定します。縦方向のマージンは、上部または下部の色セルとクライアント領域の境界の間の領域です。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCColorBar::AdjustLocations](../Topic/CMFCColorBar::AdjustLocations.md)|カラー バー コントロールのカラー ボタンの位置を調整します。|  
|[CMFCColorBar::AllowChangeTextLabels](../Topic/CMFCColorBar::AllowChangeTextLabels.md)|カラー ボタンのテキスト ラベルを変更できるかどうかを示します。|  
|[CMFCColorBar::AllowShowOnList](../Topic/CMFCColorBar::AllowShowOnList.md)|カスタマイズ中にツール バー一覧にカラー バー コントロール オブジェクトを表示できるかどうかを示します。|  
|[CMFCColorBar::CalcSize](../Topic/CMFCColorBar::CalcSize.md)|レイアウト計算の処理の過程でフレームワークによって呼び出されます。|  
|[CMFCColorBar::CreatePalette](../Topic/CMFCColorBar::CreatePalette.md)|指定した色の配列で色を指定して、パレットを初期化します。|  
|[CMFCColorBar::GetColorGridSize](../Topic/CMFCColorBar::GetColorGridSize.md)|カラー バー コントロールのグリッドの行数と列数を計算します。|  
|[CMFCColorBar::GetExtraHeight](../Topic/CMFCColorBar::GetExtraHeight.md)|現在のカラー バーで **\[その他\]** ボタンやドキュメントの色などのさまざまなユーザー インターフェイス要素を表示するために必要な追加の高さを計算します。|  
|[CMFCColorBar::InitColors](../Topic/CMFCColorBar::InitColors.md)|指定したパレットの色またはシステムの既定のパレットで、色の配列を初期化します。|  
|[CMFCColorBar::OnKey](../Topic/CMFCColorBar::OnKey.md)|ユーザーがキーボード ボタンを押したときに、フレームワークによって呼び出されます。|  
|[CMFCColorBar::OnSendCommand](../Topic/CMFCColorBar::OnSendCommand.md)|ポップアップ コントロールの階層構造を閉じるために、フレームワークによって呼び出されます。|  
|[CMFCColorBar::OnUpdateCmdUI](../Topic/CMFCColorBar::OnUpdateCmdUI.md)|カラー バー コントロールのユーザー インターフェイス項目を表示する前に、その項目の有効と無効を切り替えるために、フレームワークによって呼び出されます。|  
|[CMFCColorBar::OpenColorDialog](../Topic/CMFCColorBar::OpenColorDialog.md)|色のダイアログ ボックスを開きます。|  
|[CMFCColorBar::Rebuild](../Topic/CMFCColorBar::Rebuild.md)|カラー バー コントロールを完全に再描画します。|  
|[CMFCColorBar::SelectPalette](../Topic/CMFCColorBar::SelectPalette.md)|指定したデバイス コンテキストの論理パレットを、現在のカラー バー コントロールの親ボタンのパレットに設定します。|  
|[CMFCColorBar::SetPropList](../Topic/CMFCColorBar::SetPropList.md)|`m_pWndPropList` プロテクト データ メンバーを、プロパティ グリッド コントロールへの指定したポインターに設定します。|  
|[CMFCColorBar::ShowCommandMessageString](../Topic/CMFCColorBar::ShowCommandMessageString.md)|カラー バー コントロールを所有するフレーム ウィンドウに対して、ステータス バーのメッセージ行の更新を要求します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|`m_bInternal`|マウス イベントが処理されるかどうかを表すブール値フィールド。  通常、このフィールドが `TRUE` で、カスタマイズ モードが `FALSE` の場合は、マウス イベントが処理されます。|  
|`m_bIsEnabled`|コントロールが有効かどうかを示すブール値。|  
|`m_bIsTearOff`|カラー バー コントロールがドッキングをサポートするかどうかを示すブール値。|  
|`m_BoxSize`|カラー バー グリッドのセルのサイズを指定する [CSize](../../atl-mfc-shared/reference/csize-class.md) オブジェクト。|  
|`m_bShowDocColorsWhenDocked`|カラー バーがドッキングされたときにドキュメントの色を表示するかどうかを示すブール値。  詳細については、「[CMFCColorBar::SetDocumentColors](../Topic/CMFCColorBar::SetDocumentColors.md)」を参照してください。|  
|`m_bStdColorDlg`|標準システムの色のダイアログ ボックスを表示するか、[CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) ダイアログ ボックスを表示するかを示すブール値。  詳細については、「[CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md)」を参照してください。|  
|`m_ColorAutomatic`|現在の自動設定の色を格納する [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)。  詳細については、「[CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md)」を参照してください。|  
|`m_ColorNames`|RGB カラーのセットをその名前と関連付ける [CMap](../../mfc/reference/cmap-class.md) オブジェクト。|  
|`m_colors`|カラー バー コントロールに表示される色を含む [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 値の [CArray](../../mfc/reference/carray-class.md)。|  
|`m_ColorSelected`|ユーザーがカラー バー コントロールから現在選択している色を示す [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 値。|  
|`m_lstDocColors`|ドキュメントで現在使用されている色を含む [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 値の [CList](../../mfc/reference/clist-class.md)。|  
|`m_nCommandID`|カラー ボタンのコマンド ID を示す符号なし整数。|  
|`m_nHorzMargin`|色のグリッドにあるカラー ボタン間の水平マージンを示す整数。|  
|`m_nHorzOffset`|カラー ボタンの中心への水平オフセットを示す整数。  この値は、テキストまたはイメージに加えて色がボタンに表示されている場合に有効です。|  
|`m_nNumColumns`|色のカラー バー コントロール グリッドの列数を示す整数。|  
|`m_nNumColumnsVert`|色の垂直方向のグリッドの列数を示す整数。|  
|`m_nNumRowsHorz`|色の水平方向のグリッドの列数を示す整数。|  
|`m_nRowHeight`|色のグリッドにあるカラー ボタンの行の高さを示す整数。|  
|`m_nVertMargin`|色のグリッドにあるカラー ボタン間の垂直マージンを示す整数。|  
|`m_nVertOffset`|カラー ボタンの中心への垂直オフセットを示す整数。  この値は、テキストまたはイメージに加えて色がボタンに表示されている場合に有効です。|  
|`m_Palette`|カラー バー コントロールで使用される色の [CPalette](../../mfc/reference/cpalette-class.md)。|  
|`m_pParentBtn`|現在のボタンの親である [CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md) オブジェクトへのポインター。  この値は、カラー ボタンがツール バーの階層またはカラー プロパティ グリッド コントロールにある場合に有効です。|  
|`m_pParentRibbonBtn`|リボン上にあり、現在のボタンの親ボタンである [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md) オブジェクトへのポインター。  この値は、カラー ボタンがツール バーの階層またはカラー プロパティ グリッド コントロールにある場合に有効です。|  
|`m_pWndPropList`|[CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) オブジェクトへのポインター。|  
|`m_strAutoColor`|**\[自動\]** ボタンに表示されるテキストである [CString](../../atl-mfc-shared/reference/cstringt-class.md)。  詳細については、「[CMFCColorBar::EnableAutomaticButton](../Topic/CMFCColorBar::EnableAutomaticButton.md)」を参照してください。|  
|`m_strDocColors`|ドキュメントの色ボタンに表示されるテキストである [CString](../../atl-mfc-shared/reference/cstringt-class.md)。  詳細については、「[CMFCColorBar::SetDocumentColors](../Topic/CMFCColorBar::SetDocumentColors.md)」を参照してください。|  
|`m_strOtherColor`|*\[その他\]* ボタンに表示されるテキストである [CString](../../atl-mfc-shared/reference/cstringt-class.md)。  詳細については、「[CMFCColorBar::EnableOtherButton](../Topic/CMFCColorBar::EnableOtherButton.md)」を参照してください。|  
  
## 解説  
 通常は、`CMFCColorBar` オブジェクトを直接作成しないでください。  代わりに、[CMFCColorMenuButton クラス](../../mfc/reference/cmfccolormenubutton-class.md) \(メニューおよびツール バーで使用されます\) または [CMFCColorButton クラス](../../mfc/reference/cmfccolorbutton-class.md)により `CMFCColorBar` オブジェクトが作成されます。  
  
 `CMFCColorBar` クラスには、次の機能が用意されています。  
  
-   ドキュメントの色のリストを自動的に調整します。  
  
-   その状態をドキュメントの状態と共に保存および復元します。  
  
-   "自動" ボタンを管理します。  
  
-   [CMFCColorPickerCtrl クラス](../../mfc/reference/cmfccolorpickerctrl-class.md) コントロールを使用して、カスタムの色を選択します。  
  
-   "ティアオフ" 状態をサポートします \([CMFCColorMenuButton クラス](../../mfc/reference/cmfccolormenubutton-class.md)により作成される場合\)。  
  
 `CMFCColorBar` 機能をアプリケーションに組み込むには、次の操作を行います。  
  
1.  標準メニュー ボタンを作成して ID \(この例では ID\_CHAR\_COLOR\) を割り当てます。  
  
2.  フレーム ウィンドウ クラスで、[CFrameWndEx::OnShowPopupMenu](../Topic/CFrameWndEx::OnShowPopupMenu.md) メソッドをオーバーライドして、\([CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md) を呼び出すことにより\) 標準メニュー ボタンを [CMFCColorMenuButton クラス](../../mfc/reference/cmfccolormenubutton-class.md) オブジェクトと置き換えます。  
  
3.  すべてのスタイルを設定し、[CMFCColorMenuButton クラス](../../mfc/reference/cmfccolormenubutton-class.md) の作成中に `CMFCColorBar` オブジェクトの機能を有効または無効にします。  フレームワークが `CreatePopupMenu` メソッドを呼び出した後、`CMFCColorMenuButton` オブジェクトにより `CMFCColorBar` オブジェクトが動的に作成されます。  
  
 ユーザーがカラー バー コントロール ボタンをクリックすると、フレームワークは `ON_COMMAND` マクロを使用してカラー バー コントロールに通知します。  マクロでは、コマンド ID パラメーターは手順 1. でカラー バー コントロール ボタンに割り当てた値 \(この例では ID\_CHAR\_COLOR\) になります。  詳細については、「[CMFCColorMenuButton クラス](../../mfc/reference/cmfccolormenubutton-class.md)」、「[CMFCColorButton クラス](../../mfc/reference/cmfccolorbutton-class.md)」、「[CMFCColorPickerCtrl クラス](../../mfc/reference/cmfccolorpickerctrl-class.md)」、「[CFrameWndEx クラス](../../mfc/reference/cframewndex-class.md)」、および「[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)」を参照してください。  
  
## 使用例  
 `CMFCColorBar` クラスのさまざまなメソッドを使用してカラー バーを設定する方法を、次の例に示します。  これらのメソッドは、水平マージンと垂直マージンを設定して、その他ボタンを有効にし、カラー バー コントロール ウィンドウを作成して、現在選択されている色を設定します。  この例では [新しいコントロールのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!CODE [NVC_MFC_NewControls#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#1)]  
[!CODE [NVC_MFC_NewControls#2](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#2)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)  
  
 [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)  
  
## 必要条件  
 **ヘッダー :** afxcolorbar.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)