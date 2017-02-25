---
title: "CArchiveException クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CArchiveException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アーカイブの例外 [C++]"
  - "CArchiveException クラス"
  - "例外 [C++], アーカイブ"
  - "例外 [C++], シリアル化"
  - "シリアル化 [C++], 例外"
ms.assetid: da31a127-e86c-41d1-b0b6-bed0865b1b49
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CArchiveException クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

シリアル化例外条件を表します  
  
## 構文  
  
```  
class CArchiveException : public CException  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CArchiveException::CArchiveException](../Topic/CArchiveException::CArchiveException.md)|`CArchiveException` オブジェクトを構築します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CArchiveException::m\_cause](../Topic/CArchiveException::m_cause.md)|例外の原因を示します。|  
|[CArchiveException::m\_strFileName](../Topic/CArchiveException::m_strFileName.md)|この例外条件のファイルの名前を指定します。|  
  
## 解説  
 `CArchiveException` のクラスは、例外の原因を示すパブリック データ メンバーが含まれています。  
  
 `CArchiveException` のオブジェクトがスローされた中の [CArchive](../../mfc/reference/carchive-class.md) のメンバー関数、構築。  **CATCH** の式のスコープ内でこれらのオブジェクトにアクセスできます。  原因コードは、オペレーティング システムに依存しません。  例外処理に関する詳細については、[例外処理 \(MFC\)](../../mfc/exception-handling-in-mfc.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CArchiveException`  
  
## 必要条件  
 **ヘッダー:** afx.h  
  
## 参照  
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CArchive クラス](../../mfc/reference/carchive-class.md)   
 [AfxThrowArchiveException](../Topic/AfxThrowArchiveException.md)   
 [例外処理](../../mfc/reference/exception-processing.md)