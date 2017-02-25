---
title: "INVOKE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Invoke"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "INVOKE directive"
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# INVOKE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

言語の標準呼び出し規約に従ってスタックまたは登録を引数  *式*  で指定されたアドレスでプロシージャを呼び出します。  
  
## 構文  
  
```  
  
INVOKE   
expression [[, arguments]]  
```  
  
## 解説  
 プロシージャに渡す引数は式はレジスタのペアまたはアドレス式 \(`ADDR` を指定する式\) である場合があります。  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)