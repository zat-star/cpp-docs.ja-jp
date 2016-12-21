---
title: "CMFCOutlookBar クラス | Microsoft Docs"
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
  - "CMFCOutlookBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCOutlookBar クラス"
ms.assetid: 2b335f71-ce99-4efd-b103-e65ba43ffc36
caps.latest.revision: 34
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCOutlookBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Microsoft Outlook 2000 または Outlook 2003 の**ナビゲーション ウィンドウ**と同じ外観を持つタブ付きペインです。  `CMFCOutlookBar` オブジェクトには、[CMFCOutlookBarTabCtrl クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md) オブジェクトと一連のタブが含まれます。  それらのタブは、[CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md) オブジェクトまたは `CWnd` から派生したオブジェクトです。  ユーザーに対しては、Outlook バーは一連のボタンおよび表示領域として表示されます。  ユーザーがボタンをクリックすると、対応するコントロールまたはボタン ペインが表示されます。  
  
## 構文  
  
```  
class CMFCOutlookBar : public CBaseTabbedPane  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CMFCOutlookBar::CMFCOutlookBar`|既定のコンストラクターです。|  
|`CMFCOutlookBar::~CMFCOutlookBar`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](../Topic/CMFCOutlookBar::AllowDestroyEmptyTabbedPane.md)|空のタブ付きウィンドウが破棄できるかどうかを指定します。  \([CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../Topic/CBaseTabbedPane::AllowDestroyEmptyTabbedPane.md) をオーバーライドします。\)|  
|[CMFCOutlookBar::CanAcceptPane](../Topic/CMFCOutlookBar::CanAcceptPane.md)|Outlook バー ペインに別のペインをドッキングできるかどうかを判断します   \(CDockablePane::CanAcceptPane をオーバーライドします\)。|  
|[CMFCOutlookBar::CanSetCaptionTextToTabName](../Topic/CMFCOutlookBar::CanSetCaptionTextToTabName.md)|タブ付きペインのキャプションにアクティブなタブと同じテキストが表示されるかどうかを判断します   \([CBaseTabbedPane::CanSetCaptionTextToTabName](../Topic/CBaseTabbedPane::CanSetCaptionTextToTabName.md) をオーバーライドします\)。|  
|[CMFCOutlookBar::Create](../Topic/CMFCOutlookBar::Create.md)|Outlook バー コントロールを作成します。|  
|[CMFCOutlookBar::CreateCustomPage](../Topic/CMFCOutlookBar::CreateCustomPage.md)|カスタム Outlook バー タブを作成します。|  
|`CMFCOutlookBar::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークによって使用されます。|  
|[CMFCOutlookBar::DoesAllowDynInsertBefore](../Topic/CMFCOutlookBar::DoesAllowDynInsertBefore.md)|ユーザーが Outlook バーの外側にコントロール バーをドッキングできるかどうかを判断します。|  
|[CMFCOutlookBar::FloatTab](../Topic/CMFCOutlookBar::FloatTab.md)|ペインが現在切り離し可能なタブにある場合に限り、ペインをフローティングにします   \([CBaseTabbedPane::FloatTab](../Topic/CBaseTabbedPane::FloatTab.md) をオーバーライドします。\)|  
|[CMFCOutlookBar::GetButtonsFont](../Topic/CMFCOutlookBar::GetButtonsFont.md)|Outlook バーのボタンに表示されるテキストのフォントを返します。|  
|[CMFCOutlookBar::GetTabArea](../Topic/CMFCOutlookBar::GetTabArea.md)|Outlook バーのタブ領域のサイズと位置を返します   \([CBaseTabbedPane::GetTabArea](../Topic/CBaseTabbedPane::GetTabArea.md) をオーバーライドします\)。|  
|`CMFCOutlookBar::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
|[CMFCOutlookBar::IsMode2003](../Topic/CMFCOutlookBar::IsMode2003.md)|Outlook バーが Microsoft Office Outlook 2003 と同じように動作するかどうかを判断します。「解説」を参照してください。|  
|[CMFCOutlookBar::OnAfterAnimation](../Topic/CMFCOutlookBar::OnAfterAnimation.md)|アクティブなタブの後に [CMFCOutlookBarTabCtrl::SetActiveTab](../Topic/CMFCOutlookBarTabCtrl::SetActiveTab.md) によって呼び出されたアニメーションを使用して設定されました。|  
|[CMFCOutlookBar::OnBeforeAnimation](../Topic/CMFCOutlookBar::OnBeforeAnimation.md)|タブ ページがアニメーションを使用してアクティブなタブとして設定される前に [CMFCOutlookBarTabCtrl::SetActiveTab](../Topic/CMFCOutlookBarTabCtrl::SetActiveTab.md) で呼び出します。|  
|[CMFCOutlookBar::OnScroll](../Topic/CMFCOutlookBar::OnScroll.md)|Outlook バーが左右にスクロールすると、フレームワークによって呼び出されます。|  
|[CMFCOutlookBar::RemoveCustomPage](../Topic/CMFCOutlookBar::RemoveCustomPage.md)|カスタム Outlook バー タブを削除します。|  
|[CMFCOutlookBar::SetButtonsFont](../Topic/CMFCOutlookBar::SetButtonsFont.md)|Outlook バーのボタンに表示されるテキストのフォントを設定します。|  
|[CMFCOutlookBar::SetMode2003](../Topic/CMFCOutlookBar::SetMode2003.md)|Outlook バーを Outlook 2003 と同じように動作させるかどうかを指定します。「解説」を参照してください。|  
  
