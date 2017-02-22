---
title: "CMenu クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMenu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMenu クラス"
  - "HMENU"
  - "メニュー, 基本クラス"
  - "メニュー, class"
  - "メニュー, 作成"
  - "メニュー, 管理"
ms.assetid: 40cacfdc-d45c-4ec7-bf28-991c72812499
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CMenu クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows の `HMENU` をカプセル化したものです。  
  
## 構文  
  
```  
class CMenu : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMenu::CMenu](../Topic/CMenu::CMenu.md)|`CMenu` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md)|このメニューの最後に新しい項目を追加します。|  
|[CMenu::Attach](../Topic/CMenu::Attach.md)|`CMenu` のオブジェクトに Windows メニューのハンドルをアタッチします。|  
|[CMenu::CheckMenuItem](../Topic/CMenu::CheckMenuItem.md)|の横にチェック マークを設定またはポップアップ メニューのメニュー項目から削除したりします。|  
|[CMenu::CheckMenuRadioItem](../Topic/CMenu::CheckMenuRadioItem.md)|ラジオ ボタンをメニュー項目の横に設定し、グループの他のすべてのメニュー項目からラジオ ボタンを削除します。|  
|[CMenu::CreateMenu](../Topic/CMenu::CreateMenu.md)|空のメニューを作成し、`CMenu` のオブジェクトにアタッチします。|  
|[CMenu::CreatePopupMenu](../Topic/CMenu::CreatePopupMenu.md)|空のポップアップ メニューを作成し、`CMenu` のオブジェクトにアタッチします。|  
|[CMenu::DeleteMenu](../Topic/CMenu::DeleteMenu.md)|メニューから指定された項目を削除します。  メニュー項目に関連付けられたポップアップ メニューがある場合は、ハンドルのポップアップ メニューに分割し、それによって使用されているメモリを解放します。|  
|[CMenu::DeleteTempMap](../Topic/CMenu::DeleteTempMap.md)|`FromHandle` のメンバー関数によって作成された `CMenu` の一時的なオブジェクトを削除します。|  
|[CMenu::DestroyMenu](../Topic/CMenu::DestroyMenu.md)|`CMenu` のオブジェクトにアタッチされているメニューを破棄し、メニューを占めたメモリを解放します。|  
|[CMenu::Detach](../Topic/CMenu::Detach.md)|`CMenu` のオブジェクトから Windows メニューのハンドルを切り離し、そのハンドルを返します。|  
|[CMenu::DrawItem](../Topic/CMenu::DrawItem.md)|オーナー描画メニューの外観を変更するときに、フレームワークによって呼び出されます。|  
|[CMenu::EnableMenuItem](../Topic/CMenu::EnableMenuItem.md)|に設定すると、有効にするか、または \(灰\) メニュー項目を淡色表示にします。|  
|[CMenu::FromHandle](../Topic/CMenu::FromHandle.md)|Windows メニューのハンドルを持つ `CMenu` オブジェクトへのポインターを返します。|  
|[CMenu::GetDefaultItem](../Topic/CMenu::GetDefaultItem.md)|指定したメニューの既定のメニュー項目を決定します。|  
|[CMenu::GetMenuContextHelpId](../Topic/CMenu::GetMenuContextHelpId.md)|メニューに関連付けられたヘルプ コンテキスト ID を取得します。|  
|[CMenu::GetMenuInfo](../Topic/CMenu::GetMenuInfo.md)|特定のメニューの情報を取得します。|  
|[CMenu::GetMenuItemCount](../Topic/CMenu::GetMenuItemCount.md)|ポップアップまたはトップレベルのメニュー項目の数を判断します。|  
|[CMenu::GetMenuItemID](../Topic/CMenu::GetMenuItemID.md)|指定した位置にあるメニュー項目のメニュー項目の識別子を取得します。|  
|[CMenu::GetMenuItemInfo](../Topic/CMenu::GetMenuItemInfo.md)|メニュー項目に関する情報を取得します。|  
|[CMenu::GetMenuState](../Topic/CMenu::GetMenuState.md)|指定されたメニュー項目のステータスまたはポップアップ メニューの項目数を返します。|  
|[CMenu::GetMenuString](../Topic/CMenu::GetMenuString.md)|指定されたメニュー項目のラベルを取得します。|  
|[CMenu::GetSafeHmenu](../Topic/CMenu::GetSafeHmenu.md)|`CMenu` でこのオブジェクトでラップされた `m_hMenu` を返します。|  
|[CMenu::GetSubMenu](../Topic/CMenu::GetSubMenu.md)|ポップアップ メニューへのポインターを取得します。|  
|[CMenu::InsertMenu](../Topic/CMenu::InsertMenu.md)|メニューの下のそのほかの項目を移動指定した位置に新しいメニュー項目を挿入します。|  
|[CMenu::InsertMenuItem](../Topic/CMenu::InsertMenuItem.md)|メニューの指定した位置に新しいメニュー項目を挿入します。|  
|[CMenu::LoadMenu](../Topic/CMenu::LoadMenu.md)|実行可能ファイルからメニュー リソースを読み込み、`CMenu` のオブジェクトにアタッチします。|  
|[CMenu::LoadMenuIndirect](../Topic/CMenu::LoadMenuIndirect.md)|メモリのメニューのテンプレートのメニューを読み込み、`CMenu` のオブジェクトにアタッチします。|  
|[CMenu::MeasureItem](../Topic/CMenu::MeasureItem.md)|オーナー描画メニューの作成時にメニューのサイズを決定するために、フレームワークによって呼び出されます。|  
|[CMenu::ModifyMenu](../Topic/CMenu::ModifyMenu.md)|指定した位置にある既存のメニュー項目を変更します。|  
|[CMenu::RemoveMenu](../Topic/CMenu::RemoveMenu.md)|指定されたメニューから関連付けられたポップアップ メニューのメニュー項目を削除します。|  
|[CMenu::SetDefaultItem](../Topic/CMenu::SetDefaultItem.md)|指定されたメニューの既定のメニュー項目を設定します。|  
|[CMenu::SetMenuContextHelpId](../Topic/CMenu::SetMenuContextHelpId.md)|メニューに関連付けるヘルプ コンテキスト ID を設定します。|  
|[CMenu::SetMenuInfo](../Topic/CMenu::SetMenuInfo.md)|特定のメニューの情報を設定します。|  
|[CMenu::SetMenuItemBitmaps](../Topic/CMenu::SetMenuItemBitmaps.md)|メニュー項目と指定のチェックマーク ビットマップを関連付けます。|  
|[CMenu::SetMenuItemInfo](../Topic/CMenu::SetMenuItemInfo.md)|メニュー項目についての情報を変更します。|  
|[CMenu::TrackPopupMenu](../Topic/CMenu::TrackPopupMenu.md)|フローティング ポップアップ メニューを指定の位置に表示し、ポップアップ メニュー項目の選択を追跡します。|  
|[CMenu::TrackPopupMenuEx](../Topic/CMenu::TrackPopupMenuEx.md)|フローティング ポップアップ メニューを指定の位置に表示し、ポップアップ メニュー項目の選択を追跡します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CMenu::operator HMENU](../Topic/CMenu::operator%20HMENU.md)|メニュー オブジェクトのハンドルを取得します。|  
|[CMenu::operator \!\=](../Topic/CMenu::operator%20!=.md)|2 個のメニュー オブジェクトが等しくないかどうかを判定します。|  
|[CMenu::operator \=\=](../Topic/CMenu::operator%20==.md)|2 個のメニューのオブジェクトが等しいかどうかを判定します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMenu::m\_hMenu](../Topic/CMenu::m_hMenu.md)|`CMenu` のオブジェクトにアタッチされている Windows メニューのハンドルを指定します。|  
  
## 解説  
 これは、メニューを作成し、追跡し、更新、および破棄するには、メンバー関数を提供します。  
  
 必要に応じて新しいメニューを処理するローカル、呼び出しの `CMenu` のメンバー関数としてスタック フレームの `CMenu` のオブジェクトを作成します。  次に、`CMenu` のオブジェクトの [&#91;デタッチ&#93;](../Topic/CMenu::Detach.md) のメンバー関数の呼び出しに続きます。ウィンドウにメニューを設定する呼び出し [CWnd::SetMenu](../Topic/CWnd::SetMenu.md)。  `CWnd::SetMenu` のメンバー関数は新しいメニューに\[ウィンドウ\]メニューを設定し、ウィンドウのメニューの変更を反映するように再描画およびウィンドウにメニューの所有権を渡します。  **\[デタッチ\]** の呼び出しは `CMenu` のローカル変数がスコープ外に渡すと、`CMenu` のオブジェクトのデストラクターが既に所有しているメニューを破棄するようにしないように、`CMenu` のオブジェクトの `HMENU` をデタッチします。  ウィンドウが破棄されるときに、メニュー自体は自動的に破棄されます。  
  
 メモリのテンプレートのメニューを作成するために [LoadMenuIndirect](../Topic/CMenu::LoadMenuIndirect.md) のメンバー関数を使用できますが、呼び出しによってリソースから [LoadMenu](../Topic/CMenu::LoadMenu.md) に作成されたメニューが簡単に保持され、メニュー リソース自体は、メニュー エディターによって作成および変更できます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CMenu`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [MFC CTRLTEST サンプル](../../top/visual-cpp-samples.md)   
 [MFC DYNAMENU サンプル](../../top/visual-cpp-samples.md)   
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CObject クラス](../Topic/CObject%20Class.md)