---
title: "CMFCRibbonBaseElement クラス | Microsoft Docs"
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
  - "CMFCRibbonBaseElement"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonBaseElement クラス"
ms.assetid: 419ea91b-5062-44cc-b0a3-f87d29566f62
caps.latest.revision: 34
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonBaseElement クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonBaseElement` クラスは、[リボン バー](../../mfc/reference/cmfcribbonbar-class.md)に追加できるすべての要素の基本クラスです。  リボン要素とは、リボン ボタン、リボン チェック ボックス、リボン コンボ ボックスなどです。  
  
## 構文  
  
```  
class CMFCRibbonBaseElement : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CMFCRibbonBaseElement`|`CMFCRibbonBaseElement` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonBaseElement::AddToKeyList](../Topic/CMFCRibbonBaseElement::AddToKeyList.md)|リボン要素の KeyTip を KeyTip の配列に追加します。|  
|[CMFCRibbonBaseElement::AddToListBox](../Topic/CMFCRibbonBaseElement::AddToListBox.md)|指定されたリボン コマンドのリスト ボックスに、リボン要素を追加します。|  
|[CMFCRibbonBaseElement::CanBeAddedToQuickAccessToolBar](../Topic/CMFCRibbonBaseElement::CanBeAddedToQuickAccessToolBar.md)|クイック アクセス ツール バーにリボン要素を追加できるかどうかを示します。|  
|[CMFCRibbonBaseElement::CanBeCompacted](../Topic/CMFCRibbonBaseElement::CanBeCompacted.md)|リボン要素のサイズをコンパクト サイズにできるかどうかを示します。|  
|[CMFCRibbonBaseElement::CanBeStretched](../Topic/CMFCRibbonBaseElement::CanBeStretched.md)|リボン要素の高さがリボンの行の高さに合わせて縦方向に拡大可能かどうかを指定します。|  
|[CMFCRibbonBaseElement::CanBeStretchedHorizontally](../Topic/CMFCRibbonBaseElement::CanBeStretchedHorizontally.md)|リボン要素の幅を変更できるかどうかを示します。|  
|[CMFCRibbonBaseElement::CleanUpSizes](../Topic/CMFCRibbonBaseElement::CleanUpSizes.md)|リボン要素のサイズ設定をクリーンアップします。|  
|[CMFCRibbonBaseElement::ClosePopupMenu](../Topic/CMFCRibbonBaseElement::ClosePopupMenu.md)|リボン要素のポップアップ メニューを閉じます。|  
|[CMFCRibbonBaseElement::CopyFrom](../Topic/CMFCRibbonBaseElement::CopyFrom.md)|指定された `CMFCRibbonBaseElement` の状態を現在のオブジェクトにコピーします。|  
|[CMFCRibbonBaseElement::DestroyCtrl](../Topic/CMFCRibbonBaseElement::DestroyCtrl.md)|リボン要素を破棄します。|  
|[CMFCRibbonBaseElement::DrawImage](../Topic/CMFCRibbonBaseElement::DrawImage.md)|リボン要素のイメージを描画します。|  
|[CMFCRibbonBaseElement::Find](../Topic/CMFCRibbonBaseElement::Find.md)|指定されたリボン要素へのポインターが現在のオブジェクトをポイントしている場合、そのポインターを返します。|  
|[CMFCRibbonBaseElement::FindByData](../Topic/CMFCRibbonBaseElement::FindByData.md)|リボン要素に指定されたデータが含まれている場合は、リボン要素へのポインターを取得します。|  
|[CMFCRibbonBaseElement::FindByID](../Topic/CMFCRibbonBaseElement::FindByID.md)|指定したコマンド ID でリボン要素が識別される場合、そのリボン要素へのポインターを取得します。|  
|[CMFCRibbonBaseElement::FindByOriginal](../Topic/CMFCRibbonBaseElement::FindByOriginal.md)|元のリボン要素が指定したリボン要素に一致する場合、リボン要素へのポインターを取得します。|  
|[CMFCRibbonBaseElement::GetCompactSize](../Topic/CMFCRibbonBaseElement::GetCompactSize.md)|リボン要素のコンパクト サイズを返します。|  
|[CMFCRibbonBaseElement::GetData](../Topic/CMFCRibbonBaseElement::GetData.md)|リボン要素に関連付けられているユーザー定義データを取得します。|  
|[CMFCRibbonBaseElement::GetDescription](../Topic/CMFCRibbonBaseElement::GetDescription.md)|リボン要素の説明を返します。|  
|[CMFCRibbonBaseElement::GetDroppedDown](../Topic/CMFCRibbonBaseElement::GetDroppedDown.md)|リボン要素のポップアップ メニューがドロップダウンされている場合に、リボン要素へのポインターを取得します。|  
|[CMFCRibbonBaseElement::GetElements](../Topic/CMFCRibbonBaseElement::GetElements.md)|現在のリボン要素を指定された配列に追加します。|  
|[CMFCRibbonBaseElement::GetElementsByID](../Topic/CMFCRibbonBaseElement::GetElementsByID.md)|現在のリボン要素に指定したコマンド ID が含まれている場合、指定した配列に現在のリボン要素を追加します。|  
|[CMFCRibbonBaseElement::GetHighlighted](../Topic/CMFCRibbonBaseElement::GetHighlighted.md)|リボン要素が強調表示されている場合、そのリボン要素へのポインターを取得します。|  
|[CMFCRibbonBaseElement::GetID](../Topic/CMFCRibbonBaseElement::GetID.md)|リボン要素のコマンド ID を返します。|  
|[CMFCRibbonBaseElement::GetImageSize](../Topic/CMFCRibbonBaseElement::GetImageSize.md)|リボン要素のイメージ サイズを返します。|  
|[CMFCRibbonBaseElement::GetIntermediateSize](../Topic/CMFCRibbonBaseElement::GetIntermediateSize.md)|サイズが中間状態になっているリボン要素のサイズを返します|  
|[CMFCRibbonBaseElement::GetKeys](../Topic/CMFCRibbonBaseElement::GetKeys.md)|リボン要素に関連付けられた KeyTip を返します。|  
|[CMFCRibbonBaseElement::GetKeyTipRect](../Topic/CMFCRibbonBaseElement::GetKeyTipRect.md)|リボン要素の KeyTip の境界を示す四角形を取得します。|  
|[CMFCRibbonBaseElement::GetKeyTipSize](../Topic/CMFCRibbonBaseElement::GetKeyTipSize.md)|KeyTip テキストのサイズを取得します。|  
|[CMFCRibbonBaseElement::GetLocationInGroup](../Topic/CMFCRibbonBaseElement::GetLocationInGroup.md)|リボン グループにおけるリボン要素の表示位置を示します。|  
|[CMFCRibbonBaseElement::GetMenuKeys](../Topic/CMFCRibbonBaseElement::GetMenuKeys.md)|ボタンに関連付けられた KeyTip を返します。|  
|[CMFCRibbonBaseElement::GetNotifyID](../Topic/CMFCRibbonBaseElement::GetNotifyID.md)|リボン要素の通知コマンドの ID を取得します。|  
|[CMFCRibbonBaseElement::GetOriginal](../Topic/CMFCRibbonBaseElement::GetOriginal.md)|元のリボン要素を取得します。|  
|[CMFCRibbonBaseElement::GetParentCategory](../Topic/CMFCRibbonBaseElement::GetParentCategory.md)|リボン要素のリボン カテゴリを取得します。|  
|[CMFCRibbonBaseElement::GetParentPanel](../Topic/CMFCRibbonBaseElement::GetParentPanel.md)|リボン要素が含まれているリボン パネルを取得します。|  
|[CMFCRibbonBaseElement::GetParentRibbonBar](../Topic/CMFCRibbonBaseElement::GetParentRibbonBar.md)|リボン要素の親リボン バーを取得します。|  
|[CMFCRibbonBaseElement::GetParentWnd](../Topic/CMFCRibbonBaseElement::GetParentWnd.md)|リボン要素の親ウィンドウを取得します。|  
|[CMFCRibbonBaseElement::GetPressed](../Topic/CMFCRibbonBaseElement::GetPressed.md)|ユーザーが現在リボン要素をクリックしている場合、そのリボン要素へのポインターを取得します。|  
|[CMFCRibbonBaseElement::GetQuickAccessToolBarID](../Topic/CMFCRibbonBaseElement::GetQuickAccessToolBarID.md)|クイック アクセス ツール バーに配置されているリボン要素のコマンド ID を取得します。|  
|[CMFCRibbonBaseElement::GetRect](../Topic/CMFCRibbonBaseElement::GetRect.md)|リボン要素の外接する四角形を返します。|  
|[CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md)|リボン要素の標準サイズを返します。|  
|[CMFCRibbonBaseElement::GetSize](../Topic/CMFCRibbonBaseElement::GetSize.md)|リボン要素の現在のサイズを返します。|  
|[CMFCRibbonBaseElement::GetText](../Topic/CMFCRibbonBaseElement::GetText.md)|リボン要素に関連付けられたテキストを返します。|  
|[CMFCRibbonBaseElement::GetToolTipText](../Topic/CMFCRibbonBaseElement::GetToolTipText.md)|リボン要素のツールヒント テキストを返します。|  
|[CMFCRibbonBaseElement::GetTopLevelRibbonBar](../Topic/CMFCRibbonBaseElement::GetTopLevelRibbonBar.md)|リボン要素の最上位のリボン バーを取得します。|  
|[CMFCRibbonBaseElement::HasCompactMode](../Topic/CMFCRibbonBaseElement::HasCompactMode.md)|リボン要素が簡易モードを持つかどうかを指定します。|  
|[CMFCRibbonBaseElement::HasFocus](../Topic/CMFCRibbonBaseElement::HasFocus.md)|親要素にキーボード フォーカスがあるかどうかを示します。|  
|[CMFCRibbonBaseElement::HasIntermediateMode](../Topic/CMFCRibbonBaseElement::HasIntermediateMode.md)|リボン要素に中間モードがあるかどうかを示します。|  
|[CMFCRibbonBaseElement::HasLargeMode](../Topic/CMFCRibbonBaseElement::HasLargeMode.md)|リボン要素に大モードがあるかどうかを指定します。|  
|[CMFCRibbonBaseElement::HasMenu](../Topic/CMFCRibbonBaseElement::HasMenu.md)|リボン要素にメニューがあるかどうかを示します。|  
|[CMFCRibbonBaseElement::HitTest](../Topic/CMFCRibbonBaseElement::HitTest.md)|指定した点がリボン要素に含まれている場合に、そのリボン要素へのポインターを取得します。|  
|[CMFCRibbonBaseElement::IsAlignByColumn](../Topic/CMFCRibbonBaseElement::IsAlignByColumn.md)|リボン要素が他のリボン要素と共に垂直に配置されるかどうかを示します。|  
|[CMFCRibbonBaseElement::IsAlwaysLargeImage](../Topic/CMFCRibbonBaseElement::IsAlwaysLargeImage.md)|リボン要素のイメージ サイズが常に大きいかどうかを示します。|  
|[CMFCRibbonBaseElement::IsAutoRepeatMode](../Topic/CMFCRibbonBaseElement::IsAutoRepeatMode.md)|リボン要素が自動繰り返しモードになっているかどうかを示します。|  
|[CMFCRibbonBaseElement::IsChecked](../Topic/CMFCRibbonBaseElement::IsChecked.md)|リボン要素がチェックされているかどうかを示します。|  
|[CMFCRibbonBaseElement::IsCompactMode](../Topic/CMFCRibbonBaseElement::IsCompactMode.md)|リボン要素が簡易モードであるかどうかを示します。|  
|[CMFCRibbonBaseElement::IsDefaultMenuLook](../Topic/CMFCRibbonBaseElement::IsDefaultMenuLook.md)||  
|[CMFCRibbonBaseElement::IsDisabled](../Topic/CMFCRibbonBaseElement::IsDisabled.md)|リボン要素が無効であるかどうかを示します。|  
|[CMFCRibbonBaseElement::IsDroppedDown](../Topic/CMFCRibbonBaseElement::IsDroppedDown.md)|リボン要素がドロップダウンされてポップアップ メニューが表示されているかどうかを調べます。|  
|[CMFCRibbonBaseElement::IsFocused](../Topic/CMFCRibbonBaseElement::IsFocused.md)|リボン要素にフォーカスがあるかどうかを示します。|  
|[CMFCRibbonBaseElement::IsGalleryIcon](../Topic/CMFCRibbonBaseElement::IsGalleryIcon.md)|リボン ギャラリーにリボン要素が含まれているかどうかを示します。|  
|[CMFCRibbonBaseElement::IsHighlighted](../Topic/CMFCRibbonBaseElement::IsHighlighted.md)|リボン要素を強調表示するかどうかを指定します。|  
|[CMFCRibbonBaseElement::IsIntermediateMode](../Topic/CMFCRibbonBaseElement::IsIntermediateMode.md)|リボン要素の現在のイメージが中間サイズであるかどうかを示します。|  
|[CMFCRibbonBaseElement::IsLargeMode](../Topic/CMFCRibbonBaseElement::IsLargeMode.md)|リボン要素の現在のイメージが大きいサイズであるかどうかを示します。|  
|[CMFCRibbonBaseElement::IsMenuMode](../Topic/CMFCRibbonBaseElement::IsMenuMode.md)|メニューにリボン要素が含まれているかどうかを示します。|  
|[CMFCRibbonBaseElement::IsPressed](../Topic/CMFCRibbonBaseElement::IsPressed.md)|ユーザーがリボン要素をクリックしたかどうかを示します。|  
|[CMFCRibbonBaseElement::IsQATMode](../Topic/CMFCRibbonBaseElement::IsQATMode.md)|リボン要素がクイック アクセス ツール バーに含まれているかどうかを示します。|  
|[CMFCRibbonBaseElement::IsSeparator](../Topic/CMFCRibbonBaseElement::IsSeparator.md)|リボン要素が表示区分線であるかどうかを示します。|  
|[CMFCRibbonBaseElement::IsShowGroupBorder](../Topic/CMFCRibbonBaseElement::IsShowGroupBorder.md)|リボン要素が、通常の境界線を表示するグループに含まれるかどうかを示します。|  
|[CMFCRibbonBaseElement::IsShowTooltipOnBottom](../Topic/CMFCRibbonBaseElement::IsShowTooltipOnBottom.md)|ツールヒントをリボン要素の下に表示するかどうかを示します。|  
|[CMFCRibbonBaseElement::IsTabStop](../Topic/CMFCRibbonBaseElement::IsTabStop.md)|リボン要素をキーボードで選択できるかどうかを示します。|  
|[CMFCRibbonBaseElement::IsTextAlwaysOnRight](../Topic/CMFCRibbonBaseElement::IsTextAlwaysOnRight.md)|リボン要素のテキストを右側に表示するかどうかを示します。|  
|[CMFCRibbonBaseElement::IsVisible](../Topic/CMFCRibbonBaseElement::IsVisible.md)|リボン要素が現在表示されているかどうかを示します。|  
|[CMFCRibbonBaseElement::IsWholeRowHeight](../Topic/CMFCRibbonBaseElement::IsWholeRowHeight.md)|リボン要素の表示高さが、そのリボン要素を含むリボン パネルの表示の高さと同じであるかどうかを示します。|  
|[CMFCRibbonBaseElement::NotifyCommand](../Topic/CMFCRibbonBaseElement::NotifyCommand.md)|リボン要素の親ウィンドウにコマンド通知を送信します。|  
|[CMFCRibbonBaseElement::NotifyHighlightListItem](../Topic/CMFCRibbonBaseElement::NotifyHighlightListItem.md)|ユーザーがリスト内にあるリボン要素を強調表示したときに、リボン バーの親ウィンドウに通知します。|  
|[CMFCRibbonBaseElement::OnAddToQAToolbar](../Topic/CMFCRibbonBaseElement::OnAddToQAToolbar.md)|指定したクイック アクセス ツール バーにリボン要素を追加します。|  
|[CMFCRibbonBaseElement::OnAfterChangeRect](../Topic/CMFCRibbonBaseElement::OnAfterChangeRect.md)|リボン要素のツールヒントを更新します。|  
|[CMFCRibbonBaseElement::OnAutoRepeat](../Topic/CMFCRibbonBaseElement::OnAutoRepeat.md)|維持されたユーザー入力に応答してリボン要素を更新します。|  
|[CMFCRibbonBaseElement::OnCalcTextSize](../Topic/CMFCRibbonBaseElement::OnCalcTextSize.md)|リボン要素のテキストのサイズを計算します。|  
|[CMFCRibbonBaseElement::OnChangeMenuHighlight](../Topic/CMFCRibbonBaseElement::OnChangeMenuHighlight.md)|メニューに含まれるリボン要素の強調表示が変更されたときに、フレームワークによって呼び出されます。|  
|[CMFCRibbonBaseElement::OnDraw](../Topic/CMFCRibbonBaseElement::OnDraw.md)|リボン要素を描画するために、フレームワークによって呼び出されます。|  
|[CMFCRibbonBaseElement::OnDrawKeyTip](../Topic/CMFCRibbonBaseElement::OnDrawKeyTip.md)|リボン要素の KeyTip を描画するために、フレームワークによって呼び出されます|  
|[CMFCRibbonBaseElement::OnDrawMenuImage](../Topic/CMFCRibbonBaseElement::OnDrawMenuImage.md)|リボン要素のメニュー イメージが描画されるときに、フレームワークによって呼び出されます。|  
|[CMFCRibbonBaseElement::OnDrawOnList](../Topic/CMFCRibbonBaseElement::OnDrawOnList.md)|コマンド リスト ボックス内のリボン要素を描画するために、フレームワークによって呼び出されます。|  
|[CMFCRibbonBaseElement::OnKey](../Topic/CMFCRibbonBaseElement::OnKey.md)|ユーザーが KeyTip を押し、リボン要素にフォーカスがあるときに、フレームワークによって呼び出されます|  
|[CMFCRibbonBaseElement::OnMenuKey](../Topic/CMFCRibbonBaseElement::OnMenuKey.md)||  
|[CMFCRibbonBaseElement::OnRTLChanged](../Topic/CMFCRibbonBaseElement::OnRTLChanged.md)|レイアウトの方向が変更されたときに、フレームワークによって呼び出されます。|  
|[CMFCRibbonBaseElement::OnShow](../Topic/CMFCRibbonBaseElement::OnShow.md)|リボン要素の表示と非表示を切り替えるために、フレームワークによって呼び出されます。|  
|[CMFCRibbonBaseElement::OnShowPopupMenu](../Topic/CMFCRibbonBaseElement::OnShowPopupMenu.md)|リボン要素にポップアップ メニューを表示するときに、フレームワークによって呼び出されます。|  
|[CMFCRibbonBaseElement::PostMenuCommand](../Topic/CMFCRibbonBaseElement::PostMenuCommand.md)||  
|[CMFCRibbonBaseElement::Redraw](../Topic/CMFCRibbonBaseElement::Redraw.md)|リボン要素の表示を更新します。|  
|[CMFCRibbonBaseElement::SetACCData](../Topic/CMFCRibbonBaseElement::SetACCData.md)|リボン要素のアクセシビリティ データを設定します。|  
|[CMFCRibbonBaseElement::SetCompactMode](../Topic/CMFCRibbonBaseElement::SetCompactMode.md)|リボン要素の表示サイズを設定します|  
|[CMFCRibbonBaseElement::SetData](../Topic/CMFCRibbonBaseElement::SetData.md)|データ項目をリボン要素に関連付けます。|  
|[CMFCRibbonBaseElement::SetDefaultMenuLook](../Topic/CMFCRibbonBaseElement::SetDefaultMenuLook.md)||  
|[CMFCRibbonBaseElement::SetDescription](../Topic/CMFCRibbonBaseElement::SetDescription.md)|リボン要素の説明を設定します。|  
|[CMFCRibbonBaseElement::SetID](../Topic/CMFCRibbonBaseElement::SetID.md)|リボン要素のコマンド ID を設定します。|  
|[CMFCRibbonBaseElement::SetInitialMode](../Topic/CMFCRibbonBaseElement::SetInitialMode.md)|リボン要素の初期表示サイズを設定します。|  
|[CMFCRibbonBaseElement::SetKeys](../Topic/CMFCRibbonBaseElement::SetKeys.md)|リボン要素の KeyTip を設定します。|  
|[CMFCRibbonBaseElement::SetOriginal](../Topic/CMFCRibbonBaseElement::SetOriginal.md)|リボン要素に対して元のリボン要素を設定します。|  
|[CMFCRibbonBaseElement::SetParentCategory](../Topic/CMFCRibbonBaseElement::SetParentCategory.md)|リボン要素に対して親カテゴリを設定します。|  
|[CMFCRibbonBaseElement::SetParentMenu](../Topic/CMFCRibbonBaseElement::SetParentMenu.md)|リボン要素に対して親メニュー コンテナーを設定します。|  
|[CMFCRibbonBaseElement::SetParentRibbonBar](../Topic/CMFCRibbonBaseElement::SetParentRibbonBar.md)|リボン要素に対して親リボン バーを設定します。|  
|[CMFCRibbonBaseElement::SetRect](../Topic/CMFCRibbonBaseElement::SetRect.md)|リボン要素を表示する四角形の寸法を設定します。|  
|[CMFCRibbonBaseElement::SetText](../Topic/CMFCRibbonBaseElement::SetText.md)|リボン要素のテキストを設定します|  
|[CMFCRibbonBaseElement::SetTextAlwaysOnRight](../Topic/CMFCRibbonBaseElement::SetTextAlwaysOnRight.md)|リボン要素の右側に表示するテキストを設定します。|  
|[CMFCRibbonBaseElement::SetToolTipText](../Topic/CMFCRibbonBaseElement::SetToolTipText.md)|リボン要素のツールヒント テキストを設定します。|  
|[CMFCRibbonBaseElement::SetVisible](../Topic/CMFCRibbonBaseElement::SetVisible.md)|リボン要素の表示状態を設定します。|  
|[CMFCRibbonBaseElement::StretchHorizontally](../Topic/CMFCRibbonBaseElement::StretchHorizontally.md)|リボン要素の幅を広げます。|  
|[CMFCRibbonBaseElement::StretchToWholeRow](../Topic/CMFCRibbonBaseElement::StretchToWholeRow.md)|リボン要素の表示の高さを、指定した行の高さに変更します。|  
|[CMFCRibbonBaseElement::UpdateTooltipInfo](../Topic/CMFCRibbonBaseElement::UpdateTooltipInfo.md)|リボン要素のコマンド リソースを使用してツールヒント テキストを更新します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonBaseElement::OnProcessKey](../Topic/CMFCRibbonBaseElement::OnProcessKey.md)|ユーザーがショートカット キーを押したときに、フレームワークによって呼び出されます。|  
|[CMFCRibbonBaseElement::OnSetFocus](../Topic/CMFCRibbonBaseElement::OnSetFocus.md)|リボン要素が入力フォーカスを受け取ったか失ったときに、フレームワークによって呼び出されます。|  
  
## 解説  
 `CMFCRibbonBaseElement` クラスは、コマンド ID、テキスト ラベル、ツールヒント テキスト、要素の説明、および状態 \(フォーカスを置く、強調表示する、押す、無効にする、チェックする、またはドロップダウンするなど\) が含まれるすべてのリボン要素に共通のプロパティを定義します。  
  
 リボン要素のイメージ サイズは、`RibbonImageType` メンバーに次のいずれかの値を指定することによって定義します。  
  
-   `RibbonImageLarge`  
  
-   `RibbonImageSmall`  
  
 そのサイズに応じて、リボン要素には小さいイメージと大きいイメージのいずれかが表示されます。  
  
## 使用例  
 次の例は、`CMFCRibbonBaseElement` クラスのさまざまなメソッドの使用方法を説明しています。  この例は、`CMFCRibbonStatusBar` クラスからの `CMFCRibbonBaseElement` オブジェクトの取得方法、リボン要素の説明の設定方法、テキストの設定方法、KeyTip の設定方法、リボン要素のツールヒント テキストの設定方法を示しています。  このコード スニペットは [クライアント サンプルを描画](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_DrawClient#8](../../mfc/reference/codesnippet/CPP/cmfcribbonbaseelement-class_1.cpp)]  
[!code-cpp[NVC_MFC_DrawClient#9](../../mfc/reference/codesnippet/CPP/cmfcribbonbaseelement-class_2.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
## 必要条件  
 **ヘッダー :** afxbaseribbonelement.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)