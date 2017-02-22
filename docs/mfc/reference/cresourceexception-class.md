---
title: "CResourceException クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CResourceException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CResourceException クラス"
  - "例外, リソース"
  - "リソース割り当て例外"
  - "リソース例外"
  - "リソース [C++], 割り当て"
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CResourceException クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows が要求されたリソースを見つけられないか、割り当てられないときに生成されます。  
  
## 構文  
  
```  
class CResourceException : public CSimpleException  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CResourceException::CResourceException](../Topic/CResourceException::CResourceException.md)|`CResourceException` オブジェクトを構築します。|  
  
## 解説  
 そのほかの資格はしたりはできません。  
  
 `CResourceException` の使い方の詳細については、「[例外処理 \(MFC\)](../../mfc/exception-handling-in-mfc.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CResourceException`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)