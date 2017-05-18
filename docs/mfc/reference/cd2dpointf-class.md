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
- CD2DPointF class
ms.assetid: 30f72083-1c8a-4f50-adb2-72dbbe3522d4
caps.latest.revision: 18
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 8449fcadfb72305e9e5b6ed2c6829ba9963ba7ca
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

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
|[CD2DPointF::CD2DPointF](#cd2dpointf)|オーバーロードされます。 構築、`CD2DPointF`オブジェクトから`D2D1_POINT_2F`オブジェクトです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DPointF::operator CPoint](#operator_cpoint)|変換`CD2DPointF`に`CPoint`オブジェクトです。|  
  
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

