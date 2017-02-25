---
title: "unsupported_os クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::unsupported_os"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unsupported_os クラス"
ms.assetid: 6fa57636-341b-4b51-84cc-261d283ff736
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# unsupported_os クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

このクラスは、サポート外のオペレーティング システムが使用された場合にスローされる例外を表します。  
  
## 構文  
  
```  
class unsupported_os : public std::exception;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[unsupported\_os::unsupported\_os コンストラクター](../Topic/unsupported_os::unsupported_os%20Constructor.md)|オーバーロードされます。  `unsupported_os` オブジェクトを構築します。|  
  
## 継承階層  
 `exception`  
  
 `unsupported_os`  
  
## 必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)