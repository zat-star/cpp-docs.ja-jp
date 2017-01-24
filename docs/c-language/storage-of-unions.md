---
title: "共用体の格納 | Microsoft Docs"
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
  - "ストレージ, union"
  - "union キーワード [C]"
  - "union キーワード [C], ストレージ"
ms.assetid: b33d246a-8d20-41c4-89b2-ab05f1428792
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 共用体の格納
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

共用体変数に関連付けられたストレージは共用体の最大メンバーに必要なストレージです。  小さいメンバーが格納されると、共有体変数に未使用のメモリ領域が含まれる場合があります。  すべてのメンバーは、同じメモリ空間に格納され、同じアドレスで開始されます。  格納されている値は、値が別のメンバーに割り当てられるたびに上書きされます。  次に例を示します。  
  
```  
union         /* Defines a union named x */  
{  
    char *a, b;  
    float f[20];  
} x;  
```  
  
 `x` 共有体のメンバーは、宣言の順番に、`char` 値へのポインター、`char` 値、**float** 値の配列です。  `x` に対して割り当てられたストレージは、`f` が共用体の最長メンバーであるため、20 要素の配列 `f` に必要なストレージです。  タグが共用体に関連付けられていないため、型は名前がないか "匿名" です。  
  
## 参照  
 [共用体の宣言](../c-language/union-declarations.md)