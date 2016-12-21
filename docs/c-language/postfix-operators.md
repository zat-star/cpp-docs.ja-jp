---
title: "後置演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "演算子 [C], 後置"
  - "後置演算子"
ms.assetid: 76260011-1624-484e-8bef-72ae7ab556cc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 後置演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

後置演算子は、式の評価で優先順位が最高位 \(最も強力なバインディング\) になります。  
  
## 構文  
 *postfix\-expression*:  
 *primary\-expression*  
  
 *postfix\-expression*  **\[**  *expression*  **\]**  
  
 *postfix\-expression*  **\(**  *argument\-expression\-list*  opt **\)**  
  
 *postfix\-expression*  **.**  *identifier*  
  
 *postfix\-expression*  **–\>**  *identifier*  
  
 *postfix\-expression*  **\+\+**  
  
 *postfix\-expression*  **––**  
  
 この優先順位レベルの演算子は、配列の添字、関数呼び出し、構造体\/共用体メンバー、および後置インクリメント\/デクリメント演算子です。  
  
## 参照  
 [C 演算子](../c-language/c-operators.md)