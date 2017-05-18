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
- RECT structure
- LPRECT structure
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
caps.latest.revision: 13
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
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: bc91b22f291f23ed396a054b0c929410718286a3
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

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
 [!code-cpp[NVC_MFC_Utilities #&38;](../../mfc/codesnippet/cpp/rect-structure1_1.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** windef.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRect クラス](../../atl-mfc-shared/reference/crect-class.md)

