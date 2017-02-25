---
title: "CMFCDragFrameImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCDragFrameImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDragFrameImpl クラス"
ms.assetid: 500cd824-8188-43c2-8754-b7bb46b5648a
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CMFCDragFrameImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCDragFrameImpl` クラスは、標準ドッキング モードでユーザーがペインをドラッグするときに表示されるドラッグ四角形を描画します。  
  
## 構文  
  
```  
class CMFCDragFrameImpl  
```  
  
## 解説  
 このクラスのオブジェクトは、各 [CPane クラス](../../mfc/reference/cpane-class.md) オブジェクトに埋め込まれます。  したがって、`CanFloat` メソッドを使用する各ペインには、ユーザーがドラッグするとドラッグ四角形が表示されます。  
  
 [AFX\_GLOBAL\_DATA::m\_nDragFrameThicknessFloat](../Topic/AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat.md) と [AFX\_GLOBAL\_DATA::m\_nDragFrameThicknessDock](../Topic/AFX_GLOBAL_DATA::m_nDragFrameThicknessDock.md) を使用して、ドラッグ四角形の太さを制御できます。  
  
## 継承階層  
 [CMFCDragFrameImpl](../../mfc/reference/cmfcdragframeimpl-class.md)  
  
## 必要条件  
 **ヘッダー :** afxdragframeimpl.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CPane クラス](../../mfc/reference/cpane-class.md)   
 [AFX\_GLOBAL\_DATA::m\_nDragFrameThicknessFloat](../Topic/AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat.md)   
 [AFX\_GLOBAL\_DATA::m\_nDragFrameThicknessDock](../Topic/AFX_GLOBAL_DATA::m_nDragFrameThicknessDock.md)