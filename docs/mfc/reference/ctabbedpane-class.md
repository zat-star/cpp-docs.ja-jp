---
title: "CTabbedPane クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTabbedPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabbedPane クラス"
ms.assetid: f4dc5215-b789-4f2d-8c62-477aceda3578
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CTabbedPane クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

切り離し可能なタブを持つペインの機能を実装します。  
  
## 構文  
  
```  
class CTabbedPane : public CBaseTabbedPane  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CTabbedPane::CTabbedPane`|既定のコンストラクター|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CTabbedPane::DetachPane](../Topic/CTabbedPane::DetachPane.md)|\([CBaseTabbedPane::DetachPane](../Topic/CBaseTabbedPane::DetachPane.md) をオーバーライドします。\)|  
|[CTabbedPane::EnableTabAutoColor](../Topic/CTabbedPane::EnableTabAutoColor.md)|タブの色の自動設定を有効または無効にします。|  
|[CTabbedPane::FloatTab](../Topic/CTabbedPane::FloatTab.md)|現在ペインが切り離し可能なタブに存在する場合のみ、そのペインを切り離して表示します。  \([CBaseTabbedPane::FloatTab](../Topic/CBaseTabbedPane::FloatTab.md) をオーバーライドします。\)|  
|[CTabbedPane::GetTabArea](../Topic/CTabbedPane::GetTabArea.md)|タブ付きウィンドウ内のタブ領域のサイズと位置を返します。|  
|[CTabbedPane::GetTabWnd](../Topic/CTabbedPane::GetTabWnd.md)||  
|[CTabbedPane::HasAutoHideMode](../Topic/CTabbedPane::HasAutoHideMode.md)|タブ付きペインを AutoHide モードに切り替えられるかどうかを判断します。  \([CBaseTabbedPane::HasAutoHideMode](../Topic/CBaseTabbedPane::HasAutoHideMode.md) をオーバーライドします。\)|  
|[CTabbedPane::IsTabLocationBottom](../Topic/CTabbedPane::IsTabLocationBottom.md)|タブがウィンドウの下部にあるかどうかを判断します。|  
|[CTabbedPane::ResetTabs](../Topic/CTabbedPane::ResetTabs.md)|すべてのタブ付きペインを既定の状態にリセットします。|  
|[CTabbedPane::SetTabAutoColors](../Topic/CTabbedPane::SetTabAutoColors.md)|色の自動設定機能が有効になっているときに使用できるカスタム色の一覧を設定します。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CTabbedPane::m\_bTabsAlwaysTop](../Topic/CTabbedPane::m_bTabsAlwaysTop.md)|アプリケーション内のタブの既定の場所。|  
|[CTabbedPane::m\_pTabWndRTC](../Topic/CTabbedPane::m_pTabWndRTC.md)|カスタムの `CMFCTabCtrl` から派生したオブジェクトに関するランタイム クラス情報。|  
  
## 解説  
 2 つ目のペインのキャプションをポイントして、ユーザーがあるペインを別のペインにアタッチすると、フレームワークにより自動的にこのクラスのインスタンスが作成されます。  \-1 の ID を持つフレームワークにより作成される、すべてのタブ付きペイン。  
  
 Outlook スタイルのタブではなく通常のタブを指定するには、`AFX_CBRS_REGULAR_TABS` スタイルを [CDockablePane::CreateEx](../Topic/CDockablePane::CreateEx.md) メソッドに渡します。  
  
 切り離し可能なタブを持つタブ付きペインを作成すると、フレームワークによってペインが自動的に破棄される可能性があるため、ポインターを格納しないでください。  タブ付きペインへのポインターを取得するには、`CBasePane::GetParentTabbedPane` メソッドを呼び出します。  
  
## 使用例  
 この例では `CTabbedPane` オブジェクトを作成します。  次に [CBaseTabbedPane::AddTab](../Topic/CBaseTabbedPane::AddTab.md) を使用して、追加のタブをアタッチします。  
  
```  
CTabbedPane* pTabbededBar = new CTabbedPane (TRUE);  
if (!pTabbededBar->Create (_T(""), this, CRect (0, 0, 200, 200),  
                           TRUE,   
                           (UINT) -1,  
                           WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS |  
                           WS_CLIPCHILDREN | CBRS_LEFT |    
                           CBRS_FLOAT_MULTI))  
{  
    TRACE0("Failed to create Solution Explorer bar\n");  
    return FALSE;      // fail to create  
}  
  
pTabbededBar->AddTab (&m_wndClassView);  
pTabbededBar->AddTab (&m_wndResourceView);  
pTabbededBar->AddTab (&m_wndFileView);  
pTabbededBar->EnableDocking(CBRS_ALIGN_ANY);  
DockPane(pTabbededBar);  
```  
  
## 使用例  
 タブ形式のコントロール バー オブジェクトを作成する別の方法として、[CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md) を使用します。  `AttachToTabWnd` メソッドでは、[CDockablePane::SetTabbedPaneRTC](../Topic/CDockablePane::SetTabbedPaneRTC.md) により設定されたランタイム クラス情報を使用して、タブ付きペインのオブジェクトを動的に作成します。  
  
 この例では、タブ付きペインを動的に作成し、2 つのタブをアタッチし、2 番目のタブを切り離し不可能にします。  
  
```  
DockPane(&m_wndClassView);  
CTabbedPane* pTabbedBar = NULL;  
m_wndResourceView.AttachToTabWnd (&m_wndClassView, DM_SHOW, TRUE,  
                                  (CDockablePane**) &pTabbedBar);  
m_wndFileView.AttachToTabWnd (pTabbedBar, DM_SHOW, TRUE,  
                              (CDockablePane**) &pTabbedBar);  
pTabbedBar->GetUnderlyingWindow ()->EnableTabDetach (1, FALSE);  
```  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../Topic/CDockablePane%20Class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CTabbedPane](../../mfc/reference/ctabbedpane-class.md)  
  
## 必要条件  
 **ヘッダー:** afxTabbedPane.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CDockablePane クラス](../Topic/CDockablePane%20Class.md)   
 [CBaseTabbedPane クラス](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)