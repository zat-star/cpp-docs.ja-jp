---
title: "CD2DPathGeometry クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::Attach
- AFXRENDERTARGET/CD2DPathGeometry::Create
- AFXRENDERTARGET/CD2DPathGeometry::Destroy
- AFXRENDERTARGET/CD2DPathGeometry::Detach
- AFXRENDERTARGET/CD2DPathGeometry::GetFigureCount
- AFXRENDERTARGET/CD2DPathGeometry::GetSegmentCount
- AFXRENDERTARGET/CD2DPathGeometry::Open
- AFXRENDERTARGET/CD2DPathGeometry::Stream
- AFXRENDERTARGET/CD2DPathGeometry::m_pPathGeometry
dev_langs:
- C++
helpviewer_keywords:
- CD2DPathGeometry class
ms.assetid: 686216eb-5080-4242-ace5-8fa1ce96307c
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
ms.openlocfilehash: 1c1158e55bf12d44f34896dd6752c9b8706db636
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dpathgeometry-class"></a>CD2DPathGeometry クラス
ID2D1PathGeometry のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DPathGeometry : public CD2DGeometry;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DPathGeometry::CD2DPathGeometry](#cd2dpathgeometry)|CD2DPathGeometry オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DPathGeometry::Attach](#attach)|オブジェクトにリソース インタ フェースを既存の接続|  
|[CD2DPathGeometry::Create](#create)|CD2DPathGeometry を作成します。 (上書き[CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create))。|  
|[CD2DPathGeometry::Destroy](#destroy)|CD2DPathGeometry オブジェクトを破棄します。 (上書き[CD2DGeometry::Destroy](../../mfc/reference/cd2dgeometry-class.md#destroy))。|  
|[CD2DPathGeometry::Detach](#detach)|オブジェクトからリソース インタ フェースをデタッチします。|  
|[CD2DPathGeometry::GetFigureCount](#getfigurecount)|パス ジオメトリに数字の数を取得します。|  
|[CD2DPathGeometry::GetSegmentCount](#getsegmentcount)|パス ジオメトリにセグメントの数を取得します。|  
|[CD2DPathGeometry::Open](#open)|図形やセグメントのパス ジオメトリを作成するために使用する geometry シンクを取得します。|  
|[CD2DPathGeometry::Stream](#stream)|指定した ID2D1GeometrySink にパス ジオメトリの内容をコピーします。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DPathGeometry::m_pPathGeometry](#m_ppathgeometry)|ID2D1PathGeometry へのポインター。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DGeometry](../../mfc/reference/cd2dgeometry-class.md)  
  
 `CD2DPathGeometry`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="attach"></a>CD2DPathGeometry::Attach  
 オブジェクトにリソース インタ フェースを既存の接続  
  
```  
void Attach(ID2D1PathGeometry* pResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `pResource`  
 既存のリソースのインターフェイスです。 NULL にすることはできません。  
  
##  <a name="cd2dpathgeometry"></a>CD2DPathGeometry::CD2DPathGeometry  
 CD2DPathGeometry オブジェクトを構築します。  
  
```  
CD2DPathGeometry(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentTarget`  
 レンダー ターゲットへのポインター。  
  
 `bAutoDestroy`  
 所有者 (pParentTarget) によって、オブジェクトが破棄されることを示します。  
  
##  <a name="create"></a>CD2DPathGeometry::Create  
 CD2DPathGeometry を作成します。  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRenderTarget`  
 レンダー ターゲットへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="destroy"></a>CD2DPathGeometry::Destroy  
 CD2DPathGeometry オブジェクトを破棄します。  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DPathGeometry::Detach  
 オブジェクトからリソース インタ フェースをデタッチします。  
  
```  
ID2D1PathGeometry* Detach();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされたリソース インタ フェースへのポインター。  
  
##  <a name="getfigurecount"></a>CD2DPathGeometry::GetFigureCount  
 パス ジオメトリに数字の数を取得します。  
  
```  
int GetFigureCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 パス ジオメトリに数字の数を返します。  
  
##  <a name="getsegmentcount"></a>CD2DPathGeometry::GetSegmentCount  
 パス ジオメトリにセグメントの数を取得します。  
  
```  
int GetSegmentCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 パス ジオメトリにセグメントの数を返します。  
  
##  <a name="m_ppathgeometry"></a>CD2DPathGeometry::m_pPathGeometry  
 ID2D1PathGeometry へのポインター。  
  
```  
ID2D1PathGeometry* m_pPathGeometry;  
```  
  
##  <a name="open"></a>CD2DPathGeometry::Open  
 図形やセグメントのパス ジオメトリを作成するために使用する geometry シンクを取得します。  
  
```  
ID2D1GeometrySink* Open();
```  
  
### <a name="return-value"></a>戻り値  
 図形やセグメントのパス ジオメトリを設定に使用される ID2D1GeometrySink へのポインター。  
  
##  <a name="stream"></a>CD2DPathGeometry::Stream  
 指定した ID2D1GeometrySink にパス ジオメトリの内容をコピーします。  
  
```  
BOOL Stream(ID2D1GeometrySink* geometrySink);
```  
  
### <a name="parameters"></a>パラメーター  
 `geometrySink`  
 パス ジオメトリの内容のコピー先となるシンクです。 このシンクを変更しても、このパス ジオメトリの内容は変更されません。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、TRUE を返します。 それ以外の場合、FALSE を返します。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