## 解説  
 Outlook バーの例については、[OutlookDemo サンプル: MFC OutlookDemo アプリケーション](../../top/visual-cpp-samples.md)を参照してください。  
  
## Outlook バーの実装  
 アプリケーションで `CMFCOutlookBar` コントロールを使用するには、次の手順に従います。  
  
1.  `CMFCOutlookBar` オブジェクトをメイン フレーム ウィンドウ クラスに埋め込みます。  
  
    ```  
    class CMainFrame : public CMDIFrameWnd  
     { ...  
         CMFCOutlookBar         m_wndOutlookBar;  
         CMFCOutlookBarPane     m_wndOutlookPane;  
    ... };  
    ```  
  
2.  メイン フレームで `WM_CREATE` メッセージを処理するときに、[CMFCOutlookBar::Create](../Topic/CMFCOutlookBar::Create.md) メソッドを呼び出して Outlook バー タブ コントロールを作成します。  
  
    ```  
    m_wndOutlookBar.Create (_T("Shortcuts"), this, CRect (0, 0, 100, 100), ID_VIEW_OUTLOOKBAR, WS_CHILD | WS_VISIBLE | CBRS_LEFT);  
    ```  
  
3.  [CBaseTabbedPane::GetUnderlyingWindow](../Topic/CBaseTabbedPane::GetUnderlyingWindow.md) を使用して、基になる `CMFCOutlookBarTabCtrl` へのポインターを取得します。  
  
    ```  
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();  
    ```  
  
4.  ボタンを含むタブごとに [CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md) オブジェクトを作成します。  
  
    ```  
    m_wndOutlookPane.Create (&m_wndOutlookBar, AFX_DEFAULT_TOOLBAR_STYLE, ID_OUTLOOK_PANE_GENERAL, AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);  
    // make the Outlook pane detachable (enable docking)  
    m_wndOutlookPane.EnableDocking (CBRS_ALIGN_ANY);  
    // add buttons  
    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_MAINFRAME), "About", ID_APP_ABOUT);  
    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON), "Open", ID_FILE_OPEN);  
    ```  
  
5.  [CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md) を呼び出して新しいタブをそれぞれ追加します。  ページをデタッチできないようにするには、`bDetachable` パラメーターを `FALSE` に設定します。  デタッチできるページを追加するには、[CMFCOutlookBarTabCtrl::AddControl](../Topic/CMFCOutlookBarTabCtrl::AddControl.md) を使用します。  
  
    ```  
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1, TRUE);   
    ```  
  
6.  `CWnd` から派生したコントロール \([CMFCShellTreeCtrl クラス](../../mfc/reference/cmfcshelltreectrl-class.md)など\) をタブとして追加するには、コントロールを作成し、[CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md) を呼び出してそのコントロールを Outlook バーに追加します。  
  
> [!NOTE]
>  各 [CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md) オブジェクトおよび `CWnd` から派生した各オブジェクトに一意のコントロール ID を使用する必要があります。  
  
 新しいページを実行時に動的に追加または削除するには、それぞれ [CMFCOutlookBar::CreateCustomPage](../Topic/CMFCOutlookBar::CreateCustomPage.md) と [CMFCOutlookBar::RemoveCustomPage](../Topic/CMFCOutlookBar::RemoveCustomPage.md) を使用します。  
  
## Outlook 2003 モード  
 Outlook 2003 モードでは、タブ ボタンは Outlook バー ペインの下部に配置されます。  ボタンを表示できる十分な領域がない場合、ボタンはペインの下部にあるツール バーに似た領域にアイコンとして表示されます。  
  
 Outlook 2003 モードを有効にするには、[CMFCOutlookBar::SetMode2003](../Topic/CMFCOutlookBar::SetMode2003.md) を使用します。  Outlook バーの下部に表示されるアイコンが含まれたビットマップを設定するには、[CMFCOutlookBarTabCtrl::SetToolbarImageList](../Topic/CMFCOutlookBarTabCtrl::SetToolbarImageList.md) を使用します。  ビットマップのアイコンは、タブ インデックス順に並べる必要があります。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../Topic/CDockablePane%20Class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)  
  
## 必要条件  
 **ヘッダー :** afxoutlookbar.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CBaseTabbedPane クラス](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBarTabCtrl クラス](../../mfc/reference/cmfcoutlookbartabctrl-class.md)   
 [CMFCOutlookBarPane クラス](../../mfc/reference/cmfcoutlookbarpane-class.md)