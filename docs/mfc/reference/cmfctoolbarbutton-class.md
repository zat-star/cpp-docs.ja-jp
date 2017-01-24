---
title: "CMFCToolBarButton クラス | Microsoft Docs"
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
  - "CMFCToolBarButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarButton クラス"
ms.assetid: 8a6ecffb-86b0-4f5c-8211-a9146b463efd
caps.latest.revision: 34
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarButton クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ツール バーのボタン機能を提供します。  
  
## 構文  
  
```  
class CMFCToolBarButton : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolBarButton::CMFCToolBarButton](../Topic/CMFCToolBarButton::CMFCToolBarButton.md)|`CMFCToolBarButton` オブジェクトを構築し、初期化します。|  
|`CMFCToolBarButton::~CMFCToolBarButton`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolBarButton::CanBeDropped](../Topic/CMFCToolBarButton::CanBeDropped.md)|カスタマイズの際、ユーザーがツール バーまたはメニューにボタンを配置できるかどうかを指定します。|  
|[CMFCToolBarButton::CanBeStored](../Topic/CMFCToolBarButton::CanBeStored.md)|ボタンを格納できるかどうかを指定します。|  
|[CMFCToolBarButton::CanBeStretched](../Topic/CMFCToolBarButton::CanBeStretched.md)|ユーザーがカスタマイズ中にボタンを引き伸ばせるかどうかを指定します|  
|[CMFCToolBarButton::CompareWith](../Topic/CMFCToolBarButton::CompareWith.md)|指定された `CMFCToolBarButton` オブジェクトを、このインスタンスと比較します。|  
|[CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md)|別のツール バー ボタンのプロパティを現在のボタンにコピーします。|  
|[CMFCToolBarButton::CreateFromOleData](../Topic/CMFCToolBarButton::CreateFromOleData.md)|指定した `COleDataObject` オブジェクトから `CMFCToolBarButton` オブジェクトを作成します。|  
|`CMFCToolBarButton::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークによって使用されます。|  
|[CMFCToolBarButton::EnableWindow](../Topic/CMFCToolBarButton::EnableWindow.md)|マウス入力およびキーボード入力を許可または禁止します。|  
|[CMFCToolBarButton::ExportToMenuButton](../Topic/CMFCToolBarButton::ExportToMenuButton.md)|ツール バー ボタンのテキストをメニューにコピーします。|  
|[CMFCToolBarButton::GetClipboardFormat](../Topic/CMFCToolBarButton::GetClipboardFormat.md)|アプリケーションのグローバル クリップボード形式を取得します。|  
|[CMFCToolBarButton::GetHwnd](../Topic/CMFCToolBarButton::GetHwnd.md)|ツール バー ボタンに関連付けられたウィンドウ ハンドルを取得します。|  
|[CMFCToolBarButton::GetImage](../Topic/CMFCToolBarButton::GetImage.md)|ボタンのイメージのインデックスを取得します。|  
|[CMFCToolBarButton::GetInvalidateRect](../Topic/CMFCToolBarButton::GetInvalidateRect.md)|再描画する必要がある、ボタンのクライアント領域内での部分を取得します。|  
|[CMFCToolBarButton::GetParentWnd](../Topic/CMFCToolBarButton::GetParentWnd.md)|ボタンの親ウィンドウを取得します。|  
|[CMFCToolBarButton::GetProtectedCommands](../Topic/CMFCToolBarButton::GetProtectedCommands.md)|ユーザーがカスタマイズできないコマンドの一覧を取得します。|  
|[CMFCToolBarButton::GetTextSize](../Topic/CMFCToolBarButton::GetTextSize.md)|ボタン テキストのサイズを取得します。|  
|[CMFCToolBarButton::HasFocus](../Topic/CMFCToolBarButton::HasFocus.md)|ボタンに現在の入力フォーカスがあるかどうかを判断します。|  
|[CMFCToolBarButton::HaveHotBorder](../Topic/CMFCToolBarButton::HaveHotBorder.md)|ユーザーがボタンを選択したときに、ボタンの境界線を表示するかどうかを判定します|  
|[CMFCToolBarButton::IsDrawImage](../Topic/CMFCToolBarButton::IsDrawImage.md)|ボタンにイメージが表示されるかどうかを判断します。|  
|[CMFCToolBarButton::IsDrawText](../Topic/CMFCToolBarButton::IsDrawText.md)|ボタンにテキスト ラベルを表示するかどうかを判断します。|  
|[CMFCToolBarButton::IsDroppedDown](../Topic/CMFCToolBarButton::IsDroppedDown.md)|ボタンがサブメニューを表示するかどうかを判断します。|  
|[CMFCToolBarButton::IsEditable](../Topic/CMFCToolBarButton::IsEditable.md)|ボタンをカスタマイズできるかどうかを判断します。|  
|[CMFCToolBarButton::IsExtraSize](../Topic/CMFCToolBarButton::IsExtraSize.md)|拡張された境界でボタンを表示できるかどうかを指定します。|  
|[CMFCToolBarButton::IsFirstInGroup](../Topic/CMFCToolBarButton::IsFirstInGroup.md)|ボタンがボタン グループの先頭にあるかどうかを判断します。|  
|[CMFCToolBarButton::IsHidden](../Topic/CMFCToolBarButton::IsHidden.md)|ボタンが非表示かどうかを判断します。|  
|[CMFCToolBarButton::IsHorizontal](../Topic/CMFCToolBarButton::IsHorizontal.md)|ボタンが水平方向のツール バーに配置されているかどうかを判断します。|  
|[CMFCToolBarButton::IsLastInGroup](../Topic/CMFCToolBarButton::IsLastInGroup.md)|そのボタンを、ボタン グループの末尾に配置するかどうかを指定します。|  
|[CMFCToolBarButton::IsLocked](../Topic/CMFCToolBarButton::IsLocked.md)|ボタンがロックされた \(カスタマイズできない\) ツール バー上にあるかどうかを判断します。|  
|[CMFCToolBarButton::IsOwnerOf](../Topic/CMFCToolBarButton::IsOwnerOf.md)|ボタンが、指定されたウィンドウ ハンドルのオーナーかどうかを判断します。|  
|[CMFCToolBarButton::IsVisible](../Topic/CMFCToolBarButton::IsVisible.md)|ツール バー ボタンが表示されているかどうかを判断します。|  
|[CMFCToolBarButton::IsWindowVisible](../Topic/CMFCToolBarButton::IsWindowVisible.md)|ボタンの基になるウィンドウ ハンドルが表示されているかどうかを判断します。|  
|[CMFCToolBarButton::NotifyCommand](../Topic/CMFCToolBarButton::NotifyCommand.md)|ボタンで [WM\_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) メッセージを処理するかどうかを指定します。|  
|[CMFCToolBarButton::OnAddToCustomizePage](../Topic/CMFCToolBarButton::OnAddToCustomizePage.md)|ボタンが **\[カスタマイズ\]** ダイアログ ボックスに追加されたときに、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::OnBeforeDrag](../Topic/CMFCToolBarButton::OnBeforeDrag.md)|ボタンをドラッグできるかどうかを指定します。|  
|[CMFCToolBarButton::OnBeforeDrop](../Topic/CMFCToolBarButton::OnBeforeDrop.md)|ユーザーがボタンをターゲットのツール バーにドロップできるかどうかを指定します。|  
|[CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md)|指定されたデバイス コンテキストとドッキングの状態に応じたボタンのサイズを計算するために、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::OnCancelMode](../Topic/CMFCToolBarButton::OnCancelMode.md)|[WM\_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) メッセージを処理するために、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md)|新しいツール バーにボタンが挿入されたときに、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md)|ユーザーがマウス ボタンをクリックしたときに、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::OnClickUp](../Topic/CMFCToolBarButton::OnClickUp.md)|ユーザーがマウス ボタンを放すと、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::OnContextHelp](../Topic/CMFCToolBarButton::OnContextHelp.md)|親ツール バーが `WM_HELPHITTEST` メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::OnCtlColor](../Topic/CMFCToolBarButton::OnCtlColor.md)|親ツール バーが `WM_CTLCOLOR` メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::OnCustomizeMenu](../Topic/CMFCToolBarButton::OnCustomizeMenu.md)|アプリケーションが親ツール バーにショートカット メニューを表示する場合、指定されたメニューをボタンが変更できるようにします。|  
|[CMFCToolBarButton::OnDblClk](../Topic/CMFCToolBarButton::OnDblClk.md)|親ツール バーが [WM\_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md)|指定されたスタイルとオプションを使用してボタンを描画するために、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md)|**\[カスタマイズ\]** ダイアログ ボックスの **\[コマンド\]** ペインにボタンを描画するために、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::OnGetCustomToolTipText](../Topic/CMFCToolBarButton::OnGetCustomToolTipText.md)|ボタンのカスタム ツールヒントのテキストを取得するために、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::OnGlobalFontsChanged](../Topic/CMFCToolBarButton::OnGlobalFontsChanged.md)|グローバル フォントが変更されたときに、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::OnMove](../Topic/CMFCToolBarButton::OnMove.md)|親ツール バーが移動されたときに、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::OnShow](../Topic/CMFCToolBarButton::OnShow.md)|ボタンが表示または非表示に切り替わったときに、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::OnSize](../Topic/CMFCToolBarButton::OnSize.md)|親ツール バーのサイズまたは位置が変更され、それに伴ってホタンのサイズを変更する必要がある場合に、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::OnToolHitTest](../Topic/CMFCToolBarButton::OnToolHitTest.md)|ボタンに外接する四角形内にポインターがあるかどうかを親ツール バーが判断する必要がある場合に、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::OnUpdateToolTip](../Topic/CMFCToolBarButton::OnUpdateToolTip.md)|親ツール バーが、そのツールヒント テキストを更新するときに、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::PrepareDrag](../Topic/CMFCToolBarButton::PrepareDrag.md)|ボタンがドラッグ アンド ドロップ操作を実行しようとすると、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::Rect](../Topic/CMFCToolBarButton::Rect.md)|ボタンの外接する四角形を取得します。|  
|[CMFCToolBarButton::ResetImageToDefault](../Topic/CMFCToolBarButton::ResetImageToDefault.md)|ボタンに関連付けられるイメージに既定の値を設定します。|  
|[CMFCToolBarButton::SaveBarState](../Topic/CMFCToolBarButton::SaveBarState.md)|ツール バー ボタンの状態を保存します。|  
|[CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md)|このオブジェクトをアーカイブから読み取るか、アーカイブに書き込みます   \([CObject::Serialize](../Topic/CObject::Serialize.md) をオーバーライドします。\)|  
|[CMFCToolBarButton::SetACCData](../Topic/CMFCToolBarButton::SetACCData.md)|指定された `CAccessibilityData` オブジェクトに、ツール バー ボタンのアクセシビリティ データを設定します。|  
|[CMFCToolBarButton::SetClipboardFormatName](../Topic/CMFCToolBarButton::SetClipboardFormatName.md)|グローバル クリップボード形式の名前を変更します。|  
|[CMFCToolBarButton::SetImage](../Topic/CMFCToolBarButton::SetImage.md)|ボタンのイメージのインデックスを設定します。|  
|[CMFCToolBarButton::SetProtectedCommands](../Topic/CMFCToolBarButton::SetProtectedCommands.md)|ユーザーがカスタマイズできないコマンドの一覧を設定します。|  
|[CMFCToolBarButton::SetRadio](../Topic/CMFCToolBarButton::SetRadio.md)|ボタンがオンになっている状態を変更したときに、フレームワークによって呼び出されます。|  
|[CMFCToolBarButton::SetRect](../Topic/CMFCToolBarButton::SetRect.md)|ボタンの外接する四角形を設定します。|  
|[CMFCToolBarButton::SetStyle](../Topic/CMFCToolBarButton::SetStyle.md)|ボタンのスタイルを設定します。|  
|[CMFCToolBarButton::SetVisible](../Topic/CMFCToolBarButton::SetVisible.md)|ボタンを表示するかどうかを指定します。|  
|[CMFCToolBarButton::Show](../Topic/CMFCToolBarButton::Show.md)|ボタンの表示、非表示を切り替えます。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolBarButton::m\_bImage](../Topic/CMFCToolBarButton::m_bImage.md)|ボタンにイメージを表示するかどうかを指定します。|  
|[CMFCToolBarButton::m\_bText](../Topic/CMFCToolBarButton::m_bText.md)|ボタンにテキスト ラベルを表示するかどうかを指定します。|  
|[CMFCToolBarButton::m\_bTextBelow](../Topic/CMFCToolBarButton::m_bTextBelow.md)|ボタンのイメージの下にテキスト ラベルを表示するかどうかを指定します。|  
|[CMFCToolBarButton::m\_bUserButton](../Topic/CMFCToolBarButton::m_bUserButton.md)|ボタンにユーザー定義のイメージがあるかどうかを指定します。|  
|[CMFCToolBarButton::m\_bWholeText](../Topic/CMFCToolBarButton::m_bWholeText.md)|テキスト ラベルが外接する四角形に収まらない場合でもボタンにフル テキスト ラベルを表示するかどうかを指定します。|  
|[CMFCToolBarButton::m\_bWrap](../Topic/CMFCToolBarButton::m_bWrap.md)|区切りの横のボタンが次の行に挿入されるかどうかを指定します。|  
|[CMFCToolBarButton::m\_bWrapText](../Topic/CMFCToolBarButton::m_bWrapText.md)|複数行のテキスト ラベルを有効にするかどうかを指定します。|  
|[CMFCToolBarButton::m\_nID](../Topic/CMFCToolBarButton::m_nID.md)|ボタンのコマンド ID。|  
|[CMFCToolBarButton::m\_nStyle](../Topic/CMFCToolBarButton::m_nStyle.md)|ボタンのスタイル。|  
|[CMFCToolBarButton::m\_strText](../Topic/CMFCToolBarButton::m_strText.md)|ボタンのテキスト ラベル。|  
  
