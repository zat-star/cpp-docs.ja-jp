---
title: "CD2DPointU クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
dev_langs:
- C++
helpviewer_keywords:
- CD2DPointU class
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 605415ad5a2739d8f8ac3a6a47c562796d55a813
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dpointu-class"></a>CD2DPointU クラス
`D2D1_POINT_2U`のラッパー。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DPointU : public D2D1_POINT_2U;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DPointU::CD2DPointU](#cd2dpointu)|オーバーロードされます。 構築、`CD2DPointU`オブジェクトから`D2D1_POINT_2U`オブジェクトです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DPointU::operator CPoint](#operator_cpoint)|変換`CD2DPointU`に`CPoint`オブジェクトです。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `D2D1_POINT_2U`  
  
 `CD2DPointU`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="cd2dpointu"></a>CD2DPointU::CD2DPointU  
 CPoint オブジェクトから CD2DPointU オブジェクトを構築します。  
  
```  
CD2DPointU(const CPoint& pt);  
CD2DPointU(const D2D1_POINT_2U& pt);  
  CD2DPointU(const D2D1_POINT_2U* pt);  
CD2DPointU(UINT32 uX = 0, UINT32 uY = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 ソース ポイント  
  
 `uX`  
 ソース X  
  
 `uY`  
 ソース Y  
  
##  <a name="operator_cpoint"></a>CD2DPointU::operator CPoint  
 CD2DPointU を CPoint オブジェクトに変換します。  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>戻り値  
 D2D ポイントの現在の値。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

