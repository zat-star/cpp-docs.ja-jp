---
title: "CD2DSolidColorBrush クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DSolidColorBrush
- afxrendertarget/CD2DSolidColorBrush
dev_langs:
- C++
helpviewer_keywords:
- CD2DSolidColorBrush class
ms.assetid: d4506637-acce-4f74-8a9b-f0a45571a735
caps.latest.revision: 16
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
ms.openlocfilehash: 5b6cbd6a6a5557f5ea23c0556a4b87011b510411
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dsolidcolorbrush-class"></a>CD2DSolidColorBrush クラス
ID2D1SolidColorBrush のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DSolidColorBrush : public CD2DBrush;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DSolidColorBrush::CD2DSolidColorBrush](#cd2dsolidcolorbrush)|オーバーロードされます。 CD2DSolidColorBrush オブジェクトを構築します。|  
|[CD2DSolidColorBrush:: ~ CD2DSolidColorBrush](#cd2dsolidcolorbrush__~cd2dsolidcolorbrush)|デストラクターです。 D2D ソリッド ブラシ オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DSolidColorBrush::Attach](#attach)|オブジェクトにリソース インタ フェースを既存の接続|  
|[CD2DSolidColorBrush::Create](#create)|CD2DSolidColorBrush を作成します。 (上書き[CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create))。|  
|[CD2DSolidColorBrush::Destroy](#destroy)|CD2DSolidColorBrush オブジェクトを破棄します。 (上書き[CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy))。|  
|[CD2DSolidColorBrush::Detach](#detach)|オブジェクトからリソース インタ フェースをデタッチします。|  
|[CD2DSolidColorBrush::Get](#get)|返します。 ID2D1SolidColorBrush インターフェイス|  
|[CD2DSolidColorBrush::GetColor](#getcolor)|単色ブラシの色を取得します。|  
|[CD2DSolidColorBrush::SetColor](#setcolor)|この単色ブラシの色を指定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DSolidColorBrush::operator ID2D1SolidColorBrush *](#operator_id2d1solidcolorbrush_star)|返します。 ID2D1SolidColorBrush インターフェイス|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DSolidColorBrush::m_colorSolid](#m_colorsolid)|純色のブラシです。|  
|[CD2DSolidColorBrush::m_pSolidColorBrush](#m_psolidcolorbrush)|ID2D1SolidColorBrush オブジェクトへのポインターを格納します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DSolidColorBrush](../../mfc/reference/cd2dsolidcolorbrush-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dsolidcolorbrusha--cd2dsolidcolorbrushcd2dsolidcolorbrush"></a><a name="_dtorcd2dsolidcolorbrush"></a>CD2DSolidColorBrush:: ~ CD2DSolidColorBrush  
 デストラクターです。 D2D ソリッド ブラシ オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CD2DSolidColorBrush();
```  
  
##  <a name="a-nameattacha--cd2dsolidcolorbrushattach"></a><a name="attach"></a>CD2DSolidColorBrush::Attach  
 オブジェクトにリソース インタ フェースを既存の接続  
  
```  
void Attach(ID2D1SolidColorBrush* pResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `pResource`  
 既存のリソースのインターフェイスです。 NULL にすることはできません。  
  
##  <a name="a-namecd2dsolidcolorbrusha--cd2dsolidcolorbrushcd2dsolidcolorbrush"></a><a name="cd2dsolidcolorbrush"></a>CD2DSolidColorBrush::CD2DSolidColorBrush  
 CD2DSolidColorBrush オブジェクトを構築します。  
  
```  
CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,  
    D2D1_COLOR_F color,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);

 
CD2DSolidColorBrush(
    CRenderTarget* pParentTarget,  
    COLORREF color,  
    int nAlpha = 255,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentTarget`  
 レンダー ターゲットへのポインター。  
  
 `color`  
 ブラシの色の赤、緑、青、およびアルファ値。  
  
 `pBrushProperties`  
 不透明度とブラシの変換へのポインター。  
  
 `bAutoDestroy`  
 所有者 (pParentTarget) によって、オブジェクトが破棄されることを示します。  
  
 `nAlpha`  
 ブラシの色の不透明度。  
  
##  <a name="a-namecreatea--cd2dsolidcolorbrushcreate"></a><a name="create"></a>CD2DSolidColorBrush::Create  
 CD2DSolidColorBrush を作成します。  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRenderTarget`  
 レンダー ターゲットへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="a-namedestroya--cd2dsolidcolorbrushdestroy"></a><a name="destroy"></a>CD2DSolidColorBrush::Destroy  
 CD2DSolidColorBrush オブジェクトを破棄します。  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namedetacha--cd2dsolidcolorbrushdetach"></a><a name="detach"></a>CD2DSolidColorBrush::Detach  
 オブジェクトからリソース インタ フェースをデタッチします。  
  
```  
ID2D1SolidColorBrush* Detach();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされたリソース インタ フェースへのポインター。  
  
##  <a name="a-namegeta--cd2dsolidcolorbrushget"></a><a name="get"></a>CD2DSolidColorBrush::Get  
 返します。 ID2D1SolidColorBrush インターフェイス  
  
```  
ID2D1SolidColorBrush* Get();
```  
  
### <a name="return-value"></a>戻り値  
 ID2D1SolidColorBrush インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
##  <a name="a-namegetcolora--cd2dsolidcolorbrushgetcolor"></a><a name="getcolor"></a>CD2DSolidColorBrush::GetColor  
 単色ブラシの色を取得します。  
  
```  
D2D1_COLOR_F GetColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 この単色ブラシの色  
  
##  <a name="a-namemcolorsolida--cd2dsolidcolorbrushmcolorsolid"></a><a name="m_colorsolid"></a>CD2DSolidColorBrush::m_colorSolid  
 純色のブラシです。  
  
```  
D2D1_COLOR_F m_colorSolid;  
```  
  
##  <a name="a-namempsolidcolorbrusha--cd2dsolidcolorbrushmpsolidcolorbrush"></a><a name="m_psolidcolorbrush"></a>CD2DSolidColorBrush::m_pSolidColorBrush  
 ID2D1SolidColorBrush オブジェクトへのポインターを格納します。  
  
```  
ID2D1SolidColorBrush* m_pSolidColorBrush;  
```  
  
##  <a name="a-nameoperatorid2d1solidcolorbrushstara--cd2dsolidcolorbrushoperator-id2d1solidcolorbrush"></a><a name="operator_id2d1solidcolorbrush_star"></a>CD2DSolidColorBrush::operator ID2D1SolidColorBrush *  
 返します。 ID2D1SolidColorBrush インターフェイス  
  
```  
operator ID2D1SolidColorBrush*();
```   
  
### <a name="return-value"></a>戻り値  
 ID2D1SolidColorBrush インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
##  <a name="a-namesetcolora--cd2dsolidcolorbrushsetcolor"></a><a name="setcolor"></a>CD2DSolidColorBrush::SetColor  
 この単色ブラシの色を指定します。  
  
```  
void SetColor(D2D1_COLOR_F color);
```  
  
### <a name="parameters"></a>パラメーター  
 `color`  
 この単色ブラシの色  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

