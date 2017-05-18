---
title: "CAtlDllModuleT クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::DllCanUnloadNow
- ATLBASE/ATL::CAtlDllModuleT::DllGetClassObject
- ATLBASE/ATL::CAtlDllModuleT::DllMain
- ATLBASE/ATL::CAtlDllModuleT::DllRegisterServer
- ATLBASE/ATL::CAtlDllModuleT::DllUnregisterServer
- ATLBASE/ATL::CAtlDllModuleT::GetClassObject
dev_langs:
- C++
helpviewer_keywords:
- CAtlDllModuleT class
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 13cd0adb860660e06c92e8f02c07721ede391fb7
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="catldllmodulet-class"></a>CAtlDllModuleT クラス
このクラスは、DLL のモジュールを表します。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス`CAtlDllModuleT`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlDllModuleT::CAtlDllModuleT](#catldllmodulet)|コンストラクターです。|  
|[CAtlDllModuleT:: ~ CAtlDllModuleT](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlDllModuleT::DllCanUnloadNow](#dllcanunloadnow)|DLL をアンロードできるかどうか。|  
|[CAtlDllModuleT::DllGetClassObject](#dllgetclassobject)|クラス ファクトリを返します。|  
|[CAtlDllModuleT::DllMain](#dllmain)|ダイナミック リンク ライブラリ (DLL) への省略可能なエントリ ポイントです。|  
|[CAtlDllModuleT::DllRegisterServer](#dllregisterserver)|DLL 内のオブジェクトのシステム レジストリにエントリを追加します。|  
|[CAtlDllModuleT::DllUnregisterServer](#dllunregisterserver)|DLL 内のオブジェクトのシステム レジストリのエントリを削除します。|  
|[CAtlDllModuleT::GetClassObject](#getclassobject)|クラス ファクトリを返します。 によって呼び出された[DllGetClassObject](#dllgetclassobject)します。|  
  
## <a name="remarks"></a>コメント  
 `CAtlDllModuleT`ダイナミック リンク ライブラリ (DLL) については、モジュールを表し、すべての DLL プロジェクトで使用される関数を提供します。 この特殊化した[CAtlModuleT](../../atl/reference/catlmodulet-class.md)クラスには、登録のサポートが含まれています。  
  
 ATL でのモジュールの詳細については、次を参照してください。 [ATL モジュール クラス](../../atl/atl-module-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [不要](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlDllModuleT`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="catldllmodulet"></a>CAtlDllModuleT::CAtlDllModuleT  
 コンストラクターです。  
  
```
CAtlDllModuleT() throw();
```  
  
##  <a name="dtor"></a>CAtlDllModuleT:: ~ CAtlDllModuleT  
 デストラクターです。  
  
```
~CAtlDllModuleT() throw();
```  
  
##  <a name="dllcanunloadnow"></a>CAtlDllModuleT::DllCanUnloadNow  
 DLL をアンロードできるかどうか。  
  
```
HRESULT DllCanUnloadNow() throw();
```  
  
### <a name="return-value"></a>戻り値  
 できない場合は、DLL をアンロードすると、できる場合は S_OK または S_FALSE を返します。  
  
##  <a name="dllgetclassobject"></a>CAtlDllModuleT::DllGetClassObject  
 クラス ファクトリを返します。  
  
```
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rclsid`  
 作成するオブジェクトの CLSID。  
  
 `riid`  
 要求されたインターフェイスの IID です。  
  
 `ppv`  
 によって識別されるインターフェイス ポインターへのポインター`riid`します。 オブジェクトがこのインターフェイスをサポートしていない場合`ppv`は NULL に設定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="dllmain"></a>CAtlDllModuleT::DllMain  
 ダイナミック リンク ライブラリ (DLL) への省略可能なエントリ ポイントです。  
  
```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwReason`  
 場合に DLL_PROCESS_ATTACH、DLL_THREAD_ATTACH および DLL_THREAD_DETACH の通知呼び出しのセットが無効になります。  
  
 *lpReserved*  
 予約済み。  
  
### <a name="return-value"></a>戻り値  
 常に TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 DLL_THREAD_ATTACH と DLL_THREAD_DETACH を無効にすると通知の呼び出しは多くの Dll、Dll を持つでは、これらの添付ファイル/デタッチ スレッド レベルの通知は必要はありませんし、頻繁に作成して、スレッドを削除することがあるマルチ スレッド アプリケーションの有効な最適化を指定できます。  
  
##  <a name="dllregisterserver"></a>CAtlDllModuleT::DllRegisterServer  
 DLL 内のオブジェクトのシステム レジストリにエントリを追加します。  
  
```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bRegTypeLib`  
 タイプ ライブラリを登録する場合は TRUE です。 既定値は TRUE です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="dllunregisterserver"></a>CAtlDllModuleT::DllUnregisterServer  
 DLL 内のオブジェクトのシステム レジストリのエントリを削除します。  
  
```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bUnRegTypeLib`  
 タイプ ライブラリをレジストリから削除する場合は TRUE。 既定値は TRUE です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="getclassobject"></a>CAtlDllModuleT::GetClassObject  
 指定された CLSID のオブジェクトを作成します。  
  
```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rclsid`  
 作成するオブジェクトの CLSID。  
  
 `riid`  
 要求されたインターフェイスの IID です。  
  
 `ppv`  
 によって識別されるインターフェイス ポインターへのポインター`riid`します。 オブジェクトがこのインターフェイスをサポートしていない場合`ppv`は NULL に設定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは[CAtlDllModuleT::DllGetClassObject](#dllgetclassobject)と下位互換性のために用意されています。  
  
## <a name="see-also"></a>関連項目  
 [CAtlModuleT クラス](../../atl/reference/catlmodulet-class.md)   
 [CAtlExeModuleT クラス](../../atl/reference/catlexemodulet-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [モジュール クラス](../../atl/atl-module-classes.md)

