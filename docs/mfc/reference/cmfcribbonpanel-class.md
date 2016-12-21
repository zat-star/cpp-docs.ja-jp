---
title: "CMFCRibbonPanel クラス | Microsoft Docs"
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
  - "CMFCRibbonPanel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonPanel クラス"
ms.assetid: 51d70749-1140-4386-b103-f14082049ba6
caps.latest.revision: 34
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonPanel クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

一連のリボン要素を含むパネルを実装します。  このパネルが描画されると、そのパネルに指定されたサイズに対して可能な限り多くの要素が表示されます。  
  
## 構文  
  
```  
class CMFCRibbonPanel : public CObject  
```  
  
## メンバー  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonPanel::CMFCRibbonPanel](../Topic/CMFCRibbonPanel::CMFCRibbonPanel.md)|`CMFCRibbonPanel` オブジェクトを構築し、初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonPanel::Add](../Topic/CMFCRibbonPanel::Add.md)|リボン要素をパネルに追加します。|  
|[CMFCRibbonPanel::AddSeparator](../Topic/CMFCRibbonPanel::AddSeparator.md)|リボン パネルに区分線を追加します。|  
|[CMFCRibbonPanel::AddToolBar](../Topic/CMFCRibbonPanel::AddToolBar.md)|ツール バーをリボン パネルに追加します。|  
|[CMFCRibbonPanel::FindByData](../Topic/CMFCRibbonPanel::FindByData.md)||  
|[CMFCRibbonPanel::FindByID](../Topic/CMFCRibbonPanel::FindByID.md)|指定したコマンド ID により識別される要素を返します。|  
|[CMFCRibbonPanel::GetCaptionHeight](../Topic/CMFCRibbonPanel::GetCaptionHeight.md)||  
|[CMFCRibbonPanel::GetCount](../Topic/CMFCRibbonPanel::GetCount.md)|リボン パネル内の要素数を返します。|  
|[CMFCRibbonPanel::GetData](../Topic/CMFCRibbonPanel::GetData.md)|パネルに関連付けられているユーザー定義データを返します。|  
|[CMFCRibbonPanel::GetDefaultButton](../Topic/CMFCRibbonPanel::GetDefaultButton.md)||  
|[CMFCRibbonPanel::GetDroppedDown](../Topic/CMFCRibbonPanel::GetDroppedDown.md)||  
|[CMFCRibbonPanel::GetElement](../Topic/CMFCRibbonPanel::GetElement.md)|指定されたインデックス位置にあるリボン要素を返します。|  
|[CMFCRibbonPanel::GetElements](../Topic/CMFCRibbonPanel::GetElements.md)|リボン パネルに含まれるすべての要素を取得します。|  
|[CMFCRibbonPanel::GetElementsByID](../Topic/CMFCRibbonPanel::GetElementsByID.md)||  
|[CMFCRibbonPanel::GetFocused](../Topic/CMFCRibbonPanel::GetFocused.md)|フォーカスのある要素を返します。|  
|[CMFCRibbonPanel::GetGalleryRect](../Topic/CMFCRibbonPanel::GetGalleryRect.md)|ギャラリー要素の外接する四角形を返します。|  
|[CMFCRibbonPanel::GetHighlighted](../Topic/CMFCRibbonPanel::GetHighlighted.md)||  
|[CMFCRibbonPanel::GetIndex](../Topic/CMFCRibbonPanel::GetIndex.md)||  
|[CMFCRibbonPanel::GetItemIDsList](../Topic/CMFCRibbonPanel::GetItemIDsList.md)||  
|[CMFCRibbonPanel::GetName](../Topic/CMFCRibbonPanel::GetName.md)||  
|[CMFCRibbonPanel::GetParentButton](../Topic/CMFCRibbonPanel::GetParentButton.md)||  
|[CMFCRibbonPanel::GetParentCategory](../Topic/CMFCRibbonPanel::GetParentCategory.md)|リボン パネルの親カテゴリを返します。|  
|[CMFCRibbonPanel::GetParentMenuBar](../Topic/CMFCRibbonPanel::GetParentMenuBar.md)||  
|[CMFCRibbonPanel::GetPreferedMenuLocation](../Topic/CMFCRibbonPanel::GetPreferedMenuLocation.md)||  
|[CMFCRibbonPanel::GetPressed](../Topic/CMFCRibbonPanel::GetPressed.md)||  
|[CMFCRibbonPanel::GetRect](../Topic/CMFCRibbonPanel::GetRect.md)||  
|[CMFCRibbonPanel::GetVisibleElements](../Topic/CMFCRibbonPanel::GetVisibleElements.md)|可視要素の配列を取得します。|  
|[CMFCRibbonPanel::HasElement](../Topic/CMFCRibbonPanel::HasElement.md)||  
|[CMFCRibbonPanel::HitTest](../Topic/CMFCRibbonPanel::HitTest.md)||  
|[CMFCRibbonPanel::HitTestEx](../Topic/CMFCRibbonPanel::HitTestEx.md)||  
|[CMFCRibbonPanel::Insert](../Topic/CMFCRibbonPanel::Insert.md)|指定した位置にリボン要素を挿入します。|  
|[CMFCRibbonPanel::InsertSeparator](../Topic/CMFCRibbonPanel::InsertSeparator.md)|指定した位置に区分線を挿入します。|  
|[CMFCRibbonPanel::IsCenterColumnVert](../Topic/CMFCRibbonPanel::IsCenterColumnVert.md)|すべてのパネル要素を垂直方向に列単位で中央揃えするかどうかを指定します。|  
|[CMFCRibbonPanel::IsCollapsed](../Topic/CMFCRibbonPanel::IsCollapsed.md)||  
|[CMFCRibbonPanel::IsHighlighted](../Topic/CMFCRibbonPanel::IsHighlighted.md)||  
|[CMFCRibbonPanel::IsJustifyColumns](../Topic/CMFCRibbonPanel::IsJustifyColumns.md)|すべてのパネルの列が同じ幅であるかどうかを示します。|  
|[CMFCRibbonPanel::IsMainPanel](../Topic/CMFCRibbonPanel::IsMainPanel.md)||  
|[CMFCRibbonPanel::IsMenuMode](../Topic/CMFCRibbonPanel::IsMenuMode.md)||  
|[CMFCRibbonPanel::MakeGalleryItemVisible](../Topic/CMFCRibbonPanel::MakeGalleryItemVisible.md)|指定したリボン要素が表示されるようにギャラリーをスクロールします。|  
|[CMFCRibbonPanel::OnKey](../Topic/CMFCRibbonPanel::OnKey.md)||  
|[CMFCRibbonPanel::RecalcWidths](../Topic/CMFCRibbonPanel::RecalcWidths.md)||  
|[CMFCRibbonPanel::Remove](../Topic/CMFCRibbonPanel::Remove.md)|指定したインデックス位置の要素を必要に応じて削除します。|  
|[CMFCRibbonPanel::RemoveAll](../Topic/CMFCRibbonPanel::RemoveAll.md)|リボン パネルからすべての要素を削除します。|  
|[CMFCRibbonPanel::Replace](../Topic/CMFCRibbonPanel::Replace.md)|要素の対応するインデックス値に基づいて、要素を別の要素と置き換えます。|  
|[CMFCRibbonPanel::ReplaceByID](../Topic/CMFCRibbonPanel::ReplaceByID.md)|指定したコマンド ID に基づいて、要素を別の要素に置き換えます。|  
|[CMFCRibbonPanel::SetCenterColumnVert](../Topic/CMFCRibbonPanel::SetCenterColumnVert.md)|要素を垂直方向に列単位で配置するようにパネルに指示します。|  
|[CMFCRibbonPanel::SetData](../Topic/CMFCRibbonPanel::SetData.md)|ユーザー定義データをリボン パネルに関連付けます。|  
|[CMFCRibbonPanel::SetElementMenu](../Topic/CMFCRibbonPanel::SetElementMenu.md)|指定されたコマンド ID を持つ要素にポップアップ メニューを関連付けます。|  
|[CMFCRibbonPanel::SetElementRTC](../Topic/CMFCRibbonPanel::SetElementRTC.md)|指定したランタイム クラス情報で指定されたリボン要素をリボン パネルに追加します。|  
|[CMFCRibbonPanel::SetElementRTCByID](../Topic/CMFCRibbonPanel::SetElementRTCByID.md)|指定したランタイム クラス情報で指定されたリボン要素をリボン パネルに追加します。|  
|[CMFCRibbonPanel::SetFocused](../Topic/CMFCRibbonPanel::SetFocused.md)|指定したリボン要素にフォーカスを設定します。|  
|[CMFCRibbonPanel::SetJustifyColumns](../Topic/CMFCRibbonPanel::SetJustifyColumns.md)|列の位置合わせを有効または無効にします。|  
|[CMFCRibbonPanel::SetKeys](../Topic/CMFCRibbonPanel::SetKeys.md)|リボン パネルを表示するキーボード ショートカットを設定します。|  
|[CMFCRibbonPanel::ShowPopup](../Topic/CMFCRibbonPanel::ShowPopup.md)||  
  