## 解説  
 `CMFCToolbarButton` オブジェクトはツール バー上にあるコントロールです。  その動作は通常のボタンの動作に似ています。  このオブジェクトには、イメージとテキスト ラベルを割り当てることができます。  ツール バー ボタンはコマンド ID を持つこともできます。  ユーザーがツール バー ボタンをクリックすると、フレームワークは、この ID で指定されるコマンドを実行します。  
  
 通常、ツール バー ボタンはカスタマイズできます。ユーザーは 1 つのツール バーから別のツール バーにボタンをドラッグし、テキスト ラベルとイメージをコピー、貼り付け、削除、および編集することができます。  ユーザーがツール バーをカスタマイズできないようにするために、ツール バーをロックできます。  そのためには、[CMFCToolBar::LoadToolBar](../Topic/CMFCToolBar::LoadToolBar.md) を呼び出すときに `bLocked` フラグを `TRUE` に設定するか、または [CMFCToolBarButton::SetProtectedCommands](../Topic/CMFCToolBarButton::SetProtectedCommands.md) メソッドを使用して保護されたコマンドのグローバル リストに個別のボタンのコマンド ID を追加します。  
  
 `CMFCToolBarButton` オブジェクトは、ツール バー イメージのグローバル コレクションのイメージをアプリケーションに表示します。  これらのコレクションは、親ツール バー [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)によって保持されます。  詳細については、「[CMFCToolBarImages クラス](../../mfc/reference/cmfctoolbarimages-class.md)」を参照してください。  
  
 ユーザーがツール バー ボタンをクリックすると、その親ツール バーは、マウス メッセージを処理して適切なアクションをボタンに伝えます。  ボタンに有効なコマンド ID があれば、親ツール バーは親フレームに `WM_COMMAND` メッセージを送信します。  
  
 `CMFCToolBarButton` クラスは、[CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)、[CMFCToolBarEditBoxButton クラス](../Topic/CMFCToolBarEditBoxButton%20Class.md)、および [CMFCToolBarComboBoxButton クラス](../Topic/CMFCToolBarComboBoxButton%20Class.md)など、他のツール バー ボタン クラスの基本クラスです。  
  
## 使用例  
 `CMFCToolBarButton` クラスのさまざまなメソッドを使用して `CMFCToolBarButton` オブジェクトを構成する方法を次の例に示します。  また、マウスおよびキーボードの入力を有効にし、ボタンのイメージ インデックスを設定し、ボタンに外接した四角形を設定し、ボタンを表示する方法も示します。  このコード スニペットは [タブ コントロールのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_TabControl#1](../../mfc/reference/codesnippet/CPP/cmfctoolbarbutton-class_1.cpp)]  
[!code-cpp[NVC_MFC_TabControl#2](../../mfc/reference/codesnippet/CPP/cmfctoolbarbutton-class_2.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
## 必要条件  
 **ヘッダー :** afxtoolbarbutton.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarImages クラス](../../mfc/reference/cmfctoolbarimages-class.md)   
 [CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md)   
 [CMFCToolBarButton::NotifyCommand](../Topic/CMFCToolBarButton::NotifyCommand.md)