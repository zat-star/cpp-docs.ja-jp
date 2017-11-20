---
title: "CD2DEllipse クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
dev_langs: C++
helpviewer_keywords: CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 396d462b76b1aaa2fac5d0fdf2d0b89e581085e7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="cd2dellipse-class"></a>CD2DEllipse クラス
`D2D1_ELLIPSE` のラッパー。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DEllipse : public D2D1_ELLIPSE;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DEllipse::CD2DEllipse](#cd2dellipse)|オーバーロードされます。 構築、`CD2DEllipse`オブジェクトから`D2D1_ELLIPSE`オブジェクト。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `D2D1_ELLIPSE`  
  
 `CD2DEllipse`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="cd2dellipse"></a>CD2DEllipse::CD2DEllipse  
 CD2DRectF オブジェクトから CD2DEllipse オブジェクトを構築します。  
  
```  
CD2DEllipse(const CD2DRectF& rect);  
CD2DEllipse(const D2D1_ELLIPSE& ellipse);  
  CD2DEllipse(const D2D1_ELLIPSE* ellipse);

 
CD2DEllipse(
    const CD2DPointF& ptCenter,  
    const CD2DSizeF& sizeRadius);
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 元の四角形  
  
 `ellipse`  
 ソース楕円  
  
 `ptCenter`  
 楕円の中心点。  
  
 `sizeRadius`  
 X 半径と楕円の Y 半径。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
