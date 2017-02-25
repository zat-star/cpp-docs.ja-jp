---
title: "CPaneDialog クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPaneDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaneDialog クラス"
  - "CPaneDialog コンストラクター"
  - "CPaneDialog::CreateObject メソッド"
  - "CPaneDialog::OnEraseBkgnd メソッド"
  - "CPaneDialog::OnLButtonDblClk メソッド"
  - "CPaneDialog::OnLButtonDown メソッド"
  - "CPaneDialog::OnUpdateCmdUI メソッド"
  - "CPaneDialog::OnWindowPosChanging メソッド"
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CPaneDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CPaneDialog` クラスは、モードレスでドッキング可能なダイアログ ボックスをサポートします。  
  
## 構文  
  
```  
class CPaneDialog : public CDockablePane  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CPaneDialog::CPaneDialog`|既定のコンストラクターです。|  
|`CPaneDialog::~CPaneDialog`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CPaneDialog::Create](../Topic/CPaneDialog::Create.md)|ドッキング可能なダイアログ ボックスを作成し、`CPaneDialog` オブジェクトに関連付けます。|  
|`CPaneDialog::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークによって使用されます。|  
|`CPaneDialog::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
|[CPaneDialog::HandleInitDialog](../Topic/CPaneDialog::HandleInitDialog.md)|[WM\_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) メッセージを処理します   \(`CBasePane::HandleInitDialog` を再定義します\)。|  
|`CPaneDialog::OnEraseBkgnd`|[WM\_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) メッセージを処理します   \([CWnd::OnEraseBkgnd](../Topic/CWnd::OnEraseBkgnd.md) を再定義します\)。|  
|`CPaneDialog::OnLButtonDblClk`|[WM\_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) メッセージを処理します   \([CWnd::OnLButtonDblClk](../Topic/CWnd::OnLButtonDblClk.md) を再定義します\)。|  
|`CPaneDialog::OnLButtonDown`|[WM\_LBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645607) メッセージを処理します   \([CWnd::OnLButtonDown](../Topic/CWnd::OnLButtonDown.md) を再定義します\)。|  
|`CPaneDialog::OnUpdateCmdUI`|ダイアログ ボックス ウィンドウを更新するために、フレームワークによって呼び出されます   \([CDockablePane::OnUpdateCmdUI](http://msdn.microsoft.com/ja-jp/5dd61606-1c12-40d4-b024-f3839aa5e2e0) をオーバーライドします\)。|  
|`CPaneDialog::OnWindowPosChanging`|[WM\_WINDOWPOSCHANGING](http://msdn.microsoft.com/library/windows/desktop/ms632653) メッセージを処理します   \([CWnd::OnWindowPosChanging](../Topic/CWnd::OnWindowPosChanging.md) を再定義します\)。|  
|[CPaneDialog::SetOccDialogInfo](../Topic/CPaneDialog::SetOccDialogInfo.md)|OLE コントロール コンテナーであるダイアログ ボックスのテンプレートを指定します。|  
  
## 解説  
 `CPaneDialog` オブジェクトは 2 ステップで構築します。  まず、コードでオブジェクトを構築します。  次に、[CPaneDialog::Create](../Topic/CPaneDialog::Create.md) を呼び出します。  有効なリソース テンプレート名またはテンプレート ID を指定し、親ウィンドウへのポインターを渡す必要があります。  そのようにしないと、作成処理に失敗します。  ダイアログ ボックスには、WS\_CHILD および WS\_VISIBLE スタイルを指定する必要があります。  WS\_CLIPCHILDREN および WS\_CLIPSIBLINGS スタイルも指定することをお勧めします。  詳細については、「[ウィンドウ スタイル](../Topic/Window%20Styles.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../Topic/CDockablePane%20Class.md)  
  
 [CPaneDialog](../../mfc/reference/cpanedialog-class.md)  
  
## 必要条件  
 **ヘッダー :** afxpanedialog.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CDockablePane クラス](../Topic/CDockablePane%20Class.md)   
 [ウィンドウ スタイル](../Topic/Window%20Styles.md)