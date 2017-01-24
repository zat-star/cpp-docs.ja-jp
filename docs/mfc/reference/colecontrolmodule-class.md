---
title: "COleControlModule クラス | Microsoft Docs"
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
  - "COleControlModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleControlModule クラス"
  - "コントロール モジュール"
  - "MFC ActiveX コントロール, OLE コントロール モジュール"
  - "OLE コントロール モジュール"
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleControlModule クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE コントロール モジュール オブジェクトを派生するための基本クラスです。  
  
## 構文  
  
```  
class COleControlModule : public CWinApp  
```  
  
## 解説  
 このクラスは、コントロールのモジュールを初期化するためにメンバー関数を提供します。  Microsoft Foundation のクラスを使用する各 OLE コントロール モジュールは `COleControlModule`から派生した 1 種類のオブジェクトだけを含めることができます。  このオブジェクトは、他の C\+\+ のグローバル オブジェクトの構築時に生成されます。  `COleControlModule` 派生クラスのオブジェクトはグローバル レベルで宣言します。  
  
 `COleControlModule` のクラスの使用の詳細については、[CWinApp](../../mfc/reference/cwinapp-class.md) のクラスと [&#91;ActiveX コントロール&#93;](../../mfc/mfc-activex-controls.md)" "を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 `COleControlModule`  
  
## 必要条件  
 **Header:** afxctl.h  
  
## 参照  
 [MFC の TESTHELP サンプル](../../top/visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)