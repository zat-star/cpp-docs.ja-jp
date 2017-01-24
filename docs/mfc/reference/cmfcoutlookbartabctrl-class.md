---
title: "CMFCOutlookBarTabCtrl クラス | Microsoft Docs"
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
  - "CMFCOutlookBarTabCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCOutlookBarTabCtrl クラス"
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
caps.latest.revision: 26
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCOutlookBarTabCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Microsoft Outlook の**ナビゲーション ウィンドウ**と同じ外観を持つタブ コントロールです。  
  
## 構文  
  
```  
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|既定のコンストラクターです。|  
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCOutlookBarTabCtrl::AddControl](../Topic/CMFCOutlookBarTabCtrl::AddControl.md)|Windows コントロールを新しいタブとして Outlook バーに追加します。|  
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|ユーザーがタブの名前を変更するときに表示されるエディット ボックスのサイズを決定するために、フレームワークによって呼び出されます。  \(`CMFCBaseTabCtrl::CalcRectEdit` をオーバーライドします。\)|  
|[CMFCOutlookBarTabCtrl::CanShowFewerPageButtons](../Topic/CMFCOutlookBarTabCtrl::CanShowFewerPageButtons.md)|サイズ変更の操作中に、Outlook バーに表示されるタブ ページ ボタンの数を現在より減らすことができるかどうかを判定するために、フレームワークによって呼び出されます。|  
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](../Topic/CMFCOutlookBarTabCtrl::CanShowMorePageButtons.md)|サイズ変更の操作中に、Outlook バーに表示されるタブ ページ ボタンの数を現在より増やすことができるかどうかを判定するために、フレームワークによって呼び出されます。|  
|[CMFCOutlookBarTabCtrl::Create](../Topic/CMFCOutlookBarTabCtrl::Create.md)|Outlook バー タブ コントロールを作成します。|  
|`CMFCOutlookBarTabCtrl::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークによって使用されます。|  
|[CMFCOutlookBarTabCtrl::EnableAnimation](../Topic/CMFCOutlookBarTabCtrl::EnableAnimation.md)|アクティブなタブの切り替え中に発生するアニメーションを有効にするかどうかを指定します。|  
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](../Topic/CMFCOutlookBarTabCtrl::EnableInPlaceEdit.md)|ユーザーが Outlook バーのタブ ボタンに表示されるテキスト ラベルを変更できるかどうかを指定します。  \([CMFCBaseTabCtrl::EnableInPlaceEdit](../Topic/CMFCBaseTabCtrl::EnableInPlaceEdit.md) をオーバーライドします。\)|  
|[CMFCOutlookBarTabCtrl::EnableScrollButtons](../Topic/CMFCOutlookBarTabCtrl::EnableScrollButtons.md)|ユーザーが Outlook バー ペインの各ボタンをスクロールするボタンを有効にするために、フレームワークによって呼び出されます。|  
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|指定した点を含むペインを識別します。  \([CMFCBaseTabCtrl::FindTargetWnd](../Topic/CMFCBaseTabCtrl::FindTargetWnd.md) をオーバーライドします。\)|  
|[CMFCOutlookBarTabCtrl::GetBorderSize](../Topic/CMFCOutlookBarTabCtrl::GetBorderSize.md)|Outlook タブ コントロールの境界線のサイズを返します。|  
|`CMFCOutlookBarTabCtrl::GetTabArea`|タブ コントロールのタブ領域のサイズと位置を取得します。  \([CMFCBaseTabCtrl::GetTabArea](../Topic/CMFCBaseTabCtrl::GetTabArea.md) をオーバーライドします。\)|  
|`CMFCOutlookBarTabCtrl::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](../Topic/CMFCOutlookBarTabCtrl::GetVisiblePageButtons.md)||  
|[CMFCOutlookBarTabCtrl::IsAnimation](../Topic/CMFCOutlookBarTabCtrl::IsAnimation.md)|アクティブなタブの切り替え中に発生したアニメーションが有効かどうかを判定します。|  
|[CMFCOutlookBarTabCtrl::IsMode2003](../Topic/CMFCOutlookBarTabCtrl::IsMode2003.md)|Outlook バー タブ コントロールが Microsoft Outlook 2003 をエミュレートするモードになっているかどうかを判定します。|  
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|点がタブ領域の内部にあるかどうかを確認します。  \([CMFCBaseTabCtrl::IsPtInTabArea](../Topic/CMFCBaseTabCtrl::IsPtInTabArea.md) をオーバーライドします。\)|  
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|タブが切り離せるかどうかを判定します。  \([CMFCBaseTabCtrl::IsTabDetachable](../Topic/CMFCBaseTabCtrl::IsTabDetachable.md) をオーバーライドします。\)|  
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|タブが挿入または削除されると、フレームワークによって呼び出されます。  \(`CMFCBaseTabCtrl::OnChangeTabs` をオーバーライドします。\)|  
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](../Topic/CMFCOutlookBarTabCtrl::OnShowFewerPageButtons.md)|表示されるタブ ページ ボタンの数を減らすために、フレームワークによって呼び出されます。|  
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](../Topic/CMFCOutlookBarTabCtrl::OnShowMorePageButtons.md)|表示されるタブ ページ ボタンの数を増やすために、フレームワークによって呼び出されます。|  
|[CMFCOutlookBarTabCtrl::OnShowOptions](../Topic/CMFCOutlookBarTabCtrl::OnShowOptions.md)|**\[ナビゲーション ウィンドウ オプション\]** ダイアログ ボックスを表示します。|  
|`CMFCOutlookBarTabCtrl::RecalcLayout`|タブ コントロールの内部レイアウトを再計算します。  \([CMFCBaseTabCtrl::RecalcLayout](../Topic/CMFCBaseTabCtrl::RecalcLayout.md) をオーバーライドします。\)|  
|[CMFCOutlookBarTabCtrl::SetActiveTab](../Topic/CMFCOutlookBarTabCtrl::SetActiveTab.md)|アクティブなタブを設定します。  \([CMFCBaseTabCtrl::SetActiveTab](../Topic/CMFCBaseTabCtrl::SetActiveTab.md) をオーバーライドします。\)|  
|[CMFCOutlookBarTabCtrl::SetBorderSize](../Topic/CMFCOutlookBarTabCtrl::SetBorderSize.md)|Outlook タブ コントロールの境界線のサイズを設定します。|  
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](../Topic/CMFCOutlookBarTabCtrl::SetPageButtonTextAlign.md)|Outlook バーのタブ ボタンに表示されるテキスト ラベルの配置を設定します。|  
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](../Topic/CMFCOutlookBarTabCtrl::SetToolbarImageList.md)|Outlook 2003 モードの Outlook バーの下部に表示されるアイコンが含まれたビットマップを設定します \(「[CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)」を参照\)。|  
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](../Topic/CMFCOutlookBarTabCtrl::SetVisiblePageButtons.md)||  
  
## 解説  
 ドッキングをサポートする Outlook バーを作成するには、`CMFCOutlookBar` オブジェクトを使用して Outlook バー タブ コントロールをホストします。  詳細については、「[CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)」を参照してください。  
  
## 使用例  
 `CMFCOutlookBarTabCtrl` オブジェクトを初期化して `CMFCOutlookBarTabCtrl` クラスのさまざまなメソッドを使用する方法を次の例に示します。  この例は、Outlook バーのタブ ページ ボタンのテキスト ラベルをその場で編集できるようにする方法、アニメーションを有効にする方法、ユーザーが Outlook バー ペインのボタンをスクロールするためのスクロール ハンドルを有効にする方法、Outlook タブ コントロールの境界線のサイズを設定する方法、および Outlook バーのタブ ボタンのテキスト ラベルの整列を設定する方法を示しています。  このコード スニペットは [Outlook のデモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!CODE [NVC_MFC_OutlookDemo#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_OutlookDemo#1)]  
[!CODE [NVC_MFC_OutlookDemo#2](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_OutlookDemo#2)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)  
  
## 必要条件  
 **ヘッダー :** afxoutlookbartabctrl.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md)   
 [CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)