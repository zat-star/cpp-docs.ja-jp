---
title: "LOGPEN 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LOGPEN
dev_langs:
- C++
helpviewer_keywords:
- LOGPEN structure [MFC]
ms.assetid: a89e8690-6b61-4af5-990c-7c82da24f3b0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b7bfa598a59f62c11dbda13356559816b5bd47ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="logpen-structure"></a>LOGPEN 構造体
`LOGPEN`構造体は、スタイル、幅、およびペンの色を定義、描画に使用する描画オブジェクトの直線し罫線します。 [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect)関数は、`LOGPEN`構造体。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagLOGPEN {  /* lgpn */  
    UINT lopnStyle;  
    POINT lopnWidth;  
    COLORREF lopnColor;  
} LOGPEN;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *lopnStyle*  
 ペンの種類を指定します。 このメンバーは、次の値のいずれかになります。  
  
- **きは**ソリッド ペンを作成します。  
  
- **PS_DASH**破線のペンを作成します。 (ペンの幅が 1 である場合にのみ有効です。)  
  
- **PS_DOT**点線ペンを作成します。 (ペンの幅が 1 である場合にのみ有効です。)  
  
- **PS_DASHDOT**の代替ダッシュとのドットでペンを作成します。 (ペンの幅が 1 である場合にのみ有効です。)  
  
- **PS_DASHDOTDOT**の代替ダッシュと 2 つのドットでペンを作成します。 (ペンの幅が 1 である場合にのみ有効です。)  
  
- **必ず**null ペンを作成します。  
  
- **ペン**外接する四角形を指定する GDI 出力関数によって生成される閉じた図形のフレーム内の行を描画するペンを作成 (たとえば、**楕円**、**四角形**、 `RoundRect`、 `Pie`、および`Chord`メンバー関数)。 外接する四角形が指定されていない関数の出力 GDI を使用してこのスタイルを使用する場合 (たとえば、`LineTo`メンバー関数)、ペンの描画領域は、フレームによって制限を受けません。  
  
     ペンがある場合、**ペン**スタイルと色が論理カラー テーブルで使用する色に一致しない、ペンをディザリングされた色で描画します。 **きは**をディザリングされた色でペンを作成するのには、ペンのスタイルを使用できません。 **ペン**スタイルは**きは**ペンの幅が 1 未満の場合。  
  
     ときに、**ペン**以外の関数によって生成される GDI オブジェクトのスタイルは使用**楕円**、**四角形**、および`RoundRect`行が完全にできません指定したフレーム内です。  
  
 *lopnWidth*  
 論理ユニットでは、ペンの幅を指定します。 場合、 **lopnWidth**メンバーが 0 のペンが現在のマップ モードに関係なくラスター デバイスで 1 ピクセル場合、です。  
  
 *lopnColor*  
 ペンの色を指定します。  
  
## <a name="remarks"></a>コメント  
 **Y**値で、[ポイント](../../mfc/reference/point-structure1.md)の構造体、 **lopnWidth**メンバーは使用されません。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** wingdi.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect)

