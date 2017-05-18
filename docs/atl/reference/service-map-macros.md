---
title: "サービス マップ マクロ |Microsoft ドキュメント"
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
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: eea45a3315237c77eff0231d485111cefb8557cc
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="service-map-macros"></a>サービス マップ マクロ
これらのマクロは、サービス マップとエントリを定義します。  
  
|||  
|-|-|  
|[BEGIN_SERVICE_MAP](#begin_service_map)|ATL サービス マップの先頭をマークします。|  
|[END_SERVICE_MAP](#end_service_map)|ATL サービス マップの最後をマークします。|  
|[SERVICE_ENTRY](#service_entry)|オブジェクトが特定のサービス ID をサポートしていることを示します。|  
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|指示[IServiceProviderImpl::QueryService](#queryservice)指定したオブジェクトのチェーンにします。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
   
##  <a name="begin_service_map"></a>BEGIN_SERVICE_MAP  
 サービス マップの先頭をマークします。  
  
```
BEGIN_SERVICE_MAP(theClass)
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 [in]サービス マップを含むクラスを指定します。  
  
### <a name="remarks"></a>コメント  
 サービス マップを使用すると、COM オブジェクトでサービス プロバイダーの機能を実装します。 最初からクラスを派生する必要があります[IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md)します。 2 種類のエントリがあります。  
  
- [SERVICE_ENTRY](#service_entry)指定されたサービス ID (SID) のサポートを示します。  
  
- [SERVICE_ENTRY_CHAIN](#service_entry_chain)ように指示[IServiceProviderImpl::QueryService](#queryservice)チェーンを指定した別のオブジェクトにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&#57;](../../atl/codesnippet/cpp/service-map-macros_1.h)]  
  
##  <a name="end_service_map"></a>END_SERVICE_MAP  
 サービス マップの最後をマークします。  
  
```
END_SERVICE_MAP()
```  
  
### <a name="example"></a>例  
 例を参照してください[BEGIN_SERVICE_MAP](#begin_service_map)します。  
  
##  <a name="service_entry"></a>SERVICE_ENTRY  
 オブジェクトで指定されたサービス id をサポートしていることを示します*SID*します。  
  
```
SERVICE_ENTRY( SID )
```  
  
### <a name="parameters"></a>パラメーター  
 *SID*  
 サービス id です。  
  
### <a name="example"></a>例  
 例を参照してください[BEGIN_SERVICE_MAP](#begin_service_map)します。  
  
##  <a name="service_entry_chain"></a>SERVICE_ENTRY_CHAIN  
 指示[IServiceProviderImpl::QueryService](#queryservice)で指定したオブジェクトのチェーンを`punk`します。  
  
```
SERVICE_ENTRY_CHAIN( punk )
```  
  
### <a name="parameters"></a>パラメーター  
 `punk`  
 ポインター、 **IUnknown**チェーンにするインターフェイスです。  
  
### <a name="example"></a>例  
 例を参照してください[BEGIN_SERVICE_MAP](#begin_service_map)します。  
  
##  <a name="queryservice"></a>IServiceProviderImpl::QueryService  
 作成または指定したサービスにアクセスし、サービスの指定したインターフェイスにインターフェイス ポインターを返します。  
  
```
STDMETHOD(QueryService)( 
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 [IN]`guidService`  
 サービス id (SID) へのポインター。  
  
 [IN]`riid`  
 呼び出し元がアクセスできるインターフェイスの識別子です。  
  
 [出力].`ppvObj`  
 要求されたインターフェイスへの間接ポインター。  
  
### <a name="return-value"></a>戻り値  
 返された`HRESULT`値は、次のいずれか。  
  
|戻り値|説明|  
|------------------|-------------|  
|S_OK|サービスが正常に作成または取得します。|  
|E_INVALIDARG|1 つ以上の引数が無効です。|  
|E_OUTOFMEMORY|メモリは、サービスを作成するための十分なです。|  
|E_UNEXPECTED|不明なエラーが発生しました。|  
|E_NOINTERFACE|要求されたインターフェイスは、このサービスの一部ではないか、サービスが不明です。|  
  
### <a name="remarks"></a>コメント  
 `QueryService`指定されたサービスで要求されたインターフェイスへの間接ポインターを返します。 呼び出し元が必要でなくなったときに、このポインターを解放するためです。  
  
 呼び出すと`QueryService`、両方のサービスの識別子を渡す ( `guidService`) と、インターフェイス識別子 ( `riid`)。 `guidService` 、アクセス サービスを指定し、`riid`サービスの一部であるインターフェイスを識別します。 代わりに、インターフェイスへの間接ポインターが表示されます。  
  
 インターフェイスを実装するオブジェクトは、他のサービスの一部であるインターフェイスを実装も可能性があります。 次に例を示します。  
  
-   これらのインターフェイスの一部は、省略可能な可能性があります。 サービスの説明で定義されていないすべてのインターフェイスは、サービスのすべての実装または返されたすべてのオブジェクトとは限りません存在します。  
  
-   呼び出しとは異なり`QueryInterface`、別のサービスの識別子を渡すことは必ずしもその別のコンポーネント オブジェクト モデル (COM) オブジェクトが返されます。  
  
-   返されたオブジェクトは、サービスの定義の一部ではない追加のインターフェイスがあります。  
  
 SID_SMyService SID_SYourService などの&2; つの異なるサービス両方を指定できます同じインターフェイスの使用場合でも、何も&2; つのサービス間で共通のインターフェイスの実装があります。 この動作を呼び出す`QueryService`よりも、別のオブジェクトを返すことができます (SID_SMyService、IID_IDispatch) `QueryService` (SID_SYourService、IID_IDispatch)。 別のサービスの識別子を指定する場合は、オブジェクトの id は想定されません。  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)

