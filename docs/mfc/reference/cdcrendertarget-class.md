---
title: "CDCRenderTarget クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::Attach
- AFXRENDERTARGET/CDCRenderTarget::BindDC
- AFXRENDERTARGET/CDCRenderTarget::Create
- AFXRENDERTARGET/CDCRenderTarget::Detach
- AFXRENDERTARGET/CDCRenderTarget::GetDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::m_pDCRenderTarget
dev_langs:
- C++
helpviewer_keywords:
- CDCRenderTarget class
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 2bbd62b06f4287904fce49f8a6ce9900476b07c0
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cdcrendertarget-class"></a>CDCRenderTarget クラス
ID2D1DCRenderTarget のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CDCRenderTarget : public CRenderTarget;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDCRenderTarget::CDCRenderTarget](#cdcrendertarget)|CDCRenderTarget オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDCRenderTarget::Attach](#attach)|既存の接続は、ターゲット オブジェクトのインターフェイスをレンダリングします。|  
|[CDCRenderTarget::BindDC](#binddc)|レンダー ターゲットを描画コマンドを発行先デバイス コンテキストにバインドします。|  
|[CDCRenderTarget::Create](#create)|CDCRenderTarget を作成します。|  
|[CDCRenderTarget::Detach](#detach)|レンダー ターゲット インターフェイス オブジェクトからのデタッチします。|  
|[CDCRenderTarget::GetDCRenderTarget](#getdcrendertarget)|返します。 ID2D1DCRenderTarget インターフェイス|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CDCRenderTarget::operator ID2D1DCRenderTarget *](#operator_id2d1dcrendertarget_star)|返します。 ID2D1DCRenderTarget インターフェイス|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDCRenderTarget::m_pDCRenderTarget](#m_pdcrendertarget)|ID2D1DCRenderTarget オブジェクトへのポインター。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="attach"></a>CDCRenderTarget::Attach  
 既存の接続は、ターゲット オブジェクトのインターフェイスをレンダリングします。  
  
```  
void Attach(ID2D1DCRenderTarget* pTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `pTarget`  
 既存のレンダー ターゲットのインターフェイスです。 NULL にすることはできません。  
  
##  <a name="binddc"></a>CDCRenderTarget::BindDC  
 レンダー ターゲットを描画コマンドを発行先デバイス コンテキストにバインドします。  
  
```  
BOOL BindDC(
    const CDC& dc,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 `dc`  
 レンダー ターゲットが描画コマンドを発行したデバイス コンテキスト  
  
 `rect`  
 レンダー ターゲットがバインドされているデバイス コンテキスト (HDC) へのハンドルのサイズ  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="cdcrendertarget"></a>CDCRenderTarget::CDCRenderTarget  
 CDCRenderTarget オブジェクトを構築します。  
  
```  
CDCRenderTarget();
```  
  
##  <a name="create"></a>CDCRenderTarget::Create  
 CDCRenderTarget を作成します。  
  
```  
BOOL Create(const D2D1_RENDER_TARGET_PROPERTIES& props);
```  
  
### <a name="parameters"></a>パラメーター  
 `props`  
 レンダリング モード、ピクセル形式、リモート処理オプション、DPI 情報、およびハードウェア レンダリングに必要な最小の DirectX サポートします。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="detach"></a>CDCRenderTarget::Detach  
 レンダー ターゲット インターフェイス オブジェクトからのデタッチします。  
  
```  
ID2D1DCRenderTarget* Detach();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされたへのポインターは、対象のインターフェイスをレンダリングします。  
  
##  <a name="getdcrendertarget"></a>CDCRenderTarget::GetDCRenderTarget  
 返します。 ID2D1DCRenderTarget インターフェイス  
  
```  
ID2D1DCRenderTarget* GetDCRenderTarget();
```  
  
### <a name="return-value"></a>戻り値  
 ID2D1DCRenderTarget インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
##  <a name="m_pdcrendertarget"></a>CDCRenderTarget::m_pDCRenderTarget  
 ID2D1DCRenderTarget オブジェクトへのポインター。  
  
```  
ID2D1DCRenderTarget* m_pDCRenderTarget;  
```  
  
##  <a name="operator_id2d1dcrendertarget_star"></a>CDCRenderTarget::operator ID2D1DCRenderTarget *  
 返します。 ID2D1DCRenderTarget インターフェイス  
  
```  
operator ID2D1DCRenderTarget*();
```   
  
### <a name="return-value"></a>戻り値  
 ID2D1DCRenderTarget インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

