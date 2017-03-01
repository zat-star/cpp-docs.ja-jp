---
title: "CHwndRenderTarget クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHwndRenderTarget
- afxrendertarget/CHwndRenderTarget
dev_langs:
- C++
helpviewer_keywords:
- CHwndRenderTarget class
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 1af6795e89c995ba6b5a7b094f06b0aea776f561
ms.lasthandoff: 02/24/2017

---
# <a name="chwndrendertarget-class"></a>CHwndRenderTarget クラス
ID2D1HwndRenderTarget のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CHwndRenderTarget : public CRenderTarget;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHwndRenderTarget::CHwndRenderTarget](#chwndrendertarget)|Hwnd の分離 CHwndRenderTarget オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CHwndRenderTarget::Attach](#attach)|既存の接続は、ターゲット オブジェクトのインターフェイスを表示します。|  
|[CHwndRenderTarget::CheckWindowState](#checkwindowstate)|このレンダー ターゲットに関連付けられている HWND が遮蔽かどうかを示します。|  
|[CHwndRenderTarget::Create](#create)|ウィンドウに関連付けられているレンダー ターゲットを作成します。|  
|[CHwndRenderTarget::Detach](#detach)|レンダー ターゲットのインターフェイス、オブジェクトからのデタッチします。|  
|[CHwndRenderTarget::GetHwnd](#gethwnd)|これに関連付けられている HWND を返します。 は、ターゲットをレンダリングします。|  
|[CHwndRenderTarget::GetHwndRenderTarget](#gethwndrendertarget)|ID2D1HwndRenderTarget インターフェイスを返します。|  
|[CHwndRenderTarget::ReCreate](#recreate)|ウィンドウに関連付けられているレンダー ターゲットを再作成します。|  
|[CHwndRenderTarget::Resize](#resize)|指定したピクセル サイズにレンダー ターゲットのサイズを変更します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CHwndRenderTarget::operator ID2D1HwndRenderTarget *](#operator_id2d1hwndrendertarget_star)|ID2D1HwndRenderTarget インターフェイスを返します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CHwndRenderTarget::m_pHwndRenderTarget](#m_phwndrendertarget)|ID2D1HwndRenderTarget オブジェクトへのポインター。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="a-nameattacha--chwndrendertargetattach"></a><a name="attach"></a>CHwndRenderTarget::Attach  
 既存の接続は、ターゲット オブジェクトのインターフェイスを表示します。  
  
```  
void Attach(ID2D1HwndRenderTarget* pTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `pTarget`  
 既存のレンダー ターゲットのインターフェイスです。 NULL にすることはできません。  
  
##  <a name="a-namecheckwindowstatea--chwndrendertargetcheckwindowstate"></a><a name="checkwindowstate"></a>CHwndRenderTarget::CheckWindowState  
 このレンダー ターゲットに関連付けられている HWND が遮蔽かどうかを示します。  
  
```  
D2D1_WINDOW_STATE CheckWindowState() const;  
```  
  
### <a name="return-value"></a>戻り値  
 これに関連付けられている HWND がターゲットをレンダリングするかどうかを示す値が遮蔽されます。  
  
##  <a name="a-namechwndrendertargeta--chwndrendertargetchwndrendertarget"></a><a name="chwndrendertarget"></a>CHwndRenderTarget::CHwndRenderTarget  
 Hwnd の分離 CHwndRenderTarget オブジェクトを構築します。  
  
```  
CHwndRenderTarget(HWND hwnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `hwnd`  
 これに関連付けられている HWND レンダリング ターゲット  
  
##  <a name="a-namecreatea--chwndrendertargetcreate"></a><a name="create"></a>CHwndRenderTarget::Create  
 ウィンドウに関連付けられているレンダー ターゲットを作成します。  
  
```  
BOOL Create(HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 これに関連付けられている HWND レンダリング ターゲット  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します  
  
##  <a name="a-namedetacha--chwndrendertargetdetach"></a><a name="detach"></a>CHwndRenderTarget::Detach  
 レンダー ターゲットのインターフェイス、オブジェクトからのデタッチします。  
  
```  
ID2D1HwndRenderTarget* Detach();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされたへのポインターは、対象のインターフェイスをレンダリングします。  
  
##  <a name="a-namegethwnda--chwndrendertargetgethwnd"></a><a name="gethwnd"></a>CHwndRenderTarget::GetHwnd  
 これに関連付けられている HWND を返します。 は、ターゲットをレンダリングします。  
  
```  
HWND GetHwnd() const;  
```  
  
### <a name="return-value"></a>戻り値  
 これに関連付けられている HWND では、ターゲットをレンダリングします。  
  
##  <a name="a-namegethwndrendertargeta--chwndrendertargetgethwndrendertarget"></a><a name="gethwndrendertarget"></a>CHwndRenderTarget::GetHwndRenderTarget  
 ID2D1HwndRenderTarget インターフェイスを返します。  
  
```  
ID2D1HwndRenderTarget* GetHwndRenderTarget();
```  
  
### <a name="return-value"></a>戻り値  
 ID2D1HwndRenderTarget インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
##  <a name="a-namemphwndrendertargeta--chwndrendertargetmphwndrendertarget"></a><a name="m_phwndrendertarget"></a>CHwndRenderTarget::m_pHwndRenderTarget  
 ID2D1HwndRenderTarget オブジェクトへのポインター。  
  
```  
ID2D1HwndRenderTarget* m_pHwndRenderTarget;  
```  
  
##  <a name="a-nameoperatorid2d1hwndrendertargetstara--chwndrendertargetoperator-id2d1hwndrendertarget"></a><a name="operator_id2d1hwndrendertarget_star"></a>CHwndRenderTarget::operator ID2D1HwndRenderTarget *  
 ID2D1HwndRenderTarget インターフェイスを返します。  
  
```  
operator ID2D1HwndRenderTarget*();
```   
  
### <a name="return-value"></a>戻り値  
 ID2D1HwndRenderTarget インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
##  <a name="a-namerecreatea--chwndrendertargetrecreate"></a><a name="recreate"></a>CHwndRenderTarget::ReCreate  
 ウィンドウに関連付けられているレンダー ターゲットを再作成します。  
  
```  
BOOL ReCreate(HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 これに関連付けられている HWND レンダリング ターゲット  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="a-nameresizea--chwndrendertargetresize"></a><a name="resize"></a>CHwndRenderTarget::Resize  
 指定したピクセル サイズにレンダー ターゲットのサイズを変更します。  
  
```  
BOOL Resize(const CD2DSizeU& size);
```  
  
### <a name="parameters"></a>パラメーター  
 `size`  
 デバイス ピクセル単位で、レンダー ターゲットの新しいサイズ  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合、FALSE を返します。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

