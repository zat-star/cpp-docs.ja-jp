---
title: "CComboBox クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComboBox クラス"
  - "コンボ ボックス, CComboBox オブジェクト"
ms.assetid: 4e73b5df-0d2e-4658-9706-38133fb10513
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CComboBox クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows のコンボ ボックスの機能が用意されています。  
  
## 構文  
  
```  
class CComboBox : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComboBox::CComboBox](../Topic/CComboBox::CComboBox.md)|`CComboBox` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComboBox::AddString](../Topic/CComboBox::AddString.md)|コンボ ボックス、または **CBS\_SORT** のスタイルのリスト ボックスの分類された位置のリスト ボックスの一覧の末尾に文字列を追加します。|  
|[CComboBox::Clear](../Topic/CComboBox::Clear.md)|エディット コントロールの現在の選択がある場合、削除 \(クリア\) します。|  
|[CComboBox::CompareItem](../Topic/CComboBox::CompareItem.md)|並べ替えられたオーナー描画コンボ ボックスのリストに新しい項目の相対位置を決定するために、フレームワークによって呼び出されます。|  
|[CComboBox::Copy](../Topic/CComboBox::Copy.md)|**CF\_TEXT** 形式でクリップボードに現在の選択がある場合、コピーします。|  
|[CComboBox::Create](../Topic/CComboBox::Create.md)|コンボ ボックスを作成し、`CComboBox` のオブジェクトにアタッチします。|  
|[CComboBox::Cut](../Topic/CComboBox::Cut.md)|エディット コントロール、コピーの現在の選択範囲がある場合は、**CF\_TEXT** 形式でクリップボードに削除されたテキスト削除し \(切り取り\) ます。|  
|[CComboBox::DeleteItem](../Topic/CComboBox::DeleteItem.md)|リスト項目がオーナー描画コンボ ボックスから削除されるときに、フレームワークによって呼び出されます。|  
|[CComboBox::DeleteString](../Topic/CComboBox::DeleteString.md)|コンボ ボックスのリスト ボックスから文字列を削除します。|  
|[CComboBox::Dir](../Topic/CComboBox::Dir.md)|コンボ ボックスのリスト ボックスにファイル名のリストを追加します。|  
|[CComboBox::DrawItem](../Topic/CComboBox::DrawItem.md)|オーナー描画コンボ ボックスの外観が変更されたときに、フレームワークによって呼び出されます。|  
|[CComboBox::FindString](../Topic/CComboBox::FindString.md)|コンボ ボックスのリスト ボックスで指定されているプレフィックスを含む最初の文字列を検索します。|  
|[CComboBox::FindStringExact](../Topic/CComboBox::FindStringExact.md)|その最初のリスト ボックスの文字列 \(コンボ ボックス\) で一致した文字列を検索します。|  
|[CComboBox::GetComboBoxInfo](../Topic/CComboBox::GetComboBoxInfo.md)|`CComboBox` のオブジェクトについての情報を取得します。|  
|[CComboBox::GetCount](../Topic/CComboBox::GetCount.md)|コンボ ボックスのリスト ボックスの項目数を取得します。|  
|[CComboBox::GetCueBanner](../Topic/CComboBox::GetCueBanner.md)|コンボ ボックス コントロールに表示されるキューのテキストを取得します。|  
|[CComboBox::GetCurSel](../Topic/CComboBox::GetCurSel.md)|コンボ ボックスのリスト ボックスで現在選択されている項目のインデックス \(存在する場合\) を取得します。|  
|[CComboBox::GetDroppedControlRect](../Topic/CComboBox::GetDroppedControlRect.md)|コンボ ボックスの表示 \(ドロップダウン\) ドロップダウン リスト ボックスの画面座標を取得します。|  
|[CComboBox::GetDroppedState](../Topic/CComboBox::GetDroppedState.md)|ドロップダウン コンボ ボックスのリスト ボックスが表示されるかどうかを判断します \(削除\)。|  
|[CComboBox::GetDroppedWidth](../Topic/CComboBox::GetDroppedWidth.md)|コンボ ボックスのドロップダウン リスト ボックス部分の最小によって割り当てられた幅を取得します。|  
|[CComboBox::GetEditSel](../Topic/CComboBox::GetEditSel.md)|コンボ ボックスのエディット コントロールの現在の選択範囲の開始文字と終了文字位置を取得します。|  
|[CComboBox::GetExtendedUI](../Topic/CComboBox::GetExtendedUI.md)|コンボ ボックスが既定のユーザー インターフェイスや拡張ユーザー インターフェイスを持つかどうかを判定します。|  
|[CComboBox::GetHorizontalExtent](../Topic/CComboBox::GetHorizontalExtent.md)|コンボ ボックスのリスト ボックス部分を水平方向にスクロールできるピクセル幅を返します。|  
|[CComboBox::GetItemData](../Topic/CComboBox::GetItemData.md)|指定したコンボ ボックスの項目に関連付けられたアプリケーションに用意された 32 ビット値を取得します。|  
|[CComboBox::GetItemDataPtr](../Topic/CComboBox::GetItemDataPtr.md)|指定したコンボ ボックスの項目に関連付けられたアプリケーションに用意された 32 ビット ポインターを取得します。|  
|[CComboBox::GetItemHeight](../Topic/CComboBox::GetItemHeight.md)|コンボ ボックス リストの項目の高さを取得します。|  
|[CComboBox::GetLBText](../Topic/CComboBox::GetLBText.md)|コンボ ボックスのリスト ボックスから文字列を取得します。|  
|[CComboBox::GetLBTextLen](../Topic/CComboBox::GetLBTextLen.md)|コンボ ボックスのリスト ボックスの文字列の長さを取得します。|  
|[CComboBox::GetLocale](../Topic/CComboBox::GetLocale.md)|コンボ ボックスのロケール識別子を取得します。|  
|[CComboBox::GetMinVisible](../Topic/CComboBox::GetMinVisible.md)|現在のコンボ ボックスのドロップダウン リストに表示されるアイテムの最小数を取得します。|  
|[CComboBox::GetTopIndex](../Topic/CComboBox::GetTopIndex.md)|コンボ ボックスのリスト ボックス部分に最初に表示される項目のインデックスを返します。|  
|[CComboBox::InitStorage](../Topic/CComboBox::InitStorage.md)|コンボ ボックスのリスト ボックス部分の項目と文字列のメモリ ブロックを割り当てします。|  
|[CComboBox::InsertString](../Topic/CComboBox::InsertString.md)|コンボ ボックスのリスト ボックスに文字列を追加します。|  
|[CComboBox::LimitText](../Topic/CComboBox::LimitText.md)|ユーザーがコンボ ボックスのエディット コントロールに入力できるテキストの長さを制限します。|  
|[CComboBox::MeasureItem](../Topic/CComboBox::MeasureItem.md)|オーナー描画コンボ ボックスが作成されると、コンボ ボックスのサイズを決定するために、フレームワークによって呼び出されます。|  
|[CComboBox::Paste](../Topic/CComboBox::Paste.md)|現在のカーソル位置で編集コントロールにクリップボードからデータを挿入します。  データがクリップボードに **CF\_TEXT** の形式のデータが含まれている場合にのみ挿入します。|  
|[CComboBox::ResetContent](../Topic/CComboBox::ResetContent.md)|コンボ ボックスのリスト ボックスとエディット コントロールからすべての項目を削除します。|  
|[CComboBox::SelectString](../Topic/CComboBox::SelectString.md)|文字列の場合、コンボ ボックスのリスト ボックスの文字列の検索で、リスト ボックスに文字列を選択し、エディット コントロールに文字列をコピーします。|  
|[CComboBox::SetCueBanner](../Topic/CComboBox::SetCueBanner.md)|コンボ ボックス コントロールに表示されるキューのテキストを設定します。|  
|[CComboBox::SetCurSel](../Topic/CComboBox::SetCurSel.md)|コンボ ボックスのリスト ボックスの文字列を選択します。|  
|[CComboBox::SetDroppedWidth](../Topic/CComboBox::SetDroppedWidth.md)|コンボ ボックスのドロップダウン リスト ボックス部分の最小によって割り当てられた幅を設定します。|  
|[CComboBox::SetEditSel](../Topic/CComboBox::SetEditSel.md)|コンボ ボックスのエディット コントロール内の文字を選択します。|  
|[CComboBox::SetExtendedUI](../Topic/CComboBox::SetExtendedUI.md)|**CBS\_DROPDOWN** または **CBS\_DROPDOWNLIST** のスタイルを持つコンボ ボックスの既定のユーザー インターフェイスや拡張ユーザー インターフェイスを選択します。|  
|[CComboBox::SetHorizontalExtent](../Topic/CComboBox::SetHorizontalExtent.md)|コンボ ボックスのリスト ボックス部分を水平方向にスクロールできるピクセル幅を設定します。|  
|[CComboBox::SetItemData](../Topic/CComboBox::SetItemData.md)|32 ビット値をコンボ ボックスの指定項目に関連付けられる。|  
|[CComboBox::SetItemDataPtr](../Topic/CComboBox::SetItemDataPtr.md)|32 ビット ポインターをコンボ ボックスの指定項目に関連付けられる。|  
|[CComboBox::SetItemHeight](../Topic/CComboBox::SetItemHeight.md)|コンボ ボックス リストの項目の高さまたはコンボ ボックスのエディット コントロール \(または静的テキスト\) 部分の高さを設定します。|  
|[CComboBox::SetLocale](../Topic/CComboBox::SetLocale.md)|コンボ ボックスのロケール識別子を設定します。|  
|[CComboBox::SetMinVisibleItems](../Topic/CComboBox::SetMinVisibleItems.md)|現在のコンボ ボックスのドロップダウン リストに表示されるアイテムの最小数を設定します。|  
|[CComboBox::SetTopIndex](../Topic/CComboBox::SetTopIndex.md)|コンボ ボックスのリスト ボックス部分を先頭で指定されたインデックスの項目を表示するように指定します。|  
|[CComboBox::ShowDropDown](../Topic/CComboBox::ShowDropDown.md)|**CBS\_DROPDOWN** または **CBS\_DROPDOWNLIST** のスタイルを持つコンボ ボックスのリスト ボックスを表示または非表示にします。|  
  
## 解説  
 コンボ ボックスは、静的コントロールまたはエディット コントロールのいずれかとリスト ボックスを組み合わせたものです。  コントロールのリスト ボックス部分は、常に表示することも、ユーザーがエディット コントロールの横のドロップダウン矢印を選択したときだけ表示することもできます。  
  
 リスト ボックスで現在選択されている項目があると、その項目が静的コントロールまたはエディット コントロールに表示されます。  また、ドロップダウン リスト スタイルが指定されているコンボ ボックスでは、ユーザーがリスト ボックス内にある項目の先頭の文字を入力できます。リスト ボックスが表示されている場合、入力された文字で始まる次の項目が強調表示されます。  
  
 コンボ ボックスの 3 つの[スタイル](../../mfc/reference/combo-box-styles.md)を次の表で比較します。  
  
|スタイル|リスト ボックスが表示されるとき|コントロールの種類|  
|----------|----------------------|---------------|  
|シンプル|常時|Edit|  
|ドロップダウン|ドロップダウンされたとき|Edit|  
|ドロップダウン リスト|ドロップダウンされたとき|静的|  
  
 `CComboBox` オブジェクトを作成するには、ダイアログ テンプレートを使用するか、直接コードを記述します。  いずれの場合も、まず `CComboBox` クラスのコンストラクターを呼び出して `CComboBox` オブジェクトを構築します。続いて、コントロールを作成するために [Create](../Topic/CComboBox::Create.md) メンバー関数を呼び出し、作成したコントロールを `CComboBox` オブジェクトを結び付けます。  
  
 コンボ ボックスからその親クラス \(通常は `CDialog` の派生クラス\) に送られた Windows の通知メッセージを処理するには、各メッセージの送信先の親クラスに、メッセージ マップのエントリとメッセージ ハンドラー メンバー関数を追加します。  
  
 各メッセージ マップのエントリは次の形式を持ちます。  
  
 **ON\_**Notification**\(** `id`**,** `memberFxn` **\)**  
  
 `id` には、通知を送るコンボ ボックス コントロールの子ウィンドウ ID を指定します。`memberFxn` には、通知を処理する親クラスのメンバー関数名を指定します。  
  
 親の関数のプロトタイプは次のようになります。  
  
 **afx\_msg** `void` `memberFxn`**\( \);**  
  
 送られてくる通知の順序は決まっていません。  特に、**CBN\_SELCHANGE** 通知は、**CBN\_CLOSEUP** 通知の前に発生するのか、後に発生するのかがわかりません。  
  
 有効なメッセージ マップのエントリを次に示します。  
  
-   **ON\_CBN\_CLOSEUP** \(Windows 3.1 以降\)。コンボ ボックスのリスト ボックスが閉じられました。  この通知メッセージは、[CBS\_SIMPLE](../../mfc/reference/combo-box-styles.md) スタイルを持つコンボ ボックスについては送られません。  
  
-   **ON\_CBN\_DBLCLK** ユーザーはコンボ ボックスのリスト ボックス内の文字列をダブルクリックします。  この通知メッセージは、**CBS\_SIMPLE** スタイルを持つコンボ ボックスについてだけ送られます。  [CBS\_DROPDOWN](../../mfc/reference/combo-box-styles.md) スタイルまたは [CBS\_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) スタイルを持つコンボ ボックスでは、シングルクリックするとリスト ボックスが非表示になるので、ダブルクリックされることはありません。  
  
-   **ON\_CBN\_DROPDOWN** は、コンボ ボックスのリスト ボックス ドロップ通知 \(表示されるようにしてください\)。  この通知メッセージは、**CBS\_DROPDOWN** または **CBS\_DROPDOWNLIST** スタイルを持つコンボ ボックスについてだけ送られます。  
  
-   **ON\_CBN\_EDITCHANGE** ユーザーはコンボ ボックスのエディット コントロール部分のテキストを変更する可能性があるアクションをされました。  このメッセージは、**CBN\_EDITUPDATE** メッセージと異なり、Windows が画面を更新した後で送られます。  このメッセージはコンボ ボックスが **CBS\_DROPDOWNLIST** スタイルを持つときには送られません。  
  
-   **ON\_CBN\_EDITUPDATE** はによって表示されるテキストにコンボ ボックスのエディット コントロール部分を通知します。  この通知メッセージは、コントロールがテキストの書式を設定し、そのテキストを表示するまでの間に送られます。  このメッセージはコンボ ボックスが **CBS\_DROPDOWNLIST** スタイルを持つときには送られません。  
  
-   コンボ ボックス**ON\_CBN\_ERRSPACE** は、特定の要求に対して十分なメモリを割り当てることはできません。  
  
-   **ON\_CBN\_SELENDCANCEL** \(Windows 3.1 以降\)。ユーザーによる選択がキャンセルされることを通知します。  つまり、ユーザーが項目をクリックしてから、ほかのウィンドウやコントロールをクリックし、コンボ ボックスのリスト ボックスを非表示にした場合などです。  この通知メッセージは、選択が無効になったことを伝えるため、**CBN\_CLOSEUP** 通知メッセージの前に送られます。  **CBN\_SELENDCANCEL** または **CBN\_SELENDOK** 通知メッセージは、**CBN\_CLOSEUP** 通知メッセージが送られない場合 \(コンボ ボックスが **CBS\_SIMPLE** スタイルを持つ場合\) でも送られます。  
  
-   **ON\_CBN\_SELENDOK** ユーザーが項目を選択し、Enter キーを押すか、コンボ ボックスのリスト ボックスを非表示にしたことを通知します。  この通知メッセージは、ユーザーによる選択が有効であることを伝えるために **CBN\_CLOSEUP** メッセージの前に送られます。  **CBN\_SELENDCANCEL** または **CBN\_SELENDOK** 通知メッセージは、**CBN\_CLOSEUP** 通知メッセージが送られない場合 \(コンボ ボックスが **CBS\_SIMPLE** スタイルを持つ場合\) でも送られます。  
  
-   **ON\_CBN\_KILLFOCUS** コンボ ボックスが入力フォーカスを失うことを通知します。  
  
-   **ON\_CBN\_SELCHANGE** は、コンボ ボックスのリスト ボックスで選択リスト ボックスでをクリックするか、方向キーを使用してオプションを変更するユーザーの結果、変更されたことを通知します。  このメッセージを処理するとき、コンボ ボックスのエディット コントロール内のテキストを取得するには、`GetLBText` 関数または別の同種の関数を使います。  `GetWindowText` 関数は使用できません。  
  
-   **ON\_CBN\_SETFOCUS** コンボ ボックスが入力フォーカスを受け取ります。  
  
 ダイアログ ボックス内に \(ダイアログ リソースを使って\) `CComboBox` オブジェクトを作成したときは、ダイアログ ボックスを閉じたときに `CComboBox` オブジェクトは自動的に破棄されます。  
  
 その他のウィンドウ オブジェクトに `CComboBox` オブジェクトを埋め込んだときは、オブジェクトを破棄する必要はありません。  `CComboBox` オブジェクトをスタック上に作成したときは、自動的に破棄されます。  `CComboBox` オブジェクトを **new** 関数を使ってヒープ領域に作成したときは、Windows のコンボ ボックスを破棄したときにオブジェクトが破棄されるように、オブジェクトに対する **delete** 関数を呼び出します。  
  
 `WM_KEYDOWN` と `WM_CHAR` のメッセージを処理する場合は**Note** サブクラス コンボ ボックスのエディット コントロール、リスト ボックス コントロール、クラスを `CEdit` と `CListBox`から取得し、それらのメッセージのハンドラーを派生クラスに追加する必要があります。  詳細については、[http:\/\/support.microsoft.com\/default.aspx?scid\=kb;ja\-jp;q174667](http://support.microsoft.com/default.aspx?scid=kb;ja-jp;q174667) および「[CWnd::SubclassWindow](../Topic/CWnd::SubclassWindow.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CComboBox`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [MFC CTRLBARS サンプル](../../top/visual-cpp-samples.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [CButton クラス](../../mfc/reference/cbutton-class.md)   
 [CEdit クラス](../Topic/CEdit%20Class.md)   
 [CListBox クラス](../Topic/CListBox%20Class.md)   
 [CScrollBar クラス](../../mfc/reference/cscrollbar-class.md)   
 [CStatic クラス](../Topic/CStatic%20Class.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)