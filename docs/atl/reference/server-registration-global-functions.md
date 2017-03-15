---
title: "サーバー登録のグローバル関数 |Microsoft ドキュメント"
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
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 4ace3bb50d824827071260e3f43cec3cda32742f
ms.lasthandoff: 02/24/2017

---
# <a name="server-registration-global-functions"></a>サーバー登録のグローバル関数
これらの関数は、登録およびオブジェクト マップ内のサーバー オブジェクトを登録解除のサポートを提供します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでは、次の表に示されている関数を使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
|||  
|-|-|  
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|オブジェクト マップのオブジェクトをすべて登録します。|  
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|オブジェクト マップのオブジェクトの登録をすべて解除します。|  
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|この関数は、クラス オブジェクトを登録するために呼び出されます。|  
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|この関数は COM モジュールのクラス オブジェクトを無効にします。|  
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|この関数はクラス オブジェクトを取得します。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
   
##  <a name="a-nameatlcommoduleregisterservera--atlcommoduleregisterserver"></a><a name="atlcommoduleregisterserver"></a>AtlComModuleRegisterServer  
 オブジェクト マップのオブジェクトをすべて登録します。  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>パラメーター  
 `pComModule`  
 COM モジュールへのポインター。  
  
 `bRegTypeLib`  
 タイプ ライブラリを登録する場合は TRUE です。  
  
 `pCLSID`  
 登録されるオブジェクトの CLSID を指します。 NULL の場合は、オブジェクト マップ内のすべてのオブジェクトが登録されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 `AtlComModuleRegisterServer`ATL の自動生成されたオブジェクトのマップおよびマップ内の各オブジェクトを登録します。 場合`pCLSID`が NULL の場合で参照されるオブジェクトのみ`pCLSID`が登録されている場合、それ以外の場合に登録されたすべてのオブジェクト。  
  
 この関数は[CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver)します。  
  
##  <a name="a-nameatlcommoduleunregisterservera--atlcommoduleunregisterserver"></a><a name="atlcommoduleunregisterserver"></a>AtlComModuleUnregisterServer  
 オブジェクト マップのオブジェクトの登録をすべて解除します。  
  
```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>パラメーター  
 `pComModule`  
 COM モジュールへのポインター。  
  
 `bUnRegTypeLib`  
 タイプ ライブラリを登録する場合は TRUE です。  
  
 `pCLSID`  
 登録解除するオブジェクトの CLSID を指します。 NULL の場合は、オブジェクト マップ内のすべてのオブジェクトは登録できません。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 `AtlComModuleUnregisterServer`ATL オブジェクト マップし、マップ内の各オブジェクトの登録を解除します。 場合`pCLSID`が NULL の場合で参照されるオブジェクトのみ`pCLSID`未登録以外の場合は、すべてのオブジェクトは登録を解除します。  
  
 この関数は[CAtlComModule::UnregisterServer](catlcommodule-class.md#unregisterserver)します。  
  
##  <a name="a-nameatlcommoduleregisterclassobjectsa--atlcommoduleregisterclassobjects"></a><a name="atlcommoduleregisterclassobjects"></a>AtlComModuleRegisterClassObjects  
 この関数は、クラス オブジェクトを登録するために呼び出されます。  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `pComModule`  
 COM モジュールへのポインター。  
  
 `dwClsContext`  
 クラスのオブジェクトが実行されるコンテキストを指定します。 使用可能な値は CLSCTX_INPROC_SERVER、CLSCTX_INPROC_HANDLER、または CLSCTX_LOCAL_SERVER です。 参照してください[CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716)詳細です。  
  
 `dwFlags`  
 クラス オブジェクトへの接続の種類を決定します。 使用可能な値は REGCLS_SINGLEUSE、REGCLS_MULTIPLEUSE、または REGCLS_MULTI_SEPARATE です。 参照してください[REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697)詳細です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このヘルパー関数が利用[CComModule::RegisterClassObjects](ccommodule-class.md#registerclassobjects) (ATL 7.0 では古い形式) と[CAtlExeModuleT::RegisterClassObjects](catlexemodulet-class.md#registerclassobjects)します。  
  
##  <a name="a-nameatlcommodulerevokeclassobjectsa--atlcommodulerevokeclassobjects"></a><a name="atlcommodulerevokeclassobjects"></a>AtlComModuleRevokeClassObjects  
 クラス ファクトリをランニング オブジェクト テーブルから削除します。  
  
```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```  
  
### <a name="parameters"></a>パラメーター  
 `pComModule`  
 COM モジュールへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このヘルパー関数が利用[CComModule::RevokeClassObjects](ccommodule-class.md#revokeclassobjects) (ATL 7.0 では古い形式) と[で](catlexemodulet-class.md#revokeclassobjects)します。  
  
##  <a name="a-nameatlcommodulegetclassobjecta--atlcommodulegetclassobject"></a><a name="atlcommodulegetclassobject"></a>AtlComModuleGetClassObject  
 この関数は、クラス ファクトリを返すために呼び出されます。  
  
```
ATLINLINE ATLAPI AtlComModuleGetClassObject(
    _ATL_COM_MODULE* pComModule,
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv);
```  
  
### <a name="parameters"></a>パラメーター  
 `pComModule`  
 COM モジュールへのポインター。  
  
 `rclsid`  
 作成するオブジェクトの CLSID。  
  
 `riid`  
 要求されたインターフェイスの IID です。  
  
 `ppv`  
 によって識別されるインターフェイス ポインターへのポインター`riid`します。 オブジェクトがこのインターフェイスをサポートしていない場合`ppv`は NULL に設定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このヘルパー関数が利用[CComModule::GetClassObject](ccommodule-class.md#getclassobject) (ATL 7.0 では古い形式) と[CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject)します。  
  
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)

