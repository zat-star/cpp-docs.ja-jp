---
title: "レジストリおよびタイプ ライブラリのグローバル関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- RegistryDataExchange function, global functions
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 9d454f2eac1b29785fe40a480fc43c7c34a861a3
ms.lasthandoff: 02/24/2017

---
# <a name="registry-and-typelib-global-functions"></a>レジストリとタイプ ライブラリに関するグローバル関数
これらの関数は、読み込みと登録のタイプ ライブラリのサポートを提供します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでは、次の表に示されている関数を使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
|||  
|-|-|  
|[AtlRegisterTypeLib](#atlregistertypelib)|この関数は、タイプ ライブラリを登録するために呼び出されます。|  
|[この代替](#atlunregistertypelib)|この関数はタイプ ライブラリの登録を解除するには|  
|[AtlLoadTypeLib](#atlloadtypelib)|この関数は、タイプ ライブラリを読み込むために呼び出されます。|  
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|この関数は、提供されたリソースのレジストリを更新するために呼び出されます。|  
|[RegistryDataExchange](#registrydataexchange)|システム レジストリのデータの読み取り/書き込みを行います。 によって呼び出される、[レジストリ Data Exchange マクロ](../../atl/reference/registry-data-exchange-macros.md)します。|  
  
 これらの関数は、情報を格納するプログラムを使用して、レジストリ内のどのノードを制御します。  
  
|||  
|-|-|  
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|アプリケーションがレジストリ アクセスをリダイレクトするかどうかを取得、 **HKEY_CURRENT_USER** ( **HKCU**) ノードです。|  
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|アプリケーションがレジストリ アクセスをリダイレクトするかどうかを設定、 **HKEY_CURRENT_USER** ( **HKCU**) ノードです。|  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h

## <a name="a-nameatlgetperuserregistrationa-atlgetperuserregistration"></a><a name="atlgetperuserregistration"></a>AtlGetPerUserRegistration
この関数を使用して、アプリケーションがレジストリ アクセスをリダイレクトするかどうかを判断、 **HKEY_CURRENT_USER** (**HKCU**) ノードです。  
  
### <a name="syntax"></a>構文  
  
```  
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `pEnabled`  
 `TRUE`レジストリ情報が転送されるかを示す、 **HKCU**ノードです。`FALSE`アプリケーションが既定のノードにレジストリ情報を書き出すことを示します。 既定のノードが**HKEY_CLASSES_ROOT** (**HKCR**)。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`メソッドが成功すると、それ以外の場合、`HRESULT`エラーが発生した場合のエラー コード。  
  
### <a name="remarks"></a>コメント  
 レジストリのリダイレクトは、既定では無効です。 このオプションを有効にすると、レジストリへのアクセスにリダイレクトされます**する**です。  
  
 リダイレクトはグローバルではありません。 MFC と ATL のフレームワークは、このレジストリのリダイレクトの影響を受けます。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  

##  <a name="a-nameatlregistertypeliba--atlregistertypelib"></a><a name="atlregistertypelib"></a>AtlRegisterTypeLib  
 この関数は、タイプ ライブラリを登録するために呼び出されます。  
  
  
```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstTypeLib`  
 モジュールのインスタンスへのハンドル。  
  
 `lpszIndex`  
 形式の文字列"\\\N"で、N はタイプ ライブラリのリソースの整数のインデックス。 インデックスが必要ない場合、NULL を設定できます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このヘルパー関数が利用[AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver)と[CAtlComModule::RegisterTypeLib](../../atl/reference/catlcommodule-class.md#registertypelib)します。  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h

## <a name="a-nameatlsetperuserregistrationa-atlsetperuserregistration"></a><a name="atlsetperuserregistration"></a>AtlSetPerUserRegistration
アプリケーションがレジストリ アクセスをリダイレクトするかどうかを設定、 **HKEY_CURRENT_USER** (**HKCU**) ノードです。  
  
### <a name="syntax"></a>構文  
  
```  
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`レジストリ情報が転送されるかを示す、 **HKCU**ノードです。`FALSE`アプリケーションが既定のノードにレジストリ情報を書き出すことを示します。 既定のノードが**HKEY_CLASSES_ROOT** (**HKCR**)。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`メソッドが成功すると、それ以外の場合、`HRESULT`エラーが発生した場合のエラー コード。  
  
### <a name="remarks"></a>コメント  
 レジストリのリダイレクトは、既定では無効です。 このオプションを有効にすると、レジストリへのアクセスにリダイレクトされます**する**です。  
  
 リダイレクトはグローバルではありません。 MFC と ATL のフレームワークは、このレジストリのリダイレクトの影響を受けます。  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  

##  <a name="a-nameatlunregistertypeliba--atlunregistertypelib"></a><a name="atlunregistertypelib"></a>この代替  
 この関数は、タイプ ライブラリの登録を解除するために呼び出されます。  
  
### <a name="syntax"></a>構文  
```
ATLAPI AtlUnRegisterTypeLib(
    HINSTANCE hInstTypeLib, 
    LPCOLESTR lpszIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstTypeLib`  
 モジュールのインスタンスへのハンドル。  
  
 `lpszIndex`  
 形式の文字列"\\\N"で、N はタイプ ライブラリのリソースの整数のインデックス。 インデックスが必要ない場合、NULL を設定できます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このヘルパー関数が利用[CAtlComModule::UnRegisterTypeLib](../../atl/reference/catlcommodule-class.md#unregistertypelib)と[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)します。  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h

##  <a name="a-nameatlloadtypeliba--atlloadtypelib"></a><a name="atlloadtypelib"></a>AtlLoadTypeLib  
 この関数は、タイプ ライブラリを読み込むために呼び出されます。  
  
### <a name="syntax"></a>構文  
```
ATLINLINE ATLAPI AtlLoadTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex,
    BSTR* pbstrPath,
    ITypeLib** ppTypeLib);
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstTypeLib`  
 タイプ ライブラリに関連付けられているモジュールへのハンドルします。  
  
 `lpszIndex`  
 形式の文字列"\\\N"で、N はタイプ ライブラリのリソースの整数のインデックス。 インデックスが必要ない場合、NULL を設定できます。  
  
 *pbstrPath*  
 正常に返された場合は、タイプ ライブラリに関連付けられているモジュールの完全なパスを格納します。  
  
 `ppTypeLib`  
 正常に返された場合は、読み込まれた型のライブラリへのポインターへのポインターを格納します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このヘルパー関数が利用[AtlRegisterTypeLib](#atlregistertypelib)と[この代替](#atlunregistertypelib)します。  
  
##  <a name="a-nameatlupdateregistryfromresourceda--atlupdateregistryfromresourced"></a><a name="atlupdateregistryfromresourced"></a>AtlUpdateRegistryFromResourceD  
 この関数は Visual Studio 2013 で使用されなくなり、Visual Studio 2015 で削除されます。  
  
```
<removed>
```  
  
### <a name="parameters"></a>パラメーター  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameregistrydataexchangea--registrydataexchange"></a><a name="registrydataexchange"></a>RegistryDataExchange  
 システム レジストリのデータの読み取り/書き込みを行います。  

### <a name="syntax"></a>構文  
```
HRESULT RegistryDataExchange(
    T* pT,
    enum RDXOperations rdxOp,
    void* pItem = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pT*  
 現在のオブジェクトへのポインター。  
  
 *rdxOp*  
 どちらの操作を示す列挙値関数を実行する必要があります。 許可される値の「解説」表を参照してください。  
  
 `pItem`  
 データの読み取りまたはレジストリに書き込まれるデータへのポインター。 データは、レジストリから削除するキーを表すこともできます。 既定値は NULL です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 マクロ[BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map)と[END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map)が呼び出す関数を拡張`RegistryDataExchange`します。  
  
 関数の操作を実行する必要がありますかを示す列挙値は、次の表に示します。  
  
|列挙値|操作|  
|----------------|---------------|  
|eReadFromReg|レジストリからデータを読み取ります。|  
|eWriteToReg|データをレジストリに書き込めません。|  
|eDeleteFromReg|キーがレジストリから削除します。|  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h

## <a name="see-also"></a>関連項目  
 [関数](atl-functions.md)
 [レジストリ Data Exchange マクロ](registry-data-exchange-macros.md)






