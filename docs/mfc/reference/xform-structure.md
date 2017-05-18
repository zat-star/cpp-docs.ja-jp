---
title: "XFORM 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- XFORM
dev_langs:
- C++
helpviewer_keywords:
- XFORM structure
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
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
ms.openlocfilehash: 2d23b3838f1e2dcabb2affb96fa6f18942581ff8
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

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
 `XFORM`構造体は、ページ領域の変換にワールド空間を指定します。 **EDx**と**構造体**メンバーは、水平および垂直方向の変換コンポーネントをそれぞれ指定します。 次の表は、操作によって、他のメンバーの使用方法を示しています。  
  
|操作|eM11|eM12|eM21|eM22|  
|---------------|----------|----------|----------|----------|  
|`Rotation`|回転角度のコサイン|回転角度のサイン (正弦)|回転角度のサインを負の値|回転角度のコサイン|  
|**拡大/縮小**|水平スケーリング コンポーネント|Nothing|Nothing|垂直スケーリング コンポーネント|  
|**傾斜させる**|Nothing|水平プロポーショナル定数|垂直プロポーショナル定数|Nothing|  
|**リフレクション**|水平方向の反転コンポーネント|Nothing|Nothing|垂直方向の反転コンポーネント|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** wingdi.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)


