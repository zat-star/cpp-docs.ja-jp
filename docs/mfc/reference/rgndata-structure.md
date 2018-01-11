---
title: "RGNDATA 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: RGNDATA
dev_langs: C++
helpviewer_keywords: RGNDATA structure [MFC]
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d4170b3590cc841f3edc10d4767045a4fede9782
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="rgndata-structure"></a>RGNDATA 構造体
`RGNDATA`構造には、ヘッダーと領域を構成する四角形の配列が含まれています。 これらの四角形、並べ替えられた上から下、左右からへは重複しません。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct _RGNDATA { /* rgnd */  
    RGNDATAHEADER rdh;  
    char Buffer[1];  
} RGNDATA;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *rdh*  
 指定します、 [RGNDATAHEADER](http://msdn.microsoft.com/library/windows/desktop/dd162941)構造体。 (この構造体の詳細については、Windows SDK を参照してください)。この構造体のメンバーは、領域 (かどうかは四角形または台形)、領域、四角形の構造体を格納しているバッファーのサイズを構成する四角形の番号の種類を指定し、します。  
  
 `Buffer`  
 含む任意のサイズのバッファーを指定します、 [RECT](../../mfc/reference/rect-structure1.md)領域を構成する構造体。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** wingdi.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)   
 [CRgn::GetRegionData](../../mfc/reference/crgn-class.md#getregiondata)

