---
title: "CMFCPropertyGridToolTipCtrl クラス | Microsoft Docs"
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
  - "CMFCPropertyGridToolTipCtrl::PreTranslateMessage"
  - "~CMFCPropertyGridToolTipCtrl"
  - "PreTranslateMessage"
  - "CMFCPropertyGridToolTipCtrl.~CMFCPropertyGridToolTipCtrl"
  - "CMFCPropertyGridToolTipCtrl"
  - "CMFCPropertyGridToolTipCtrl.PreTranslateMessage"
  - "CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~CMFCPropertyGridToolTipCtrl デストラクター"
  - "CMFCPropertyGridToolTipCtrl クラス"
  - "CMFCPropertyGridToolTipCtrl クラス, デストラクター"
  - "PreTranslateMessage メソッド"
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCPropertyGridToolTipCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)がツールヒントを表示するために使用するツールヒント コントロールを実装します。  
  
## 構文  
  
```  
class CMFCPropertyGridToolTipCtrl : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl](../Topic/CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl.md)|`CMFCPropertyGridToolTipCtrl` オブジェクトを構築します。|  
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|デストラクターです。|  
  
### パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCPropertyGridToolTipCtrl::Create](../Topic/CMFCPropertyGridToolTipCtrl::Create.md)|ツールヒント コントロールのウィンドウを作成します。|  
|[CMFCPropertyGridToolTipCtrl::Deactivate](../Topic/CMFCPropertyGridToolTipCtrl::Deactivate.md)|ツールヒント コントロールを非アクティブおよび非表示にします。|  
|[CMFCPropertyGridToolTipCtrl::GetLastRect](../Topic/CMFCPropertyGridToolTipCtrl::GetLastRect.md)|ツールヒント コントロールの最後の位置を示す座標を返します。|  
|[CMFCPropertyGridToolTipCtrl::Hide](../Topic/CMFCPropertyGridToolTipCtrl::Hide.md)|ツールヒント コントロールを非表示にします。|  
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|ウィンドウ メッセージが Windows 関数の [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) および [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) にディスパッチされる前に、メッセージを変換するために [CWinApp](../../mfc/reference/cwinapp-class.md) クラスによって使用されます   \([CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md) をオーバーライドします\)。|  
|[CMFCPropertyGridToolTipCtrl::SetTextMargin](../Topic/CMFCPropertyGridToolTipCtrl::SetTextMargin.md)|ツールヒント テキストとツールヒント ウィンドウの境界線との間隔を指定します。|  
|[CMFCPropertyGridToolTipCtrl::Track](../Topic/CMFCPropertyGridToolTipCtrl::Track.md)|ツールヒント コントロールを表示します。|  
  
## 解説  
 ツールヒントは、ポインターをプロパティ名に重ねると表示されます。  [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md) は、ユーザーにとってわかりやすいようにツールヒントを表示します。  通常、ツールヒントの位置はポインターの位置によって決まります。  このクラスを使用すると、ツールヒントはプロパティ名の上に本来のプロパティ拡張のように表示されるので、プロパティ名は完全に表示されます。  
  
 MFC は自動的にこのコントロールを作成し、それを [CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)内で使用します。  
  
## 使用例  
 次の例は、`CMFCPropertyGridToolTipCtrl` クラスのオブジェクトを構築する方法、およびツールヒント コントロールを表示する方法について説明しています。  
  
 [!code-cpp[NVC_MFC_RibbonApp#23](../../mfc/reference/codesnippet/CPP/cmfcpropertygridtooltipctrl-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)  
  
## 必要条件  
 **ヘッダー :** afxpropertygridtooltipctrl.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)