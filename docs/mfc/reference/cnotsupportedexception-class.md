---
title: "CNotSupportedException クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CNotSupportedException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNotSupportedException クラス"
  - "例外, サポート外"
  - " サポートされない機能"
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CNotSupportedException クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

サポートされていない機能を要求した結果として起こる例外を表します。  
  
## 構文  
  
```  
class CNotSupportedException : public CSimpleException  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CNotSupportedException::CNotSupportedException](../Topic/CNotSupportedException::CNotSupportedException.md)|`CNotSupportedException` オブジェクトを構築します。|  
  
## 解説  
 そのほかの資格はしたりはできません。  
  
 `CNotSupportedException` の使い方の詳細については、「[例外処理 \(MFC\)](../../mfc/exception-handling-in-mfc.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CNotSupportedException`  
  
## 必要条件  
 **ヘッダー:** afx.h  
  
## 参照  
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)