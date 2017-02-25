---
title: "CMFCToolBar クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBar クラス"
ms.assetid: e7679c01-fb94-44c0-98c6-3af955292fb5
caps.latest.revision: 48
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 50
---
# CMFCToolBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCToolBar` クラスは [CToolBar クラス](../../mfc/reference/ctoolbar-class.md) に似ていますが、ユーザー インターフェイス機能に対する追加サポートを提供します。  フラット ツール バー、ホット イメージのツール バー、大きいアイコン、ページャー ボタン、ロックされたツール バー、rebar コントロール、イメージの下のテキスト、背景イメージ、およびタブ付きのツール バーなどがサポートされます。  `CMFCToolBar` クラスには、ツール バーおよびメニューに対するユーザーのカスタマイズ、ツール バーとメニューの間のドラッグ アンド ドロップ、コンボ ボックス ボタン、エディット ボックス ボタン、カラー ピッカー、およびロールアップ ボタンのサポートも組み込まれています。  
  
## 構文  
  
```  
class CMFCToolBar : public CMFCBaseToolBar  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CMFCToolBar::CMFCToolBar`|既定のコンストラクターです。|  
|`CMFCToolBar::~CMFCToolBar`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolBar::AddBasicCommand](../Topic/CMFCToolBar::AddBasicCommand.md)|ユーザーがメニューを開いたときに常に表示されるコマンドの一覧にメニュー コマンドを追加します。|  
|[CMFCToolBar::AddCommandUsage](../Topic/CMFCToolBar::AddCommandUsage.md)|指定されたコマンドに関連付けられたカウンターを 1 だけインクリメントします。|  
|[CMFCToolBar::AddToolBarForImageCollection](../Topic/CMFCToolBar::AddToolBarForImageCollection.md)|ユーザー インターフェイス リソースからアプリケーション内のイメージのコレクションへ、イメージを追加します。|  
|[CMFCToolBar::AdjustLayout](../Topic/CMFCToolBar::AdjustLayout.md)|ツール バーのサイズと位置を再計算します。   \([CBasePane::AdjustLayout](../Topic/CBasePane::AdjustLayout.md) をオーバーライドします。\)|  
|[CMFCToolBar::AdjustSize](../Topic/CMFCToolBar::AdjustSize.md)|ツール バーのサイズを再計算します。|  
|[CMFCToolBar::AllowChangeTextLabels](../Topic/CMFCToolBar::AllowChangeTextLabels.md)|ツール バー ボタンのイメージの下にテキスト ラベルを表示できるかどうかを示します|  
|[CMFCToolBar::AreTextLabels](../Topic/CMFCToolBar::AreTextLabels.md)|ツール バー ボタンで、イメージの下のテキスト ラベルが現在表示されているかどうかを示します。|  
|[CMFCToolBar::AutoGrayInactiveImages](../Topic/CMFCToolBar::AutoGrayInactiveImages.md)|アクティブでないボタンのイメージの自動生成を有効または無効にします。|  
|[CMFCToolBar::ButtonToIndex](../Topic/CMFCToolBar::ButtonToIndex.md)|このツール バーの指定した [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md) オブジェクトのインデックスを返します。|  
|[CMFCToolBar::CalcFixedLayout](../Topic/CMFCToolBar::CalcFixedLayout.md)|ツール バーの水平サイズを計算します。  \([CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md) をオーバーライドします。\)|  
|[CMFCToolBar::CalcSize](../Topic/CMFCToolBar::CalcSize.md)|レイアウト計算の処理の過程でフレームワークによって呼び出されます。  \([CPane::CalcSize](../Topic/CPane::CalcSize.md) をオーバーライドします。\)|  
|[CMFCToolBar::CanHandleSiblings](../Topic/CMFCToolBar::CanHandleSiblings.md)|ツール バーとその兄弟が同じペインに配置されているかどうかを判定します。|  
|[CMFCToolBar::CleanUpImages](../Topic/CMFCToolBar::CleanUpImages.md)|ツール バー イメージに割り当てられたシステム リソースを解放します。|  
|[CMFCToolBar::CleanUpLockedImages](../Topic/CMFCToolBar::CleanUpLockedImages.md)|ロックされたツール バー イメージに割り当てられたシステム リソースを解放します。|  
|[CMFCToolBar::CanBeClosed](../Topic/CMFCToolBar::CanBeClosed.md)|ユーザーがツール バーを閉じることができるかどうかを示します。  \([CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md) をオーバーライドします。\)|  
|[CMFCToolBar::CanBeRestored](../Topic/CMFCToolBar::CanBeRestored.md)|カスタマイズ後にツール バーを元の状態に復元できるかどうかを判断します。|  
|[CMFCToolBar::CanFocus](../Topic/CMFCToolBar::CanFocus.md)|ペインがフォーカスを受け取ることができるかどうかを指定します。  \([CBasePane::CanFocus](../Topic/CBasePane::CanFocus.md) をオーバーライドします。\)|  
|[CMFCToolBar::CanHandleSiblings](../Topic/CMFCToolBar::CanHandleSiblings.md)|ツール バーとその兄弟が同じペインに配置されているかどうかを判定します。|  
|[CMFCToolBar::CommandToIndex](../Topic/CMFCToolBar::CommandToIndex.md)|指定したコマンド ID を持つ、ツール バー内のボタンのインデックスを返します。|  
|[CMFCToolBar::Create](../Topic/CMFCToolBar::Create.md)|`CMFCToolBar` オブジェクトを作成します。|  
|[CMFCToolBar::CreateEx](../Topic/CMFCToolBar::CreateEx.md)|大きいアイコンなどの追加スタイル オプションを使用する `CMFCToolBar` オブジェクトを作成します。|  
|[CMFCToolBar::Deactivate](../Topic/CMFCToolBar::Deactivate.md)|ツール バーを非アクティブにします。|  
|[CMFCToolBar::EnableCustomizeButton](../Topic/CMFCToolBar::EnableCustomizeButton.md)|ツール バーの末尾に表示される **\[ボタンの表示\/非表示\]** ボタンを有効または無効にします。|  
|[CMFCToolBar::EnableDocking](../Topic/CMFCToolBar::EnableDocking.md)|メイン フレームへのペインのドッキングを有効にします。  \([CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md) をオーバーライドします。\)|  
|[CMFCToolBar::EnableLargeIcons](../Topic/CMFCToolBar::EnableLargeIcons.md)|ツール バー ボタンの大きいアイコンを有効、または無効にします。|  
|[CMFCToolBar::EnableQuickCustomization](../Topic/CMFCToolBar::EnableQuickCustomization.md)|ユーザーが Alt キーを押してボタンを新しい位置にドラッグできるようにするために、ツール バーのクイック カスタマイズを有効または無効にします。|  
|[CMFCToolBar::EnableReflections](../Topic/CMFCToolBar::EnableReflections.md)|コマンド リフレクションを有効または無効にします。|  
|[CMFCToolBar::EnableTextLabels](../Topic/CMFCToolBar::EnableTextLabels.md)|ツール バー ボタン イメージの下のテキスト ラベルを有効または無効にします。|  
|[CMFCToolBar::FromHandlePermanent](../Topic/CMFCToolBar::FromHandlePermanent.md)|指定されたウィンドウ ハンドルを含む `CMFCToolBar` オブジェクトへのポインターを取得します。|  
|[CMFCToolBar::GetAllButtons](../Topic/CMFCToolBar::GetAllButtons.md)|ツール バー内のボタンの読み取り専用のリストを返します。|  
|[CMFCToolBar::GetAllToolbars](../Topic/CMFCToolBar::GetAllToolbars.md)|アプリケーション内のすべてのツール バーの読み取り専用のリストを返します。|  
|[CMFCToolBar::GetBasicCommands](../Topic/CMFCToolBar::GetBasicCommands.md)|アプリケーションで定義された基本コマンドの読み取り専用リストを返します。|  
|[CMFCToolBar::GetButton](../Topic/CMFCToolBar::GetButton.md)|指定されたツール バー ボタンのインデックスを持つ `CMFCToolBarButton` オブジェクトへのポインターを返します。|  
|[CMFCToolBar::GetButtonInfo](../Topic/CMFCToolBar::GetButtonInfo.md)|指定したインデックス位置にあるボタンのコマンド ID、スタイル、およびイメージのインデックスを返します。|  
|[CMFCToolBar::GetButtonSize](../Topic/CMFCToolBar::GetButtonSize.md)|ツール バー上の各ボタンの寸法を返します。|  
|[CMFCToolBar::GetButtonStyle](../Topic/CMFCToolBar::GetButtonStyle.md)|指定したインデックス位置にあるツール バー ボタンの現在のスタイルを返します。|  
|[CMFCToolBar::GetButtonText](../Topic/CMFCToolBar::GetButtonText.md)|指定したインデックス位置にあるボタンのテキスト ラベルを返します。|  
|[CMFCToolBar::GetColdImages](../Topic/CMFCToolBar::GetColdImages.md)|アプリケーションで、ツール バー ボタンのコールド イメージのコレクションへのポインターを返します。|  
|[CMFCToolBar::GetColumnWidth](../Topic/CMFCToolBar::GetColumnWidth.md)|ツール バー ボタンの幅を返します。|  
|[CMFCToolBar::GetCommandButtons](../Topic/CMFCToolBar::GetCommandButtons.md)|アプリケーションのツール バーにある、指定されたコマンド ID を持つボタンのリストを返します。|  
|[CMFCToolBar::GetCount](../Topic/CMFCToolBar::GetCount.md)|ツール バーのボタンと区切りの数を返します。|  
|[CMFCToolBar::GetCustomizeButton](../Topic/CMFCToolBar::GetCustomizeButton.md)|ツール バーに関連付けられた `CMFCCustomizeButton` オブジェクトへのポインターを取得します。|  
|[CMFCToolBar::GetDefaultImage](../Topic/CMFCToolBar::GetDefaultImage.md)|指定したコマンド ID を持つツール バーの、既定のイメージのインデックスを返します。|  
|[CMFCToolBar::GetDisabledImages](../Topic/CMFCToolBar::GetDisabledImages.md)|アプリケーションで無効ツール バー ボタンで使用されているイメージのコレクションへのポインターを返します。|  
|[CMFCToolBar::GetDisabledMenuImages](../Topic/CMFCToolBar::GetDisabledMenuImages.md)|アプリケーションで無効なメニュー ボタンで使用されているイメージのコレクションへのポインターを返します。|  
|[CMFCToolBar::GetDroppedDownMenu](../Topic/CMFCToolBar::GetDroppedDownMenu.md)|現在サブメニューが表示されているメニュー ボタン オブジェクトへのポインターを取得します。|  
|[CMFCToolBar::GetGrayDisabledButtons](../Topic/CMFCToolBar::GetGrayDisabledButtons.md)|無効ボタンのイメージを通常のボタン イメージの淡色表示バージョンにするか、無効なボタン イメージのコレクションから得るようにするかを指定します。|  
|[CMFCToolBar::GetHighlightedButton](../Topic/CMFCToolBar::GetHighlightedButton.md)|現在強調表示されているツール バー ボタンへのポインターを返します。|  
|[CMFCToolBar::GetHotBorder](../Topic/CMFCToolBar::GetHotBorder.md)|ツール バー ボタンがホット トラッキングされているかどうかを確認します。|  
|[CMFCToolBar::GetHotTextColor](../Topic/CMFCToolBar::GetHotTextColor.md)|強調表示されているツール バー ボタンのテキストの色を返します。|  
|[CMFCToolBar::GetHwndLastFocus](../Topic/CMFCToolBar::GetHwndLastFocus.md)|ツール バーが入力フォーカスを受け取る直前に入力フォーカスを持っていたウィンドウへのハンドルを返します。|  
|[CMFCToolBar::GetIgnoreSetText](../Topic/CMFCToolBar::GetIgnoreSetText.md)|定数のボタンのラベルへの呼び出しを無視するかどうかを指定します。|  
|[CMFCToolBar::GetImageSize](../Topic/CMFCToolBar::GetImageSize.md)|ツール バー ボタン イメージの現在のサイズを返します。|  
|[CMFCToolBar::GetImages](../Topic/CMFCToolBar::GetImages.md)|アプリケーションにおける既定のボタン イメージのコレクションへのポインターを返します。|  
|[CMFCToolBar::GetImagesOffset](../Topic/CMFCToolBar::GetImagesOffset.md)|このツール バーのツール バー ボタン イメージをツール バー ボタン イメージのグローバル リスト内で検索するために使用するインデックスのオフセットを返します。|  
|[CMFCToolBar::GetInvalidateItemRect](../Topic/CMFCToolBar::GetInvalidateItemRect.md)|特定のインデックスのボタンの、再描画が必要なクライアント領域内での部分を取得します。|  
|[CMFCToolBar::GetItemID](../Topic/CMFCToolBar::GetItemID.md)|指定したインデックスのツール バー ボタンのコマンド ID を返します。|  
|[CMFCToolBar::GetItemRect](../Topic/CMFCToolBar::GetItemRect.md)|指定されたインデックスのボタンの外接する四角形を返します。|  
|[CMFCToolBar::GetLargeColdImages](../Topic/CMFCToolBar::GetLargeColdImages.md)|アプリケーションの、大きいツール バー ボタンのコールド イメージのコレクションへのポインターを返します。|  
|[CMFCToolBar::GetLargeDisabledImages](../Topic/CMFCToolBar::GetLargeDisabledImages.md)|アプリケーションの、大きい無効ツール バー ボタン イメージのコレクションへのポインターを返します。|  
|[CMFCToolBar::GetLargeImages](../Topic/CMFCToolBar::GetLargeImages.md)|アプリケーションの、大きいツール バー ボタン イメージのコレクションへのポインターを返します。|  
|[CMFCToolBar::GetLockedColdImages](../Topic/CMFCToolBar::GetLockedColdImages.md)|ツール バーの、ロックされたコールド イメージのコレクションへのポインターを返します。|  
|[CMFCToolBar::GetLockedDisabledImages](../Topic/CMFCToolBar::GetLockedDisabledImages.md)|ツール バーの、ロックされた無効イメージのコレクションへのポインターを返します。|  
|[CMFCToolBar::GetLockedImages](../Topic/CMFCToolBar::GetLockedImages.md)|ツール バーの、ロックされたボタン イメージのコレクションへのポインターを返します。|  
|[CMFCToolBar::GetLockedImageSize](../Topic/CMFCToolBar::GetLockedImageSize.md)|ロックされたツール バー イメージの既定のサイズを返します。|  
|[CMFCToolBar::GetLockedMenuImages](../Topic/CMFCToolBar::GetLockedMenuImages.md)|ツール バーの、ロックされたツール バー メニュー イメージのコレクションへのポインターを返します。|  
|[CMFCToolBar::GetMenuButtonSize](../Topic/CMFCToolBar::GetMenuButtonSize.md)|アプリケーション内のメニュー ボタンのサイズを返します。|  
|[CMFCToolBar::GetMenuImageSize](../Topic/CMFCToolBar::GetMenuImageSize.md)|アプリケーションのメニュー ボタン イメージのサイズを返します。|  
|[CMFCToolBar::GetMenuImages](../Topic/CMFCToolBar::GetMenuImages.md)|アプリケーションの、メニュー ボタン イメージのコレクションへのポインターを返します。|  
|[CMFCToolBar::GetOrigButtons](../Topic/CMFCToolBar::GetOrigButtons.md)|ツール バーの、カスタマイズされていないボタンのコレクションを取得します。|  
|[CMFCToolBar::GetOrigResetButtons](../Topic/CMFCToolBar::GetOrigResetButtons.md)|ツール バーのカスタマイズされていないリセット ボタンのコレクションを取得します。|  
|[CMFCToolBar::GetResourceID](../Topic/CMFCToolBar::GetResourceID.md)|ツール バーのリソース ID を取得します。|  
|[CMFCToolBar::GetRouteCommandsViaFrame](../Topic/CMFCToolBar::GetRouteCommandsViaFrame.md)|親フレームとオーナーのどちらのオブジェクトがコマンドをツール バーに送信するかを確認します。|  
|[CMFCToolBar::GetRowHeight](../Topic/CMFCToolBar::GetRowHeight.md)|ツール バー ボタンの高さを返します。|  
|[CMFCToolBar::GetShowTooltips](../Topic/CMFCToolBar::GetShowTooltips.md)|ツール ヒントをツールバー ボタンに表示するかどうかを指定します。|  
|[CMFCToolBar::GetSiblingToolBar](../Topic/CMFCToolBar::GetSiblingToolBar.md)|ツール バーの兄弟を取得します。|  
|[CMFCToolBar::GetUserImages](../Topic/CMFCToolBar::GetUserImages.md)|アプリケーションの、ユーザー定義のツール バー ボタン イメージのコレクションへのポインターを返します。|  
|[CMFCToolBar::HitTest](../Topic/CMFCToolBar::HitTest.md)|指定された位置にあるツール バー ボタンのインデックスを返します。|  
|[CMFCToolBar::InsertButton](../Topic/CMFCToolBar::InsertButton.md)|ツール バーにボタンを挿入します。|  
|[CMFCToolBar::InsertSeparator](../Topic/CMFCToolBar::InsertSeparator.md)|ツール バーに区分線を挿入します。|  
|[CMFCToolBar::InvalidateButton](../Topic/CMFCToolBar::InvalidateButton.md)|指定されたインデックスに存在するツール バー ボタンのクライアント領域を無効にします。|  
|[CMFCToolBar::IsAddRemoveQuickCustomize](../Topic/CMFCToolBar::IsAddRemoveQuickCustomize.md)|ユーザーが **\[カスタマイズ\]** のメニュー オプションを使用してツール バー ボタンを追加または削除できるかどうかを判定します。|  
|[CMFCToolBar::IsAltCustomizeMode](../Topic/CMFCToolBar::IsAltCustomizeMode.md)|ボタンをドラッグするに *クイック カスタマイズを* 使用するかどうかを指定します。|  
|[CMFCToolBar::IsAutoGrayInactiveImages](../Topic/CMFCToolBar::IsAutoGrayInactiveImages.md)|非アクティブな \(強調表示されていない\) ボタンのイメージの自動生成を有効にするかどうかを指定します。|  
|[CMFCToolBar::IsBasicCommand](../Topic/CMFCToolBar::IsBasicCommand.md)|コマンドが基本コマンドのリスト上にあるかどうかを確認します。|  
|[CMFCToolBar::IsButtonExtraSizeAvailable](../Topic/CMFCToolBar::IsButtonExtraSizeAvailable.md)|拡張された境界を持つボタンをツール バーが表示できるかどうかを判断します|  
|[CMFCToolBar::IsButtonHighlighted](../Topic/CMFCToolBar::IsButtonHighlighted.md)|ツール バー ボタンを強調表示するかどうかを判定します。|  
|[CMFCToolBar::IsCommandPermitted](../Topic/CMFCToolBar::IsCommandPermitted.md)|コマンドが許可されているかどうかを判断します。|  
|[CMFCToolBar::IsCommandRarelyUsed](../Topic/CMFCToolBar::IsCommandRarelyUsed.md)|コマンドがほとんど使用されていないのかどうかを判断します \(「[CMFCToolBar::SetCommandUsageOptions](../Topic/CMFCToolBar::SetCommandUsageOptions.md)」を参照\)。|  
|[CMFCToolBar::IsCustomizeMode](../Topic/CMFCToolBar::IsCustomizeMode.md)|ツール バー フレームワークがカスタマイズ モードであるかどうかを指定します。|  
|[CMFCToolBar::IsDragButton](../Topic/CMFCToolBar::IsDragButton.md)|ツール バーのボタンをドラッグするかどうかを指定します。|  
|[CMFCToolBar::IsExistCustomizeButton](../Topic/CMFCToolBar::IsExistCustomizeButton.md)|ツール バーに **\[Customize\]** ボタンがあるかどうかを判定します。|  
|[CMFCToolBar::IsFloating](../Topic/CMFCToolBar::IsFloating.md)|ツール バーが固定されていないかどうかを判定します。|  
|[CMFCToolBar::IsLargeIcons](../Topic/CMFCToolBar::IsLargeIcons.md)|アプリケーションのツール バーに現在、大きいアイコンが表示されているかどうかを判断します。|  
|[CMFCToolBar::IsLastCommandFromButton](../Topic/CMFCToolBar::IsLastCommandFromButton.md)|最後に実行したコマンドが、指定されたツール バー ボタンから送信されたかどうかを判断します。|  
|[CMFCToolBar::IsLocked](../Topic/CMFCToolBar::IsLocked.md)|ツール バーがロックされているかどうかを判断します。|  
|[CMFCToolBar::IsOneRowWithSibling](../Topic/CMFCToolBar::IsOneRowWithSibling.md)|ツール バーとその兄弟ツール バーが同じ行に配置されているかどうか判断します。|  
|[CMFCToolBar::IsUserDefined](../Topic/CMFCToolBar::IsUserDefined.md)|ツール バーがユーザー定義かどうかを指定します。|  
|[CMFCToolBar::LoadBitmap](../Topic/CMFCToolBar::LoadBitmap.md)|アプリケーション リソースからツール バー イメージを読み込みます。|  
|[CMFCToolBar::LoadBitmapEx](../Topic/CMFCToolBar::LoadBitmapEx.md)|アプリケーション リソースからツール バー イメージを読み込みます。  大きいイメージが含まれます。|  
|[CMFCToolBar::LoadParameters](../Topic/CMFCToolBar::LoadParameters.md)|Windows レジストリからグローバル ツール バー オプションを読み込みます。|  
|[CMFCToolBar::LoadState](../Topic/CMFCToolBar::LoadState.md)|Windows レジストリからツール バー状態情報を読み込みます。  \([CPane::LoadState](../Topic/CPane::LoadState.md) をオーバーライドします。\)|  
|[CMFCToolBar::LoadToolBar](../Topic/CMFCToolBar::LoadToolBar.md)|アプリケーション リソースからツール バーを読み込みます。|  
|[CMFCToolBar::LoadToolBarEx](../Topic/CMFCToolBar::LoadToolBarEx.md)|`CMFCToolBarInfo` ヘルパー クラスを使用してアプリケーション リソースからツール バーを読み込み、アプリケーションで大きいイメージを使用できるようにします。|  
|[CMFCToolBar::OnChangeHot](../Topic/CMFCToolBar::OnChangeHot.md)|ツール バー上のボタンが選択されたときに、フレームワークによって呼び出されます。|  
|[CMFCToolBar::OnFillBackground](../Topic/CMFCToolBar::OnFillBackground.md)|ツール バーの背景を塗りつぶすために、フレームワークによって [CBasePane::DoPaint](../Topic/CBasePane::DoPaint.md) から呼び出されます。|  
|[CMFCToolBar::OnReset](../Topic/CMFCToolBar::OnReset.md)|ツール バーを元の状態に戻します。|  
|[CMFCToolBar::OnSetAccData](../Topic/CMFCToolBar::OnSetAccData.md)|\([CBasePane::OnSetAccData](../Topic/CBasePane::OnSetAccData.md) をオーバーライドします。\)|  
|[CMFCToolBar::OnSetDefaultButtonText](../Topic/CMFCToolBar::OnSetDefaultButtonText.md)|ツール バー ボタンのテキストを既定の状態に復元します。|  
|`CMFCToolBar::OnUpdateCmdUI`|内部使用。|  
|[CMFCToolBar::RemoveAllButtons](../Topic/CMFCToolBar::RemoveAllButtons.md)|ツール バーからすべてのボタンを削除します。|  
|[CMFCToolBar::RemoveButton](../Topic/CMFCToolBar::RemoveButton.md)|指定したインデックスのボタンをツール バーから削除します。|  
|[CMFCToolBar::RemoveStateFromRegistry](../Topic/CMFCToolBar::RemoveStateFromRegistry.md)|ツール バーの状態情報を Windows レジストリから削除します。|  
|[CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)|ツール バー ボタンを別のツール バー ボタンに置き換えます。|  
|[CMFCToolBar::ResetAll](../Topic/CMFCToolBar::ResetAll.md)|すべてのツール バーを元の状態に復元します。|  
|[CMFCToolBar::ResetAllImages](../Topic/CMFCToolBar::ResetAllImages.md)|アプリケーション内のすべてのツール バー イメージのコレクションをクリアします。|  
|[CMFCToolBar::RestoreOriginalState](../Topic/CMFCToolBar::RestoreOriginalState.md)|ツール バーの元の状態を復元します|  
|[CMFCToolBar::SaveState](../Topic/CMFCToolBar::SaveState.md)|ツール バーの状態情報を Windows レジストリに保存します。  \([CPane::SaveState](../Topic/CPane::SaveState.md) をオーバーライドします。\)|  
|`CMFCToolBar::Serialize`|\(`CBasePane::Serialize` をオーバーライドします。\)|  
|[CMFCToolBar::SetBasicCommands](../Topic/CMFCToolBar::SetBasicCommands.md)|ユーザーがメニューを開いたときに常に表示されるコマンドの一覧を設定します。|  
|[CMFCToolBar::SetButtonInfo](../Topic/CMFCToolBar::SetButtonInfo.md)|ツール バー ボタンのコマンド ID、スタイル、およびイメージ ID を設定します。|  
|[CMFCToolBar::SetButtonStyle](../Topic/CMFCToolBar::SetButtonStyle.md)|特定のインデックスのツール バー ボタンのスタイルを設定します。|  
|[CMFCToolBar::SetButtonText](../Topic/CMFCToolBar::SetButtonText.md)|ツール バー ボタンのテキスト ラベルを設定します。|  
|[CMFCToolBar::SetButtons](../Topic/CMFCToolBar::SetButtons.md)|ツール バーのボタンを設定します。|  
|[CMFCToolBar::SetCommandUsageOptions](../Topic/CMFCToolBar::SetCommandUsageOptions.md)|ほとんど使用されないコマンドを、どのような場合にアプリケーションのメニューに表示しないようにするかを指定します。|  
|[CMFCToolBar::SetCustomizeMode](../Topic/CMFCToolBar::SetCustomizeMode.md)|アプリケーション内のすべてのツール バーのカスタマイズ モードを有効または無効にします。|  
|[CMFCToolBar::SetGrayDisabledButtons](../Topic/CMFCToolBar::SetGrayDisabledButtons.md)|ツール バーの無効なボタンを淡色表示にするかどうか、また無効なボタンに無効なイメージを使用するかどうかを指定します。|  
|[CMFCToolBar::SetHeight](../Topic/CMFCToolBar::SetHeight.md)|ツール バーの高さを設定します。|  
|[CMFCToolBar::SetHotBorder](../Topic/CMFCToolBar::SetHotBorder.md)|ツール バー ボタンがホット トラッキングされるかどうかを指定します。|  
|[CMFCToolBar::SetHotTextColor](../Topic/CMFCToolBar::SetHotTextColor.md)|ホット ツール バー ボタンのテキストの色を設定します。|  
|[CMFCToolBar::SetLargeIcons](../Topic/CMFCToolBar::SetLargeIcons.md)|ツール バー ボタンに大きいアイコンを表示するかどうかを指定します。|  
|[CMFCToolBar::SetLockedSizes](../Topic/CMFCToolBar::SetLockedSizes.md)|ツール バー上のロックされたボタンおよびロックされたイメージのサイズを設定します|  
|[CMFCToolBar::SetMenuSizes](../Topic/CMFCToolBar::SetMenuSizes.md)|ツール バー メニューのボタンとそのイメージのサイズを設定します。|  
|[CMFCToolBar::SetNonPermittedCommands](../Topic/CMFCToolBar::SetNonPermittedCommands.md)|ユーザーが実行できないコマンドの一覧を設定します。|  
|[CMFCToolBar::SetOneRowWithSibling](../Topic/CMFCToolBar::SetOneRowWithSibling.md)|ツール バーとその兄弟を同じ行に配置します。|  
|[CMFCToolBar::SetPermament](../Topic/CMFCToolBar::SetPermament.md)|ユーザーがツール バーを閉じることができるかどうかを示します。|  
|[CMFCToolBar::SetRouteCommandsViaFrame](../Topic/CMFCToolBar::SetRouteCommandsViaFrame.md)|親フレームとオーナーのどちらがツール バーにコマンドを送信するかを指定します。|  
|[CMFCToolBar::SetShowTooltips](../Topic/CMFCToolBar::SetShowTooltips.md)|フレームワークにツールヒントを表示するかどうかを指定します。|  
|[CMFCToolBar::SetSiblingToolBar](../Topic/CMFCToolBar::SetSiblingToolBar.md)|ツール バーの兄弟を指定します。|  
|[CMFCToolBar::SetSizes](../Topic/CMFCToolBar::SetSizes.md)|すべてのツール バーのボタンとイメージのサイズを指定します。|  
|[CMFCToolBar::SetToolBarBtnText](../Topic/CMFCToolBar::SetToolBarBtnText.md)|ツール バーのボタンのプロパティを指定します。|  
|[CMFCToolBar::SetTwoRowsWithSibling](../Topic/CMFCToolBar::SetTwoRowsWithSibling.md)|ツール バーとその兄弟を別々の行に配置します。|  
|[CMFCToolBar::SetUserImages](../Topic/CMFCToolBar::SetUserImages.md)|アプリケーションにおけるユーザー定義のイメージのコレクションを設定します。|  
|[CMFCToolBar::StretchPane](../Topic/CMFCToolBar::StretchPane.md)|ツール バーを垂直方向または水平方向に伸縮します。\([CBasePane::StretchPane](../Topic/CBasePane::StretchPane.md) をオーバーライドします。\)|  
|[CMFCToolBar::TranslateChar](../Topic/CMFCToolBar::TranslateChar.md)|指定したキー コードが有効なショートカット キーに対応するボタンのコマンドを実行します。|  
|[CMFCToolBar::UpdateButton](../Topic/CMFCToolBar::UpdateButton.md)|指定したボタンの状態を更新します。|  
|[CMFCToolBar::WrapToolBar](../Topic/CMFCToolBar::WrapToolBar.md)|特定の次元内のツール バー ボタンの位置を変更します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolBar::AllowShowOnList](../Topic/CMFCToolBar::AllowShowOnList.md)|**\[Customize\]** ダイアログ ボックスの **\[Toolbars\]** ペイン上の一覧に、ツール バーが表示されているかどうかを判断します。|  
|[CMFCToolBar::CalcMaxButtonHeight](../Topic/CMFCToolBar::CalcMaxButtonHeight.md)|ツール バーのボタンの高さの最大値を計算します。|  
|[CMFCToolBar::DoPaint](../Topic/CMFCToolBar::DoPaint.md)|ツール バーを再描画します。|  
|[CMFCToolBar::DrawButton](../Topic/CMFCToolBar::DrawButton.md)|ツール バー ボタンを再描画します。|  
|[CMFCToolBar::DrawSeparator](../Topic/CMFCToolBar::DrawSeparator.md)|ツール バーに区分線を再描画します。|  
|[CMFCToolBar::OnUserToolTip](../Topic/CMFCToolBar::OnUserToolTip.md)|ボタンのツールヒントを表示する直前に、フレームワークによって呼び出されます。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolBar::m\_bDontScaleImages](../Topic/CMFCToolBar::m_bDontScaleImages.md)|高解像度モードでツール バーのイメージを拡大縮小するかどうかを指定します。|  
|[CMFCToolBar::m\_dblLargeImageRatio](../Topic/CMFCToolBar::m_dblLargeImageRatio.md)|大きいイメージの大きさ \(高さまたは幅\) と通常のイメージの大きさとの比を指定します。|  
  
