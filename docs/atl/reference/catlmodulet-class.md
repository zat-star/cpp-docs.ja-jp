---
title: "CAtlModuleT クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlModuleT
- ATLBASE/ATL::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::InitLibId
- ATLBASE/ATL::CAtlModuleT::RegisterAppId
- ATLBASE/ATL::CAtlModuleT::RegisterServer
- ATLBASE/ATL::CAtlModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlModuleT::UnregisterServer
- ATLBASE/ATL::CAtlModuleT::UpdateRegistryAppId
dev_langs:
- C++
helpviewer_keywords:
- CAtlModuleT class
ms.assetid: 9b74d02f-9117-47b1-a05e-c5945f83dd2b
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 9c0c6a2302932df06db7166d83fe9a561dfe38ac
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="catlmodulet-class"></a>CAtlModuleT クラス
このクラスは、ATL モジュールを実装します。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlModuleT : public CAtlModule
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス`CAtlModuleT`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlModuleT::CAtlModuleT](#catlmodulet)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlModuleT::InitLibId](#initlibid)|現在のモジュールの GUID を表すデータ メンバーを初期化します。|  
|[CAtlModuleT::RegisterAppId](#registerappid)|レジストリに、実行可能ファイルを追加します。|  
|[CAtlModuleT::RegisterServer](#registerserver)|レジストリにサービスを追加します。|  
|[CAtlModuleT::UnregisterAppId](#unregisterappid)|レジストリから、実行可能ファイルを削除します。|  
|[CAtlModuleT::UnregisterServer](#unregisterserver)|レジストリからサービスを削除します。|  
|[CAtlModuleT::UpdateRegistryAppId](#updateregistryappid)|レジストリの EXE の情報を更新します。|  
  
## <a name="remarks"></a>コメント  
 `CAtlModuleT`、から派生した[不要](../../atl/reference/catlmodule-class.md)、実行可能ファイル (EXE) またはサービス (EXE) ATL モジュールを実装します。 実行可能モジュールは、ローカルのアウト プロセス サーバー、サービス モジュールは Windows の起動時に、バック グラウンドで実行される Windows アプリケーションです。  
  
 `CAtlModuleT`初期化、登録、およびモジュールの登録を解除するには、サポートを提供します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  

  
 [不要](../../atl/reference/catlmodule-class.md)  
  
 `CAtlModuleT`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="catlmodulet"></a>CAtlModuleT::CAtlModuleT  
 コンストラクターです。  
  
```
CAtlModuleT() throw();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し[CAtlModuleT::InitLibId](#initlibid)します。  
  
##  <a name="initlibid"></a>CAtlModuleT::InitLibId  
 現在のモジュールの GUID を表すデータ メンバーを初期化します。  
  
```
static void InitLibId() throw();
```  
  
### <a name="remarks"></a>コメント  
 コンス トラクターによって呼び出される[CAtlModuleT::CAtlModuleT](#catlmodulet)します。  
  
##  <a name="registerappid"></a>CAtlModuleT::RegisterAppId  
 レジストリに、実行可能ファイルを追加します。  
  
```
HRESULT RegisterAppId() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="registerserver"></a>CAtlModuleT::RegisterServer  
 レジストリにサービスを追加します。  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bRegTypeLib`  
 タイプ ライブラリを登録する場合は TRUE です。 既定値は FALSE です。  
  
 `pCLSID`  
 登録されるオブジェクトの CLSID を指します。 NULL (既定値) の場合は、オブジェクト マップ内のすべてのオブジェクトを登録するかどうか。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="unregisterappid"></a>CAtlModuleT::UnregisterAppId  
 レジストリから、実行可能ファイルを削除します。  
  
```
HRESULT UnregisterAppId() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="unregisterserver"></a>CAtlModuleT::UnregisterServer  
 レジストリからサービスを削除します。  
  
```
HRESULT UnregisterServer(
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bUnRegTypeLib`  
 タイプ ライブラリが登録解除する場合は TRUE です。  
  
 `pCLSID`  
 登録解除するオブジェクトの CLSID を指します。 NULL (既定値) の場合は、オブジェクト マップ内のすべてのオブジェクトは、登録されているとなります。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="updateregistryappid"></a>CAtlModuleT::UpdateRegistryAppId  
 レジストリの EXE の情報を更新します。  
  
```
static HRESULT WINAPI UpdateRegistryAppId(BOOL /* bRegister*/) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bRegister`  
 予約済み。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
## <a name="see-also"></a>関連項目  
 [不要クラス](../../atl/reference/catlmodule-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [モジュール クラス](../../atl/atl-module-classes.md)

