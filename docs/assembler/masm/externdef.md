---
title: "EXTERNDEF | Microsoft Docs"
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
  - "EXTERNDEF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EXTERNDEF directive"
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# EXTERNDEF
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

型が `type` の  *名前と*  呼ばれる一つ以上の外部変数ラベルまたはシンボルを定義します。  
  
## 構文  
  
```  
  
EXTERNDEF [[langtype]] name:type [[, [[langtype]] name:type]]...  
```  
  
## 解説  
 *名前が*  モジュールで定義されている場合[パブリック](../Topic/PUBLIC%20\(MASM\).md) として扱われます。   *名前が*  モジュールで参照されている場合[外部](../../assembler/masm/extern-masm.md) として扱われます。   *名前が*  参照する場合は無視されます。  `type` は [abs](../../assembler/masm/operator-abs.md) でもかまいません定数として  *名前を*  インポートします。  通常使用されるファイルを追加します。  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)