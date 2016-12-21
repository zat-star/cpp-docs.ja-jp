---
title: "CBaseTabbedPane クラス | Microsoft Docs"
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
  - "CBaseTabbedPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBaseTabbedPane クラス"
ms.assetid: f22c0080-5b29-4a0a-8f74-8f0a4cd2dbcf
caps.latest.revision: 26
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBaseTabbedPane クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CDockablePane クラス](../Topic/CDockablePane%20Class.md)の機能を拡張して、タブ付きウィンドウの作成をサポートします。  
  
## 構文  
  
```  
class CBaseTabbedPane : public CDockablePane  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CBaseTabbedPane::CBaseTabbedPane`|既定のコンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CBaseTabbedPane::AddTab](../Topic/CBaseTabbedPane::AddTab.md)|新しいタブをタブ付きペインに追加します。|  
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../Topic/CBaseTabbedPane::AllowDestroyEmptyTabbedPane.md)|空のタブ付きウィンドウが破棄できるかどうかを指定します。|  
|[CBaseTabbedPane::ApplyRestoredTabInfo](../Topic/CBaseTabbedPane::ApplyRestoredTabInfo.md)|レジストリから読み込まれるタブ付きウィンドウにタブ設定を追加します。|  
|[CBaseTabbedPane::CanFloat](../Topic/CBaseTabbedPane::CanFloat.md)|ペインをフローティングできるかどうかを判断します。  \([CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md) をオーバーライドします。\)|  
|[CBaseTabbedPane::CanSetCaptionTextToTabName](../Topic/CBaseTabbedPane::CanSetCaptionTextToTabName.md)|タブ付きペインのキャプションにアクティブなタブと同じテキストが表示されるかどうかを判断します。|  
|[CBaseTabbedPane::ConvertToTabbedDocument](../Topic/CBaseTabbedPane::ConvertToTabbedDocument.md)|\([CDockablePane::ConvertToTabbedDocument](../Topic/CDockablePane::ConvertToTabbedDocument.md) をオーバーライドします。\)|  
|[CBaseTabbedPane::DetachPane](../Topic/CBaseTabbedPane::DetachPane.md)|MDI タブ付きドキュメントに一つ以上のドッキング可能なペインを変換します。|  
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](../Topic/CBaseTabbedPane::EnableSetCaptionTextToTabName.md)|アクティブなタブのラベル テキストとキャプション テキストを同期させるタブ付きペインの機能を有効または無効にします。|  
|[CBaseTabbedPane::FillDefaultTabsOrderArray](../Topic/CBaseTabbedPane::FillDefaultTabsOrderArray.md)|既定の内部にタブ オーダーを復元します。|  
|[CBaseTabbedPane::FindBarByTabNumber](../Topic/CBaseTabbedPane::FindBarByTabNumber.md)|0 から始まるタブ インデックスによってタブが識別されると、そのタブ内にあるペインを返します。|  
|||  
|[CBaseTabbedPane::FindPaneByID](../Topic/CBaseTabbedPane::FindPaneByID.md)|ペイン ID で識別されるペインを返します|  
|[CBaseTabbedPane::FloatTab](../Topic/CBaseTabbedPane::FloatTab.md)|ペインが現在切り離し可能なタブにある場合に限り、ペインをフローティングにします|  
|[CBaseTabbedPane::GetDefaultTabsOrder](../Topic/CBaseTabbedPane::GetDefaultTabsOrder.md)|ウィンドウのタブの既定の注文を返します。|  
|[CBaseTabbedPane::GetFirstVisibleTab](../Topic/CBaseTabbedPane::GetFirstVisibleTab.md)|最初に表示されるタブへのポインターを取得します。|  
|[CBaseTabbedPane::GetMinSize](../Topic/CBaseTabbedPane::GetMinSize.md)|ウィンドウのサイズを指定された最小値を取得します。  \([CPane::GetMinSize](../Topic/CPane::GetMinSize.md) をオーバーライドします。\)|  
|[CBaseTabbedPane::GetPaneIcon](../Topic/CBaseTabbedPane::GetPaneIcon.md)|ペイン アイコンへのハンドルを返します。  \([CBasePane::GetPaneIcon](../Topic/CBasePane::GetPaneIcon.md) をオーバーライドします。\)|  
|[CBaseTabbedPane::GetPaneList](../Topic/CBaseTabbedPane::GetPaneList.md)|タブ付きウィンドウに含まれているペインのリストを返します。|  
|[CBaseTabbedPane::GetTabArea](../Topic/CBaseTabbedPane::GetTabArea.md)|上部および下部のタブ領域に外接する四角形を返します。|  
|[CBaseTabbedPane::GetTabsNum](../Topic/CBaseTabbedPane::GetTabsNum.md)|タブ ウィンドウ内のタブの数を返します。|  
|[CBaseTabbedPane::GetUnderlyingWindow](../Topic/CBaseTabbedPane::GetUnderlyingWindow.md)|基になる \(ラップされた\) タブ ウィンドウを取得します。|  
|[CBaseTabbedPane::GetVisibleTabsNum](../Topic/CBaseTabbedPane::GetVisibleTabsNum.md)|表示されるタブの数を返します。|  
|[CBaseTabbedPane::HasAutoHideMode](../Topic/CBaseTabbedPane::HasAutoHideMode.md)|タブ付きペインが自動非表示モードに切り替えることができるかどうかを判定します。|  
|[CBaseTabbedPane::IsHideSingleTab](../Topic/CBaseTabbedPane::IsHideSingleTab.md)|タブが 1 つしか表示されていない場合に、タブ付きペインが非表示になっているかどうかを確認します。|  
|`CBaseTabbedPane::LoadSiblingPaneIDs`|内部的にシリアル化の際に使用します。|  
|[CBaseTabbedPane::RecalcLayout](../Topic/CBaseTabbedPane::RecalcLayout.md)|ウィンドウのレイアウト情報を再計算します。  \([CPane::RecalcLayout](../Topic/CPane::RecalcLayout.md) をオーバーライドします。\)|  
|[CBaseTabbedPane::RemovePane](../Topic/CBaseTabbedPane::RemovePane.md)|タブ付きペインからペインを削除します。|  
|`CBaseTabbedPane::SaveSiblingBarIDs`|内部的にシリアル化の際に使用します。|  
|`CBaseTabbedPane::Serialize`|\([CDockablePane::Serialize](http://msdn.microsoft.com/ja-jp/09787e59-e446-4e76-894b-206d303dcfd6) をオーバーライドします。\)|  
|`CBaseTabbedPane::SerializeTabWindow`|内部的にシリアル化の際に使用します。|  
|[CBaseTabbedPane::SetAutoDestroy](../Topic/CBaseTabbedPane::SetAutoDestroy.md)|タブ付きコントロール バーが自動的に破棄されるかどうかを判断します。|  
|[CBaseTabbedPane::SetAutoHideMode](../Topic/CBaseTabbedPane::SetAutoHideMode.md)|表示モードと自動非表示のドッキング ペインの表示と非表示を切り替えます。  \([CDockablePane::SetAutoHideMode](../Topic/CDockablePane::SetAutoHideMode.md) をオーバーライドします。\)|  
|[CBaseTabbedPane::ShowTab](../Topic/CBaseTabbedPane::ShowTab.md)|タブの表示と非表示を切り替えます。|  
  
## 解説  
 このクラスは抽象基本クラスであり、インスタンス化できません。  すべての種類のタブ付きペインに共通のサービスを実装します。  
  
 現在、ライブラリには 2 つのタブ付きペインの派生クラスがあります。[CTabbedPane クラス](../../mfc/reference/ctabbedpane-class.md)と [CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md) です。  
  
 `CBaseTabbedPane` オブジェクトは、[CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md) オブジェクトへのポインターをラップします。  [CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md) は、タブ付きペインの子ウィンドウになります。  
  
 タブ付きペインの作成方法の詳細については、「[CDockablePane クラス](../Topic/CDockablePane%20Class.md)」、「[CTabbedPane クラス](../../mfc/reference/ctabbedpane-class.md)」、および「[CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../Topic/CDockablePane%20Class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
## 必要条件  
 **ヘッダー :** afxBaseTabbedPane.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CDockablePane クラス](../Topic/CDockablePane%20Class.md)