---
title: "queuing_mode 列挙型 | Microsoft Docs"
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
  - "amprt/Concurrency::queuing_mode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "queuing_mode 列挙型"
ms.assetid: 8c641054-906d-40b3-bbb4-f62af9356a14
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# queuing_mode 列挙型
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

アクセラレータでサポートされているキュー モードを指定します。  
  
## 構文  
  
```  
enum queuing_mode;  
```  
  
## メンバー  
  
### 値  
  
|名前|説明|  
|--------|--------|  
|`queuing_mode_immediate`|任意のコマンド \([parallel\_for\_each 関数 \(C\+\+ AMP\)](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) など\) が呼び出し元に戻るとすぐに対応するアクセラレータ デバイスに送信されることを指定するキュー モード。|  
|`queuing_mode_automatic`|[accelerator\_view](../Topic/accelerator_view%20Class.md) オブジェクトに対応するコマンド キューでキューに入れられるコマンドを指定するキュー モード。  コマンドは、[accelerator\_view::flush](../Topic/accelerator_view::flush%20Method.md) が呼び出されたときに、デバイスに送信されます。|  
  
## 必要条件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** Concurrency  
  
## 参照  
 [Concurrency 名前空間 \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)