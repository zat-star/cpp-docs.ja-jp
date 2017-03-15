---
title: "RGNDATA 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- RGNDATA
dev_langs:
- C++
helpviewer_keywords:
- RGNDATA structure
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
caps.latest.revision: 14
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
ms.openlocfilehash: 93a7c79f175e22dcb0b40cb39b157cfe21a98e93
ms.lasthandoff: 02/24/2017

---
# <a name="rgndata-structure"></a>RGNDATA 構造体
`RGNDATA`ヘッダーと領域を構成する四角形の配列、構造体が含まれます。 これらの四角形、並べ替えられた上から下、左右からへは重複しません。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct _RGNDATA { /* rgnd */  
    RGNDATAHEADER rdh;  
    char Buffer[1];  
} RGNDATA;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *rdh*  
 指定する[RGNDATAHEADER](http://msdn.microsoft.com/library/windows/desktop/dd162941)構造体。 (この構造体の詳細については、次を参照してください、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。)。この構造体のメンバーは、領域が長方形台形のいずれか)、領域、四角形の構造体を格納しているバッファーのサイズを構成する四角形の数の種類を指定しにします。  
  
 `Buffer`  
 格納している任意のサイズ バッファーの指定、 [RECT](../../mfc/reference/rect-structure1.md)領域を構成します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** wingdi.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)   
 [CRgn::GetRegionData](../../mfc/reference/crgn-class.md#getregiondata)


