---
title: "CInvalidArgException クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CInvalidArgException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInvalidArgException クラス"
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CInvalidArgException クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、無効な引数の例外状態を表します。  
  
## 構文  
  
```  
  
class CInvalidArgException : public CSimpleException  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CInvalidArgException::CInvalidArgException](../Topic/CInvalidArgException::CInvalidArgException.md)|コンストラクターです。|  
  
## 解説  
 `CInvalidArgException` のオブジェクトが無効な引数の例外状態を表します。  
  
 例外処理の詳細については、" "および [CException クラス](../../mfc/reference/cexception-class.md)[例外処理 \(MFC\)](../../mfc/exception-handling-in-mfc.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CInvalidArgException`  
  
## 必要条件  
 **ヘッダー :** afx.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CSimpleException クラス](../../mfc/reference/csimpleexception-class.md)