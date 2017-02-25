---
title: "CMFCPropertyGridCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCPropertyGridCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCPropertyGridCtrl クラス"
  - "CMFCPropertyGridCtrl::accHitTest メソッド"
  - "CMFCPropertyGridCtrl::accLocation メソッド"
  - "CMFCPropertyGridCtrl::get_accChild メソッド"
  - "CMFCPropertyGridCtrl::get_accDefaultAction メソッド"
  - "CMFCPropertyGridCtrl::get_accDescription メソッド"
  - "CMFCPropertyGridCtrl::get_accName メソッド"
  - "CMFCPropertyGridCtrl::get_accRole メソッド"
  - "CMFCPropertyGridCtrl::get_accState メソッド"
  - "CMFCPropertyGridCtrl::get_accValue メソッド"
  - "CMFCPropertyGridCtrl::PreTranslateMessage メソッド"
ms.assetid: 95877cae-2311-4a2a-9031-0c8c3cf0a5f9
caps.latest.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# CMFCPropertyGridCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 プロパティをアルファベット順または階層順に表示できる、編集可能なプロパティ グリッド コントロールをサポートします。  
  
## 構文  
  
```  
class CMFCPropertyGridCtrl : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCPropertyGridCtrl::CMFCPropertyGridCtrl](../Topic/CMFCPropertyGridCtrl::CMFCPropertyGridCtrl.md)|`CMFCPropertyGridCtrl` オブジェクトを構築します。|  
|`CMFCPropertyGridCtrl::~CMFCPropertyGridCtrl`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|`CMFCPropertyGridCtrl::accHitTest`|画面上の指定された位置にある子要素または子オブジェクトを取得するために、フレームワークによって呼び出されます   \([CWnd::accHitTest](../Topic/CWnd::accHitTest.md) をオーバーライドします\)。|  
|`CMFCPropertyGridCtrl::accLocation`|指定されたオブジェクトの現在の画面位置を取得するために、フレームワークによって呼び出されます   \([CWnd::accLocation](../Topic/CWnd::accLocation.md) をオーバーライドします\)。|  
|[CMFCPropertyGridCtrl::accSelect](../Topic/CMFCPropertyGridCtrl::accSelect.md)|選択を変更するため、または指定されたオブジェクトのキーボード フォーカスを移動するために、フレームワークによって呼び出されます   \([CWnd::accSelect](../Topic/CWnd::accSelect.md) をオーバーライドします\)。|  
|[CMFCPropertyGridCtrl::AddProperty](../Topic/CMFCPropertyGridCtrl::AddProperty.md)|プロパティ グリッド コントロールに新しいプロパティを追加します。|  
|[CMFCPropertyGridCtrl::AlwaysShowUserToolTip](../Topic/CMFCPropertyGridCtrl::AlwaysShowUserToolTip.md)||  
|[CMFCPropertyGridCtrl::CloseColorPopup](../Topic/CMFCPropertyGridCtrl::CloseColorPopup.md)|色を選択するためのダイアログ ボックスを閉じます。|  
|[CMFCPropertyGridCtrl::Create](../Topic/CMFCPropertyGridCtrl::Create.md)|プロパティ グリッド コントロールを作成し、プロパティ グリッド コントロール オブジェクトに関連付けます。|  
|[CMFCPropertyGridCtrl::DeleteProperty](../Topic/CMFCPropertyGridCtrl::DeleteProperty.md)|指定したプロパティをプロパティ グリッド コントロールから削除します。|  
|[CMFCPropertyGridCtrl::DrawControlBarColors](../Topic/CMFCPropertyGridCtrl::DrawControlBarColors.md)||  
|[CMFCPropertyGridCtrl::EnableDescriptionArea](../Topic/CMFCPropertyGridCtrl::EnableDescriptionArea.md)|プロパティの一覧の下に表示される説明領域を有効または無効にします。|  
|[CMFCPropertyGridCtrl::EnableHeaderCtrl](../Topic/CMFCPropertyGridCtrl::EnableHeaderCtrl.md)|プロパティ グリッド コントロールの上部にあるヘッダー コントロールを有効または無効にします。|  
|[CMFCPropertyGridCtrl::EnsureVisible](../Topic/CMFCPropertyGridCtrl::EnsureVisible.md)|プロパティ グリッド コントロールをスクロールし、指定されたプロパティが表示されるまで、プロパティ項目を展開します。|  
|[CMFCPropertyGridCtrl::ExpandAll](../Topic/CMFCPropertyGridCtrl::ExpandAll.md)|すべてのプロパティ グリッド コントロール ノードの展開または折りたたみを行います。|  
|[CMFCPropertyGridCtrl::FindItemByData](../Topic/CMFCPropertyGridCtrl::FindItemByData.md)|ユーザー定義の `DWORD` 値に関連付けられているプロパティを取得します。|  
|`CMFCPropertyGridCtrl::get_accChild`|指定された子の `IDispatch`インターフェイスのアドレスを取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accChild](../Topic/CWnd::get_accChild.md) をオーバーライドします\)。|  
|[CMFCPropertyGridCtrl::get\_accChildCount](../Topic/CMFCPropertyGridCtrl::get_accChildCount.md)|オブジェクトに属する子の数を取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accChildCount](../Topic/CWnd::get_accChildCount.md) をオーバーライドします\)。|  
|`CMFCPropertyGridCtrl::get_accDefaultAction`|オブジェクトの既定のアクションを記述する文字列を取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accDefaultAction](../Topic/CWnd::get_accDefaultAction.md) をオーバーライドします\)。|  
|`CMFCPropertyGridCtrl::get_accDescription`|指定されたオブジェクトの外観を記述する文字列を取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accDescription](../Topic/CWnd::get_accDescription.md) をオーバーライドします\)。|  
|[CMFCPropertyGridCtrl::get\_accFocus](../Topic/CMFCPropertyGridCtrl::get_accFocus.md)|キーボード フォーカスを保持するオブジェクトを取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accFocus](../Topic/CWnd::get_accFocus.md) をオーバーライドします\)。|  
|[CMFCPropertyGridCtrl::get\_accHelp](../Topic/CMFCPropertyGridCtrl::get_accHelp.md)|オブジェクトの `Help` プロパティ文字列を取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accHelp](../Topic/CWnd::get_accHelp.md) をオーバーライドします\)。|  
|[CMFCPropertyGridCtrl::get\_accHelpTopic](../Topic/CMFCPropertyGridCtrl::get_accHelpTopic.md)|指定されたオブジェクトに関連付けられている `WinHelp` ``  ファイルの完全パスと、そのファイル内の適切なトピックの識別子を取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accHelpTopic](../Topic/CWnd::get_accHelpTopic.md) をオーバーライドします\)。|  
|[CMFCPropertyGridCtrl::get\_accKeyboardShortcut](../Topic/CMFCPropertyGridCtrl::get_accKeyboardShortcut.md)|指定されたオブジェクトのショートカット キーまたはアクセス キーを取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accKeyboardShortcut](../Topic/CWnd::get_accKeyboardShortcut.md) をオーバーライドします\)。|  
|`CMFCPropertyGridCtrl::get_accName`|指定されたオブジェクトの名前を取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accName](../Topic/CWnd::get_accName.md) をオーバーライドします\)。|  
|`CMFCPropertyGridCtrl::get_accRole`|指定されたオブジェクトの役割を記述する情報を取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accRole](../Topic/CWnd::get_accRole.md) をオーバーライドします\)。|  
|[CMFCPropertyGridCtrl::get\_accSelection](../Topic/CMFCPropertyGridCtrl::get_accSelection.md)|オブジェクトの選択されている子を取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accSelection](../Topic/CWnd::get_accSelection.md) をオーバーライドします\)。|  
|`CMFCPropertyGridCtrl::get_accState`|指定されたオブジェクトの現在の状態を取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accState](../Topic/CWnd::get_accState.md) をオーバーライドします\)。|  
|`CMFCPropertyGridCtrl::get_accValue`|指定されたオブジェクトの値を取得するために、フレームワークによって呼び出されます   \([CWnd::get\_accValue](../Topic/CWnd::get_accValue.md) をオーバーライドします\)。|  
|[CMFCPropertyGridCtrl::GetBkColor](../Topic/CMFCPropertyGridCtrl::GetBkColor.md)|現在のプロパティ グリッド コントロールの背景色を取得します。|  
|[CMFCPropertyGridCtrl::GetBoldFont](../Topic/CMFCPropertyGridCtrl::GetBoldFont.md)|現在のプロパティ グリッド コントロールのテキストの Windows フォントを太字スタイルで取得します。|  
|[CMFCPropertyGridCtrl::GetCurSel](../Topic/CMFCPropertyGridCtrl::GetCurSel.md)|現在選択されているプロパティを取得します。|  
|[CMFCPropertyGridCtrl::GetCustomColors](../Topic/CMFCPropertyGridCtrl::GetCustomColors.md)|プロパティ グリッド コントロール要素に対して現在定義されているカスタム カラーを取得します。|  
|[CMFCPropertyGridCtrl::GetDescriptionHeight](../Topic/CMFCPropertyGridCtrl::GetDescriptionHeight.md)|プロパティ グリッド コントロールの下部にある説明領域の高さを取得します。|  
|[CMFCPropertyGridCtrl::GetDescriptionRows](../Topic/CMFCPropertyGridCtrl::GetDescriptionRows.md)|現在のプロパティ グリッド コントロールの説明領域の行数を取得します。|  
|[CMFCPropertyGridCtrl::GetHeaderCtrl](../Topic/CMFCPropertyGridCtrl::GetHeaderCtrl.md)|現在のプロパティ グリッド コントロールを表示するためにフレームワークによって使用される内部 [CMFCHeaderCtrl](../Topic/CMFCHeaderCtrl%20Class.md) オブジェクトを取得します。|  
|[CMFCPropertyGridCtrl::GetHeaderHeight](../Topic/CMFCPropertyGridCtrl::GetHeaderHeight.md)|プロパティ グリッド コントロールのヘッダーの高さを取得します。|  
|[CMFCPropertyGridCtrl::GetLeftColumnWidth](../Topic/CMFCPropertyGridCtrl::GetLeftColumnWidth.md)|現在のプロパティ グリッド コントロールの左側の列の幅を取得します。この列には、各プロパティの名前が格納されます。|  
|[CMFCPropertyGridCtrl::GetListRect](../Topic/CMFCPropertyGridCtrl::GetListRect.md)|プロパティ グリッド コントロールに外接する四角形を取得します。|  
|[CMFCPropertyGridCtrl::GetProperty](../Topic/CMFCPropertyGridCtrl::GetProperty.md)|プロパティ グリッド コントロール項目の指定したインデックスに対応するプロパティ オブジェクトへのポインターを取得します。|  
|[CMFCPropertyGridCtrl::GetPropertyColumnWidth](../Topic/CMFCPropertyGridCtrl::GetPropertyColumnWidth.md)|プロパティ値を格納する列の現在の幅を取得します。|  
|[CMFCPropertyGridCtrl::GetPropertyCount](../Topic/CMFCPropertyGridCtrl::GetPropertyCount.md)|プロパティ グリッド コントロール内のプロパティの数を取得します。|  
|[CMFCPropertyGridCtrl::GetRowHeight](../Topic/CMFCPropertyGridCtrl::GetRowHeight.md)|プロパティ グリッド コントロールの行の高さを取得します。|  
|[CMFCPropertyGridCtrl::GetScrollBarCtrl](../Topic/CMFCPropertyGridCtrl::GetScrollBarCtrl.md)|プロパティ グリッド コントロール内のスクロール バー コントロールへのポインターを取得します   \([CWnd::GetScrollBarCtrl](../Topic/CWnd::GetScrollBarCtrl.md) をオーバーライドします。\)|  
|[CMFCPropertyGridCtrl::GetTextColor](../Topic/CMFCPropertyGridCtrl::GetTextColor.md)|現在のプロパティ グリッド コントロールのプロパティ項目のテキストの色を取得します。|  
|`CMFCPropertyGridCtrl::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
|[CMFCPropertyGridCtrl::HitTest](../Topic/CMFCPropertyGridCtrl::HitTest.md)|指定された位置がプロパティ グリッド コントロール項目内に存在する場合、その項目に対応するプロパティ オブジェクトへのポインターを取得します。  このメソッドは、位置を含むプロパティ グリッド コントロール内の領域も示します。|  
|[CMFCPropertyGridCtrl::InitHeader](../Topic/CMFCPropertyGridCtrl::InitHeader.md)|現在のプロパティ グリッド コントロールを表示するためにフレームワークによって使用される内部 [CMFCHeaderCtrl](../Topic/CMFCHeaderCtrl%20Class.md) オブジェクトを初期化します。|  
|[CMFCPropertyGridCtrl::IsAlphabeticMode](../Topic/CMFCPropertyGridCtrl::IsAlphabeticMode.md)|プロパティ グリッド コントロールがアルファベット モードであるかどうかを示します。|  
|[CMFCPropertyGridCtrl::IsAlwaysShowUserToolTip](../Topic/CMFCPropertyGridCtrl::IsAlwaysShowUserToolTip.md)||  
|[CMFCPropertyGridCtrl::IsDescriptionArea](../Topic/CMFCPropertyGridCtrl::IsDescriptionArea.md)|プロパティ グリッド コントロールの説明領域が表示されるかどうかを示します。|  
|[CMFCPropertyGridCtrl::IsGroupNameFullWidth](../Topic/CMFCPropertyGridCtrl::IsGroupNameFullWidth.md)|現在のプロパティ グリッド コントロールの幅いっぱいに各プロパティ グループ名を表示するかどうかを指定します。|  
|[CMFCPropertyGridCtrl::IsHeaderCtrl](../Topic/CMFCPropertyGridCtrl::IsHeaderCtrl.md)|ヘッダー コントロールが表示されるかどうかを示します。|  
|[CMFCPropertyGridCtrl::IsMarkModifiedProperties](../Topic/CMFCPropertyGridCtrl::IsMarkModifiedProperties.md)|プロパティ グリッド コントロールが変更されたプロパティを表示する方法を示します。|  
|[CMFCPropertyGridCtrl::IsShowDragContext](../Topic/CMFCPropertyGridCtrl::IsShowDragContext.md)|ユーザーが列のサイズを変更するときに、フレームワークが現在のプロパティ グリッド コントロールの名前と値の列を再描画するかどうかを指定します。|  
|[CMFCPropertyGridCtrl::IsVSDotNetLook](../Topic/CMFCPropertyGridCtrl::IsVSDotNetLook.md)|プロパティ グリッド コントロールの外観が VS .NET で使用されるスタイルかどうかを示します。|  
|[CMFCPropertyGridCtrl::MarkModifiedProperties](../Topic/CMFCPropertyGridCtrl::MarkModifiedProperties.md)|変更されたプロパティの表示方法を指定します。|  
|`CMFCPropertyGridCtrl::PreTranslateMessage`|ウィンドウ メッセージが Windows 関数の [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) および [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) にディスパッチされる前に、メッセージを変換するために [CWinApp](../../mfc/reference/cwinapp-class.md) クラスによって使用されます   \([CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md) をオーバーライドします\)。|  
|[CMFCPropertyGridCtrl::RemoveAll](../Topic/CMFCPropertyGridCtrl::RemoveAll.md)|プロパティ グリッド コントロールからすべてのプロパティ オブジェクトを削除します。|  
|[CMFCPropertyGridCtrl::ResetOriginalValues](../Topic/CMFCPropertyGridCtrl::ResetOriginalValues.md)|すべてのプロパティの元の値を復元します。|  
|[CMFCPropertyGridCtrl::SetAlphabeticMode](../Topic/CMFCPropertyGridCtrl::SetAlphabeticMode.md)|アルファベット モードを設定またはリセットします。|  
|[CMFCPropertyGridCtrl::SetBoolLabels](../Topic/CMFCPropertyGridCtrl::SetBoolLabels.md)|ブール値ラベルのテキストを指定します。|  
|[CMFCPropertyGridCtrl::SetCurSel](../Topic/CMFCPropertyGridCtrl::SetCurSel.md)|プロパティ グリッド コントロールのプロパティを選択します。|  
|[CMFCPropertyGridCtrl::SetCustomColors](../Topic/CMFCPropertyGridCtrl::SetCustomColors.md)|プロパティ グリッド コントロールの各種要素のカスタム カラーを指定します。|  
|[CMFCPropertyGridCtrl::SetDescriptionRows](../Topic/CMFCPropertyGridCtrl::SetDescriptionRows.md)|現在のプロパティ グリッド コントロールの説明セクションに表示する行数を指定します。|  
|[CMFCPropertyGridCtrl::SetGroupNameFullWidth](../Topic/CMFCPropertyGridCtrl::SetGroupNameFullWidth.md)|現在のプロパティ グリッド コントロールの幅いっぱいにプロパティのグループのカテゴリ名を表示するかどうかを指定します。|  
|[CMFCPropertyGridCtrl::SetListDelimiter](../Topic/CMFCPropertyGridCtrl::SetListDelimiter.md)|プロパティ値のリストで区切り記号として使用される文字を定義します。|  
|[CMFCPropertyGridCtrl::SetShowDragContext](../Topic/CMFCPropertyGridCtrl::SetShowDragContext.md)|ユーザーが列のサイズを変更するときに、フレームワークが現在のプロパティ グリッド コントロールの名前と値の列を再描画するかどうかを指定します。|  
|[CMFCPropertyGridCtrl::SetVSDotNetLook](../Topic/CMFCPropertyGridCtrl::SetVSDotNetLook.md)|プロパティ グリッド コントロールの外観を、VS .NET で使用されているスタイルに設定します。|  
|[CMFCPropertyGridCtrl::UpdateColor](../Topic/CMFCPropertyGridCtrl::UpdateColor.md)|現在選択されている色プロパティのカラー値を設定します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCPropertyGridCtrl::AdjustLayout](../Topic/CMFCPropertyGridCtrl::AdjustLayout.md)|プロパティ グリッド コントロールおよびそのプロパティを再描画します。|  
|[CMFCPropertyGridCtrl::CompareProps](../Topic/CMFCPropertyGridCtrl::CompareProps.md)|プロパティを並べ替えるために、プロパティ グリッド コントロールによって呼び出されます。|  
|[CMFCPropertyGridCtrl::EditItem](../Topic/CMFCPropertyGridCtrl::EditItem.md)|ユーザーがプロパティの変更を開始したときに、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridCtrl::EndEditItem](../Topic/CMFCPropertyGridCtrl::EndEditItem.md)|ユーザーがプロパティの変更を停止したときに、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridCtrl::Init](../Topic/CMFCPropertyGridCtrl::Init.md)|プロパティ グリッド コントロールを初期化するために、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridCtrl::OnChangeSelection](../Topic/CMFCPropertyGridCtrl::OnChangeSelection.md)|現在の選択項目が変更されたときに、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridCtrl::OnClickButton](../Topic/CMFCPropertyGridCtrl::OnClickButton.md)|プロパティ ボタンがクリックされたときに、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridCtrl::OnDrawBorder](../Topic/CMFCPropertyGridCtrl::OnDrawBorder.md)|プロパティ グリッド コントロールの周囲に境界線を描画するために、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridCtrl::OnDrawDescription](../Topic/CMFCPropertyGridCtrl::OnDrawDescription.md)|説明領域の描画および説明テキストの表示を行うためにフレームワークによって呼び出されます。|  
|[CMFCPropertyGridCtrl::OnDrawList](../Topic/CMFCPropertyGridCtrl::OnDrawList.md)|プロパティ グリッド コントロールのプロパティ リストを表示するために、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridCtrl::OnDrawProperty](../Topic/CMFCPropertyGridCtrl::OnDrawProperty.md)|プロパティを表示するために、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridCtrl::OnPropertyChanged](../Topic/CMFCPropertyGridCtrl::OnPropertyChanged.md)|プロパティの値が変更されたときに、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridCtrl::OnSelectCombo](../Topic/CMFCPropertyGridCtrl::OnSelectCombo.md)|コンボ ボックス コントロールを含むプロパティが選択されたときに、フレームワークによって呼び出されます。|  
|[CMFCPropertyGridCtrl::ValidateItemData](../Topic/CMFCPropertyGridCtrl::ValidateItemData.md)|プロパティ データを検証するために、フレームワークによって呼び出されます。|  
  
