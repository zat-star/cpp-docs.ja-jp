---
title: "CMFCRibbonBar クラス | Microsoft Docs"
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
  - "CMFCRibbonBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonBar クラス"
ms.assetid: a65d06fa-1a28-4cc0-8971-bc9d7c9198fe
caps.latest.revision: 41
caps.handback.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonBar` クラスは、Office 2007 で使用されているものに似たリボン バーを実装します。  
  
## 構文  
  
```  
class CMFCRibbonBar : public CPane  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CMFCRibbonBar::CMFCRibbonBar`|既定のコンストラクター|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonBar::ActivateContextCategory](../Topic/CMFCRibbonBar::ActivateContextCategory.md)|既に表示されているコンテキスト カテゴリをアクティブにします。|  
|[CMFCRibbonBar::AddCategory](../Topic/CMFCRibbonBar::AddCategory.md)|新しいリボン カテゴリをリボンに追加します。|  
|[CMFCRibbonBar::AddContextCategory](../Topic/CMFCRibbonBar::AddContextCategory.md)|コンテキスト カテゴリを追加します。|  
|[CMFCRibbonBar::AddMainCategory](../Topic/CMFCRibbonBar::AddMainCategory.md)|新しいメイン リボン カテゴリを追加します。|  
|[CMFCRibbonBar::AddPrintPreviewCategory](../Topic/CMFCRibbonBar::AddPrintPreviewCategory.md)||  
|[CMFCRibbonBar::AddQATOnlyCategory](../Topic/CMFCRibbonBar::AddQATOnlyCategory.md)||  
|[CMFCRibbonBar::AddToTabs](../Topic/CMFCRibbonBar::AddToTabs.md)|リボン バーの右側にリボン要素を追加します。|  
|[CMFCRibbonBar::CreateEx](../Topic/CMFCRibbonBar::CreateEx.md)|コントロール バーを作成し、それを [CPane](../../mfc/reference/cpane-class.md) オブジェクトにアタッチします  \([CPane::CreateEx](../Topic/CPane::CreateEx.md) をオーバーライドします\)。|  
|[CMFCRibbonBar::Create](../Topic/CMFCRibbonBar::Create.md)|リボン バー コントロールを作成し、それをリボン バーにアタッチします。|  
|[CMFCRibbonBar::DeactivateKeyboardFocus](../Topic/CMFCRibbonBar::DeactivateKeyboardFocus.md)||  
|[CMFCRibbonBar::DrawMenuImage](../Topic/CMFCRibbonBar::DrawMenuImage.md)||  
|[CMFCRibbonBar::DWMCompositionChanged](../Topic/CMFCRibbonBar::DWMCompositionChanged.md)||  
|[CMFCRibbonBar::EnableKeyTips](../Topic/CMFCRibbonBar::EnableKeyTips.md)|リボン コントロールのキーのヒントを有効または無効にします。|  
|[CMFCRibbonBar::EnablePrintPreview](../Topic/CMFCRibbonBar::EnablePrintPreview.md)|**\[印刷プレビュー\]** タブを有効にします。|  
|[CMFCRibbonBar::EnableToolTips](../Topic/CMFCRibbonBar::EnableToolTips.md)|リボン バー上のツールヒントとその説明を有効または無効にします。|  
|[CMFCRibbonBar::FindByData](../Topic/CMFCRibbonBar::FindByData.md)|ユーザーが指定するデータを使用してリボン要素を検索します。|  
|[CMFCRibbonBar::FindByID](../Topic/CMFCRibbonBar::FindByID.md)|指定されたコマンド ID を持つリボン要素を検索します。|  
|[CMFCRibbonBar::FindCategoryIndexByData](../Topic/CMFCRibbonBar::FindCategoryIndexByData.md)|ユーザー定義データを含むリボン カテゴリのインデックスを検索します。|  
|[CMFCRibbonBar::ForceRecalcLayout](../Topic/CMFCRibbonBar::ForceRecalcLayout.md)||  
|[CMFCRibbonBar::GetActiveCategory](../Topic/CMFCRibbonBar::GetActiveCategory.md)|アクティブなカテゴリへのポインターを取得します。|  
|[CMFCRibbonBar::GetCaptionHeight](../Topic/CMFCRibbonBar::GetCaptionHeight.md)|キャプションの高さを返します。  \([CBasePane::GetCaptionHeight](../Topic/CBasePane::GetCaptionHeight.md) をオーバーライドします\)。|  
|[CMFCRibbonBar::GetCategory](../Topic/CMFCRibbonBar::GetCategory.md)|指定されたインデックス位置にあるカテゴリへのポインターを取得します。|  
|[CMFCRibbonBar::GetCategoryCount](../Topic/CMFCRibbonBar::GetCategoryCount.md)|リボン バー内のリボン カテゴリの数を取得します。|  
|[CMFCRibbonBar::GetCategoryHeight](../Topic/CMFCRibbonBar::GetCategoryHeight.md)||  
|[CMFCRibbonBar::GetCategoryIndex](../Topic/CMFCRibbonBar::GetCategoryIndex.md)|リボン カテゴリのインデックスを返します。|  
|[CMFCRibbonBar::GetContextName](../Topic/CMFCRibbonBar::GetContextName.md)|ID を使用して指定するコンテキスト カテゴリ キャプションの名前を取得します。|  
|[CMFCRibbonBar::GetDroppedDown](../Topic/CMFCRibbonBar::GetDroppedDown.md)||  
|[CMFCRibbonBar::GetElementsByID](../Topic/CMFCRibbonBar::GetElementsByID.md)|指定された ID を持つすべてのリボン要素へのポインターが含まれている配列を取得します。|  
|[CMFCRibbonBar::GetApplicationButton](../Topic/CMFCRibbonBar::GetApplicationButton.md)|リボン ボタンへのポインターを取得します。|  
|[CMFCRibbonBar::GetFocused](../Topic/CMFCRibbonBar::GetFocused.md)|フォーカスされた要素を返します。|  
|[CMFCRibbonBar::GetHideFlags](../Topic/CMFCRibbonBar::GetHideFlags.md)||  
|[CMFCRibbonBar::GetItemIDsList](../Topic/CMFCRibbonBar::GetItemIDsList.md)||  
|[CMFCRibbonBar::GetKeyboardNavigationLevel](../Topic/CMFCRibbonBar::GetKeyboardNavigationLevel.md)||  
|[CMFCRibbonBar::GetKeyboardNavLevelCurrent](../Topic/CMFCRibbonBar::GetKeyboardNavLevelCurrent.md)||  
|[CMFCRibbonBar::GetKeyboardNavLevelParent](../Topic/CMFCRibbonBar::GetKeyboardNavLevelParent.md)||  
|[CMFCRibbonBar::GetMainCategory](../Topic/CMFCRibbonBar::GetMainCategory.md)|現在選択されているリボン カテゴリへのポインターを返します。|  
|[CMFCRibbonBar::GetQATCommandsLocation](../Topic/CMFCRibbonBar::GetQATCommandsLocation.md)||  
|[CMFCRibbonBar::GetQATDroppedDown](../Topic/CMFCRibbonBar::GetQATDroppedDown.md)||  
|[CMFCRibbonBar::GetQuickAccessCommands](../Topic/CMFCRibbonBar::GetQuickAccessCommands.md)|クイック アクセス ツール バーに表示されるすべての要素のコマンド ID が含まれるリストにデータを入力します。|  
|[CMFCRibbonBar::GetQuickAccessToolbarLocation](../Topic/CMFCRibbonBar::GetQuickAccessToolbarLocation.md)||  
|[CMFCRibbonBar::GetTabTrancateRatio](../Topic/CMFCRibbonBar::GetTabTrancateRatio.md)||  
|[CMFCRibbonBar::GetTooltipFixedWidthLargeImage](../Topic/CMFCRibbonBar::GetTooltipFixedWidthLargeImage.md)||  
|[CMFCRibbonBar::GetTooltipFixedWidthRegular](../Topic/CMFCRibbonBar::GetTooltipFixedWidthRegular.md)||  
|[CMFCRibbonBar::GetVisibleCategoryCount](../Topic/CMFCRibbonBar::GetVisibleCategoryCount.md)||  
|[CMFCRibbonBar::HideAllContextCategories](../Topic/CMFCRibbonBar::HideAllContextCategories.md)|アクティブかつ表示中のすべてのカテゴリを非表示にします。|  
|[CMFCRibbonBar::HideKeyTips](../Topic/CMFCRibbonBar::HideKeyTips.md)||  
|[CMFCRibbonBar::HitTest](../Topic/CMFCRibbonBar::HitTest.md)|リボン バーのクライアント座標の指定されたポイントに位置するリボン要素へのポインターを検索します。|  
|[CMFCRibbonBar::IsKeyTipEnabled](../Topic/CMFCRibbonBar::IsKeyTipEnabled.md)|keytip が有効かどうかを決定します。|  
|[CMFCRibbonBar::IsMainRibbonBar](../Topic/CMFCRibbonBar::IsMainRibbonBar.md)||  
|[CMFCRibbonBar::IsPrintPreviewEnabled](../Topic/CMFCRibbonBar::IsPrintPreviewEnabled.md)|**\[印刷プレビュー\]** タブが有効かどうかを決定します。|  
|[CMFCRibbonBar::IsQATEmpty](../Topic/CMFCRibbonBar::IsQATEmpty.md)||  
|[CMFCRibbonBar::IsQuickAccessToolbarOnTop](../Topic/CMFCRibbonBar::IsQuickAccessToolbarOnTop.md)|クイック アクセス ツール バーがリボン バーの上に配置されるかどうかを指定します。|  
|[CMFCRibbonBar::IsReplaceFrameCaption](../Topic/CMFCRibbonBar::IsReplaceFrameCaption.md)|リボン バーでメイン フレーム キャプションを置き換えるか、またはフレーム キャプションの下に追加するかを決定します。|  
|[CMFCRibbonBar::IsShowGroupBorder](../Topic/CMFCRibbonBar::IsShowGroupBorder.md)||  
|[CMFCRibbonBar::IsToolTipDescrEnabled](../Topic/CMFCRibbonBar::IsToolTipDescrEnabled.md)|ツールヒントの説明が有効かどうかを決定します。|  
|[CMFCRibbonBar::IsToolTipEnabled](../Topic/CMFCRibbonBar::IsToolTipEnabled.md)|リボン バーのツールヒントが有効かどうかを決定します。|  
|[CMFCRibbonBar::IsTransparentCaption](../Topic/CMFCRibbonBar::IsTransparentCaption.md)||  
|[CMFCRibbonBar::IsWindows7Look](../Topic/CMFCRibbonBar::IsWindows7Look.md)|リボンの外観が Windows 7 スタイル \(小さな四角形のアプリケーション ボタン\) であるかどうかを示します。|  
|[CMFCRibbonBar::LoadFromResource](../Topic/CMFCRibbonBar::LoadFromResource.md)|オーバーロードされます。  アプリケーション リソースからリボン バーを読み込みます。|  
|[CMFCRibbonBar::OnClickButton](../Topic/CMFCRibbonBar::OnClickButton.md)||  
|[CMFCRibbonBar::OnEditContextMenu](../Topic/CMFCRibbonBar::OnEditContextMenu.md)||  
|[CMFCRibbonBar::OnRTLChanged](../Topic/CMFCRibbonBar::OnRTLChanged.md)|\(`CPane::OnRTLChanged` をオーバーライドします\)。|  
|[CMFCRibbonBar::OnSetAccData](../Topic/CMFCRibbonBar::OnSetAccData.md)|\([CBasePane::OnSetAccData](../Topic/CBasePane::OnSetAccData.md) をオーバーライドします\)。|  
|[CMFCRibbonBar::OnShowRibbonContextMenu](../Topic/CMFCRibbonBar::OnShowRibbonContextMenu.md)||  
|[CMFCRibbonBar::OnShowRibbonQATMenu](../Topic/CMFCRibbonBar::OnShowRibbonQATMenu.md)||  
|[CMFCRibbonBar::OnSysKeyDown](../Topic/CMFCRibbonBar::OnSysKeyDown.md)||  
|[CMFCRibbonBar::OnSysKeyUp](../Topic/CMFCRibbonBar::OnSysKeyUp.md)||  
|[CMFCRibbonBar::PopTooltip](../Topic/CMFCRibbonBar::PopTooltip.md)||  
|[CMFCRibbonBar::PreTranslateMessage](../Topic/CMFCRibbonBar::PreTranslateMessage.md)|\(`CBasePane::PreTranslateMessage` をオーバーライドします\)。|  
|[CMFCRibbonBar::RecalcLayout](../Topic/CMFCRibbonBar::RecalcLayout.md)|\([CPane::RecalcLayout](../Topic/CPane::RecalcLayout.md) をオーバーライドします\)。|  
|[CMFCRibbonBar::RemoveAllCategories](../Topic/CMFCRibbonBar::RemoveAllCategories.md)|リボン バーからすべてのリボン カテゴリを削除します。|  
|[CMFCRibbonBar::RemoveAllFromTabs](../Topic/CMFCRibbonBar::RemoveAllFromTabs.md)|タブ領域からすべてのリボン要素を削除します。|  
|[CMFCRibbonBar::RemoveCategory](../Topic/CMFCRibbonBar::RemoveCategory.md)|指定されたインデックス位置にあるリボン カテゴリを削除します。|  
|[CMFCRibbonBar::SaveToXMLBuffer](../Topic/CMFCRibbonBar::SaveToXMLBuffer.md)|リボン バーをバッファーに保存します。|  
|[CMFCRibbonBar::SaveToXMLFile](../Topic/CMFCRibbonBar::SaveToXMLFile.md)|リボン バーを XML ファイルに保存します。|  
|[CMFCRibbonBar::SetActiveCategory](../Topic/CMFCRibbonBar::SetActiveCategory.md)|指定されたリボン カテゴリをアクティブに設定します。|  
|[CMFCRibbonBar::SetActiveMDIChild](../Topic/CMFCRibbonBar::SetActiveMDIChild.md)||  
|[CMFCRibbonBar::SetElementKeys](../Topic/CMFCRibbonBar::SetElementKeys.md)|指定された keytip を、指定されたコマンド ID を持つすべてのリボン要素に対して設定します。|  
|[CMFCRibbonBar::SetApplicationButton](../Topic/CMFCRibbonBar::SetApplicationButton.md)|リボン バーにアプリケーション リボン ボタンを割り当てます。|  
|[CMFCRibbonBar::SetKeyboardNavigationLevel](../Topic/CMFCRibbonBar::SetKeyboardNavigationLevel.md)||  
|[CMFCRibbonBar::SetMaximizeMode](../Topic/CMFCRibbonBar::SetMaximizeMode.md)||  
|[CMFCRibbonBar::SetQuickAccessCommands](../Topic/CMFCRibbonBar::SetQuickAccessCommands.md)|クイック アクセス ツール バーに 1 つ以上のリボン要素を追加します。|  
|[CMFCRibbonBar::SetQuickAccessDefaultState](../Topic/CMFCRibbonBar::SetQuickAccessDefaultState.md)|クイック アクセス ツール バーの既定の状態を指定します。|  
|[CMFCRibbonBar::SetQuickAccessToolbarOnTop](../Topic/CMFCRibbonBar::SetQuickAccessToolbarOnTop.md)|クイック アクセス ツール バー \(QAT\) を、リボン バーの上または下に配置します。|  
|[CMFCRibbonBar::SetTooltipFixedWidth](../Topic/CMFCRibbonBar::SetTooltipFixedWidth.md)||  
|[CMFCRibbonBar::SetWindows7Look](../Topic/CMFCRibbonBar::SetWindows7Look.md)|リボンの Windows 7 スタイル \(小さな四角形のアプリケーション ボタン\) の外観を有効または無効にします。|  
|[CMFCRibbonBar::ShowCategory](../Topic/CMFCRibbonBar::ShowCategory.md)|指定されたリボン カテゴリを表示または非表示にします。|  
|[CMFCRibbonBar::ShowContextCategories](../Topic/CMFCRibbonBar::ShowContextCategories.md)|指定された ID を持つコンテキスト カテゴリを表示または非表示にします。|  
|[CMFCRibbonBar::ShowKeyTips](../Topic/CMFCRibbonBar::ShowKeyTips.md)||  
|[CMFCRibbonBar::ToggleMimimizeState](../Topic/CMFCRibbonBar::ToggleMimimizeState.md)|リボン バーの最小化された状態と最大化された状態を切り替えます。|  
|[CMFCRibbonBar::TranslateChar](../Topic/CMFCRibbonBar::TranslateChar.md)||  
  
## 解説  
 Microsoft は、Microsoft Office 2007 のリリースと同時に Office Fluent Ribbon を導入しました。  このリボン バーは、単なる新しいコントロールではありません。  新たなユーザー インターフェイスのパラダイムを表すものです。  リボンとは、カテゴリと呼ばれるタブのセットを含むウィンドウです。  各カテゴリは論理的にリボン パネルへと分割され、各パネルにはさまざまなコントロールやコマンド ボタンを追加することができます。  
  
 リボン バーに表示される要素を拡大および縮小することで、スペースを最大限に活用します。  たとえば、リボン パネルに要素を表示するための十分なスペースがない場合、リボン パネルはポップアップ メニューにサブアイテムを表示するメニュー ボタンになります。  リボン バーは、静的 \(フローティングでない\) コントロール バーとして動作し、フレームの上部にドッキングできます。  
  
 `CMFCRibbonStatusBar` クラスを使用すると、Office 2007 で使われているようなステータス バーを実装できます。  リボン カテゴリには、[リボン パネル](../../mfc/reference/cmfcribbonpanel-class.md)のグループが含まれており、これが表示されます。  各リボン パネルには [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md) から派生した 1 つ以上のリボン要素が含まれます。  
  
 リボン バーを既存の MFC アプリケーションに追加する方法については、「[チュートリアル: MFC Scribble アプリケーションの更新](../../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)  
  
## 必要条件  
 **ヘッダー :** afxribbonbar.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CPane クラス](../../mfc/reference/cpane-class.md)   
 [CMFCRibbonCategory クラス](../../mfc/reference/cmfcribboncategory-class.md)   
 [CMFCRibbonPanel クラス](../../mfc/reference/cmfcribbonpanel-class.md)   
 [CMFCRibbonBaseElement クラス](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [チュートリアル: MFC Scribble アプリケーションの更新](../../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)