## 解説  
 リボン パネルは、リボン カテゴリ内で作成した関連タスクの論理グループです。  リボンのサイズが変化すると、できるだけ多くの要素が表示されるようにパネル レイアウトが自動的に調整されます。  
  
 [CMFCRibbonCategory::GetPanel](../Topic/CMFCRibbonCategory::GetPanel.md) メソッドを呼び出すことにより、リボン カテゴリに含まれているリボン パネルを取得できます。  
  
## 使用例  
 `CMFCRibbonPanel` クラスのさまざまなメソッドを使用して `CMFCRibbonPanel` オブジェクトを構成する方法を次の例に示します。  例では、リボン パネルを表示するショートカット キーを設定する方法、列ごとにパネルに対して要素を垂直に配置する方法、および列の調整を有効にする方法を示しています。  このコード スニペットは [MS の Office 2007 のデモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!CODE [NVC_MFC_MSOffice2007Demo#10](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_MSOffice2007Demo#10)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
## 必要条件  
 **ヘッダー :** afxRibbonPanel.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CObject クラス](../Topic/CObject%20Class.md)   
 [CMFCRibbonCategory クラス](../../mfc/reference/cmfcribboncategory-class.md)   
 [CMFCRibbonBaseElement クラス](../../mfc/reference/cmfcribbonbaseelement-class.md)