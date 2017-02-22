---
title: "CMFCOutlookBarPane クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCOutlookBarPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanBeRestored メソッド"
  - "CMFCOutlookBarPane クラス"
  - "Dock メソッド"
  - "IsChangeState メソッド"
  - "OnBeforeFloat メソッド"
  - "RestoreOriginalstate メソッド"
  - "SmartUpdate メソッド"
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCOutlookBarPane クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Outlook バー \([CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)\) に挿入できる、[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md) から派生したコントロールです。  Outlook バー ペインには、大きいボタンの列があります。  ボタンのリストがペインより長い場合、ユーザーはリストを上下にスクロールできます。  ユーザーが Outlook バー ペインを Outlook バーから切り離すと、そのペインをフローティング状態にするかメイン フレーム ウィンドウにドッキングできます。  
  
## 構文  
  
```  
class CMFCOutlookBarPane : public CMFCToolBar  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|既定のコンストラクターです。|  
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCOutlookBarPane::AddButton](../Topic/CMFCOutlookBarPane::AddButton.md)|Outlook バー ペインにボタンを追加します。|  
|[CMFCOutlookBarPane::CanBeAttached](../Topic/CMFCOutlookBarPane::CanBeAttached.md)|ペインを別のペインまたはフレーム ウィンドウにドッキングできるかどうかを判定します。  \([CBasePane::CanBeAttached](../Topic/CBasePane::CanBeAttached.md) をオーバーライドします\)。|  
|`CMFCOutlookBarPane::CanBeRestored`|カスタマイズ後にツール バーを元の状態に復元できるかどうかを判断します。  \([CMFCToolBar::CanBeRestored](../Topic/CMFCToolBar::CanBeRestored.md) をオーバーライドします\)。|  
|[CMFCOutlookBarPane::ClearAll](../Topic/CMFCOutlookBarPane::ClearAll.md)|Outlook バー ペインのイメージで使用されているリソースを解放します。|  
|[CMFCOutlookBarPane::Create](../Topic/CMFCOutlookBarPane::Create.md)|Outlook バー ペインを作成します。|  
|`CMFCOutlookBarPane::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークによって使用されます。|  
|`CMFCOutlookBarPane::Dock`|Outlook バー ペインをドッキングするために、フレームワークによって呼び出されます \(`CPane::Dock` をオーバーライドします\)。|  
|[CMFCOutlookBarPane::EnablePageScrollMode](../Topic/CMFCOutlookBarPane::EnablePageScrollMode.md)|Outlook バー ペインのスクロール バーの矢印ボタンをクリックしたときに、ボタンのリストをページ単位で進めるかリストのボタン単位で進めるかを指定します。|  
|[CMFCOutlookBarPane::GetRegularColor](../Topic/CMFCOutlookBarPane::GetRegularColor.md)|Outlook バー ペイン用の標準の \(選択されていない\) テキストの色を返します。|  
|`CMFCOutlookBarPane::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
|[CMFCOutlookBarPane::IsBackgroundTexture](../Topic/CMFCOutlookBarPane::IsBackgroundTexture.md)|Outlook バー ペイン用として読み込まれた背景イメージがあるかどうかを判定します。|  
|`CMFCOutlookBarPane::IsChangeState`|フローティング状態のペインをドッキングできるかどうかを判断します   \(`CPane::IsChangeState` をオーバーライドします\)。|  
|[CMFCOutlookBarPane::IsDrawShadedHighlight](../Topic/CMFCOutlookBarPane::IsDrawShadedHighlight.md)|ボタンが強調表示され、背景イメージが表示されたときに、ボタンの境界線を影付きにするかどうかを決定します。|  
|`CMFCOutlookBarPane::OnBeforeFloat`|ペインがフローティング状態になる直前に、フレームワークによって呼び出されます   \([CPane::OnBeforeFloat](../Topic/CPane::OnBeforeFloat.md) をオーバーライドします\)。|  
|[CMFCOutlookBarPane::RemoveButton](../Topic/CMFCOutlookBarPane::RemoveButton.md)|指定されたコマンド ID のボタンを削除します。|  
|`CMFCOutlookBarPane::RestoreOriginalstate`|ツール バーの元の状態を復元します   \([CMFCToolBar::RestoreOriginalState](../Topic/CMFCToolBar::RestoreOriginalState.md) をオーバーライドします\)。|  
|[CMFCOutlookBarPane::SetBackColor](../Topic/CMFCOutlookBarPane::SetBackColor.md)|背景色を設定します。|  
|[CMFCOutlookBarPane::SetBackImage](../Topic/CMFCOutlookBarPane::SetBackImage.md)|背景イメージを設定します。|  
|[CMFCOutlookBarPane::SetDefaultState](../Topic/CMFCOutlookBarPane::SetDefaultState.md)|Outlook バー ペインを元のボタンのセットにリセットします。|  
|[CMFCOutlookBarPane::SetExtraSpace](../Topic/CMFCOutlookBarPane::SetExtraSpace.md)|Outlook バー ペインのボタンの周囲に使用される埋め込みのピクセル数を設定します。|  
|[CMFCOutlookBarPane::SetTextColor](../Topic/CMFCOutlookBarPane::SetTextColor.md)|Outlook バー ペインでの通常のテキストと強調表示されたテキストの色を設定します。|  
|[CMFCOutlookBarPane::SetTransparentColor](../Topic/CMFCOutlookBarPane::SetTransparentColor.md)|Outlook バー ペインの透明色を設定します。|  
|`CMFCOutlookBarPane::SmartUpdate`|Outlook バーを更新するために内部で使用されます   \(`CMFCToolBar::SmartUpdate` をオーバーライドします\)。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCOutlookBarPane::EnableContextMenuItems](../Topic/CMFCOutlookBarPane::EnableContextMenuItems.md)|カスタマイズ モードで表示するショートカット メニュー項目を指定します。|  
|[CMFCOutlookBarPane::RemoveAllButtons](../Topic/CMFCOutlookBarPane::RemoveAllButtons.md)|Outlook バー ペインからすべてのボタンを削除します。  \([CMFCToolBar::RemoveAllButtons](../Topic/CMFCToolBar::RemoveAllButtons.md) をオーバーライドします\)。|  
  
## 解説  
 Outlook バーの実装方法の詳細については、「[CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)」を参照してください。  
  
 Outlook バーの例については、OutlookDemo サンプル プロジェクトを参照してください。  
  
## 使用例  
 次の例は、`CMFCOutlookBarPane` クラスのさまざまなメソッドの使用方法を説明しています。  例では、Outlook バー ペインの作成、ページ スクロール モードの有効化、ドッキングの有効化、Outlook バーの背景色の設定について、その方法を示しています。  このコード スニペットは [Outlook 複数のビューのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews#3](../../mfc/reference/codesnippet/CPP/cmfcoutlookbarpane-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews#4](../../mfc/reference/codesnippet/CPP/cmfcoutlookbarpane-class_2.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)  
  
## 必要条件  
 **ヘッダー :** afxoutlookbarpane.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarTabCtrl クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md)