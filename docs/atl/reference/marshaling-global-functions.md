---
title: "グローバル関数をマーシャ リング |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlFreeMarshalStream
- atlbase/ATL::AtlMarshalPtrInProc
- atlbase/ATL::AtlUnmarshalPtr
dev_langs: C++
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a12f719d2cb893a5d2989a80f5fe09a5b49aeca2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="marshaling-global-functions"></a>マーシャ リングのグローバル関数
これらの関数は、マーシャ リングとのインターフェイス ポインターにマーシャ リング データを変換するためのサポートを提供します。  
  
> [!IMPORTANT]
>  次の表に示す関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
|||  
|-|-|  
|[AtlFreeMarshalStream](#atlfreemarshalstream)|マーシャ リング データを解放し、`IStream`ポインター。|  
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|新しいストリーム オブジェクトを作成し、指定されたインターフェイス ポインターをマーシャ リングします。|  
|[AtlUnmarshalPtr](#atlunmarshalptr)|インターフェイス ポインターには、ストリームのマーシャ リング データを変換します。|  

## <a name="requirements"></a>要件:
**ヘッダー:** atlbase.h
  
##  <a name="atlfreemarshalstream"></a>AtlFreeMarshalStream  
 ストリーム内のマーシャリング データを解放し、次にストリーム ポインターも解放します。  

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStream`  
 [in]ポインター、`IStream`マーシャ リングするために使用するストリーム上のインターフェイスです。  
  
### <a name="example"></a>例  
  例を参照して[AtlMarshalPtrInProc](#atlmarshalptrinproc)です。  
  
##  <a name="atlmarshalptrinproc"></a>AtlMarshalPtrInProc  
 新しいストリーム オブジェクトを作成し、プロキシの CLSID をストリームに書き込みます。さらに、プロキシの初期化に必要なデータをストリームに書き込んで、指定されたインターフェイス ポインターをマーシャリングします。  
  
```
HRESULT AtlMarshalPtrInProc(
    IUnknown* pUnk,
    const IID& iid,
    IStream** ppStream);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]マーシャ リングするためのインターフェイスへのポインター。  
  
 `iid`  
 [in]マーシャ リングされるインターフェイスの GUID です。  
  
 `ppStream`  
 [out]ポインター、`IStream`マーシャ リングに使用する、新しいストリーム オブジェクトのインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 **MSHLFLAGS_TABLESTRONG**フラグの設定されているため、複数のストリームにポインターをマーシャ リングすることができます。 ポインターもされませんマーシャ リングされた複数回できます。  
  
 失敗をマーシャ リングする場合にストリーム ポインターが解放されます。  
  
 `AtlMarshalPtrInProc`プロセスでオブジェクトへのポインターでのみ使用できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#50](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]  
  
##  <a name="atlunmarshalptr"></a>AtlUnmarshalPtr  
 ストリームのマーシャリング データをクライアントが使用できるインターフェイス ポインターに変換します。  
   
```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStream`  
 [in]マーシャ リングを解除されているストリームへのポインター。  
  
 `iid`  
 [in]マーシャ リングを解除されているインターフェイスの GUID です。  
  
 `ppUnk`  
 [out]マーシャ リングを解除インターフェイスへのポインター。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="example"></a>例  
  例を参照して[AtlMarshalPtrInProc](#atlmarshalptrinproc)です。  
  
## <a name="see-also"></a>参照  
 [関数](../../atl/reference/atl-functions.md)
