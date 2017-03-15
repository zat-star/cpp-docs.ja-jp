---
title: "ABCFLOAT 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ABCFLOAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ABCFLOAT 構造体"
ms.assetid: 338e7e15-9d2c-42d0-aa80-273acfde5cc5
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# ABCFLOAT 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`ABCFLOAT` 構造体はフォントの文字 \(A、B、および C の幅が含まれます。  
  
## 構文  
  
```  
  
      typedef struct _ABCFLOAT { /* abcf */  
   FLOAT abcfA;  
   FLOAT abcfB;  
   FLOAT abcfC;  
} ABCFLOAT;  
```  
  
#### パラメーター  
 *abcfA*  
 文字の間隔を指定します。  A の距離は、文字グリフを描画する前に現在位置に追加する間隔です。  
  
 *abcfB*  
 文字の B の間隔を指定します。  B の距離は、文字グリフの描画した部分の幅です。  
  
 *abcfC*  
 文字の C の間隔を指定します。  C の距離は、文字グリフの右側に空白を提供する現在位置に追加する間隔です。  
  
## 解説  
 A、B、および C の幅は、フォントのベース ラインに沿って測定されます。  文字のインクリメント \(幅\) は A、B、および C の領域の合計です。  underhangs または張り出し部分を示すために、A または C の領域が負のです。  
  
## 必要条件  
 **ヘッダー :** wingdi.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../Topic/CDC::GetCharABCWidths.md)