## 解説  
 `CMFCToolBar` オブジェクトをアプリケーションに組み込むには、次の手順を実行します。  
  
1.  メイン フレーム ウィンドウに `CMFCToolBar` オブジェクトを追加します。  
  
2.  メイン フレーム ウィンドウの `WM_CREATE` メッセージを処理する場合は、[CMFCToolBar::Create](../Topic/CMFCToolBar::Create.md) または [CMFCToolBar::CreateEx](../Topic/CMFCToolBar::CreateEx.md) を呼び出してツール バーを作成し、そのスタイルを指定します。  
  
3.  [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md) を呼び出してドッキング スタイルを指定します。  
  
 コンボ ボックスやドロップダウン ツール バーのような特殊なボタンを挿入するには、親リソースでダミー ボタンを予約し、実行時に [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md) を使用してダミー ボタンを置き換えます。  詳細については、「[チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)」を参照してください。  
  
 `CMFCToolBar` は、MFC ライブラリ クラス [CMFCMenuBar クラス](../../mfc/reference/cmfcmenubar-class.md)、[CMFCPopupMenuBar クラス](../../mfc/reference/cmfcpopupmenubar-class.md)と [CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)の基本クラスです。  
  
## 使用例  
 `CMFCToolBar` クラスのさまざまなメソッドの使用方法を次の例に示します。  この例では、ツール バーのウィンドウ ラベルのテキストの設定方法、境界線の設定方法、ペインのスタイルの設定方法、およびツール バーの末尾に表示される **\[ボタンの表示\/非表示\]** ボタンを有効にする方法を示しています。  このコード スニペットは [IE のデモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_IEDemo#6](../../mfc/reference/codesnippet/CPP/cmfctoolbar-class_1.h)]  
[!code-cpp[NVC_MFC_IEDemo#8](../../mfc/reference/codesnippet/CPP/cmfctoolbar-class_2.cpp)]  
  
## 必要条件  
 **ヘッダー :** afxtoolbar.h  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCMenuBar クラス](../../mfc/reference/cmfcmenubar-class.md)   
 [CMFCPopupMenuBar クラス](../../mfc/reference/cmfcpopupmenubar-class.md)   
 [CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)