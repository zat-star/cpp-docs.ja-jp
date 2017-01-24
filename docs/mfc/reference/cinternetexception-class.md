---
title: "CInternetException クラス | Microsoft Docs"
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
  - "CInternetException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInternetException クラス"
  - "例外処理, インターネットの操作"
  - "例外, インターネット"
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
caps.latest.revision: 22
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CInternetException クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

インターネット操作に関する例外条件を表します。  
  
## 構文  
  
```  
class CInternetException : public CException  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CInternetException::CInternetException](../Topic/CInternetException::CInternetException.md)|`CInternetException` オブジェクトを構築します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CInternetException::m\_dwContext](../Topic/CInternetException::m_dwContext.md)|コンテキストの値は例外を発生させた操作に関連付けられています。|  
|[CInternetException::m\_dwError](../Topic/CInternetException::m_dwError.md)|例外の原因となったエラー。|  
  
## 解説  
 `CInternetException` のクラスは 2 人のパブリック データ メンバーが含まれています: 1 つが、エラー コードが例外に関連付けられた保持し、他のは、エラーに関連付けられているインターネット アプリケーションのコンテキスト ID を保持します。  
  
 インターネット アプリケーションのコンテキストの識別子の詳細については、" " [WinInet するインターネットのプログラミング](../../mfc/win32-internet-extensions-wininet.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CInternetException`  
  
## 必要条件  
 **ヘッダー:** afxinet.h  
  
## 参照  
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)