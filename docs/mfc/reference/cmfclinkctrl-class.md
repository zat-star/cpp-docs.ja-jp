---
title: "CMFCLinkCtrl クラス | Microsoft Docs"
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
  - "CMFCLinkCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCLinkCtrl クラス"
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
caps.latest.revision: 27
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCLinkCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCLinkCtrl` クラスはボタンをハイパーリンクとして表示し、ボタンがクリックされるとリンク先を呼び出します。  
  
## 構文  
  
```  
class CMFCLinkCtrl : public CMFCButton  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCLinkCtrl::SetURL](../Topic/CMFCLinkCtrl::SetURL.md)|指定した URL はボタン テキストとして表示されます。|  
|[CMFCLinkCtrl::SetURLPrefix](../Topic/CMFCLinkCtrl::SetURLPrefix.md)|URL の暗黙のプロトコル \(たとえば、"http:"\) を設定します。|  
|[CMFCLinkCtrl::SizeToContent](../Topic/CMFCLinkCtrl::SizeToContent.md)|ボタン テキストまたはビットマップを格納するボタンのサイズを変更します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCLinkCtrl::OnDrawFocusRect](../Topic/CMFCLinkCtrl::OnDrawFocusRect.md)|ボタンのフォーカスを示す四角形が描画される前に、フレームワークによって呼び出されます。|  
  
## 解説  
 `CMFCLinkCtrl` クラスから派生したボタンをクリックすると、フレームワークはそのボタンの URL をパラメーターとして `ShellExecute` メソッドに渡します。  次に、`ShellExecute` メソッドは URL のターゲットを開きます。  
  
## 使用例  
 次の例は、`CMFCLinkCtrl` オブジェクトのサイズを設定する方法、および `CMFCLinkCtrl` オブジェクトに URL とツールヒントを設定する方法を説明しています。  この例では [新しいコントロールのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!CODE [NVC_MFC_NewControls#9](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#9)]  
[!CODE [NVC_MFC_NewControls#10](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#10)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)  
  
## 必要条件  
 **ヘッダー :** afxlinkctrl.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CLinkCtrl クラス](../../mfc/reference/clinkctrl-class.md)   
 [CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)