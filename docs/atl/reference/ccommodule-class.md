---
title: "CComModule クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComModule
dev_langs:
- C++
helpviewer_keywords:
- CComModule class
- DLL modules [C++], ATL
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
caps.latest.revision: 23
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
ms.openlocfilehash: d2bd7566a25cd135cb541c4d90f2700b5f0d47b2
ms.lasthandoff: 02/24/2017

---
# <a name="ccommodule-class"></a>CComModule クラス
ATL 7.0 の時点で`CComModule`は使用されなくなりました。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CComModule : public _ATL_MODULE
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComModule::GetClassObject](#getclassobject)|指定された CLSID のオブジェクトを作成します。 Dll の場合のみです。|  
|[CComModule::GetModuleInstance](#getmoduleinstance)|`m_hInst` を返します。|  
|[CComModule::GetResourceInstance](#getresourceinstance)|`m_hInstResource` を返します。|  
|[CComModule::GetTypeLibInstance](#gettypelibinstance)|`m_hInstTypeLib` を返します。|  
|[できる](#init)|データ メンバーを初期化します。|  
|[CComModule::RegisterClassHelper](#registerclasshelper)|システム レジストリに、オブジェクトの標準的なクラスの登録を入力します。|  
|[CComModule::RegisterClassObjects](#registerclassobjects)|クラスのオブジェクトを登録します。 Exe だけです。|  
|[CComModule::RegisterServer](#registerserver)|オブジェクト マップ内の各オブジェクトのシステム レジストリを更新します。|  
|[CComModule::RegisterTypeLib](#registertypelib)|タイプ ライブラリを登録します。|  
|[CComModule::RevokeClassObjects](#revokeclassobjects)|クラス オブジェクトを削除します。 Exe だけです。|  
|[CComModule::Term](#term)|データ メンバーを解放します。|  
|[CComModule::UnregisterClassHelper](#unregisterclasshelper)|システム レジストリからオブジェクトの標準的なクラスの登録を削除します。|  
|[CComModule::UnregisterServer](#unregisterserver)|オブジェクト マップ内の各オブジェクトの登録を解除します。|  
|[CComModule::UpdateRegistryClass](#updateregistryclass)|登録するか、オブジェクトの標準的なクラスの登録の登録を解除します。|  
|[CComModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|登録またはオブジェクトを登録解除に指定されたリソースに含まれるスクリプトを実行します。|  
|[CComModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|ATL レジストリ コンポーネントを静的にリンクしています。 登録またはオブジェクトを登録解除に指定されたリソースに含まれるスクリプトを実行します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComModule::m_csObjMap](#m_csobjmap)|オブジェクト マップの情報への同期のアクセスを保証します。|  
|[CComModule::m_csTypeInfoHolder](#m_cstypeinfoholder)|タイプ ライブラリ情報への同期のアクセスを保証します。|  
|[CComModule::m_csWindowCreate](#m_cswindowcreate)|ウィンドウ クラスの情報をウィンドウの作成時に使用される静的データの同期のアクセスを保証します。|  
|[CComModule::m_hInst](#m_hinst)|モジュールのインスタンスを識別するハンドルが含まれています。|  
|[CComModule::m_hInstResource](#m_hinstresource)|既定では、モジュールのインスタンスを識別するハンドルが含まれています。|  
|[CComModule::m_hInstTypeLib](#m_hinsttypelib)|既定では、モジュールのインスタンスを識別するハンドルが含まれています。|  
|[CComModule::m_pObjMap](#m_pobjmap)|モジュールのインスタンスによって保持されるオブジェクトのマップへのポインター。|  
  
## <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このクラスは廃止され、これで ATL コード生成ウィザードを使用して、[残さ](../../atl/reference/catlautothreadmodule-class.md)と[不要](../../atl/reference/catlmodule-class.md)クラスを派生します。 参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。 ATL の以前のリリースで作成されたアプリケーションのために次の情報が、します。 `CComModule`まだ一部の ATL の旧バージョンと機能です。  
  
 `CComModule`モジュールのコンポーネントにアクセスするクライアントは COM サーバー モジュールを実装します。 `CComModule`(インプロセス) の DLL と EXE (ローカル) モジュールの両方をサポートしています。  
  
 A`CComModule`インスタンスは、オブジェクトのクラス定義のセットを維持するために、オブジェクトのマップを使用します。 このオブジェクトのマップの配列として実装`_ATL_OBJMAP_ENTRY`構造体、および情報について説明します。  
  
-   入力して、システム レジストリ内のオブジェクトの説明を削除します。  
  
-   クラス ファクトリを使用してオブジェクトをインスタンス化します。  
  
-   コンポーネントでは、クライアントと、ルート オブジェクト間の通信を確立します。  
  
-   クラス オブジェクトの有効期間管理を実行しています。  
  
 ATL COM AppWizard を実行すると、ウィザードは自動的に生成`_Module`のグローバル インスタンス`CComModule`またはその派生クラスです。 ATL プロジェクト ウィザードの詳細については、記事を参照してください。 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)します。  
  
 他に、 `CComModule`、ATL には、 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)Exe や Windows サービスに対するアパートメント モデルのモジュールを実装します。 モジュールからの派生`CComAutoThreadModule`複数アパートメント内でオブジェクトを作成する場合。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [不要](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CComModule`  
  
## <a name="requirements"></a>要件  
 `Header:`atlbase.h  
  
##  <a name="a-namegetclassobjecta--ccommodulegetclassobject"></a><a name="getclassobject"></a>CComModule::GetClassObject  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
HRESULT GetClassObject(  
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rclsid`  
 [in]作成するオブジェクトの CLSID。  
  
 `riid`  
 [in]要求されたインターフェイスの IID です。  
  
 `ppv`  
 [out]によって識別されるインターフェイス ポインターへのポインター`riid`します。 オブジェクトがこのインターフェイスをサポートしていない場合`ppv`に設定されている**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 指定された CLSID のオブジェクトを作成し、このオブジェクトへのインターフェイス ポインターを取得します。  
  
 `GetClassObject`Dll をできるだけです。  
  
##  <a name="a-namegetmoduleinstancea--ccommodulegetmoduleinstance"></a><a name="getmoduleinstance"></a>CComModule::GetModuleInstance  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>戻り値  
 `HINSTANCE`このモジュールを識別します。  
  
### <a name="remarks"></a>コメント  
 返します。、 [m_hInst](#m_hinst)データ メンバーです。  
  
##  <a name="a-namegetresourceinstancea--ccommodulegetresourceinstance"></a><a name="getresourceinstance"></a>CComModule::GetResourceInstance  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>戻り値  
 `HINSTANCE`。  
  
### <a name="remarks"></a>コメント  
 返します。、 [m_hInstResource](#m_hinstresource)データ メンバーです。  
  
##  <a name="a-namegettypelibinstancea--ccommodulegettypelibinstance"></a><a name="gettypelibinstance"></a>CComModule::GetTypeLibInstance  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
HINSTANCE GetTypeLibInstance() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 `HINSTANCE`。  
  
### <a name="remarks"></a>コメント  
 返します。、 [m_hInstTypeLib](#m_hinsttypelib)データ メンバーです。  
  
##  <a name="a-nameinita--ccommoduleinit"></a><a name="init"></a>できる  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 [in]オブジェクト マップ エントリの配列へのポインター。  
  
 `h`  
 [in]`HINSTANCE`に渡される**DLLMain**または`WinMain`です。  
  
 `plibid`  
 [in]プロジェクトに関連付けられているタイプ ライブラリの LIBID へのポインター。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 すべてのデータ メンバーを初期化します。  
  
##  <a name="a-namemcsobjmapa--ccommodulemcsobjmap"></a><a name="m_csobjmap"></a>CComModule::m_csObjMap  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
CRITICAL_SECTION m_csObjMap;
```  
  
### <a name="remarks"></a>コメント  
 オブジェクト マップの同期のアクセスを保証します。  
  
##  <a name="a-namemcstypeinfoholdera--ccommodulemcstypeinfoholder"></a><a name="m_cstypeinfoholder"></a>CComModule::m_csTypeInfoHolder  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
CRITICAL_SECTION m_csTypeInfoHolder;
```  
  
### <a name="remarks"></a>コメント  
 タイプ ライブラリへの同期のアクセスを保証します。  
  
##  <a name="a-namemcswindowcreatea--ccommodulemcswindowcreate"></a><a name="m_cswindowcreate"></a>CComModule::m_csWindowCreate  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
CRITICAL_SECTION m_csWindowCreate;
```  
  
### <a name="remarks"></a>コメント  
 ウィンドウ クラスの情報をウィンドウの作成時に使用される静的データの同期のアクセスを保証します。  
  
##  <a name="a-namemhinsta--ccommodulemhinst"></a><a name="m_hinst"></a>CComModule::m_hInst  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
HINSTANCE m_hInst;
```  
  
### <a name="remarks"></a>コメント  
 モジュールのインスタンスを識別するハンドルが含まれています。  
  
 [Init](#init)メソッド セット`m_hInst`に渡されるハンドルを**DLLMain**または`WinMain`です。  
  
##  <a name="a-namemhinstresourcea--ccommodulemhinstresource"></a><a name="m_hinstresource"></a>CComModule::m_hInstResource  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
HINSTANCE m_hInstResource;
```  
  
### <a name="remarks"></a>コメント  
 既定では、モジュールのインスタンスを識別するハンドルが含まれています。  
  
 [Init](#init)メソッド セット`m_hInstResource`に渡されるハンドルを**DLLMain**または`WinMain`です。 明示的に設定することができます`m_hInstResource`リソースへのハンドルにします。  
  
 [GetResourceInstance](#getresourceinstance)に格納されているハンドルを返します`m_hInstResource`します。  
  
##  <a name="a-namemhinsttypeliba--ccommodulemhinsttypelib"></a><a name="m_hinsttypelib"></a>CComModule::m_hInstTypeLib  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
HINSTANCE m_hInstTypeLib;
```  
  
### <a name="remarks"></a>コメント  
 既定では、モジュールのインスタンスを識別するハンドルが含まれています。  
  
 [Init](#init)メソッド セット`m_hInstTypeLib`に渡されるハンドルを**DLLMain**または`WinMain`です。 明示的に設定することができます`m_hInstTypeLib`にタイプ ライブラリを識別するハンドル。  
  
 [GetTypeLibInstance](#gettypelibinstance)に格納されているハンドルを返します`m_hInstTypeLib`します。  
  
##  <a name="a-namempobjmapa--ccommodulempobjmap"></a><a name="m_pobjmap"></a>CComModule::m_pObjMap  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```  
  
### <a name="remarks"></a>コメント  
 モジュールのインスタンスによって保持されるオブジェクトのマップへのポインター。  
  
##  <a name="a-nameregisterclasshelpera--ccommoduleregisterclasshelper"></a><a name="registerclasshelper"></a>CComModule::RegisterClassHelper  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
ATL_DEPRECATED HRESULT RegisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 [in]登録するオブジェクトの CLSID。  
  
 `lpszProgID`  
 [in]オブジェクトに関連付けられている ProgID です。  
  
 `lpszVerIndProgID`  
 [in]オブジェクトに関連付けられているバージョンに依存しない ProgID です。  
  
 `nDescID`  
 [in]オブジェクトの説明の文字列リソースの識別子です。  
  
 `dwFlags`  
 [in]レジストリに入力するスレッド処理モデルを指定します。 指定できる値は**THREADFLAGS_APARTMENT**、 **THREADFLAGS_BOTH**、または**AUTPRXFLAG**します。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 システム レジストリに、オブジェクトの標準的なクラスの登録を入力します。  
  
 [UpdateRegistryClass](#updateregistryclass)メソッドの呼び出し`RegisterClassHelper`します。  
  
##  <a name="a-nameregisterclassobjectsa--ccommoduleregisterclassobjects"></a><a name="registerclassobjects"></a>CComModule::RegisterClassObjects  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwClsContext`  
 [in]クラスのオブジェクトが実行されるコンテキストを指定します。 指定できる値は**CLSCTX_INPROC_SERVER**、 **CLSCTX_INPROC_HANDLER**、または**CLSCTX_LOCAL_SERVER**します。 これらの値については、次を参照してください。 [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `dwFlags`  
 [in]クラス オブジェクトへの接続の種類を決定します。 指定できる値は**REGCLS_SINGLEUSE**、 **REGCLS_MULTIPLEUSE**、または**REGCLS_MULTI_SEPARATE**します。 これらの値については、次を参照してください。 [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 その他のアプリケーションが接続できるように、OLE に EXE クラス オブジェクトを登録します。 このメソッドは、exe だけです。  
  
##  <a name="a-nameregisterservera--ccommoduleregisterserver"></a><a name="registerserver"></a>CComModule::RegisterServer  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,  
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bRegTypeLib`  
 [in]タイプ ライブラリを登録するかどうかを示します。 既定値は**FALSE**します。  
  
 `pCLSID`  
 [in]登録されるオブジェクトの CLSID を指します。 場合**NULL** (既定値) の場合は、オブジェクト マップ内のすべてのオブジェクトが登録されます。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 によって、`pCLSID`パラメーターが&1; つのクラス オブジェクトまたはオブジェクト マップ内のすべてのオブジェクトのシステムのレジストリを更新します。  
  
 場合`bRegTypeLib`は**TRUE**、タイプ ライブラリ情報も更新されます。  
  
 参照してください[は](http://msdn.microsoft.com/library/5a0f4fa5-0905-43d2-b337-e22f979c9e4c)オブジェクト マップにエントリを追加する方法の詳細。  
  
 `RegisterServer`によって自動的に呼び出される**DLLRegisterServer** dll または`WinMain`exe ファイルを使用して実行、 **/RegServer**コマンド ライン オプションです。  
  
##  <a name="a-nameregistertypeliba--ccommoduleregistertypelib"></a><a name="registertypelib"></a>CComModule::RegisterTypeLib  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszIndex`  
 [in]形式の文字列`"\\N"`ここで、`N`タイプ ライブラリのリソースの整数のインデックスです。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 タイプ ライブラリについての情報をシステム レジストリに追加します。  
  
 モジュールのインスタンスに複数のタイプ ライブラリが含まれている場合は、このメソッドの&2; 番目のバージョンを使用して、どのタイプ ライブラリを使用するかを指定します。  
  
##  <a name="a-namerevokeclassobjectsa--ccommodulerevokeclassobjects"></a><a name="revokeclassobjects"></a>CComModule::RevokeClassObjects  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 クラスのオブジェクトを削除します。 このメソッドは、exe だけです。  
  
##  <a name="a-nameterma--ccommoduleterm"></a><a name="term"></a>CComModule::Term  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>コメント  
 すべてのデータ メンバーを解放します。  
  
##  <a name="a-nameunregisterclasshelpera--ccommoduleunregisterclasshelper"></a><a name="unregisterclasshelper"></a>CComModule::UnregisterClassHelper  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
ATL_DEPRECATED HRESULT UnregisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 [in]登録解除するオブジェクトの CLSID。  
  
 `lpszProgID`  
 [in]オブジェクトに関連付けられている ProgID です。  
  
 `lpszVerIndProgID`  
 [in]オブジェクトに関連付けられているバージョンに依存しない ProgID です。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 システム レジストリからオブジェクトの標準的なクラスの登録を削除します。  
  
 [UpdateRegistryClass](#updateregistryclass)メソッドの呼び出し`UnregisterClassHelper`します。  
  
##  <a name="a-nameunregisterservera--ccommoduleunregisterserver"></a><a name="unregisterserver"></a>CComModule::UnregisterServer  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```  
  
### <a name="parameters"></a>パラメーター  
 `bUnRegTypeLib`  
 場合**TRUE**、タイプ ライブラリも登録されていません。  
  
 `pCLSID`  
 登録解除するオブジェクトの CLSID を指します。 場合**NULL** (既定値) の場合は、オブジェクト マップ内のすべてのオブジェクトが登録解除します。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 によって、`pCLSID`パラメーターを&1; つのクラス オブジェクトまたはオブジェクト マップ内のすべてのオブジェクトのいずれかの登録を解除します。  
  
 `UnregisterServer`によって自動的に呼び出される**DLLUnregisterServer** dll または`WinMain`exe ファイルを使用して実行、 **/UnregServer**コマンド ライン オプションです。  
  
 参照してください[は](http://msdn.microsoft.com/library/5a0f4fa5-0905-43d2-b337-e22f979c9e4c)オブジェクト マップにエントリを追加する方法の詳細。  
  
##  <a name="a-nameupdateregistryclassa--ccommoduleupdateregistryclass"></a><a name="updateregistryclass"></a>CComModule::UpdateRegistryClass  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
ATL_DEPRECATED HRESULT UpdateRegistryClass(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags,
    BOOL bRegister);

ATL_DEPRECATED HRESULT UpdateRegistryClass(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    LPCTSTR szDesc,
    DWORD dwFlags,
    BOOL bRegister);
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 登録または登録解除するオブジェクトの CLSID。  
  
 `lpszProgID`  
 オブジェクトに関連付けられている ProgID です。  
  
 `lpszVerIndProgID`  
 オブジェクトに関連付けられているバージョンに依存しない ProgID です。  
  
 `nDescID`  
 オブジェクトの説明の文字列リソースの識別子です。  
  
 `szDesc`  
 オブジェクトの説明を表す文字列。  
  
 `dwFlags`  
 レジストリに入力するスレッド処理モデルを指定します。 指定できる値は**THREADFLAGS_APARTMENT**、 **THREADFLAGS_BOTH**、または**AUTPRXFLAG**します。  
  
 `bRegister`  
 オブジェクトを登録するかどうかを示します。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 場合`bRegister`は**TRUE**、このメソッドは、システム レジストリに、オブジェクトの標準的なクラスの登録を入力します。  
  
 場合`bRegister`は**FALSE**オブジェクトの登録を削除します。  
  
 値に応じて`bRegister`、`UpdateRegistryClass`いずれかを呼び出して[RegisterClassHelper](#registerclasshelper)または[UnregisterClassHelper](#unregisterclasshelper)します。  
  
 指定して、 [DECLARE_REGISTRY](http://msdn.microsoft.com/library/89b8949b-5c27-4a9c-8a51-ad276bba3a54)マクロ、`UpdateRegistryClass`オブジェクト マップの処理時に自動的に起動されます。  
  
##  <a name="a-nameupdateregistryfromresourceda--ccommoduleupdateregistryfromresourced"></a><a name="updateregistryfromresourced"></a>CComModule::UpdateRegistryFromResourceD  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
virtual HRESULT UpdateRegistryFromResourceD(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceD(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw ();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszRes`  
 [in]リソース名です。  
  
 `nResID`  
 [in]リソース id。  
  
 `bRegister`  
 [in]オブジェクトを登録するかどうかを示します。  
  
 `pMapEntries`  
 [in]スクリプトの置き換え可能パラメーターに関連付けられている値を格納する置換マップへのポインター。 ATL では、自動的に`%MODULE%`します。 その他の置き換え可能パラメーターを使用するのには、詳細については、「解説」を参照してください。 それ以外の場合を使用して、 **NULL**既定値です。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 指定されたリソースに含まれるスクリプトを実行`lpszRes`または`nResID`です。  
  
 場合`bRegister`は**TRUE**、このメソッドは、システム レジストリのオブジェクトを登録、それ以外の場合、オブジェクトは登録されません。  
  
 指定して、[に](http://msdn.microsoft.com/library/7ac11498-8ee2-4156-8df2-7076f7ddda8b)または[代入](http://msdn.microsoft.com/library/65bf3576-5396-416e-ba48-e14b3236c49b)マクロ、`UpdateRegistryFromResourceD`オブジェクト マップの処理時に自動的に起動されます。  
  
> [!NOTE]
>  実行時に置換値を置き換えるには指定しないで、`DECLARE_REGISTRY_RESOURCE`または`DECLARE_REGISTRY_RESOURCEID`マクロです。 配列を作成する代わりに、**結果**実行時に、プレース ホルダーを置換対象の値と共に、構造、各エントリに変数のプレース ホルダーが含まれています。 まず`UpdateRegistryFromResourceD`の配列を渡す、`pMapEntries`パラメーター。 これにより、追加のすべての置換値、**結果**レジストラーの置換のマップの構造体。  
  
> [!NOTE]
>  ATL レジストリ コンポーネント (レジストラー) を静的にリンクするには、次を参照してください。[次](#updateregistryfromresources)します。  
  
 置き換え可能パラメーターとスクリプトの詳細については、記事を参照してください。 [ATL レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)します。  
  
##  <a name="a-nameupdateregistryfromresourcesa--ccommoduleupdateregistryfromresources"></a><a name="updateregistryfromresources"></a>CComModule::UpdateRegistryFromResourceS  
 ATL 7.0 の時点で`CComModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
virtual HRESULT UpdateRegistryFromResourceS(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceS(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszRes`  
 [in]リソース名です。  
  
 `nResID`  
 [in]リソース id。  
  
 `bRegister`  
 [in]リソースのスクリプトを登録するかどうかを示します。  
  
 `pMapEntries`  
 [in]スクリプトの置き換え可能パラメーターに関連付けられている値を格納する置換マップへのポインター。 ATL では、自動的に`%MODULE%`します。 その他の置き換え可能パラメーターを使用するのには、詳細については、「解説」を参照してください。 それ以外の場合を使用して、 **NULL**既定値です。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 ような[ため](#updateregistryfromresourced)を除く`UpdateRegistryFromResourceS`ATL レジストリ コンポーネント (レジストラー) への静的なリンクを作成します。  
  
 `UpdateRegistryFromResourceS`呼び出される自動的にオブジェクト マップの処理時に追加する指定`#define _ATL_STATIC_REGISTRY`stdafx.h にします。  
  
> [!NOTE]
>  実行時に置換値を置き換えるには指定しないで、[に](http://msdn.microsoft.com/library/7ac11498-8ee2-4156-8df2-7076f7ddda8b)または[代入](http://msdn.microsoft.com/library/65bf3576-5396-416e-ba48-e14b3236c49b)マクロです。 配列を作成する代わりに、**結果**実行時に、プレース ホルダーを置換対象の値と共に、構造、各エントリに変数のプレース ホルダーが含まれています。 まず`UpdateRegistryFromResourceS`の配列を渡す、`pMapEntries`パラメーター。 これにより、追加のすべての置換値、**結果**レジストラーの置換のマップの構造体。  
  
 置き換え可能パラメーターとスクリプトの詳細については、記事を参照してください。 [ATL レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

