---
title: "CMFCTabCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCTabCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTabCtrl クラス"
  - "CMFCTabCtrl コンストラクター"
  - "CMFCTabCtrl::GetTabFromPoint メソッド"
  - "CMFCTabCtrl::IsPtInTabArea メソッド"
  - "CMFCTabCtrl::MoveTab メソッド"
  - "CMFCTabCtrl::PreTranslateMessage メソッド"
  - "CMFCTabCtrl::RecalcLayout メソッド"
  - "CMFCTabCtrl::SwapTabs メソッド"
ms.assetid: d441385d-2c72-4203-96fa-deae2273da35
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CMFCTabCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCTabCtrl` クラスは、タブ コントロールの機能を提供します。  タブ コントロールは、上または下にフラットまたは 3D のタブを持つ、ドッキング可能なウィンドウを表示します。  タブにはテキストとイメージを表示でき、アクティブな状態のときに色を変更することもできます。  
  
## 構文  
  
```  
class CMFCTabCtrl : public CMFCBaseTabCtrl  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CMFCTabCtrl::CMFCTabCtrl`|既定のコンストラクターです。|  
|`CMFCTabCtrl::~CMFCTabCtrl`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCTabCtrl::ActivateMDITab](../Topic/CMFCTabCtrl::ActivateMDITab.md)|現在のタブ コントロールの指定されたタブを表示し、そのタブにフォーカスを設定します。|  
|[CMFCTabCtrl::AllowDestroyEmptyTabbedPane](../Topic/CMFCTabCtrl::AllowDestroyEmptyTabbedPane.md)||  
|[CMFCTabCtrl::AutoSizeWindow](../Topic/CMFCTabCtrl::AutoSizeWindow.md)|タブ コントロールのユーザー インターフェイス要素が変更されたときに、フレームワークがすべてのタブ コントロール ウィンドウのクライアント領域のサイズを変更するかどうかを指定します。|  
|[CMFCTabCtrl::CalcRectEdit](../Topic/CMFCTabCtrl::CalcRectEdit.md)|指定されたタブ領域のサイズを縮小します。  \(`CMFCBaseTabCtrl::CalcRectEdit` をオーバーライドします。\)|  
|[CMFCTabCtrl::Create](../Topic/CMFCTabCtrl::Create.md)|タブ コントロールを作成し、それを `CMFCTabCtrl` オブジェクトにアタッチします。|  
|`CMFCTabCtrl::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークによって使用されます。|  
|[CMFCTabCtrl::EnableActiveTabCloseButton](../Topic/CMFCTabCtrl::EnableActiveTabCloseButton.md)|アクティブなタブの閉じるボタン \(**X**\) の表示と非表示を切り替えます。|  
|[CMFCTabCtrl::EnableInPlaceEdit](../Topic/CMFCTabCtrl::EnableInPlaceEdit.md)|編集可能なタブ ラベルを有効または無効にします。  \([CMFCBaseTabCtrl::EnableInPlaceEdit](../Topic/CMFCBaseTabCtrl::EnableInPlaceEdit.md) をオーバーライドします。\)|  
|[CMFCTabCtrl::EnableTabDocumentsMenu](../Topic/CMFCTabCtrl::EnableTabDocumentsMenu.md)|ウィンドウ タブをスクロールする 2 つのボタンを、タブ付きウィンドウのメニューを開く 1 つのボタンに置き換えます。|  
|[CMFCTabCtrl::EnsureVisible](../Topic/CMFCTabCtrl::EnsureVisible.md)|タブを表示します。|  
|[CMFCTabCtrl::GetDocumentIcon](../Topic/CMFCTabCtrl::GetDocumentIcon.md)|タブ付きウィンドウのポップアップ メニューのタブに関連付けられているシンボルを取得します。|  
|[CMFCTabCtrl::GetFirstVisibleTabNum](../Topic/CMFCTabCtrl::GetFirstVisibleTabNum.md)|現在のタブ コントロールに表示される最初のタブのインデックスを取得します。|  
|[CMFCTabCtrl::GetResizeMode](../Topic/CMFCTabCtrl::GetResizeMode.md)|現在のタブ コントロールのサイズ変更方法を指定する値を取得します。|  
|[CMFCTabCtrl::GetScrollBar](../Topic/CMFCTabCtrl::GetScrollBar.md)|タブ コントロールと関連付けられたスクロール バー オブジェクトへのポインターを取得します。|  
|[CMFCTabCtrl::GetTabArea](../Topic/CMFCTabCtrl::GetTabArea.md)|タブ コントロールの上部または下部にあるタブ ラベル領域に外接する四角形を取得します。  \([CMFCBaseTabCtrl::GetTabArea](../Topic/CMFCBaseTabCtrl::GetTabArea.md) をオーバーライドします。\)|  
|`CMFCTabCtrl::GetTabFromPoint`|指定された位置を含むタブを取得します。  \([CMFCBaseTabCtrl::GetTabFromPoint](../Topic/CMFCBaseTabCtrl::GetTabFromPoint.md) をオーバーライドします。\)|  
|[CMFCTabCtrl::GetTabMaxWidth](../Topic/CMFCTabCtrl::GetTabMaxWidth.md)|タブの最大幅を取得します。|  
|[CMFCTabCtrl::GetTabsHeight](../Topic/CMFCTabCtrl::GetTabsHeight.md)|現在のタブ コントロールのタブ領域の高さを取得します。|  
|[CMFCTabCtrl::GetTabsRect](../Topic/CMFCTabCtrl::GetTabsRect.md)|現在のタブ コントロールのタブ領域に外接する四角形を取得します。  \([CMFCBaseTabCtrl::GetTabsRect](../Topic/CMFCBaseTabCtrl::GetTabsRect.md) をオーバーライドします。\)|  
|`CMFCTabCtrl::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
|[CMFCTabCtrl::GetWndArea](../Topic/CMFCTabCtrl::GetWndArea.md)|現在のタブ コントロールのクライアント領域の境界を取得します。|  
|[CMFCTabCtrl::HideActiveWindowHorzScrollBar](../Topic/CMFCTabCtrl::HideActiveWindowHorzScrollBar.md)|アクティブ ウィンドウの水平スクロール バーがある場合は、それを非表示にします。|  
|[CMFCTabCtrl::HideInactiveWindow](../Topic/CMFCTabCtrl::HideInactiveWindow.md)|フレームワークがアクティブでないタブ コントロール ウィンドウを表示するかどうかを指定します。|  
|[CMFCTabCtrl::HideNoTabs](../Topic/CMFCTabCtrl::HideNoTabs.md)|表示されるタブがない場合に、タブ領域の描画を有効または無効にします。|  
|[CMFCTabCtrl::HideSingleTab](../Topic/CMFCTabCtrl::HideSingleTab.md)|単一のタブ付きウィンドウがある場合に、タブの描画を有効または無効にします。  \([CMFCBaseTabCtrl::HideSingleTab](../Topic/CMFCBaseTabCtrl::HideSingleTab.md) をオーバーライドします。\)|  
|[CMFCTabCtrl::IsActiveInMDITabGroup](../Topic/CMFCTabCtrl::IsActiveInMDITabGroup.md)|タブ コントロールの現在のタブが、マルチ ドキュメント インターフェイス タブ グループでアクティブであるかどうかを示します。|  
|[CMFCTabCtrl::IsActiveTabBoldFont](../Topic/CMFCTabCtrl::IsActiveTabBoldFont.md)|アクティブなタブのテキストが太字フォントで表示されるかどうかを示します。|  
|[CMFCTabCtrl::IsActiveTabCloseButton](../Topic/CMFCTabCtrl::IsActiveTabCloseButton.md)|アクティブなタブとタブ領域の右上隅のどちらに閉じるボタン \(**\[X\]**\) が表示されるかを示します。|  
|[CMFCTabCtrl::IsDrawFrame](../Topic/CMFCTabCtrl::IsDrawFrame.md)|タブ付きウィンドウで、埋め込みペインの周囲にフレームの四角形を描画するかどうかを示します。|  
|[CMFCTabCtrl::IsFlatFrame](../Topic/CMFCTabCtrl::IsFlatFrame.md)|タブ領域を囲むフレームがフラットであるか 3D であるかを示します。|  
|[CMFCTabCtrl::IsFlatTab](../Topic/CMFCTabCtrl::IsFlatTab.md)|現在のタブ コントロールのタブの外観がフラットかどうかを示します。|  
|[CMFCTabCtrl::IsLeftRightRounded](../Topic/CMFCTabCtrl::IsLeftRightRounded.md)|現在のタブ コントロールのタブの右辺と左辺の外観が丸みをおびているかどうかを判断します。|  
|[CMFCTabCtrl::IsMDITabGroup](../Topic/CMFCTabCtrl::IsMDITabGroup.md)|現在のタブ コントロールがマルチ ドキュメント インターフェイス \(MDI\) ウィンドウのクライアント領域内に存在しているかどうかを判断します。|  
|[CMFCTabCtrl::IsOneNoteStyle](../Topic/CMFCTabCtrl::IsOneNoteStyle.md)|現在のタブ コントロールが Microsoft OneNote のスタイルで表示されるかどうかを示します。|  
|`CMFCTabCtrl::IsPtInTabArea`|点がタブ領域の内部にあるかどうかを確認します。  \([CMFCBaseTabCtrl::IsPtInTabArea](../Topic/CMFCBaseTabCtrl::IsPtInTabArea.md) をオーバーライドします。\)|  
|[CMFCTabCtrl::IsSharedScroll](../Topic/CMFCTabCtrl::IsSharedScroll.md)|現在のタブ コントロールに、タブをまとめてスクロールできるスクロール バーがあるかどうかを示します。|  
|[CMFCTabCtrl::IsTabDocumentsMenu](../Topic/CMFCTabCtrl::IsTabDocumentsMenu.md)|タブ コントロールにスクロール ボタンを表示するか、タブ付きウィンドウのメニューを表示するボタンを表示するかを示します。|  
|[CMFCTabCtrl::IsVS2005Style](../Topic/CMFCTabCtrl::IsVS2005Style.md)|タブが Visual Studio .NET 2005 のスタイルで表示されるかどうかを示します。|  
|[CMFCTabCtrl::ModifyTabStyle](../Topic/CMFCTabCtrl::ModifyTabStyle.md)|現在のタブ コントロールのタブの外観を指定します。|  
|`CMFCTabCtrl::MoveTab`|タブを別のタブ位置に移動します。  \([CMFCBaseTabCtrl::MoveTab](../Topic/CMFCBaseTabCtrl::MoveTab.md) をオーバーライドします。\)|  
|[CMFCTabCtrl::OnDragEnter](../Topic/CMFCTabCtrl::OnDragEnter.md)|カーソルがタブ コントロール ウィンドウに最初にドラッグされたときに、フレームワークによって呼び出されます。|  
|[CMFCTabCtrl::OnDragOver](../Topic/CMFCTabCtrl::OnDragOver.md)|ドラッグ操作中にマウスがドロップ ターゲット ウィンドウ上に移動されたとき、フレームワークが呼び出します。  \([CMFCBaseTabCtrl::OnDragOver](../Topic/CMFCBaseTabCtrl::OnDragOver.md) をオーバーライドします。\)|  
|[CMFCTabCtrl::OnShowTabDocumentsMenu](../Topic/CMFCTabCtrl::OnShowTabDocumentsMenu.md)|タブ付きウィンドウのポップアップ メニューを表示し、ユーザーがタブを選択するまで待って、選択されたタブをアクティブにします。|  
|`CMFCTabCtrl::PreTranslateMessage`|Windows 関数の [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) や [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) にディスパッチする前にウィンドウ メッセージを変換します。  \([CMFCBaseTabCtrl::PreTranslateMessage](../Topic/CMFCBaseTabCtrl::PreTranslateMessage.md) をオーバーライドします。\)|  
|`CMFCTabCtrl::RecalcLayout`|タブ コントロールの内部レイアウトを再計算します。  \([CMFCBaseTabCtrl::RecalcLayout](../Topic/CMFCBaseTabCtrl::RecalcLayout.md) をオーバーライドします。\)|  
|[CMFCTabCtrl::SetActiveInMDITabGroup](../Topic/CMFCTabCtrl::SetActiveInMDITabGroup.md)|タブ コントロールの現在のタブを、マルチ ドキュメント インターフェイス タブ グループのアクティブ タブとして設定します。|  
|[CMFCTabCtrl::SetActiveTab](../Topic/CMFCTabCtrl::SetActiveTab.md)|タブをアクティブにします。  \([CMFCBaseTabCtrl::SetActiveTab](../Topic/CMFCBaseTabCtrl::SetActiveTab.md) をオーバーライドします。\)|  
|[CMFCTabCtrl::SetActiveTabBoldFont](../Topic/CMFCTabCtrl::SetActiveTabBoldFont.md)|アクティブ タブでの太字フォントの使用を有効または無効にします。|  
|[CMFCTabCtrl::SetDrawFrame](../Topic/CMFCTabCtrl::SetDrawFrame.md)|埋め込みバーの周囲におけるフレームの四角形の描画を有効または無効にします。|  
|[CMFCTabCtrl::SetFlatFrame](../Topic/CMFCTabCtrl::SetFlatFrame.md)|タブ領域の周囲にフラット フレームまたは 3D フレームを描画するかどうかを指定します。|  
|[CMFCTabCtrl::SetImageList](../Topic/CMFCTabCtrl::SetImageList.md)|イメージ リストを指定します。  \([CMFCBaseTabCtrl::SetImageList](../Topic/CMFCBaseTabCtrl::SetImageList.md) をオーバーライドします。\)|  
|[CMFCTabCtrl::SetResizeMode](../Topic/CMFCTabCtrl::SetResizeMode.md)|現在のタブ コントロールのサイズを変更し、コントロールを再表示する方法を指定します。|  
|[CMFCTabCtrl::SetTabMaxWidth](../Topic/CMFCTabCtrl::SetTabMaxWidth.md)|タブ付きウィンドウ内のタブの最大幅を指定します。|  
|[CMFCTabCtrl::StopResize](../Topic/CMFCTabCtrl::StopResize.md)|タブ コントロールに対する現在のサイズ変更操作を終了します。|  
|`CMFCTabCtrl::SwapTabs`|タブのペアを交換します。  \([CMFCBaseTabCtrl::SwapTabs](../Topic/CMFCBaseTabCtrl::SwapTabs.md) をオーバーライドします。\)|  
|[CMFCTabCtrl::SynchronizeScrollBar](../Topic/CMFCTabCtrl::SynchronizeScrollBar.md)|フラット タブを表示するタブ コントロールの水平スクロール バーを描画します。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMFCTabCtrl::m\_bEnableActivate](../Topic/CMFCTabCtrl::m_bEnableActivate.md)|新しいタブが挿入され有効になったときに、アクティブなビューがフォーカスを失わないようにします。|  
  
## 解説  
 `CMFCTabCtrl` クラスは、以下をサポートします。  
  
-   3D、フラット、および共有水平スクロール バーを備えたフラットなどのタブ コントロール スタイル。  
  
-   ウィンドウの上部または下部に配置されるタブ。  
  
-   テキスト、イメージ、またはテキストとイメージを表示するタブ。  
  
-   アクティブなときに色が変わるタブ。  
  
-   調整可能なタブの境界線のサイズ変更。  
  
-   デタッチできるタブ付きウィンドウ。  
  
 `CMFCTabCtrl` クラスは、ダイアログ ボックスと共に使用できますが、[!INCLUDE[ofprexcel](../Token/ofprexcel_md.md)] や [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] のようなドッキング コントロール バーを使用するアプリケーションを対象としています。  詳細については、「[CDockablePane クラス](../Topic/CDockablePane%20Class.md)」を参照してください。  
  
 次の手順に従って、サイズ変更可能なドッキング タブ コントロールをアプリケーションに追加します。  
  
1.  [CTabbedPane クラス](../../mfc/reference/ctabbedpane-class.md) のインスタンスを作成します。  
  
2.  [CDockablePane::Create](../Topic/CDockablePane::Create.md) を呼び出します。  
  
3.  [CBaseTabbedPane::AddTab](../Topic/CBaseTabbedPane::AddTab.md) または [CMFCBaseTabCtrl::InsertTab](../Topic/CMFCBaseTabCtrl::InsertTab.md) を使用して新しいタブを追加します。  
  
4.  現在のドッキング タブ コントロールをメイン フレーム ウィンドウにドッキングできるように、[CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md) を呼び出します。  
  
5.  [CFrameWndEx::DockPane](../Topic/CFrameWndEx::DockPane.md) を呼び出して、タブ付きウィンドウをメイン フレームにドッキングします。  
  
 タブ付きウィンドウをドッキング コントロール バーとして作成する方法の例については、「[CTabbedPane クラス](../../mfc/reference/ctabbedpane-class.md)」を参照してください。  `CMFCTabCtrl` を非ドッキング コントロールとして使用するには、`CMFCTabCtrl` オブジェクトを作成した後に [CMFCTabCtrl::Create](../Topic/CMFCTabCtrl::Create.md) を呼び出します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md)  
  
## 使用例  
 `CMFCTabCtrl` クラスのさまざまなメソッドを使用して `CMFCTabCtrl` オブジェクトを構成する方法を、次の例に示します。  この例では、タブの追加、アクティブ タブの閉じるボタンの表示、編集可能なタブ ラベルの有効化、およびタブ付きウィンドウ ラベルのポップアップ メニューの表示を行う方法を説明しています。  この例では [コレクションのサンプルを表示&#93;](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_StateCollection#1](../../mfc/reference/codesnippet/CPP/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection#3](../../mfc/reference/codesnippet/CPP/cmfctabctrl-class_2.cpp)]  
  
## 必要条件  
 **ヘッダー :** afxtabctrl.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CDockablePane クラス](../Topic/CDockablePane%20Class.md)   
 [CDockablePane クラス](../Topic/CDockablePane%20Class.md)   
 [CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md)