---
title: "ABC 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ABC
dev_langs:
- C++
helpviewer_keywords:
- ABC structure [MFC]
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ba8add08fcd5ff3d7343477aafa7d910885b0b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="abc-structure"></a>ABC 構造体
**ABC**構造には、TrueType フォントの文字の幅が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct _ABC { /* abc */  
    int abcA;  
    UINT abcB;  
    int abcC;  
} ABC;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *abcA*  
 文字の A の間隔を指定します。 A の間隔は、文字のグリフを描画する前に、現在の位置に追加する距離です。  
  
 *abcB*  
 文字の B の間隔を指定します。 B の間隔は、文字のグリフの描画の部分の幅です。  
  
 *abcC*  
 文字の C 間隔を指定します。 C の間隔は、文字のグリフの右側に空白文字を提供する現在の位置に追加する距離です。  
  
## <a name="remarks"></a>コメント  
 文字の幅の合計は、A、B、および C のスペースの合計です。 A または C 領域のいずれかのスペーシングまたはオーバー ハングを示す負できます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** wingdi.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)


