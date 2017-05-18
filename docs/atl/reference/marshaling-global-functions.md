---
title: "グローバル関数をマーシャ リング |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
caps.latest.revision: 19
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
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: dd4b8d50ec69974b7b2af29438b1657e1ce592b4
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="marshaling-global-functions"></a>グローバル関数をマーシャ リング
これらの関数は、マーシャ リングとマーシャ リング データ インターフェイス ポインターに変換するためのサポートを提供します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでは、次の表に示されている関数を使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
|||  
|-|-|  
|[AtlFreeMarshalStream](#atlfreemarshalstream)|マーシャ リング データを解放し、`IStream`ポインター。|  
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|新しいストリーム オブジェクトを作成し、指定されたインターフェイス ポインターをマーシャ リングします。|  
|[AtlUnmarshalPtr](#atlunmarshalptr)|ストリームのマーシャ リング データをインターフェイス ポインターに変換します。|  
  
##  <a name="atlfreemarshalstream"></a>AtlFreeMarshalStream  
 ストリーム内のマーシャリング データを解放し、次にストリーム ポインターも解放します。  

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStream`  
 [in]ポインター、`IStream`マーシャ リングするために使用するストリームのインターフェイスです。  
  
### <a name="example"></a>例  
  例を参照してください[AtlMarshalPtrInProc](#atlmarshalptrinproc)します。  
  
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
 [in]マーシャ リングするインターフェイスへのポインター。  
  
 `iid`  
 [in]マーシャ リングされるインターフェイスの GUID です。  
  
 `ppStream`  
 [out]ポインター、`IStream`マーシャ リングに使用する新しいストリーム オブジェクトのインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 **MSHLFLAGS_TABLESTRONG**フラグが設定されて、ポインターは、複数のストリームにマーシャ リングできるようにします。 ポインターこともできないマーシャ リングされた複数回。  
  
 失敗をマーシャ リングする場合は、ストリーム ポインターが解放されます。  
  
 `AtlMarshalPtrInProc`プロセスでオブジェクトへのポインターでのみ使用できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&#50;](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]  
  
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
 [in]マーシャ リング解除されているストリームへのポインター。  
  
 `iid`  
 [in]マーシャ リング解除されているインターフェイスの GUID です。  
  
 `ppUnk`  
 [out]マーシャ リング解除されたインターフェイスへのポインター。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="example"></a>例  
  例を参照してください[AtlMarshalPtrInProc](#atlmarshalptrinproc)します。  
  
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)