## 解説  
 `CMFCPropertyGridCtrl` クラスは、[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md) クラスから派生した編集可能なプロパティを含むプロパティ グリッド コントロールを表示します。  各プロパティは 1 つの型を表し、サブ項目を含むことができます。  プロパティ グリッド コントロールは、一番下でサイズを変更できる領域を使用します。ここには、選択したプロパティの説明を表示できます。  
  
 プロパティ グリッド コントロールを使用するには、`CMFCPropertyGridCtrl` オブジェクトを構築し、次に [CMFCPropertyGridCtrl::Create](../Topic/CMFCPropertyGridCtrl::Create.md) メソッドを呼び出します。  一覧にプロパティを追加するには、[CMFCPropertyGridCtrl::AddProperty](../Topic/CMFCPropertyGridCtrl::AddProperty.md) メソッドを使用します。  
  
## 選択プロパティ  
 プロパティ項目は、値を表すのではなく、ユーザーが色、ファイル、またはフォントを選択できるダイアログ ボックスを開始することができます。  
  
 次の表は、4 種類の選択プロパティを一覧にしたものです。  
  
|Class|説明|  
|-----------|--------|  
|[CMFCPropertyGridProperty クラス](../../mfc/reference/cmfcpropertygridproperty-class.md)|文字列、ブール値、データなどを指定するために使用される一般的な目的のプロパティ。|  
|[CMFCPropertyGridColorProperty クラス](../Topic/CMFCPropertyGridColorProperty%20Class.md)|カラー値を選択するために使用されるプロパティ。|  
|[CMFCPropertyGridFileProperty クラス](../Topic/CMFCPropertyGridFileProperty%20Class.md)|ファイルを選択するために使用されるプロパティ。|  
|[CMFCPropertyGridFontProperty クラス](../../mfc/reference/cmfcpropertygridfontproperty-class.md)|フォントを選択するために使用されるプロパティ。|  
  
