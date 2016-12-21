---
title: "CMFCAutoHideButton クラス | Microsoft Docs"
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
  - "CMFCAutoHideButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCAutoHideButton クラス"
ms.assetid: c80e6b8b-25ca-4d12-9d27-457731028ab0
caps.latest.revision: 33
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCAutoHideButton クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非表示になるように構成されている [CDockablePane クラス](../Topic/CDockablePane%20Class.md)を表示または非表示にするボタンです。  
  
## 構文  
  
```  
class CMFCAutoHideButton : public CObject  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCAutoHideButton::BringToTop](../Topic/CMFCAutoHideButton::BringToTop.md)||  
|[CMFCAutoHideButton::Create](../Topic/CMFCAutoHideButton::Create.md)|自動的に隠すボタンを作成して初期化します。|  
|[CMFCAutoHideButton::GetAlignment](../Topic/CMFCAutoHideButton::GetAlignment.md)|自動的に隠すボタンの配置を取得します。|  
|[CMFCAutoHideButton::GetAutoHideWindow](../Topic/CMFCAutoHideButton::GetAutoHideWindow.md)|自動的に隠すボタンに関連付けられている [CDockablePane](../Topic/CDockablePane%20Class.md) オブジェクトを返します。|  
|[CMFCAutoHideButton::GetParentToolBar](../Topic/CMFCAutoHideButton::GetParentToolBar.md)||  
|[CMFCAutoHideButton::GetRect](../Topic/CMFCAutoHideButton::GetRect.md)||  
|[CMFCAutoHideButton::GetSize](../Topic/CMFCAutoHideButton::GetSize.md)|自動的に隠すボタンのサイズを調べます。|  
|[CMFCAutoHideButton::GetTextSize](../Topic/CMFCAutoHideButton::GetTextSize.md)|自動的に隠すボタンのテキスト ラベルのサイズを返します。|  
|[CMFCAutoHideButton::HighlightButton](../Topic/CMFCAutoHideButton::HighlightButton.md)|自動的に隠すボタンを強調表示します。|  
|[CMFCAutoHideButton::IsActive](../Topic/CMFCAutoHideButton::IsActive.md)|自動的に隠すボタンがアクティブかどうかを示します。|  
|[CMFCAutoHideButton::IsHighlighted](../Topic/CMFCAutoHideButton::IsHighlighted.md)|自動的に隠すボタンの強調表示状態を返します。|  
|[CMFCAutoHideButton::IsHorizontal](../Topic/CMFCAutoHideButton::IsHorizontal.md)|自動的に隠すボタンの表示方向が水平と垂直のどちらであるかを判断します。|  
|[CMFCAutoHideButton::IsTop](../Topic/CMFCAutoHideButton::IsTop.md)||  
|[CMFCAutoHideButton::IsVisible](../Topic/CMFCAutoHideButton::IsVisible.md)|ボタンが表示されるかどうかを示します。|  
|[CMFCAutoHideButton::Move](../Topic/CMFCAutoHideButton::Move.md)||  
|[CMFCAutoHideButton::OnDraw](../Topic/CMFCAutoHideButton::OnDraw.md)|フレームワークは、自動的に隠すボタンを描画するときにこのメソッドを呼び出します。|  
|[CMFCAutoHideButton::OnDrawBorder](../Topic/CMFCAutoHideButton::OnDrawBorder.md)|フレームワークは、自動的に隠すボタンの境界線を描画するときにこのメソッドを呼び出します。|  
|[CMFCAutoHideButton::OnFillBackground](../Topic/CMFCAutoHideButton::OnFillBackground.md)|フレームワークは、自動的に隠すボタンの背景を塗りつぶすときにこのメソッドを呼び出します。|  
|[CMFCAutoHideButton::ReplacePane](../Topic/CMFCAutoHideButton::ReplacePane.md)||  
|[CMFCAutoHideButton::ShowAttachedWindow](../Topic/CMFCAutoHideButton::ShowAttachedWindow.md)|関連付けられている [CDockablePane クラス](../Topic/CDockablePane%20Class.md)の表示と非表示を切り替えます。|  
|[CMFCAutoHideButton::ShowButton](../Topic/CMFCAutoHideButton::ShowButton.md)|自動的に隠すボタンの表示と非表示を切り替えます。|  
|[CMFCAutoHideButton::UnSetAutoHideMode](../Topic/CMFCAutoHideButton::UnSetAutoHideMode.md)||  
  
## 解説  
 作成時に、`CMFCAutoHideButton` オブジェクトは、[CDockablePane クラス](../Topic/CDockablePane%20Class.md)にアタッチされます。  ユーザーが `CMFCAutoHideButton` オブジェクトと対話操作を行うと、`CDockablePane` オブジェクトの非表示と表示が切り替えられます。  
  
 既定では、ユーザーが自動非表示をオンにすると、フレームワークが自動的に `CMFCAutoHideButton` を作成します。  フレームワークは、`CMFCAutoHideButton` クラスではなく、カスタム UI クラスの要素を作成できます。  フレームワークが使用するカスタム UI クラスを指定するには、静的メンバー変数 `CMFCAutoHideBar::m_pAutoHideButtonRTS` をカスタム UI クラスと等しくなるように設定します。  既定では、この変数は `CMFCAutoHideButton` に設定されます。  
  
## 使用例  
 `CMFCAutoHideButton` オブジェクトを構築して `CMFCAutoHideButton` クラスのさまざまなメソッドを使用する方法を次の例に示します。  この例では、`Create` メソッドを使用して `CMFCAutoHideButton` オブジェクトを初期化する方法、関連付けられている `CDockablePane` クラスを表示する方法、および自動非表示ボタンを表示する方法を示しています。  
  
 [!code-cpp[NVC_MFC_RibbonApp#32](../../mfc/reference/codesnippet/CPP/cmfcautohidebutton-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md)  
  
## 必要条件  
 **ヘッダー:** afxautohidebutton.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCAutoHideBar クラス](../Topic/CMFCAutoHideBar%20Class.md)   
 [CAutoHideDockSite クラス](../../mfc/reference/cautohidedocksite-class.md)