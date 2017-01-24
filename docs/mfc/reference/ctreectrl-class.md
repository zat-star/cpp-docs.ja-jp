---
title: "CTreeCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTreeCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl クラス"
  - "ディレクトリ一覧"
  - "ファイル リスト [C++]"
  - "ツリー ビュー コントロール"
ms.assetid: 96e20031-6161-4143-8c12-8d1816c66d90
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTreeCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows コモン ツリー ビュー コントロールの機能が用意されています。  
  
## 構文  
  
```  
class CTreeCtrl : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CTreeCtrl::CTreeCtrl](../Topic/CTreeCtrl::CTreeCtrl.md)|`CTreeCtrl` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CTreeCtrl::Create](../Topic/CTreeCtrl::Create.md)|ツリー ビュー コントロールを作成し、`CTreeCtrl` オブジェクトに結び付けます。|  
|[CTreeCtrl::CreateDragImage](../Topic/CTreeCtrl::CreateDragImage.md)|指定されたツリー ビュー アイテムのドラッグ用のビットマップを作成します。|  
|[CTreeCtrl::CreateEx](../Topic/CTreeCtrl::CreateEx.md)|指定されたウィンドウの拡張スタイルを使用して、ツリー ビュー コントロールを作成し、`CTreeCtrl` オブジェクトに結び付けます。|  
|[CTreeCtrl::DeleteAllItems](../Topic/CTreeCtrl::DeleteAllItems.md)|ツリー ビュー コントロールのすべてのアイテムを削除します。|  
|[CTreeCtrl::DeleteItem](../Topic/CTreeCtrl::DeleteItem.md)|ツリー ビュー コントロールの新しいアイテムを削除します。|  
|[CTreeCtrl::EditLabel](../Topic/CTreeCtrl::EditLabel.md)|埋め込み先で指定されたツリー ビュー アイテムを編集します。|  
|[CTreeCtrl::EndEditLabelNow](../Topic/CTreeCtrl::EndEditLabelNow.md)|現在のツリー ビュー コントロールでツリー ビュー アイテムのラベルに対して行った編集操作をキャンセルします。|  
|[CTreeCtrl::EnsureVisible](../Topic/CTreeCtrl::EnsureVisible.md)|ツリー ビュー アイテムがツリー ビュー コントロール内に表示されるようにします。|  
|[CTreeCtrl::Expand](../Topic/CTreeCtrl::Expand.md)|指定されたツリー ビュー アイテムの子アイテムを開いたり、閉じたりします。|  
|[CTreeCtrl::GetBkColor](../Topic/CTreeCtrl::GetBkColor.md)|ツリー ビュー コントロールの現在の背景色を取得します。|  
|[CTreeCtrl::GetCheck](../Topic/CTreeCtrl::GetCheck.md)|ツリー ビュー コントロールのアイテムのチェック状態を取得します。|  
|[CTreeCtrl::GetChildItem](../Topic/CTreeCtrl::GetChildItem.md)|指定されたツリー ビュー アイテムの子アイテムを取得します。|  
|[CTreeCtrl::GetCount](../Topic/CTreeCtrl::GetCount.md)|ツリー ビュー コントロールに関連付けられているツリー ビュー アイテムの数を取得します。|  
|[CTreeCtrl::GetDropHilightItem](../Topic/CTreeCtrl::GetDropHilightItem.md)|ドラッグ アンド ドロップ操作のターゲットを取得します。|  
|[CTreeCtrl::GetEditControl](../Topic/CTreeCtrl::GetEditControl.md)|指定されたツリー ビュー アイテムの編集に使われるエディット コントロールのハンドルを取得します。|  
|[CTreeCtrl::GetExtendedStyle](../Topic/CTreeCtrl::GetExtendedStyle.md)|現在のツリー ビュー コントロールが使用している拡張スタイルを取得します。|  
|[CTreeCtrl::GetFirstVisibleItem](../Topic/CTreeCtrl::GetFirstVisibleItem.md)|指定されたビュー アイテムの最初に表示されるアイテムを取得します。|  
|[CTreeCtrl::GetImageList](../Topic/CTreeCtrl::GetImageList.md)|ツリー ビュー コントロールに関連付けられているイメージ リストのハンドルを取得します。|  
|[CTreeCtrl::GetIndent](../Topic/CTreeCtrl::GetIndent.md)|ツリー ビュー アイテムの親からのオフセットを \(ピクセル単位で\) 取得します。|  
|[CTreeCtrl::GetInsertMarkColor](../Topic/CTreeCtrl::GetInsertMarkColor.md)|ツリー ビューの挿入マークの描画色を取得します。|  
|[CTreeCtrl::GetItem](../Topic/CTreeCtrl::GetItem.md)|指定されたツリー ビュー アイテムの属性を取得します。|  
|[CTreeCtrl::GetItemData](../Topic/CTreeCtrl::GetItemData.md)|アイテムに関連付けされた 32 ビット アプリケーション固有の値を返します。|  
|[CTreeCtrl::GetItemExpandedImageIndex](../Topic/CTreeCtrl::GetItemExpandedImageIndex.md)|現在のツリー ビュー コントロール内の指定されたアイテムが展開状態になっているときに表示するイメージのインデックスを取得します。|  
|[CTreeCtrl::GetItemHeight](../Topic/CTreeCtrl::GetItemHeight.md)|ツリー ビュー アイテムの現在の高さを取得します。|  
|[CTreeCtrl::GetItemImage](../Topic/CTreeCtrl::GetItemImage.md)|アイテムに関連しているイメージを取得します。|  
|[CTreeCtrl::GetItemPartRect](../Topic/CTreeCtrl::GetItemPartRect.md)|現在のツリー ビュー コントロール内の指定されたアイテムの指定された部分に外接する四角形を取得します。|  
|[CTreeCtrl::GetItemRect](../Topic/CTreeCtrl::GetItemRect.md)|ツリー ビュー アイテムに外接する四角形を取得します。|  
|[CTreeCtrl::GetItemState](../Topic/CTreeCtrl::GetItemState.md)|アイテムの状態を返します。|  
|[CTreeCtrl::GetItemStateEx](../Topic/CTreeCtrl::GetItemStateEx.md)|現在のツリー ビュー コントロール内の指定されたアイテムの展開状態を取得します。|  
|[CTreeCtrl::GetItemText](../Topic/CTreeCtrl::GetItemText.md)|アイテムのテキストを返します。|  
|[CTreeCtrl::GetLastVisibleItem](../Topic/CTreeCtrl::GetLastVisibleItem.md)|現在のツリー ビュー コントロールで最後に展開されたアイテムを取得します。|  
|[CTreeCtrl::GetLineColor](../Topic/CTreeCtrl::GetLineColor.md)|ツリー ビュー コントロールの現在の行の色を取得します。|  
|[CTreeCtrl::GetNextItem](../Topic/CTreeCtrl::GetNextItem.md)|指定された関係に一致する次のツリー ビュー アイテムを取得します。|  
|[CTreeCtrl::GetNextSiblingItem](../Topic/CTreeCtrl::GetNextSiblingItem.md)|指定したツリー ビュー アイテムの次の兄弟アイテムを取得します。|  
|[CTreeCtrl::GetNextVisibleItem](../Topic/CTreeCtrl::GetNextVisibleItem.md)|指定されたビュー アイテムの次に表示されるアイテムを取得します。|  
|[CTreeCtrl::GetParentItem](../Topic/CTreeCtrl::GetParentItem.md)|指定されたツリー ビュー アイテムの親アイテムを取得します。|  
|[CTreeCtrl::GetPrevSiblingItem](../Topic/CTreeCtrl::GetPrevSiblingItem.md)|指定したツリー ビュー アイテムの前の兄弟アイテムを取得します。|  
|[CTreeCtrl::GetPrevVisibleItem](../Topic/CTreeCtrl::GetPrevVisibleItem.md)|指定されたビュー アイテムの前に表示されるアイテムを取得します。|  
|[CTreeCtrl::GetRootItem](../Topic/CTreeCtrl::GetRootItem.md)|指定されたツリー ビュー アイテムのルートを取得します。|  
|[CTreeCtrl::GetScrollTime](../Topic/CTreeCtrl::GetScrollTime.md)|ツリー ビュー コントロールの最長スクロール時間を取得します。|  
|[CTreeCtrl::GetSelectedCount](../Topic/CTreeCtrl::GetSelectedCount.md)|現在のツリー ビュー コントロールで選択されているアイテム数を取得します。|  
|[CTreeCtrl::GetSelectedItem](../Topic/CTreeCtrl::GetSelectedItem.md)|現在選択されているツリー ビュー アイテムを取得します。|  
|[CTreeCtrl::GetTextColor](../Topic/CTreeCtrl::GetTextColor.md)|ツリー ビュー コントロールの現在のテキスト色を取得します。|  
|[CTreeCtrl::GetToolTips](../Topic/CTreeCtrl::GetToolTips.md)|ツリー ビュー コントロールで使用する子ツール ヒント コントロールのハンドルを取得します。|  
|[CTreeCtrl::GetVisibleCount](../Topic/CTreeCtrl::GetVisibleCount.md)|ツリー ビュー コントロールに関連付けられている、表示されるツリー ビュー アイテムの数を取得します。|  
|[CTreeCtrl::HitTest](../Topic/CTreeCtrl::HitTest.md)|`CTreeCtrl` オブジェクトに関連するカーソルの現在位置を返します。|  
|[CTreeCtrl::InsertItem](../Topic/CTreeCtrl::InsertItem.md)|ツリー ビュー コントロールに新しいアイテムを挿入します。|  
|[CTreeCtrl::ItemHasChildren](../Topic/CTreeCtrl::ItemHasChildren.md)|指定されたアイテムが子アイテムを持っていれば 0 以外を返します。|  
|[CTreeCtrl::MapAccIdToItem](../Topic/CTreeCtrl::MapAccIdToItem.md)|指定したアクセシビリティ識別子を現在のツリー ビュー コントロール内のツリー ビュー アイテムのハンドルに割り当てます。|  
|[CTreeCtrl::MapItemToAccID](../Topic/CTreeCtrl::MapItemToAccID.md)|現在のツリー ビュー コントロール内のツリー ビュー アイテムの指定されたハンドルをアクセシビリティ識別子に割り当てます。|  
|[CTreeCtrl::Select](../Topic/CTreeCtrl::Select.md)|指定されたツリー ビュー アイテムを選択するか、表示領域にスクロールするか、または再描画します。|  
|[CTreeCtrl::SelectDropTarget](../Topic/CTreeCtrl::SelectDropTarget.md)|ドラッグ アンド ドロップ操作のターゲットとして、ツリー アイテムを再描画します。|  
|[CTreeCtrl::SelectItem](../Topic/CTreeCtrl::SelectItem.md)|指定されたツリー ビュー アイテムを選択します。|  
|[CTreeCtrl::SelectSetFirstVisible](../Topic/CTreeCtrl::SelectSetFirstVisible.md)|最初に表示されるアイテムとして、指定されたツリー ビューのアイテムを選択します。|  
|[CTreeCtrl::SetAutoscrollInfo](../Topic/CTreeCtrl::SetAutoscrollInfo.md)|現在のツリー ビュー コントロールの自動スクロール速度を設定します。|  
|[CTreeCtrl::SetBkColor](../Topic/CTreeCtrl::SetBkColor.md)|ツリー ビュー コントロールの背景色を設定します。|  
|[CTreeCtrl::SetCheck](../Topic/CTreeCtrl::SetCheck.md)|ツリー ビュー コントロールのアイテムのチェック状態を設定します。|  
|[CTreeCtrl::SetExtendedStyle](../Topic/CTreeCtrl::SetExtendedStyle.md)|現在のツリー ビュー コントロールの拡張スタイルを設定します。|  
|[CTreeCtrl::SetImageList](../Topic/CTreeCtrl::SetImageList.md)|ツリー ビュー コントロールに関連付けるイメージ リストのハンドルを設定します。|  
|[CTreeCtrl::SetIndent](../Topic/CTreeCtrl::SetIndent.md)|ツリー ビュー アイテムの親からのオフセットを \(ピクセル単位で\) 設定します。|  
|[CTreeCtrl::SetInsertMark](../Topic/CTreeCtrl::SetInsertMark.md)|ツリー ビュー コントロールに挿入マークを設定します。|  
|[CTreeCtrl::SetInsertMarkColor](../Topic/CTreeCtrl::SetInsertMarkColor.md)|ツリー ビューの挿入マークの描画色を設定します。|  
|[CTreeCtrl::SetItem](../Topic/CTreeCtrl::SetItem.md)|指定されたツリー ビュー アイテムの属性を設定します。|  
|[CTreeCtrl::SetItemData](../Topic/CTreeCtrl::SetItemData.md)|アイテムに関連付けされた 32 ビットアプリケーション固有の値を返します。|  
|[CTreeCtrl::SetItemExpandedImageIndex](../Topic/CTreeCtrl::SetItemExpandedImageIndex.md)|現在のツリー ビュー コントロール内の指定されたアイテムが展開状態になっているときに表示するイメージのインデックスを設定します。|  
|[CTreeCtrl::SetItemHeight](../Topic/CTreeCtrl::SetItemHeight.md)|ツリー ビュー アイテムの高さを設定します。|  
|[CTreeCtrl::SetItemImage](../Topic/CTreeCtrl::SetItemImage.md)|アイテムに関連しているイメージを設定します。|  
|[CTreeCtrl::SetItemState](../Topic/CTreeCtrl::SetItemState.md)|アイテムの状態を設定します。|  
|[CTreeCtrl::SetItemStateEx](../Topic/CTreeCtrl::SetItemStateEx.md)|現在のツリー ビュー コントロール内の指定されたアイテムの展開状態を設定します。|  
|[CTreeCtrl::SetItemText](../Topic/CTreeCtrl::SetItemText.md)|アイテムのテキストを設定します。|  
|[CTreeCtrl::SetLineColor](../Topic/CTreeCtrl::SetLineColor.md)|ツリー ビュー コントロールの現在の行の色を設定します。|  
|[CTreeCtrl::SetScrollTime](../Topic/CTreeCtrl::SetScrollTime.md)|ツリー ビュー コントロールの最長スクロール時間を設定します。|  
|[CTreeCtrl::SetTextColor](../Topic/CTreeCtrl::SetTextColor.md)|ツリー ビュー コントロールのテキスト色を設定します。|  
|[CTreeCtrl::SetToolTips](../Topic/CTreeCtrl::SetToolTips.md)|ツリー ビュー コントロールの子ツール ヒント コントロールを設定します。|  
|[CTreeCtrl::ShowInfoTip](../Topic/CTreeCtrl::ShowInfoTip.md)|現在のツリー ビュー コントロールで指定されているアイテムのヒントを表示します。|  
|[CTreeCtrl::SortChildren](../Topic/CTreeCtrl::SortChildren.md)|指定された親アイテムの子を並べ替えます。|  
|[CTreeCtrl::SortChildrenCB](../Topic/CTreeCtrl::SortChildrenCB.md)|アプリケーション定義の並べ替え関数を使って、指定した親アイテムの子アイテムを並べ替えます。|  
  
## 解説  
 「ツリー ビュー コントロール」はインデックスのドキュメントの見出しなどの項目の階層的な一覧が、エントリ、またはディスク上のファイルとディレクトリ表示するウィンドウです。  各項目はラベルと省略可能なビットマップ イメージから構成され、各項目は関連付けられたサブ項目の一覧を持つことができます。  項目をクリックして、ユーザーは、サブ項目に関連付けられたリストを展開したり折りたたんだりできます。  
  
 このコントロール \(したがって `CTreeCtrl` のクラス\) Windows 98 および Windows NT 4 以降で実行されるプログラムにのみ使用できます。  
  
 `CTreeCtrl`の使用の詳細については、" "を参照してください:  
  
-   [コントロール](../../mfc/controls-mfc.md)  
  
-   [を使用して CTreeCtrl](../Topic/Using%20CTreeCtrl.md)  
  
-   [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] の[ツリー ビュー コントロールの参照](http://msdn.microsoft.com/library/windows/desktop/bb759988)。  
  
-   サポート技術情報の文書 Q222905: " HOWTO: CTreeCtrl のコンテキスト メニューを表示します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CTreeCtrl`  
  
## 必要条件  
 **ヘッダー :** afxcmn.h  
  
## 参照  
 [MFC CMNCTRL1 サンプル](../../top/visual-cpp-samples.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CImageList クラス](../Topic/CImageList%20Class.md)