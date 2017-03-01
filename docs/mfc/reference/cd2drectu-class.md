---
title: "CD2DRectU クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DRectU
- afxrendertarget/CD2DRectU
dev_langs:
- C++
helpviewer_keywords:
- CD2DRectU class
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
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
ms.openlocfilehash: 74c05d7f4be9b9308cdcb2b91a0455a4cd025dc1
ms.lasthandoff: 02/24/2017

---
# <a name="cd2drectu-class"></a>CD2DRectU クラス
`D2D1_RECT_U`のラッパー。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DRectU : public D2D1_RECT_U;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DRectU::CD2DRectU](#cd2drectu)|オーバーロードされます。 構築、`CD2DRectU`オブジェクトから`D2D1_RECT_U`オブジェクトです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DRectU::IsNull](#isnull)|返します。、`boolean`式に有効なデータが含まれていないかどうかを示す値 ( `null`)。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DRectU::operator CRect](#operator_crect)|変換`CD2DRectU`に`CRect`オブジェクトです。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `D2D1_RECT_U`  
  
 `CD2DRectU`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="a-namecd2drectua--cd2drectucd2drectu"></a><a name="cd2drectu"></a>CD2DRectU::CD2DRectU  
 CRect オブジェクトから CD2DRectU オブジェクトを構築します。  
  
```  
CD2DRectU(const CRect& rect);  
CD2DRectU(const D2D1_RECT_U& rect);  
  CD2DRectU(const D2D1_RECT_U* rect);

 
CD2DRectU(
    UINT32 uLeft = 0,  
    UINT32 uTop = 0,  
    UINT32 uRight = 0,  
    UINT32 uBottom = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 元の四角形  
  
 `uLeft`  
 ソースの左座標  
  
 `uTop`  
 ソース上座標  
  
 `uRight`  
 右側の座標のソース  
  
 `uBottom`  
 ソースの下部にある座標  
  
##  <a name="a-nameisnulla--cd2drectuisnull"></a><a name="isnull"></a>CD2DRectU::IsNull  
 式に有効なデータ (Null) が含まれていないかどうかを示すブール値を返します。  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>戻り値  
 四角形の上、左、下、および適切な値はすべて 0 に等しい場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="a-nameoperatorcrecta--cd2drectuoperator-crect"></a><a name="operator_crect"></a>CD2DRectU::operator CRect  
 CD2DRectU を含む CRect オブジェクトに変換します。  
  
```  
operator CRect();
```   
  
### <a name="return-value"></a>戻り値  
 D2D 四角形の現在の値。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

