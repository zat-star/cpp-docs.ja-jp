---
title: "CD2DGradientBrush クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DGradientBrush
- afxrendertarget/CD2DGradientBrush
dev_langs:
- C++
helpviewer_keywords:
- CD2DGradientBrush class
ms.assetid: 5bf133e6-16b7-4e3a-845d-0ce63fafe5ec
caps.latest.revision: 17
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
ms.sourcegitcommit: 73410ae17465880f455e5b15026f6cc010803c19
ms.openlocfilehash: 0b0a692ef2b5194daf7b38eed9ebe3b2f4eda448
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dgradientbrush-class"></a>CD2DGradientBrush クラス
CD2DLinearGradientBrush と CD2DRadialGradientBrush クラスの基本クラス。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DGradientBrush : public CD2DBrush;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGradientBrush::CD2DGradientBrush](#cd2dgradientbrush)|CD2DGradientBrush オブジェクトを構築します。|  
|[CD2DGradientBrush:: ~ CD2DGradientBrush](#cd2dgradientbrush__~cd2dgradientbrush)|デストラクターです。 D2D グラデーション ブラシのオブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGradientBrush::Destroy](#destroy)|CD2DGradientBrush のオブジェクトを破棄します。 (上書き[CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy))。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGradientBrush::m_arGradientStops](#m_argradientstops)|D2D1_GRADIENT_STOP 構造体の配列。|  
|[CD2DGradientBrush::m_colorInterpolationGamma](#m_colorinterpolationgamma)|どの色のグラデーションの分岐点間の補間が実行される領域です。|  
|[CD2DGradientBrush::m_extendMode](#m_extendmode)|[0,&1;] の正規化された範囲外のグラデーションの動作です。|  
|[CD2DGradientBrush::m_pGradientStops](#m_pgradientstops)|D2D1_GRADIENT_STOP 構造体の配列へのポインター。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 `CD2DGradientBrush`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dgradientbrusha--cd2dgradientbrushcd2dgradientbrush"></a><a name="_dtorcd2dgradientbrush"></a>CD2DGradientBrush:: ~ CD2DGradientBrush  
 デストラクターです。 D2D グラデーション ブラシのオブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CD2DGradientBrush();
```  
  
##  <a name="a-namecd2dgradientbrusha--cd2dgradientbrushcd2dgradientbrush"></a><a name="cd2dgradientbrush"></a>CD2DGradientBrush::CD2DGradientBrush  
 CD2DGradientBrush オブジェクトを構築します。  
  
```  
CD2DGradientBrush(
    CRenderTarget* pParentTarget,  
    const D2D1_GRADIENT_STOP* gradientStops,  
    UINT gradientStopsCount,  
    D2D1_GAMMA colorInterpolationGamma = D2D1_GAMMA_2_2,  
    D2D1_EXTEND_MODE extendMode = D2D1_EXTEND_MODE_CLAMP,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentTarget`  
 レンダー ターゲットへのポインター。  
  
 `gradientStops`  
 D2D1_GRADIENT_STOP 構造体の配列へのポインター。  
  
 `gradientStopsCount`  
 GradientStops 配列内のグラデーションの分岐点の数を指定する 1 以上の値です。  
  
 `colorInterpolationGamma`  
 どの色のグラデーションの分岐点間の補間が実行される領域です。  
  
 `extendMode`  
 [0,&1;] の正規化された範囲外のグラデーションの動作です。  
  
 `pBrushProperties`  
 不透明度とブラシの変換へのポインター。  
  
 `bAutoDestroy`  
 所有者 (pParentTarget) によって、オブジェクトが破棄されることを示します。  
  
##  <a name="a-namedestroya--cd2dgradientbrushdestroy"></a><a name="destroy"></a>CD2DGradientBrush::Destroy  
 CD2DGradientBrush のオブジェクトを破棄します。  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namemargradientstopsa--cd2dgradientbrushmargradientstops"></a><a name="m_argradientstops"></a>CD2DGradientBrush::m_arGradientStops  
 D2D1_GRADIENT_STOP 構造体の配列。  
  
```  
CArray<D2D1_GRADIENT_STOP, D2D1_GRADIENT_STOP> m_arGradientStops;  
```  
  
##  <a name="a-namemcolorinterpolationgammaa--cd2dgradientbrushmcolorinterpolationgamma"></a><a name="m_colorinterpolationgamma"></a>CD2DGradientBrush::m_colorInterpolationGamma  
 どの色のグラデーションの分岐点間の補間が実行される領域です。  
  
```  
D2D1_GAMMA m_colorInterpolationGamma;  
```  
  
##  <a name="a-namemextendmodea--cd2dgradientbrushmextendmode"></a><a name="m_extendmode"></a>CD2DGradientBrush::m_extendMode  
 [0,&1;] の正規化された範囲外のグラデーションの動作です。  
  
```  
D2D1_EXTEND_MODE m_extendMode;  
```  
  
##  <a name="a-namempgradientstopsa--cd2dgradientbrushmpgradientstops"></a><a name="m_pgradientstops"></a>CD2DGradientBrush::m_pGradientStops  
 D2D1_GRADIENT_STOP 構造体の配列へのポインター。  
  
```  
ID2D1GradientStopCollection* m_pGradientStops;  
```  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

