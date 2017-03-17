---
title: "IServiceProviderImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl::QueryService
dev_langs:
- C++
helpviewer_keywords:
- IServiceProviderImpl class
- IServiceProvider interface, ATL implementation
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
caps.latest.revision: 22
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 69a59fe23b3ca787dee86b1bbdc6775a44903f91
ms.lasthandoff: 02/24/2017

---
# <a name="iserviceproviderimpl-class"></a>IServiceProviderImpl クラス
このクラスの既定の実装を提供する、`IServiceProvider`インターフェイスです。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class ATL_NO_VTABLE IServiceProviderImpl : public IServiceProvider
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`IServiceProviderImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IServiceProviderImpl::QueryService](#queryservice)|作成または指定したサービスにアクセスし、サービスの指定したインターフェイスにインターフェイス ポインターを返します。|  
  
## <a name="remarks"></a>コメント  
 `IServiceProvider`インターフェイスは、その GUID で指定されたサービスを検索し、サービスに要求されたインターフェイスのインターフェイス ポインターを返します。 クラス`IServiceProviderImpl`このインターフェイスの既定の実装を提供します。  
  
 **IServiceProviderImpl**&1; つの方法を指定します。 [QueryService](#queryservice)、を作成または指定したサービスにアクセスおよびサービスの指定したインターフェイスにインターフェイス ポインターを返しますを実行します。  
  
 `IServiceProviderImpl`以降で、サービス マップを使用して[BEGIN_SERVICE_MAP](http://msdn.microsoft.com/library/3c6ae156-8776-4588-8227-2d234daec236)で終わる[END_SERVICE_MAP](http://msdn.microsoft.com/library/9a35d02a-014c-413a-bb0b-bcca11ab45a6)します。  
  
 サービス マップには、2 つのエントリが含まれています: [SERVICE_ENTRY](http://msdn.microsoft.com/library/e65ff9cc-15e8-41cf-b686-f99eb6686ca9)、オブジェクトでサポートされている、指定されたサービス id (SID) を示すと[SERVICE_ENTRY_CHAIN](http://msdn.microsoft.com/library/09be4ce4-3ccd-4ff2-a95e-a9d5275354c1)、呼び出し`QueryService`を別のオブジェクトのチェーンにします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IServiceProvider`  
  
 `IServiceProviderImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
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
 [クラスの概要](../../atl/atl-class-overview.md)

