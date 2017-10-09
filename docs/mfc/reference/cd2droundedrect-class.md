---
title: "CD2DRoundedRect クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect::CD2DRoundedRect
dev_langs:
- C++
helpviewer_keywords:
- CD2DRoundedRect [MFC], CD2DRoundedRect
ms.assetid: 06207fb5-e92b-41c0-bceb-b45d8f466531
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 5496ad1262246e44871cc540b4021c7fb18216ca
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="cd2droundedrect-class"></a>CD2DRoundedRect クラス
`D2D1_ROUNDED_RECT`のラッパー。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DRoundedRect : public D2D1_ROUNDED_RECT;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DRoundedRect::CD2DRoundedRect](#cd2droundedrect)|オーバーロードされます。 構築、`CD2DRoundedRect`オブジェクトから`D2D1_ROUNDED_RECT`オブジェクト。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `D2D1_ROUNDED_RECT`  
  
 [CD2DRoundedRect](../../mfc/reference/cd2droundedrect-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="cd2droundedrect"></a>CD2DRoundedRect::CD2DRoundedRect  
 CD2DRectF オブジェクトから CD2DRoundedRect オブジェクトを構築します。  
  
```  
CD2DRoundedRect(
    const CD2DRectF& rectIn,  
    const CD2DSizeF& sizeRadius);  
  
CD2DRoundedRect(const D2D1_ROUNDED_RECT& rectIn);  
CD2DRoundedRect(const D2D1_ROUNDED_RECT* rectIn);
```  
  
### <a name="parameters"></a>パラメーター  
 `rectIn`  
 元の四角形  
  
 `sizeRadius`  
 半径のサイズ  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

