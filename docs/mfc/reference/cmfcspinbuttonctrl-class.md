---
title: "CMFCSpinButtonCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCSpinButtonCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCSpinButtonCtrl クラス"
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CMFCSpinButtonCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCSpinButtonCtrl` クラスは、スピン ボタン コントロールを描画するビジュアル マネージャーをサポートします。  
  
## 構文  
  
```  
class CMFCSpinButtonCtrl : public CSpinButtonCtrl  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|既定のコンストラクターです。|  
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCSpinButtonCtrl::OnDraw](../Topic/CMFCSpinButtonCtrl::OnDraw.md)|現在のスピン ボタン コントロールを再描画します。|  
  
## 解説  
 ビジュアル マネージャーを使用してアプリケーション内にスピン ボタン コントロールを描画するには、`CSpinButtonCtrl` クラスのすべてのインスタンスを `CMFCSpinButtonCtrl` クラスで置き換えます。  
  
## 使用例  
 次の例は、`CMFCSpinButtonCtrl` クラスのオブジェクトを作成し、その `Create` メソッドを使用する方法について説明しています。  
  
 [!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/CPP/cmfcspinbuttonctrl-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)  
  
 [CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)  
  
## 必要条件  
 **ヘッダー :** afxspinbuttonctrl.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCVisualManager クラス](../../mfc/reference/cmfcvisualmanager-class.md)