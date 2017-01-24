---
title: "COLORADJUSTMENT 構造体 | Microsoft Docs"
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
  - "COLORADJUSTMENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLORADJUSTMENT 構造体"
ms.assetid: 67fc4e63-0e0e-4fcb-8c45-aa5ebfefa013
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COLORADJUSTMENT 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`COLORADJUSTMENT` 構造体は `StretchBlt` モードが **HALFTONE**の場合は、Windows `StretchBlt` と **StretchDIBits** 関数が使用するカラー補正値を定義します。  
  
## 構文  
  
```  
  
      typedef struct  tagCOLORADJUSTMENT {    /* ca */  
    WORD  caSize;  
    WORD  caFlags;  
    WORD  caIlluminantIndex;  
    WORD  caRedGamma;  
    WORD  caGreenGamma;  
    WORD  caBlueGamma;  
    WORD  caReferenceBlack;  
    WORD  caReferenceWhite;  
    SHORT caContrast;  
    SHORT caBrightness;  
    SHORT caColorfulness;  
    SHORT caRedGreenTint;  
} COLORADJUSTMENT;  
```  
  
#### パラメーター  
 *caSize*  
 構造体のサイズをバイト単位で指定します。  
  
 *caFlags*  
 出力イメージをどのように作成するかを指定します。  このメンバーは、次の値の **NULL** または組み合わせに設定できます。:  
  
-   **CA\_NEGATIVE**は元のイメージの否定を表示する必要があることを指定します。  
  
-   **CA\_LOG\_FILTER**は対数関数が出力色の最終的な密度に適用されることを指定します。  これは、光が少ないとき色のコントラストが向上します。  
  
 *caIlluminantIndex*  
 イメージ オブジェクトを示す光源のライトを指定します。  このメンバーは、次の値のいずれか 1 つがに設定できます。:  
  
-   **ILLUMINANT\_EQUAL\_ENERGY**  
  
-   **ILLUMINANT\_A**  
  
-   **ILLUMINANT\_B**  
  
-   **ILLUMINANT\_C**  
  
-   **ILLUMINANT\_D50**  
  
-   **ILLUMINANT\_D55**  
  
-   **ILLUMINANT\_D65**  
  
-   **ILLUMINANT\_D75**  
  
-   **ILLUMINANT\_F2**  
  
-   **ILLUMINANT\_TURNGSTEN**  
  
-   **ILLUMINANT\_DAYLIGHT**  
  
-   **ILLUMINANT\_FLUORESCENT**  
  
-   **ILLUMINANT\_NTSC**  
  
 *caRedGamma*  
 ソース カラーの赤の主に n 次ガンマ補正値を指定します。  値は、2,500 ~ 65,000 の範囲で指定します。  値 10,000 はガンマ補正されません。  
  
 *caGreenGamma*  
 ソース カラーの主要な緑に n 次ガンマ補正値を指定します。  値は、2,500 ~ 65,000 の範囲で指定します。  値 10,000 はガンマ補正されません。  
  
 *caBlueGamma*  
 ソース カラーの主要な青で n 次ガンマ補正値を指定します。  値は、2,500 ~ 65,000 の範囲で指定します。  値 10,000 はガンマ補正されません。  
  
 *caReferenceBlack*  
 ソース カラーに黒い参照を指定します。  これにより、暗い色が黒として扱われます。  値は、0 ~ 4,000 の範囲で指定します。  
  
 *caReferenceWhite*  
 ソース カラーに白い参照を指定します。  これよりライトの色が白として扱われます。  値は、6,000 ~ 10,000 の範囲で指定します。  
  
 *caContrast*  
 ソース オブジェクトに適用される一方の量を指定します。  値は、\-100 ~ 100 の範囲で指定します。  値が 0 の場合、これは意味しません。  
  
 *caBrightness*  
 ソース オブジェクトに適用される明るさの量を指定します。  値は、\-100 ~ 100 の範囲で指定します。  0 という値は、明るさの調整を意味しません。  
  
 *caColorfulness*  
 ソース オブジェクトに適用する colorfulness の量を指定します。  値は、\-100 ~ 100 の範囲で指定します。  0 という値は colorfulness の調整を意味しません。  
  
 *caRedGreenTint*  
 ソース オブジェクトに適用される赤色または緑色の色合いの調整の量を指定します。  値は、\-100 ~ 100 の範囲で指定します。  正数は赤の方向に調整し、負数は緑の方向に調整します。  0 は色合いの調整を意味しません。  
  
## 必要条件  
 **ヘッダー :** wingdi.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetColorAdjustment](../Topic/CDC::GetColorAdjustment.md)