---
title: "LOGBRUSH 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LOGBRUSH
dev_langs:
- C++
helpviewer_keywords:
- LOGBRUSH structure
ms.assetid: 1bf96768-52c5-4444-9bb8-d41ba2e27e68
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: eea7caf6139fd43dd77163271701d170c7a744e2
ms.lasthandoff: 02/24/2017

---
# <a name="logbrush-structure"></a>LOGBRUSH 構造体
`LOGBRUSH`構造体は、スタイル、色、および物理的なブラシのパターンを定義します。 Windows が使用して[CreateBrushIndirect](http://msdn.microsoft.com/library/windows/desktop/dd183487)と[構造体](http://msdn.microsoft.com/library/windows/desktop/dd162705)関数です。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tag LOGBRUSH { /* lb */  
    UINT lbStyle;  
    COLORREF lbColor;  
    LONG lbHatch;  
} LOGBRUSH;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `lbStyle`  
 ブラシのスタイルを指定します。 `lbStyle`メンバーは、次のスタイルのいずれかを指定する必要があります。  
  
- **BS_DIBPATTERN**ブラシをデバイスに依存しないビットマップ (DIB) 仕様で定義されるパターンです。 場合`lbStyle`は**BS_DIBPATTERN**、 **lbHatch**メンバーには、パックされた DIB へのハンドルが含まれています。  
  
- **BS_DIBPATTERNPT**ブラシをデバイスに依存しないビットマップ (DIB) 仕様で定義されるパターンです。 場合`lbStyle`は**BS_DIBPATTERNPT**、 **lbHatch**メンバーには、パックされた DIB へのポインターが含まれています。  
  
- **BS_HATCHED**ハッチ ブラシ。  
  
- **BS_HOLLOW**白抜きのブラシ。  
  
- **BS_NULL**と同じ**BS_HOLLOW**します。  
  
- **BS_PATTERN**メモリ ビットマップで定義されるパターン ブラシ。  
  
- **BS_SOLID**ソリッド ブラシ。  
  
 `lbColor`  
 描画するブラシの色を指定します。 場合`lbStyle`は、 **BS_HOLLOW**または**BS_PATTERN**スタイル、 **lbColor**は無視されます。 場合`lbStyle`は**BS_DIBPATTERN**または**BS_DIBPATTERNBT**の下位ワード**lbColor**を指定するかどうか、 **bmiColors**のメンバー、 [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md)構造は、明示的な赤、緑、青 (RGB) の値またはインデックスを現在実現論理パレットに含まれています。 **LbColor**メンバーは、次の値のいずれかを指定する必要があります。  
  
- **DIB_PAL_COLORS**カラー テーブルは、現在実現論理パレットに 16 ビットのインデックスの配列で構成されています。  
  
- **DIB_RGB_COLORS**カラー テーブルには、リテラルの RGB 値が含まれています。  
  
 *lbHatch*  
 陰影のスタイルを指定します。 定義されているブラシのスタイルの意味は、`lbStyle`です。 場合`lbStyle`は**BS_DIBPATTERN**、 **lbHatch**メンバーには、パックされた DIB へのハンドルが含まれています。 場合`lbStyle`は**BS_DIBPATTERNPT**、 **lbHatch**メンバーには、パックされた DIB へのポインターが含まれています。 場合`lbStyle`は**BS_HATCHED**、 **lbHatch**メンバーは、陰影を作成するために使用する線の方向を指定します。 次の値のいずれかを指定できます。  
  
- `HS_BDIAGONAL`45 度の上位方向へ、左から右へハッチ  
  
- `HS_CROSS`水平および垂直方向の格子  
  
- `HS_DIAGCROSS`45 度格子  
  
- `HS_FDIAGONAL`45 度の下、左から右へハッチ  
  
- `HS_HORIZONTAL`水平方向の陰影  
  
- `HS_VERTICAL`垂直方向の陰影  
  
 場合`lbStyle`は**BS_PATTERN**、 **lbHatch**パターンを定義するビットマップへのハンドルします。 場合`lbStyle`は**BS_SOLID**または**BS_HOLLOW**、 **lbHatch**は無視されます。  
  
## <a name="remarks"></a>コメント  
 **LbColor**ハッチ ブラシの前景の色を制御、 [CDC::SetBkMode](../../mfc/reference/cdc-class.md#setbkmode)と[CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor)関数は、背景色を制御します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** wingdi.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)


