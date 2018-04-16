---
title: "IProvideClassInfo2Impl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::GetClassInfo
- ATLCOM/ATL::IProvideClassInfo2Impl::GetGUID
- ATLCOM/ATL::IProvideClassInfo2Impl::_tih
dev_langs:
- C++
helpviewer_keywords:
- IProvideClassInfo2Impl class
- IProvideClassInfo2 ATL implementation
- class information, ATL
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6fe466608acaecfaf6219b6d15d27e0611ac2511
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="iprovideclassinfo2impl-class"></a>IProvideClassInfo2Impl クラス
このクラスの既定の実装を提供する、 [IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303)と[IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764)メソッドです。  
  
## <a name="syntax"></a>構文  
  
```
template <const CLSID* pcoclsid,
    const IID* psrcid,
    const GUID* plibid = &CAtlModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CComTypeInfoHolder>  
class ATL_NO_VTABLE IProvideClassInfo2Impl : public IProvideClassInfo2
```  
  
#### <a name="parameters"></a>パラメーター  
 *pcoclsid*  
 コクラスの識別子へのポインター。  
  
 *psrcid*  
 コクラスの既定のディスパッチ インターフェイスの送信の識別子へのポインター。  
  
 `plibid`  
 インターフェイスに関する情報を格納するタイプ ライブラリの LIBID へのポインター。 既定では、サーバー レベルのタイプ ライブラリが渡されます。  
  
 `wMajor`  
 タイプ ライブラリのメジャー バージョンです。 既定値は 1 です。  
  
 `wMinor`  
 タイプ ライブラリのマイナー バージョンです。 既定値は 0 です。  
  
 `tihclass`  
 コクラスの種類の情報を管理するために使用するクラスです。 既定値は `CComTypeInfoHolder` です。  
  
## <a name="members"></a>メンバー  
  
### <a name="constructors"></a>コンストラクター  
  
|name|説明|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|取得、 **ITypeInfo**コクラス型の情報へのポインター。|  
|[IProvideClassInfo2Impl::GetGUID](#getguid)|オブジェクトの送信のディスパッチ インターフェイスの GUID を取得します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::_tih](#_tih)|コクラスの型情報を管理します。|  
  
## <a name="remarks"></a>コメント  
 [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764)インターフェイスを拡張[IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303)追加することによって、`GetGUID`メソッドです。 このメソッドは、既定のイベント セットのオブジェクトの送信インターフェイス IID を取得するクライアントを使用します。 クラス`IProvideClassInfo2Impl`の既定の実装を提供、 **IProvideClassInfo**と`IProvideClassInfo2`メソッドです。  
  
 `IProvideClassInfo2Impl`型の静的メンバーを含む`CComTypeInfoHolder`コクラスの型情報を管理します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IProvideClassInfo2`  
  
 `IProvideClassInfo2Impl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcom.h  
  
##  <a name="getclassinfo"></a>IProvideClassInfo2Impl::GetClassInfo  
 取得、`ITypeInfo`コクラス型の情報へのポインター。  
  
```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IProvideClassInfo::GetClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms690192) Windows SDK にします。  
  
##  <a name="getguid"></a>IProvideClassInfo2Impl::GetGUID  
 オブジェクトの送信のディスパッチ インターフェイスの GUID を取得します。  
  
```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IProvideClassInfo2::GetGUID](http://msdn.microsoft.com/library/windows/desktop/ms679721) Windows SDK にします。  
  
##  <a name="iprovideclassinfo2impl"></a>IProvideClassInfo2Impl::IProvideClassInfo2Impl  
 コンストラクターです。  
  
```
IProvideClassInfo2Impl();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し`AddRef`上、 [_tih](#_tih)メンバー。 デストラクター**リリース**です。  
  
##  <a name="_tih"></a>IProvideClassInfo2Impl::_tih  
 この静的データ メンバーは、クラス テンプレート パラメーターのインスタンス`tihclass`、既定では、`CComTypeInfoHolder`です。  
  
```
static  tihclass
    _tih;
```     
  
### <a name="remarks"></a>コメント  
 `_tih`コクラスの型情報を管理します。  
  
## <a name="see-also"></a>参照  
 [クラスの概要](../../atl/atl-class-overview.md)
