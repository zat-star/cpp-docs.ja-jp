---
title: "push_macro | Microsoft Docs"
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
  - "vc-pragma.push_macro"
  - "push_macro_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "プラグマ, push_macro"
  - "push_macro プラグマ"
ms.assetid: ac89efc9-afd1-4dfe-bfd1-497229b3e81d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# push_macro
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このマクロのスタックの上部にある *macro\_name* マクロの値を保存します。  
  
## 構文  
  
```  
  
#pragma push_macro("  
macro_name  
")  
  
```  
  
## 解説  
 *macro\_name* の値を **pop\_macro** で取得できます。  
  
 例については、「[pop\_macro](../Topic/pop_macro.md)」を参照してください。  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)