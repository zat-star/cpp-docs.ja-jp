---
title: "CD2DLayer クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DLayer
- AFXRENDERTARGET/CD2DLayer
- AFXRENDERTARGET/CD2DLayer::CD2DLayer
- AFXRENDERTARGET/CD2DLayer::Attach
- AFXRENDERTARGET/CD2DLayer::Create
- AFXRENDERTARGET/CD2DLayer::Destroy
- AFXRENDERTARGET/CD2DLayer::Detach
- AFXRENDERTARGET/CD2DLayer::Get
- AFXRENDERTARGET/CD2DLayer::GetSize
- AFXRENDERTARGET/CD2DLayer::IsValid
- AFXRENDERTARGET/CD2DLayer::m_pLayer
dev_langs:
- C++
helpviewer_keywords:
- CD2DLayer class
ms.assetid: 2f96378e-66bb-40d1-9661-6afe324de3c1
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
ms.openlocfilehash: d0034c37da7fa61c10cf6c7662ba361de8313aa0
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dlayer-class"></a>CD2DLayer クラス
ID2D1Layer のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DLayer : public CD2DResource;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DLayer::CD2DLayer](#cd2dlayer)|CD2DLayer オブジェクトを構築します。|  
|[CD2DLayer:: ~ CD2DLayer](#_dtorcd2dlayer)|デストラクターです。 D2D layer オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DLayer::Attach](#attach)|オブジェクトにリソース インタ フェースを既存の接続|  
|[CD2DLayer::Create](#create)|CD2DLayer を作成します。 (上書き[CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create))。|  
|[CD2DLayer::Destroy](#destroy)|CD2DLayer オブジェクトを破棄します。 (上書き[CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy))。|  
|[CD2DLayer::Detach](#detach)|オブジェクトからリソース インタ フェースをデタッチします。|  
|[CD2DLayer::Get](#get)|返します。 ID2D1Layer インターフェイス|  
|[CD2DLayer::GetSize](#getsize)|デバイスに依存しないピクセル単位で、レンダー ターゲットのサイズを返します|  
|[CD2DLayer::IsValid](#isvalid)|リソースの有効性をチェックする (上書き[CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid))。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DLayer::operator ID2D1Layer *](#operator_id2d1layer_star)|返します。 ID2D1Layer インターフェイス|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DLayer::m_pLayer](#m_player)|ID2D1Layer オブジェクトへのポインターを格納します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DLayer`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="_dtorcd2dlayer"></a>CD2DLayer:: ~ CD2DLayer  
 デストラクターです。 D2D layer オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CD2DLayer();
```  
  
##  <a name="attach"></a>CD2DLayer::Attach  
 オブジェクトにリソース インタ フェースを既存の接続  
  
```  
void Attach(ID2D1Layer* pResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `pResource`  
 既存のリソースのインターフェイスです。 NULL にすることはできません。  
  
##  <a name="cd2dlayer"></a>CD2DLayer::CD2DLayer  
 CD2DLayer オブジェクトを構築します。  
  
```  
CD2DLayer(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentTarget`  
 レンダー ターゲットへのポインター。  
  
 `bAutoDestroy`  
 所有者 (pParentTarget) によって、オブジェクトが破棄されることを示します。  
  
##  <a name="create"></a>CD2DLayer::Create  
 CD2DLayer を作成します。  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRenderTarget`  
 レンダー ターゲットへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="destroy"></a>CD2DLayer::Destroy  
 CD2DLayer オブジェクトを破棄します。  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DLayer::Detach  
 オブジェクトからリソース インタ フェースをデタッチします。  
  
```  
ID2D1Layer* Detach();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされたリソース インタ フェースへのポインター。  
  
##  <a name="get"></a>CD2DLayer::Get  
 返します。 ID2D1Layer インターフェイス  
  
```  
ID2D1Layer* Get();
```  
  
### <a name="return-value"></a>戻り値  
 ID2D1Layer インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
##  <a name="getsize"></a>CD2DLayer::GetSize  
 デバイスに依存しないピクセル単位で、レンダー ターゲットのサイズを返します  
  
```  
CD2DSizeF GetSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 デバイスに依存しないピクセルで、レンダー ターゲットの現在のサイズ  
  
##  <a name="isvalid"></a>CD2DLayer::IsValid  
 リソースの有効性のチェック  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リソースが無効である場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="m_player"></a>CD2DLayer::m_pLayer  
 ID2D1Layer オブジェクトへのポインターを格納します。  
  
```  
ID2D1Layer* m_pLayer;  
```  
  
##  <a name="operator_id2d1layer_star"></a>CD2DLayer::operator ID2D1Layer *  
 返します。 ID2D1Layer インターフェイス  
  
```  
operator ID2D1Layer* ();
```  
  
### <a name="return-value"></a>戻り値  
 ID2D1Layer インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

