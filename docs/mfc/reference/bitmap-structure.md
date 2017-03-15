---
title: "BITMAP 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BITMAP
dev_langs:
- C++
helpviewer_keywords:
- BITMAP structure
ms.assetid: 05d33b4d-7232-4643-a108-87dda8ff5f22
caps.latest.revision: 12
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
ms.openlocfilehash: cd7e63cfe9e7a0f2305ca5c3cd7c2571a080a718
ms.lasthandoff: 02/24/2017

---
# <a name="bitmap-structure"></a>BITMAP 構造体
**ビットマップ**構造体は、高さ、幅、カラー形式および論理ビットマップのビット値を定義**します。**  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagBITMAP {  /* bm */  
    int bmType;  
    int bmWidth;  
    int bmHeight;  
    int bmWidthBytes;  
    BYTE bmPlanes;  
    BYTE bmBitsPixel;  
    LPVOID bmBits;  
} BITMAP;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *bmType*  
 ビットマップの種類を指定します。 論理ビットマップの場合、このメンバーは 0 であることが必要です。  
  
 *bmWidth*  
 ビットマップの幅 (ピクセル単位) を指定します。 幅は 0 より大きい値でなければなりません。  
  
 *bmHeight*  
 ラスター行数を使用してビットマップの高さを指定します。 高さは 0 より大きい値でなければなりません。  
  
 *bmWidthBytes*  
 各ラスター行に含まれるバイト数を指定します。 グラフィック デバイス インターフェイス (GDI) は、ビットマップ形式のビット値が整数値 (2 バイト) の配列を形成することを想定するため、この値は偶数であることが必要です。 つまり、 **bmWidthBytes** \* 8 は、ときに得られる値以上の 16 の倍数である必要があります、 **bmWidth**メンバーを掛けた、 **bmBitsPixel**メンバーです。  
  
 *bmPlanes*  
 ビットマップ内でのカラー プレーンの数を指定します。  
  
 *bmBitsPixel*  
 ピクセルを定義するために必要とされる各プレーンで、隣接するカラー ビット数を指定します。  
  
 *bmBits*  
 ビットマップのビット値が配置されている位置へのポインター。 **BmBits**メンバーは 1 バイト値の配列への long ポインターである必要があります。  
  
## <a name="remarks"></a>コメント  
 現在使用されているビットマップ形式は、モノクロおよびカラーです。 モノクロ ビットマップは、1 ビット、1 プレーンのファイル形式を使用します。 各スキャンは 16 ビットの倍数です。  
  
 モノクロ ビットマップの高さのスキャンが次のように編成された*n*:  
  
 `Scan 0`  
  
 `Scan 1`  
  
 `.`  
  
 `.`  
  
 `.`  
  
 `Scan n-2`  
  
 `Scan n-1`  
  
 モノクロ デバイス上のピクセルは黒と白のどちらかです。 ビットマップ内で対応するビットが 1 の場合、そのピクセルはオン (白) になります。 ビットマップ内で対応するビットが 0 の場合、そのピクセルはオフ (黒) になります。  
  
 ビットマップをサポートするすべてのデバイス、 **RC_BITBLT**ビット設定されている、 **RASTERCAPS**のインデックス、[は](../../mfc/reference/cdc-class.md#getdevicecaps)メンバー関数。  
  
 各デバイスには、独自のカラー形式があります。 ビットマップを別の&1; つのデバイスに転送、するために使用して、 [GetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd144879)と[SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973) Windows 関数です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** wingdi.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect)

