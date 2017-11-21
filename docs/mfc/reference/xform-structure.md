---
title: "XFORM 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: XFORM
dev_langs: C++
helpviewer_keywords: XFORM structure [MFC]
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3c9e5978d82b1bbaed08eaa05dda53c78160579f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="xform-structure"></a>XFORM 構造体
`XFORM`構造体には、次の形式。  
  
## <a name="syntax"></a>構文  
  
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
  
## <a name="remarks"></a>コメント  
 `XFORM`構造体は、ページ領域変換へワールド空間を指定します。 **EDx**と**構造体**メンバーが、水平および垂直方向の変換コンポーネントをそれぞれ指定します。 次の表は、操作に応じて、他のメンバーの使用方法を示しています。  
  
|操作|eM11|eM12|eM21|eM22|  
|---------------|----------|----------|----------|----------|  
|`Rotation`|回転角度のコサインの値|回転角度のサイン (正弦)|回転角度のサインを負の値|回転角度のコサインの値|  
|**スケーリング**|水平方向のスケーリング コンポーネント|Nothing|Nothing|垂直方向のスケーリング コンポーネント|  
|**傾斜**|Nothing|水平方向のプロポーショナル定数|垂直方向のプロポーショナル定数|Nothing|  
|**リフレクション**|水平方向の反転コンポーネント|Nothing|Nothing|垂直方向の反転コンポーネント|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** wingdi.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)

