---
title: "XFORM 構造体 | Microsoft Docs"
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
  - "XFORM"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "XFORM 構造体"
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# XFORM 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`XFORM` 構造体には、次のフォームがあります:  
  
## 構文  
  
```  
  
      typedef struct  tagXFORM {  /* xfrm */  
    FLOAT eM11;  
    FLOAT eM12;  
    FLOAT eM21;  
    FLOAT eM22;  
    FLOAT eDx;  
    FLOAT eDy;  
} XFORM;  
```  
  
## 解説  
 `XFORM` 構造体はワールド空間ページ空間への変換を指定します。  **eDx** と **eDy** のメンバーは、水平方向と垂直方向の変換の要素をそれぞれ指定します。  他のメンバーがどのように使用されるかを次の表に示します。操作によって:  
  
|操作|eM11|eM12|eM21|eM22|  
|--------|----------|----------|----------|----------|  
|`Rotation`|回転の角度のコサイン。|回転の角度のサイン。|回転の角度のサイン負のな|回転の角度のコサイン。|  
|**スケーリング**|水平方向のスケーリング コンポーネント|Nothing|Nothing|垂直方向のスケーリング コンポーネント|  
|**傾斜**|Nothing|水平方向の比率定数|垂直方向の比率定数|Nothing|  
|**リフレクション**|水平方向のリフレクションのコンポーネント|Nothing|Nothing|垂直方向のリフレクションのコンポーネント|  
  
## 必要条件  
 **ヘッダー :** wingdi.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../Topic/CRgn::CreateFromData.md)