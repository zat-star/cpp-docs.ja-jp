---
title: "CMemoryException クラス | Microsoft Docs"
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
  - "CMemoryException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ 例外処理, メモリ"
  - "CMemoryException クラス"
  - "例外, メモリの型"
  - "メモリ例外"
  - "メモリ, 例外処理"
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMemoryException クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

メモリ不足例外条件を表します。  
  
## 構文  
  
```  
class CMemoryException : public CSimpleException  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMemoryException::CMemoryException](../Topic/CMemoryException::CMemoryException.md)|`CMemoryException` オブジェクトを構築します。|  
  
## 解説  
 そのほかの資格はしたりはできません。  メモリ不足の例外が **new**によって自動的にスローされます。  、`malloc`を使用して、独自のメモリ関数を作成する場合など、メモリ不足の例外をスローすることがあります。  
  
 `CMemoryException`の詳細については、" " [例外処理 \(MFC\)](../../mfc/exception-handling-in-mfc.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CMemoryException`  
  
## 必要条件  
 **ヘッダー:** afx.h  
  
## 参照  
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)