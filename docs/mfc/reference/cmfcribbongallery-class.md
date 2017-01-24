---
title: "CMFCRibbonGallery クラス | Microsoft Docs"
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
  - "CMFCRibbonGallery"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonGallery クラス"
ms.assetid: 9734c9c9-981c-4b3f-8c59-264fd41811b4
caps.latest.revision: 28
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonGallery クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Office 2007 スタイルのリボン ギャラリーを実装します。  
  
## 構文  
  
```  
class CMFCRibbonGallery : public CMFCRibbonButton  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonGallery::CMFCRibbonGallery](../Topic/CMFCRibbonGallery::CMFCRibbonGallery.md)|`CMFCRibbonGallery` オブジェクトを構築し、初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonGallery::AddGroup](../Topic/CMFCRibbonGallery::AddGroup.md)|新しいグループをギャラリーに追加します。|  
|[CMFCRibbonGallery::AddSubItem](../Topic/CMFCRibbonGallery::AddSubItem.md)|新しいメニュー項目をドロップダウン メニューに追加します。|  
|[CMFCRibbonGallery::Clear](../Topic/CMFCRibbonGallery::Clear.md)|ギャラリーの内容を消去します。|  
|[CMFCRibbonGallery::EnableMenuResize](../Topic/CMFCRibbonGallery::EnableMenuResize.md)|メニュー パネルのサイズ変更を有効または無効にします。|  
|[CMFCRibbonGallery::EnableMenuSideBar](../Topic/CMFCRibbonGallery::EnableMenuSideBar.md)|ポップアップ メニューの左側のサイド バーを有効または無効にします。|  
|[CMFCRibbonGallery::GetCompactSize](../Topic/CMFCRibbonGallery::GetCompactSize.md)|\([CMFCRibbonButton::GetCompactSize](../Topic/CMFCRibbonButton::GetCompactSize.md) をオーバーライドします。\)|  
|[CMFCRibbonGallery::GetDroppedDown](../Topic/CMFCRibbonGallery::GetDroppedDown.md)|\([CMFCRibbonBaseElement::GetDroppedDown](../Topic/CMFCRibbonBaseElement::GetDroppedDown.md) をオーバーライドします。\)|  
|[CMFCRibbonGallery::GetGroupName](../Topic/CMFCRibbonGallery::GetGroupName.md)|指定したインデックス位置にあるグループの名前を返します。|  
|[CMFCRibbonGallery::GetGroupOffset](../Topic/CMFCRibbonGallery::GetGroupOffset.md)||  
|[CMFCRibbonGallery::GetIconsInRow](../Topic/CMFCRibbonGallery::GetIconsInRow.md)|リボン ギャラリーの 1 行の項目数を返します。|  
|[CMFCRibbonGallery::GetItemToolTip](../Topic/CMFCRibbonGallery::GetItemToolTip.md)|ギャラリーの項目に関連付けられているツールヒント テキストを返します。|  
|[CMFCRibbonGallery::GetLastSelectedItem](../Topic/CMFCRibbonGallery::GetLastSelectedItem.md)|ユーザーによって選択されたギャラリーの最後の項目のインデックスを返します。|  
|[CMFCRibbonGallery::GetPaletteID](../Topic/CMFCRibbonGallery::GetPaletteID.md)|現在のギャラリーのコマンド ID を返します。|  
|[CMFCRibbonGallery::GetRegularSize](../Topic/CMFCRibbonGallery::GetRegularSize.md)|\([CMFCRibbonButton::GetRegularSize](../Topic/CMFCRibbonButton::GetRegularSize.md) をオーバーライドします。\)|  
|[CMFCRibbonGallery::GetSelectedItem](../Topic/CMFCRibbonGallery::GetSelectedItem.md)||  
|[CMFCRibbonGallery::HasMenu](../Topic/CMFCRibbonGallery::HasMenu.md)|\([CMFCRibbonButton::HasMenu](../Topic/CMFCRibbonButton::HasMenu.md) をオーバーライドします。\)|  
|[CMFCRibbonGallery::IsButtonMode](../Topic/CMFCRibbonGallery::IsButtonMode.md)|ギャラリー ボタンにギャラリーが含まれるかどうかを示します。|  
|[CMFCRibbonGallery::IsMenuResizeEnabled](../Topic/CMFCRibbonGallery::IsMenuResizeEnabled.md)|メニューのサイズ変更を有効にするか無効にするかを指定します。|  
|[CMFCRibbonGallery::IsMenuResizeVertical](../Topic/CMFCRibbonGallery::IsMenuResizeVertical.md)||  
|[CMFCRibbonGallery::IsMenuSideBar](../Topic/CMFCRibbonGallery::IsMenuSideBar.md)|サイド バーの有効または無効を指定します。|  
|[CMFCRibbonGallery::OnAfterChangeRect](../Topic/CMFCRibbonGallery::OnAfterChangeRect.md)|\(`CMFCRibbonButton::OnAfterChangeRect` をオーバーライドします。\)|  
|[CMFCRibbonGallery::OnDraw](../Topic/CMFCRibbonGallery::OnDraw.md)|\([CMFCRibbonButton::OnDraw](../Topic/CMFCRibbonButton::OnDraw.md) をオーバーライドします。\)|  
|[CMFCRibbonGallery::OnEnable](../Topic/CMFCRibbonGallery::OnEnable.md)|\(`CMFCRibbonBaseElement::OnEnable` をオーバーライドします。\)|  
|[CMFCRibbonGallery::OnRTLChanged](../Topic/CMFCRibbonGallery::OnRTLChanged.md)|\([CMFCRibbonBaseElement::OnRTLChanged](../Topic/CMFCRibbonBaseElement::OnRTLChanged.md) をオーバーライドします。\)|  
|[CMFCRibbonGallery::RedrawIcons](../Topic/CMFCRibbonGallery::RedrawIcons.md)|ギャラリーを再描画します。|  
|[CMFCRibbonGallery::RemoveItemToolTips](../Topic/CMFCRibbonGallery::RemoveItemToolTips.md)|ギャラリー内のすべての項目からツールヒントを削除します。|  
|[CMFCRibbonGallery::SelectItem](../Topic/CMFCRibbonGallery::SelectItem.md)||  
|[CMFCRibbonGallery::SetACCData](../Topic/CMFCRibbonGallery::SetACCData.md)|\([CMFCRibbonButton::SetACCData](../Topic/CMFCRibbonButton::SetACCData.md) をオーバーライドします。\)|  
|[CMFCRibbonGallery::SetButtonMode](../Topic/CMFCRibbonGallery::SetButtonMode.md)|リボン ギャラリーをドロップダウン ボタンとして表示するか、またはパレットとして直接リボン上に表示するかを指定します。|  
|[CMFCRibbonGallery::SetGroupName](../Topic/CMFCRibbonGallery::SetGroupName.md)|グループの名前を設定します。|  
|[CMFCRibbonGallery::SetIconsInRow](../Topic/CMFCRibbonGallery::SetIconsInRow.md)|ギャラリーの各行の項目数を定義します。|  
|[CMFCRibbonGallery::SetItemToolTip](../Topic/CMFCRibbonGallery::SetItemToolTip.md)|ギャラリーの項目のツールヒント テキストを設定します。|  
|[CMFCRibbonGallery::SetPalette](../Topic/CMFCRibbonGallery::SetPalette.md)|パレットをリボン ギャラリーに表示します。|  
|[CMFCRibbonGallery::SetPaletteID](../Topic/CMFCRibbonGallery::SetPaletteID.md)|ギャラリーの項目が選択されているときに `WM_COMMAND` メッセージで送信されるコマンド ID を定義します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonGallery::OnDrawPaletteIcon](../Topic/CMFCRibbonGallery::OnDrawPaletteIcon.md)|ギャラリー アイコンが描画されるときに、フレームワークによって呼び出されます。|  
  
## 解説  
 ギャラリー ボタンは、ユーザーによって開かれたときにギャラリーを表示する点を除いて、標準のメニュー ボタンと同じように動作します。  ギャラリーで項目を選択すると、フレームワークはボタンのコマンド ID と一緒に `WM_COMMAND` メッセージを送信します。  メッセージを処理する場合は、[CMFCRibbonGallery::GetLastSelectedItem](../Topic/CMFCRibbonGallery::GetLastSelectedItem.md) を呼び出して、ギャラリーから選択された項目を判定する必要があります。  
  
## 使用例  
 `CMFCRibbonGallery` クラスのさまざまなメソッドを使用して `CMFCRibbonGallery` オブジェクトを構成する方法を次の例に示します。  この例では、ギャラリーの各行の項目数を指定する方法、メニュー パネルのサイズ変更を有効にする方法、ポップアップ メニューの左のサイド バーを有効にする方法、およびリボン ギャラリーをパレットとしてリボン バーに直接表示する方法を示しています。  このコード スニペットは [クライアント サンプルを描画](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_DrawClient#6](../../mfc/reference/codesnippet/CPP/cmfcribbongallery-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md) [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md) [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
## 必要条件  
 **ヘッダー :** afxRibbonPaletteGallery.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonGalleryMenuButton クラス](../../mfc/reference/cmfcribbongallerymenubutton-class.md)