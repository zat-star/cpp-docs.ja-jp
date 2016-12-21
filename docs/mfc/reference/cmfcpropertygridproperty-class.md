---
title: "CMFCPropertyGridProperty クラス | Microsoft Docs"
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
  - "CMFCPropertyGridProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyGridProperty クラス"
ms.assetid: 36f3fabe-0efe-468b-8a0b-5a7956db38a2
caps.latest.revision: 35
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertyGridProperty クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCPropertyGridProperty` オブジェクトは、プロパティ リスト コントロールのリスト項目を表します。  
  
## 構文  
  
```  
class CMFCPropertyGridProperty : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCPropertyGridProperty::CMFCPropertyGridProperty](../Topic/CMFCPropertyGridProperty::CMFCPropertyGridProperty.md)|`CMFCPropertyGridProperty` オブジェクトを構築します。|  
|`CMFCPropertyGridProperty::~CMFCPropertyGridProperty`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCPropertyGridProperty::AddOption](../Topic/CMFCPropertyGridProperty::AddOption.md)|プロパティ リスト コントロールに新しいリスト項目を追加します。|  
|[CMFCPropertyGridProperty::AddSubItem](../Topic/CMFCPropertyGridProperty::AddSubItem.md)|子項目をプロパティに追加します。|  
|[CMFCPropertyGridProperty::AdjustButtonRect](../Topic/CMFCPropertyGridProperty::AdjustButtonRect.md)|埋め込みボタンの外接する四角形のサイズを変更するようプロパティに通知するために、親プロパティ リスト コントロールによって呼び出されます。|  
|[CMFCPropertyGridProperty::AdjustInPlaceEditRect](../Topic/CMFCPropertyGridProperty::AdjustInPlaceEditRect.md)|プロパティ値の設定に使用されるテキスト ボックスとオプションのスピン ボタン コントロールの境界を取得します。|  
|[CMFCPropertyGridProperty::AllowEdit](../Topic/CMFCPropertyGridProperty::AllowEdit.md)|プロパティを編集可能または読み取り専用にします。|  
|[CMFCPropertyGridProperty::CreateInPlaceEdit](../Topic/CMFCPropertyGridProperty::CreateInPlaceEdit.md)|プロパティの編集可能なコントロールを作成するために、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::CreateSpinControl](../Topic/CMFCPropertyGridProperty::CreateSpinControl.md)|編集可能なスピン ボタン コントロールを作成するために、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::Enable](../Topic/CMFCPropertyGridProperty::Enable.md)|プロパティを有効または無効にします。|  
|[CMFCPropertyGridProperty::EnableSpinControl](../Topic/CMFCPropertyGridProperty::EnableSpinControl.md)|プロパティ値の変更に使用するスピン ボタン コントロールを有効または無効にします。|  
|[CMFCPropertyGridProperty::Expand](../Topic/CMFCPropertyGridProperty::Expand.md)|サブプロパティを含むプロパティを展開または折りたたみます。|  
|[CMFCPropertyGridProperty::FormatProperty](../Topic/CMFCPropertyGridProperty::FormatProperty.md)|プロパティ値のテキスト表現の書式を設定します。|  
|[CMFCPropertyGridProperty::GetData](../Topic/CMFCPropertyGridProperty::GetData.md)|プロパティに関連付けられた `DWORD` 値を取得します。|  
|[CMFCPropertyGridProperty::GetDescription](../Topic/CMFCPropertyGridProperty::GetDescription.md)|プロパティの説明を取得します。|  
|[CMFCPropertyGridProperty::GetExpandedSubItems](../Topic/CMFCPropertyGridProperty::GetExpandedSubItems.md)|展開されたサブ項目数を取得します。|  
|[CMFCPropertyGridProperty::GetHierarchyLevel](../Topic/CMFCPropertyGridProperty::GetHierarchyLevel.md)|プロパティの階層レベルの 0 から始まるインデックスを取得します。|  
|[CMFCPropertyGridProperty::GetName](../Topic/CMFCPropertyGridProperty::GetName.md)|プロパティの名前を取得します。|  
|[CMFCPropertyGridProperty::GetNameTooltip](../Topic/CMFCPropertyGridProperty::GetNameTooltip.md)|ツールヒントにプロパティの名前を表示するために、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::GetOption](../Topic/CMFCPropertyGridProperty::GetOption.md)|インデックスで指定されたオプションのテキストを取得します。|  
|[CMFCPropertyGridProperty::GetOptionCount](../Topic/CMFCPropertyGridProperty::GetOptionCount.md)|プロパティに属しているオプションの数を取得します。|  
|[CMFCPropertyGridProperty::GetOriginalValue](../Topic/CMFCPropertyGridProperty::GetOriginalValue.md)|現在のプロパティの初期値を取得します。|  
|[CMFCPropertyGridProperty::GetParent](../Topic/CMFCPropertyGridProperty::GetParent.md)|親プロパティへのポインターを取得します。|  
|[CMFCPropertyGridProperty::GetRect](../Topic/CMFCPropertyGridProperty::GetRect.md)|プロパティに外接する四角形を取得します。|  
|[CMFCPropertyGridProperty::GetSubItem](../Topic/CMFCPropertyGridProperty::GetSubItem.md)|0 から始まるインデックスで識別されるサブプロパティを取得します。|  
|[CMFCPropertyGridProperty::GetSubItemsCount](../Topic/CMFCPropertyGridProperty::GetSubItemsCount.md)|サブ項目数を取得します。|  
|`CMFCPropertyGridProperty::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
|[CMFCPropertyGridProperty::GetValue](../Topic/CMFCPropertyGridProperty::GetValue.md)|プロパティ値を取得します。|  
|[CMFCPropertyGridProperty::GetValueTooltip](../Topic/CMFCPropertyGridProperty::GetValueTooltip.md)|ツールヒントに表示されるプロパティ値のテキスト表現を取得するために、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::HitTest](../Topic/CMFCPropertyGridProperty::HitTest.md)|1 つの点に対応するプロパティ リスト項目に対応するプロパティ オブジェクトをポイントします。|  
|[CMFCPropertyGridProperty::IsAllowEdit](../Topic/CMFCPropertyGridProperty::IsAllowEdit.md)|プロパティが編集できるかどうかを示します。|  
|[CMFCPropertyGridProperty::IsEnabled](../Topic/CMFCPropertyGridProperty::IsEnabled.md)|プロパティが有効か無効かを示します。|  
|[CMFCPropertyGridProperty::IsExpanded](../Topic/CMFCPropertyGridProperty::IsExpanded.md)|プロパティが展開されているか折りたたまれているかを示します。|  
|[CMFCPropertyGridProperty::IsGroup](../Topic/CMFCPropertyGridProperty::IsGroup.md)|現在のプロパティがグループを表すかどうかを示します。|  
|[CMFCPropertyGridProperty::IsInPlaceEditing](../Topic/CMFCPropertyGridProperty::IsInPlaceEditing.md)|現在のプロパティが編集できるかどうかを示します。|  
|[CMFCPropertyGridProperty::IsModified](../Topic/CMFCPropertyGridProperty::IsModified.md)|現在のプロパティが変更されているかどうかを示します。|  
|[CMFCPropertyGridProperty::IsParentExpanded](../Topic/CMFCPropertyGridProperty::IsParentExpanded.md)|現在のプロパティの親が展開されているかどうかを示します。|  
|[CMFCPropertyGridProperty::IsSelected](../Topic/CMFCPropertyGridProperty::IsSelected.md)|現在のプロパティが選択されているかどうかを示します。|  
|[CMFCPropertyGridProperty::IsVisible](../Topic/CMFCPropertyGridProperty::IsVisible.md)|現在のプロパティが表示されるかどうかを示します。|  
|[CMFCPropertyGridProperty::OnClickButton](../Topic/CMFCPropertyGridProperty::OnClickButton.md)|ユーザーがプロパティに含まれているボタンをクリックしたときに、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::OnClickName](../Topic/CMFCPropertyGridProperty::OnClickName.md)|ユーザーがプロパティの名前フィールドをクリックしたときに、親プロパティ リスト コントロールによって呼び出されます。|  
|[CMFCPropertyGridProperty::OnClickValue](../Topic/CMFCPropertyGridProperty::OnClickValue.md)|ユーザーがプロパティの値フィールドをクリックしたときに、親プロパティ リスト コントロールによって呼び出されます。|  
|[CMFCPropertyGridProperty::OnCloseCombo](../Topic/CMFCPropertyGridProperty::OnCloseCombo.md)|プロパティに含まれているコンボ ボックスが閉じられたときに、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::OnDblClk](../Topic/CMFCPropertyGridProperty::OnDblClk.md)|ユーザーがプロパティをダブルクリックしたときに、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::OnDrawButton](../Topic/CMFCPropertyGridProperty::OnDrawButton.md)|プロパティに含まれているボタンを描画するために、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::OnDrawDescription](../Topic/CMFCPropertyGridProperty::OnDrawDescription.md)|プロパティの説明を表示するために、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::OnDrawExpandBox](../Topic/CMFCPropertyGridProperty::OnDrawExpandBox.md)|サブプロパティのあるプロパティの近辺に展開ボックス コントロールを描画するために、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::OnDrawName](../Topic/CMFCPropertyGridProperty::OnDrawName.md)|プロパティ名を表示するために、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::OnDrawValue](../Topic/CMFCPropertyGridProperty::OnDrawValue.md)|プロパティ値を表示するために、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::OnEdit](../Topic/CMFCPropertyGridProperty::OnEdit.md)|ユーザーがプロパティ値の変更を開始するときに、フレームワークにより呼び出されます。|  
|[CMFCPropertyGridProperty::OnEndEdit](../Topic/CMFCPropertyGridProperty::OnEndEdit.md)|ユーザーがプロパティ値の変更を終了したときに、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::OnKillSelection](../Topic/CMFCPropertyGridProperty::OnKillSelection.md)||  
|[CMFCPropertyGridProperty::OnPosSizeChanged](../Topic/CMFCPropertyGridProperty::OnPosSizeChanged.md)||  
|[CMFCPropertyGridProperty::OnRClickName](../Topic/CMFCPropertyGridProperty::OnRClickName.md)|プロパティ名領域内でユーザーがマウスの右ボタンをクリックしたときに、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::OnRClickValue](../Topic/CMFCPropertyGridProperty::OnRClickValue.md)|プロパティ値領域内でユーザーによってマウスの右ボタンがクリック \(右クリック\) されると、フレームワークから呼び出されます。|  
|[CMFCPropertyGridProperty::OnSelectCombo](../Topic/CMFCPropertyGridProperty::OnSelectCombo.md)|編集可能なコンボ ボックスの項目を選択したとき、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::OnSetCursor](../Topic/CMFCPropertyGridProperty::OnSetCursor.md)|マウス ポインターがプロパティ項目に移動したときに、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::OnSetSelection](../Topic/CMFCPropertyGridProperty::OnSetSelection.md)||  
|[CMFCPropertyGridProperty::OnUpdateValue](../Topic/CMFCPropertyGridProperty::OnUpdateValue.md)|編集できるプロパティの値が変更されたときに、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::PushChar](../Topic/CMFCPropertyGridProperty::PushChar.md)|プロパティが選択され、ユーザーが新しい文字を入力したときに、プロパティ リスト コントロールから呼び出されます。|  
|[CMFCPropertyGridProperty::Redraw](../Topic/CMFCPropertyGridProperty::Redraw.md)|プロパティを再描画します。|  
|[CMFCPropertyGridProperty::RemoveAllOptions](../Topic/CMFCPropertyGridProperty::RemoveAllOptions.md)|プロパティからすべてのオプション \(項目\) を削除します。|  
|[CMFCPropertyGridProperty::RemoveSubItem](../Topic/CMFCPropertyGridProperty::RemoveSubItem.md)|指定したサブ項目を削除します。|  
|[CMFCPropertyGridProperty::ResetOriginalValue](../Topic/CMFCPropertyGridProperty::ResetOriginalValue.md)|編集されたプロパティの元の値を復元します。|  
|[CMFCPropertyGridProperty::SetData](../Topic/CMFCPropertyGridProperty::SetData.md)|`DWORD` 値をプロパティに関連付けます。|  
|[CMFCPropertyGridProperty::SetDescription](../Topic/CMFCPropertyGridProperty::SetDescription.md)|現在のプロパティを説明するテキストを指定します。|  
|[CMFCPropertyGridProperty::SetName](../Topic/CMFCPropertyGridProperty::SetName.md)|プロパティの名前を設定します。|  
|[CMFCPropertyGridProperty::SetOriginalValue](../Topic/CMFCPropertyGridProperty::SetOriginalValue.md)|編集可能なプロパティの元の値を設定します。|  
|[CMFCPropertyGridProperty::SetValue](../Topic/CMFCPropertyGridProperty::SetValue.md)|グリッド プロパティの値を設定します。|  
|[CMFCPropertyGridProperty::Show](../Topic/CMFCPropertyGridProperty::Show.md)|プロパティの表示と非表示を切り替えます。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCPropertyGridProperty::CreateCombo](../Topic/CMFCPropertyGridProperty::CreateCombo.md)|プロパティにコンボ ボックスを追加するために、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::HasButton](../Topic/CMFCPropertyGridProperty::HasButton.md)|プロパティにボタンが含まれているかどうかを示します。|  
|[CMFCPropertyGridProperty::Init](../Topic/CMFCPropertyGridProperty::Init.md)|プロパティ オブジェクトを初期化するために、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::IsSubItem](../Topic/CMFCPropertyGridProperty::IsSubItem.md)|指定したプロパティが現在のプロパティのサブ項目であるかどうかを示します。|  
|[CMFCPropertyGridProperty::IsValueChanged](../Topic/CMFCPropertyGridProperty::IsValueChanged.md)|現在のプロパティの値が変更されたかどうかを示します。|  
|[CMFCPropertyGridProperty::OnCtlColor](../Topic/CMFCPropertyGridProperty::OnCtlColor.md)|ブラシを取得してプロパティの背景色を塗りつぶす必要があるときに、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::OnDestroyWindow](../Topic/CMFCPropertyGridProperty::OnDestroyWindow.md)|プロパティが破棄されたとき、または編集が終了したときに、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridProperty::OnKillFocus](../Topic/CMFCPropertyGridProperty::OnKillFocus.md)|プロパティが入力フォーカスを失ったときに、フレームワークによって呼び出されます。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMFCPropertyGridProperty::m\_strFormatDouble](../Topic/CMFCPropertyGridProperty::m_strFormatDouble.md)|double 型の値の書式指定文字列。|  
|[CMFCPropertyGridProperty::m\_strFormatFloat](../Topic/CMFCPropertyGridProperty::m_strFormatFloat.md)|float 型の値の書式指定文字列。|  
|[CMFCPropertyGridProperty::m\_strFormatLong](../Topic/CMFCPropertyGridProperty::m_strFormatLong.md)|long 型の値の書式指定文字列。|  
|[CMFCPropertyGridProperty::m\_strFormatShort](../Topic/CMFCPropertyGridProperty::m_strFormatShort.md)|short 型の値の書式指定文字列。|  
  
## 解説  
 `CMFCPropertyGridProperty` オブジェクトを使用してプロパティを表した後、それをプロパティ リスト コントロールに追加します。  詳細については、「[CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)」を参照してください。  
  
 プロパティ オブジェクトは、文字列、日付、ブール値、整数値などのデータ型を表すことができます。  子プロパティを含めたり、コンボ ボックスやボタン コントロールなどのコントロールを含めることができます。  
  
## 使用例  
 `CMFCPropertyGridProperty` オブジェクトを構築する方法を次の例に示します。  この例では、`CMFCPropertyGridProperty` クラスのさまざまなメソッドを使用して、オプションの追加、サブ項目の追加、プロパティの有効化、およびプロパティの表示を行う方法も示します。  この例では [新しいコントロールのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!CODE [NVC_MFC_NewControls#27](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#27)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
## 必要条件  
 **ヘッダー :** afxpropertygridctrl.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)