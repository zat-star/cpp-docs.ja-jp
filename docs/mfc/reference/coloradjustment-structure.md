---
title: "COLORADJUSTMENT 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- COLORADJUSTMENT
dev_langs:
- C++
helpviewer_keywords:
- COLORADJUSTMENT structure
ms.assetid: 67fc4e63-0e0e-4fcb-8c45-aa5ebfefa013
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 7f88877fa009abf4e811ba0a99b7e0e1683f998a
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="coloradjustment-structure"></a>COLORADJUSTMENT 構造体
`COLORADJUSTMENT`構造体は、Windows で使用される色の調整値を定義`StretchBlt`と**StretchDIBits**関数と、`StretchBlt`モードは**ハーフトーン**します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct  tagCOLORADJUSTMENT {    /* ca */  
    WORD caSize;  
    WORD caFlags;  
    WORD caIlluminantIndex;  
    WORD caRedGamma;  
    WORD caGreenGamma;  
    WORD caBlueGamma;  
    WORD caReferenceBlack;  
    WORD caReferenceWhite;  
    SHORT caContrast;  
    SHORT caBrightness;  
    SHORT caColorfulness;  
    SHORT caRedGreenTint;  
} COLORADJUSTMENT;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *caSize*  
 構造体のサイズをバイトで指定します。  
  
 *caFlags*  
 出力のイメージを準備する方法を指定します。 このメンバーを設定することができます**NULL**または、次の値の任意の組み合わせ。  
  
- **CA_NEGATIVE**元のイメージの負の値を表示することを指定します。  
  
- **CA_LOG_FILTER**最終的な出力色の濃さを対数関数が適用されることを指定します。 輝度が少なくなると、色コントラストが増加します。  
  
 *caIlluminantIndex*  
 イメージ オブジェクトが表示される光の光源の輝度を指定します。 このメンバーは、次の値のいずれかに設定できます。  
  
- **ILLUMINANT_EQUAL_ENERGY**  
  
- **ILLUMINANT_A**  
  
- **ILLUMINANT_B**  
  
- **ILLUMINANT_C**  
  
- **ILLUMINANT_D50**  
  
- **ILLUMINANT_D55**  
  
- **ILLUMINANT_D65**  
  
- **ILLUMINANT_D75**  
  
- **ILLUMINANT_F2**  
  
- **ILLUMINANT_TURNGSTEN**  
  
- **ILLUMINANT_DAYLIGHT**  
  
- **ILLUMINANT_FLUORESCENT**  
  
- **ILLUMINANT_NTSC**  
  
 *caRedGamma*  
 ソースの色の赤の原色の n 番目ガンマ補正値を指定します。 値は、2,500 から 65,000 の範囲内で指定する必要があります。 10,000 の値は、ガンマ補正がないことを意味します。  
  
 *caGreenGamma*  
 ソースの色の緑の原色の n 番目ガンマ補正値を指定します。 値は、2,500 から 65,000 の範囲内で指定する必要があります。 10,000 の値は、ガンマ補正がないことを意味します。  
  
 *caBlueGamma*  
 ソースの色の青の原色の n 番目ガンマ補正値を指定します。 値は、2,500 から 65,000 の範囲内で指定する必要があります。 10,000 の値は、ガンマ補正がないことを意味します。  
  
 *caReferenceBlack*  
 ソース カラーに対して黒の参照を指定します。 これよりも暗い色は黒として扱われます。 値は、0 ~ 4,000 の範囲でなければなりません。  
  
 *caReferenceWhite*  
 ソース カラーの白の参照を指定します。 これよりも明るい色は白として扱われます。 値は 6,000 から 10,000 の範囲でなければなりません。  
  
 *caContrast*  
 ソース オブジェクトに適用されるコントラストの量を指定します。 値は、100 ~-100 の範囲でなければなりません。 値 0 はコントラストの調整がないことを意味します。  
  
 *caBrightness*  
 ソース オブジェクトに適用される明るさを指定します。 値は、100 ~-100 の範囲でなければなりません。 値 0 は、明るさの調整がないことを意味します。  
  
 *caColorfulness*  
 ソース オブジェクトに適用される彩度の量を指定します。 値は、100 ~-100 の範囲でなければなりません。 値 0 は、彩度の調整がないことを意味します。  
  
 *caRedGreenTint*  
 ソース オブジェクトに適用する赤または緑の濃淡の調整の量を指定します。 値は、100 ~-100 の範囲でなければなりません。 正の数値が赤に調整し、負の数値が緑に調整します。 0 は濃淡の補正を意味します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** wingdi.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetColorAdjustment](../../mfc/reference/cdc-class.md#getcoloradjustment)



