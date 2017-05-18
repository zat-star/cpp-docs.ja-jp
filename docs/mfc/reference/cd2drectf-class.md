---
title: "CD2DRectF クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DRectF
- AFXRENDERTARGET/CD2DRectF
- AFXRENDERTARGET/CD2DRectF::CD2DRectF
- AFXRENDERTARGET/CD2DRectF::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DRectF class
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
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
ms.openlocfilehash: 5bca2dcce32679083e5917d855f711984989a489
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cd2drectf-class"></a>CD2DRectF クラス
`D2D1_RECT_F`のラッパー。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DRectF : public D2D1_RECT_F;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DRectF::CD2DRectF](#cd2drectf)|オーバーロードされます。 構築、`CD2DRectF`オブジェクトから`D2D1_RECT_F`オブジェクトです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DRectF::IsNull](#isnull)|返します。、`boolean`式に有効なデータが含まれていないかどうかを示す値 ( `null`)。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DRectF::operator CRect](#operator_crect)|変換`CD2DRectF`に`CRect`オブジェクトです。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `D2D1_RECT_F`  
  
 `CD2DRectF`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="cd2drectf"></a>CD2DRectF::CD2DRectF  
 CRect オブジェクトから CD2DRectF オブジェクトを構築します。  
  
```  
CD2DRectF(const CRect& rect);  
CD2DRectF(const D2D1_RECT_F& rect);  
  CD2DRectF(const D2D1_RECT_F* rect);

 
CD2DRectF(
    FLOAT fLeft = 0.,  
    FLOAT fTop = 0.,  
    FLOAT fRight = 0.,  
    FLOAT fBottom = 0.);
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 元の四角形  
  
 `fLeft`  
 ソースの左座標  
  
 `fTop`  
 ソース上座標  
  
 `fRight`  
 右側の座標のソース  
  
 `fBottom`  
 ソースの下部にある座標  
  
##  <a name="isnull"></a>CD2DRectF::IsNull  
 式に有効なデータ (Null) が含まれていないかどうかを示すブール値を返します。  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>戻り値  
 四角形の上、左、下、および適切な値はすべて 0 に等しい場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="operator_crect"></a>CD2DRectF::operator CRect  
 CD2DRectF を含む CRect オブジェクトに変換します。  
  
```  
operator CRect();
```   
  
### <a name="return-value"></a>戻り値  
 D2D 四角形の現在の値。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