## 図  
 次の図は、プロパティを表示するプロパティ グリッド コントロールを 2 つの方法で示します。  1 番目の図は、プロパティを階層的に示し、2 番目の図はプロパティをアルファベット順に示しています。  
  
 ![プロパティ リスト PropertySheet](../../mfc/reference/media/proplist.png "PropList")  
  
## 使用例  
 `CMFCPropertyGridCtrl` クラスのさまざまなメソッドを使用してプロパティ グリッド コントロール オブジェクトを設定する方法を次の例に示します。  例では、ヘッダー コントロールの有効化、説明領域の有効化、プロパティ グリッド コントロールの外観の設定を行う方法について示しています。  また、コントロールがすべてのプロパティをプロパティ名で並べ替えるためにアルファベット モードを設定する方法、およびプロパティ グリッド コントロールの各種の要素にカスタム カラーを設定する方法も示しています。  この例では [新しいコントロールのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!CODE [NVC_MFC_NewControls#14](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#14)]  
[!CODE [NVC_MFC_NewControls#16](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#16)]  
[!CODE [NVC_MFC_NewControls#20](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#20)]  
[!CODE [NVC_MFC_NewControls#21](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#21)]  
[!CODE [NVC_MFC_NewControls#24](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#24)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)  
  
## 必要条件  
 **ヘッダー :** afxpropertygridctrl.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)