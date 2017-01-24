---
title: "unsupported_feature クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::unsupported_feature"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unsupported_feature クラス"
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# unsupported_feature クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

サポートされていない機能が使用される場合にスローされる例外です。  
  
## 構文  
  
```  
class unsupported_feature : public runtime_exception;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[unsupported\_feature::unsupported\_feature コンストラクター](../Topic/unsupported_feature::unsupported_feature%20Constructor.md)|`unsupported_feature` 例外の新しいインスタンスを構築します。|  
  
## 継承階層  
 `exception`  
  
 `runtime_exception`  
  
 `unsupported_feature`  
  
## 必要条件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** Concurrency  
  
## 参照  
 [Concurrency 名前空間 \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)