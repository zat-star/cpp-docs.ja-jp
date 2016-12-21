---
title: "CDocItem クラス | Microsoft Docs"
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
  - "CDocItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDocItem クラス"
  - "クライアント ドキュメント アイテム"
  - "コンテナー ドキュメント アイテム"
  - "ドキュメント アイテム"
  - "項目, ドキュメント"
  - "OLE ドキュメント, 項目"
  - "サーバー ドキュメント"
  - "サーバー ドキュメント, ドキュメント アイテム"
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDocItem クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ドキュメント アイテムの基本クラスであり、ドキュメント データのコンポーネントです。  
  
## 構文  
  
```  
class CDocItem : public CCmdTarget  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDocItem::GetDocument](../Topic/CDocItem::GetDocument.md)|項目を含むドキュメントを返します。|  
|[CDocItem::IsBlank](../Topic/CDocItem::IsBlank.md)|項目が情報を含めるかどうかを決定します。|  
  
## 解説  
 `CDocItem` のオブジェクトがクライアントとサーバーの両方のドキュメントの OLE アイテムを表すために使用されます。  
  
 詳細については、" " [コンテナー: コンテナーの実装](../../mfc/containers-implementing-a-container.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `CDocItem`  
  
## 必要条件  
 **Header:** afxole.h  
  
## 参照  
 [CCmdTarget クラス](../Topic/CCmdTarget%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDocument クラス](../../mfc/reference/coledocument-class.md)   
 [COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)   
 [COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)