---
title: ".CODE | Microsoft Docs"
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
  - ".CODE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".CODE directive"
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .CODE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[.MODEL](../../assembler/masm/dot-model.md) を使用するとコード セグメントの開始を示します。  
  
## 構文  
  
```  
.CODE [[name]]  
```  
  
#### パラメーター  
  
|パラメーター|Description|  
|------------|-----------------|  
|`name`|コード セグメントの名前を指定する省略可能なパラメーター。  既定の名前が小さく大少なくフラット [モデル](../../assembler/masm/dot-model.md) の \_TEXT です。  既定の名前は他のモデルの *modulename* の \_TEXT です。|  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)   
 [.DATA](../../assembler/masm/dot-data.md)