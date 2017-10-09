---
title: "CD2DPointF クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DPointF
- AFXRENDERTARGET/CD2DPointF
- AFXRENDERTARGET/CD2DPointF::CD2DPointF
dev_langs:
- C++
helpviewer_keywords:
- CD2DPointF [MFC], CD2DPointF
ms.assetid: 30f72083-1c8a-4f50-adb2-72dbbe3522d4
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 98435819aeb0e173074a4794939bee10b00b3233
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="cd2dpointf-class"></a>CD2DPointF クラス
`D2D1_POINT_2F`のラッパー。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DPointF : public D2D1_POINT_2F;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DPointF::CD2DPointF](#cd2dpointf)|オーバーロードされます。 構築、`CD2DPointF`オブジェクトから`D2D1_POINT_2F`オブジェクト。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DPointF::operator CPoint](#operator_cpoint)|変換`CD2DPointF`に`CPoint`オブジェクト。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `D2D1_POINT_2F`  
  
 `CD2DPointF`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="cd2dpointf"></a>CD2DPointF::CD2DPointF  
 CPoint オブジェクトから CD2DPointF オブジェクトを構築します。  
  
```  
CD2DPointF(const CPoint& pt);    
CD2DPointF(const D2D1_POINT_2F& pt);    
CD2DPointF(const D2D1_POINT_2F* pt); 
CD2DPointF(FLOAT fX = 0., FLOAT fY = 0.);
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 ソース ポイント  
  
 `fX`  
 ソース X  
  
 `fY`  
 ソース Y  
  
##  <a name="operator_cpoint"></a>CD2DPointF::operator CPoint  
 CD2DPointF を CPoint オブジェクトに変換します。  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>戻り値  
 D2D ポイントの現在の値。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

