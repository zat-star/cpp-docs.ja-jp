---
title: "AsyncResultType 列挙型 | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncResultType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsyncResultType 列挙型"
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsyncResultType 列挙型
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

GetResults\(\) のメソッドから返される結果の種類を指定します。  
  
## 構文  
  
```  
enum AsyncResultType;  
```  
  
## メンバー  
  
### 値  
  
|名前|説明|  
|--------|--------|  
|`MultipleResults`|開始状態の間で漸進的に示す、および以前に Close\(\) が呼び出された一連の複数の結果。|  
|`SingleResult`|完全なイベントが発生した後に表示される単一の結果。|  
  
## 必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)