---
title: "ABC 構造体 | Microsoft Docs"
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
  - "ABC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ABC 構造体"
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ABC 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**ABC** 構造体は、TrueType フォントで文字の幅が含まれます。  
  
## 構文  
  
```  
  
      typedef struct _ABC { /* abc */  
   int abcA;  
   UINT abcB;  
   int abcC;  
} ABC;  
```  
  
#### パラメーター  
 *abcA*  
 文字の間隔を指定します。  A の距離は、文字グリフを描画する前に現在位置に追加する間隔です。  
  
 *abcB*  
 文字の B の間隔を指定します。  B の距離は、文字グリフの描画した部分の幅です。  
  
 *abcC*  
 文字の C の間隔を指定します。  C の距離は、文字グリフの右側に空白を提供する現在位置に追加する間隔です。  
  
## 解説  
 文字の幅は A、B、および C の領域の合計です。  underhangs または張り出し部分を示すために、A または C の領域が負のです。  
  
## 必要条件  
 **ヘッダー :** wingdi.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../Topic/CDC::GetCharABCWidths.md)