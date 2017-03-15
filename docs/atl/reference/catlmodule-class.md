---
title: "不要クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAtlModule
- CAtlModule
- ATL.CAtlModule
dev_langs:
- C++
helpviewer_keywords:
- CAtlModule class
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
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
ms.sourcegitcommit: 5a06fc417902378c88e2e65a9b51ee5e4356a39d
ms.openlocfilehash: 75cb5b42cd6c9de14d9abf09b20a1e23716f1149
ms.lasthandoff: 02/24/2017

---
# <a name="catlmodule-class"></a>不要クラス
このクラスは、いくつかの ATL モジュール クラスによって使用されるメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[不要](#catlmodule)|コンストラクターです。|  
|[不要:: ~ 不要](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)|ATL レジストリ コンポーネント (レジストラー) 置換マップにパラメーターを追加するには、このメソッドをオーバーライドします。|  
|[CAtlModule::AddTermFunc](#addtermfunc)|モジュールの終了時に呼び出される新しい関数を追加します。|  
|[CAtlModule::GetGITPtr](#getgitptr)|グローバル インターフェイス ポインターを返します。|  
|[CAtlModule::GetLockCount](#getlockcount)|ロック カウントを返します。|  
|[CAtlModule::Lock](#lock)|ロック カウントをインクリメントします。|  
|[CAtlModule::Term](#term)|すべてのデータ メンバーを解放します。|  
|[CAtlModule::Unlock](#unlock)|ロック カウントをデクリメントします。|  
|[して](#updateregistryfromresourced)|登録またはオブジェクトを登録解除に指定されたリソースに含まれるスクリプトを実行します。|  
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|このメソッドは`UpdateRegistryFromResourceD`レジストリの更新を実行します。|  
|[方法については](#updateregistryfromresources)|登録またはオブジェクトを登録解除に指定されたリソースに含まれるスクリプトを実行します。 このメソッドは、ATL レジストリ コンポーネントを静的にリンクします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlModule::m_libid](#m_libid)|現在のモジュールの GUID が含まれています。|  
|[されます](#m_pgit)|グローバル インターフェイス テーブルへのポインター。|  
  
## <a name="remarks"></a>コメント  
 このクラスは使用[CAtlDllModuleT クラス](../../atl/reference/catldllmodulet-class.md)、 [CAtlExeModuleT クラス](../../atl/reference/catlexemodulet-class.md)、および[CAtlServiceModuleT クラス](../../atl/reference/catlservicemodulet-class.md)それぞれアプリケーションの DLL、EXE アプリケーションおよび Windows サービスのサポートを提供します。  
  
 ATL でのモジュールの詳細については、次を参照してください。 [ATL モジュール クラス](../../atl/atl-module-classes.md)します。  
  
 このクラスは廃止された置換[CComModule クラス](../../atl/reference/ccommodule-class.md)ATL の以前のバージョンで使用されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 `CAtlModule`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="a-nameaddcommonrgsreplacementsa--catlmoduleaddcommonrgsreplacements"></a><a name="addcommonrgsreplacements"></a>CAtlModule::AddCommonRGSReplacements  
 ATL レジストリ コンポーネント (レジストラー) 置換マップにパラメーターを追加するには、このメソッドをオーバーライドします。  
  
```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 *pRegistrar*  
 予約済み。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 置き換え可能パラメーターを使用すると、レジストラーのクライアントを実行時のデータを指定します。 これを行うには、レジストラーをスクリプトに置き換え可能パラメーターに関連付けられている値を入力置換マップを保持します。 レジストラーでは、実行時にこれらのエントリを作成します。  
  
 トピックを参照して[置き換え可能パラメーターを使用して (レジストラーのプリプロセッサ)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)詳細です。  
  
##  <a name="a-nameaddtermfunca--catlmoduleaddtermfunc"></a><a name="addtermfunc"></a>CAtlModule::AddTermFunc  
 モジュールの終了時に呼び出される新しい関数を追加します。  
  
```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pFunc*  
 追加する関数へのポインター。  
  
 `dw`  
 ユーザー定義のデータは、関数に渡されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namecatlmodulea--catlmodulecatlmodule"></a><a name="catlmodule"></a>不要  
 コンストラクターです。  
  
```
CAtlModule() throw();
```  
  
### <a name="remarks"></a>コメント  
 データ メンバーを初期化し、モジュールのスレッド関連するクリティカル セクションを開始します。  
  
##  <a name="a-namedtora--catlmodulecatlmodule"></a><a name="dtor"></a>不要:: ~ 不要  
 デストラクターです。  
  
```
~CAtlModule() throw();
```  
  
### <a name="remarks"></a>コメント  
 すべてのデータ メンバーを解放します。  
  
##  <a name="a-namegetgitptra--catlmodulegetgitptr"></a><a name="getgitptr"></a>CAtlModule::GetGITPtr  
 グローバル インターフェイス テーブルへのポインターを取得します。  
  
```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ppGIT`  
 グローバル インターフェイス テーブルへのポインターを受け取る変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗した場合、エラー コードを返します。 場合は、正常が返されます。`ppGIT`が NULL です。  
  
### <a name="remarks"></a>コメント  
 グローバル インターフェイス テーブル オブジェクトが存在しない場合は、作成すると、メンバー変数にそのアドレスが格納されている[されます](#m_pgit)します。  
  
 場合はデバッグ ビルドで、アサーション エラーが発生`ppGIT`が NULL、またはグローバル インターフェイス テーブルのポインターを取得できない場合。  
  
 参照してください[については](http://msdn.microsoft.com/library/windows/desktop/ms678517)については、グローバル インターフェイス テーブルです。  
  
##  <a name="a-namegetlockcounta--catlmodulegetlockcount"></a><a name="getlockcount"></a>CAtlModule::GetLockCount  
 ロック カウントを返します。  
  
```
virtual LONG GetLockCount() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ロック カウントを返します。 この値は、診断に役立ちますし、デバッグを指定できます。  
  
##  <a name="a-namelocka--catlmodulelock"></a><a name="lock"></a>CAtlModule::Lock  
 ロック カウントをインクリメントします。  
  
```
virtual LONG Lock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ロック カウントをインクリメントし、更新後の値を返します。 この値は、診断に役立ちますし、デバッグを指定できます。  
  
##  <a name="a-namemlibida--catlmodulemlibid"></a><a name="m_libid"></a>CAtlModule::m_libid  
 現在のモジュールの GUID が含まれています。  
  
```
static GUID m_libid;
```  
  
##  <a name="a-namempgita--catlmodulempgit"></a><a name="m_pgit"></a>されます  
 グローバル インターフェイス テーブルへのポインター。  
  
```
IGlobalInterfaceTable* m_pGIT;
```  
  
##  <a name="a-nameterma--catlmoduleterm"></a><a name="term"></a>CAtlModule::Term  
 すべてのデータ メンバーを解放します。  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>コメント  
 すべてのデータ メンバーを解放します。 このメソッドは、デストラクターが呼び出されます。  
  
##  <a name="a-nameunlocka--catlmoduleunlock"></a><a name="unlock"></a>CAtlModule::Unlock  
 ロック カウントをデクリメントします。  
  
```
virtual LONG Unlock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ロック カウントをデクリメントし、更新後の値を返します。 この値は、診断に役立ちますし、デバッグを指定できます。  
  
##  <a name="a-nameupdateregistryfromresourceda--catlmoduleupdateregistryfromresourced"></a><a name="updateregistryfromresourced"></a>して  
 登録またはオブジェクトを登録解除に指定されたリソースに含まれるスクリプトを実行します。  
  
```
HRESULT WINAPI UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceD(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszRes`  
 リソース名です。  
  
 `nResID`  
 リソース id。  
  
 `bRegister`  
 **TRUE**場合は、オブジェクトを登録する必要があります。**FALSE**それ以外の場合。  
  
 `pMapEntries`  
 スクリプトの置き換え可能パラメーターに関連付けられている値を格納する置換マップへのポインター。 ATL は、モジュールの % を自動的に使用します。 その他の置き換え可能パラメーターを使用するのを参照してください。 [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)します。 それ以外の場合を使用して、 **NULL**既定値です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 指定されたリソースに含まれるスクリプトを実行*lpszRes または nResID*します。 場合`bRegister`は**TRUE**、このメソッドは、システム レジストリのオブジェクトを登録、それ以外の場合、レジストリからオブジェクトを削除します。  
  
 ATL レジストリ コンポーネント (レジストラー) を静的にリンクするには、次を参照してください。[方法については](#updateregistryfromresources)です。  
  
 このメソッドを呼び出す[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)と[IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister)します。  
  
##  <a name="a-nameupdateregistryfromresourcedhelpera--catlmoduleupdateregistryfromresourcedhelper"></a><a name="updateregistryfromresourcedhelper"></a>CAtlModule::UpdateRegistryFromResourceDHelper  
 このメソッドは`UpdateRegistryFromResourceD`レジストリの更新を実行します。  
  
```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(  
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszRes`  
 リソース名です。  
  
 `bRegister`  
 オブジェクトを登録するかどうかを示します。  
  
 `pMapEntries`  
 スクリプトの置き換え可能パラメーターに関連付けられている値を格納する置換マップへのポインター。 ATL は、モジュールの % を自動的に使用します。 その他の置き換え可能パラメーターを使用するのを参照してください。 [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)します。 それ以外の場合を使用して、 **NULL**既定値です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドの実装を提供する[として](#updateregistryfromresourced)します。  
  
##  <a name="a-nameupdateregistryfromresourcesa--catlmoduleupdateregistryfromresources"></a><a name="updateregistryfromresources"></a>方法については  
 登録またはオブジェクトを登録解除に指定されたリソースに含まれるスクリプトを実行します。 このメソッドは、ATL レジストリ コンポーネントを静的にリンクします。  
  
```
HRESULT WINAPI UpdateRegistryFromResourceS(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceS(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nResID`  
 リソース id。  
  
 `lpszRes`  
 リソース名です。  
  
 `bRegister`  
 リソースのスクリプトを登録するかどうかを示します。  
  
 `pMapEntries`  
 スクリプトの置き換え可能パラメーターに関連付けられている値を格納する置換マップへのポインター。 ATL は、モジュールの % を自動的に使用します。 その他の置き換え可能パラメーターを使用するのを参照してください。 [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)します。 それ以外の場合を使用して、 **NULL**既定値です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 ような[として](#updateregistryfromresourced)を除く`CAtlModule::UpdateRegistryFromResourceS`ATL レジストリ コンポーネント (レジストラー) への静的なリンクを作成します。  
  
## <a name="see-also"></a>関連項目  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [モジュール クラス](../../atl/atl-module-classes.md)   
 [レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)  

