---
title: "RECT Structure1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LPRECT
- RECT
dev_langs:
- C++
helpviewer_keywords:
- RECT structure [MFC]
- LPRECT structure [MFC]
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f4e56c78e717b24390a82e7cbb55670f36369044
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="rect-structure1"></a>RECT Structure1
`RECT` 構造体は、四角形の左上隅および右下隅の座標を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagRECT {  
    LONG left;  
    LONG top;  
    LONG right;  
    LONG bottom;  
} RECT;  
```  
  
## <a name="members"></a>メンバー  
 `left`  
 四角形の左上隅の X 座標を指定します。  
  
 `top`  
 四角形の左上隅の Y 座標を指定します。  
  
 `right`  
 四角形の右下隅の X 座標を指定します。  
  
 `bottom`  
 四角形の右下隅の Y 座標を指定します。  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#38](../../mfc/codesnippet/cpp/rect-structure1_1.cpp)]  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** windef.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRect クラス](../../atl-mfc-shared/reference/crect-class.md)
