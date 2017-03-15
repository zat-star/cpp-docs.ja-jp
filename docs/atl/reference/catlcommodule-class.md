---
title: "CAtlComModule クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CAtlComModule
- CAtlComModule
- ATL::CAtlComModule
dev_langs:
- C++
helpviewer_keywords:
- CAtlComModule class
ms.assetid: af5dd71a-a0d1-4a2e-9a24-154a03381c75
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
ms.openlocfilehash: 6b933b5388fccc2dc0e31d035aa7eb56de3b1866
ms.lasthandoff: 02/24/2017

---
# <a name="catlcommodule-class"></a>CAtlComModule クラス
このクラスは、COM サーバー モジュールを実装します。  
  
## <a name="syntax"></a>構文  
  
```
class CAtlComModule : public _ATL_COM_MODULE
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlComModule::CAtlComModule](#catlcommodule)|コンストラクターです。|  
|[CAtlComModule:: ~ CAtlComModule](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlComModule::RegisterServer](#registerserver)|オブジェクト マップ内の各オブジェクトのシステム レジストリを更新するには、このメソッドを呼び出します。|  
|[CAtlComModule::RegisterTypeLib](#registertypelib)|タイプ ライブラリを登録するには、このメソッドを呼び出します。|  
|[CAtlComModule::UnregisterServer](#unregisterserver)|オブジェクト マップ内の各オブジェクトの登録を解除するには、このメソッドを呼び出します。|  
|[CAtlComModule::UnRegisterTypeLib](#unregistertypelib)|タイプ ライブラリの登録を解除するには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 `CAtlComModule`モジュールのコンポーネントにアクセスするクライアントは COM サーバー モジュールを実装します。  
  
 このクラスは廃止された置換[CComModule](../../atl/reference/ccommodule-class.md) ATL の以前のバージョンで使用されるクラス 参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)  
  
 `CAtlComModule`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="a-namecatlcommodulea--catlcommodulecatlcommodule"></a><a name="catlcommodule"></a>CAtlComModule::CAtlComModule  
 コンストラクターです。  
  
```
CAtlComModule() throw();
```  
  
### <a name="remarks"></a>コメント  
 モジュールを初期化します。  
  
##  <a name="a-namedtora--catlcommodulecatlcommodule"></a><a name="dtor"></a>CAtlComModule:: ~ CAtlComModule  
 デストラクターです。  
  
```
~CAtlComModule();
```  
  
### <a name="remarks"></a>コメント  
 すべてのクラス ファクトリを解放します。  
  
##  <a name="a-nameregisterservera--catlcommoduleregisterserver"></a><a name="registerserver"></a>CAtlComModule::RegisterServer  
 オブジェクト マップ内の各オブジェクトのシステム レジストリを更新するには、このメソッドを呼び出します。  
  
```
HRESULT RegisterServer(BOOL bRegTypeLib = FALSE, const CLSID* pCLSID = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `bRegTypeLib`  
 タイプ ライブラリを登録する場合は TRUE です。 既定値は FALSE です。  
  
 `pCLSID`  
 登録されるオブジェクトの CLSID を指します。 NULL (既定値) の場合は、オブジェクト マップ内のすべてのオブジェクトを登録するかどうか。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 グローバル関数を呼び出す[AtlComModuleRegisterServer](http://msdn.microsoft.com/library/d11a0c91-0c56-4b1b-a5f5-1287970f798b)します。  
  
##  <a name="a-nameregistertypeliba--catlcommoduleregistertypelib"></a><a name="registertypelib"></a>CAtlComModule::RegisterTypeLib  
 タイプ ライブラリを登録するには、このメソッドを呼び出します。  
  
```
HRESULT RegisterTypeLib(LPCTSTR lpszIndex);
HRESULT RegisterTypeLib();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszIndex`  
 形式の文字列"\\\N"で、N はタイプ ライブラリのリソースの整数のインデックス。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 タイプ ライブラリについての情報をシステム レジストリに追加します。 モジュールのインスタンスに複数のタイプ ライブラリが含まれている場合は、このメソッドの最初のバージョンを使用して、どのタイプ ライブラリを使用するかを指定します。  
  
##  <a name="a-nameunregisterservera--catlcommoduleunregisterserver"></a><a name="unregisterserver"></a>CAtlComModule::UnregisterServer  
 オブジェクト マップ内の各オブジェクトの登録を解除するには、このメソッドを呼び出します。  
  
```
HRESULT UnregisterServer(
  BOOL bRegTypeLib = FALSE,  
  const CLSID* pCLSID = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `bRegTypeLib`  
 タイプ ライブラリの登録解除する場合は TRUE です。 既定値は FALSE です。  
  
 `pCLSID`  
 登録解除するオブジェクトの CLSID を指します。 NULL (既定値) の場合は、オブジェクト マップ内のすべてのオブジェクトは、登録されているとなります。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 グローバル関数を呼び出す[AtlComModuleUnregisterServer](http://msdn.microsoft.com/library/c4ef3da4-def7-4aaf-b005-573a02e389d5)します。  
  
##  <a name="a-nameunregistertypeliba--catlcommoduleunregistertypelib"></a><a name="unregistertypelib"></a>CAtlComModule::UnRegisterTypeLib  
 タイプ ライブラリの登録を解除するには、このメソッドを呼び出します。  
  
```
HRESULT UnRegisterTypeLib(LPCTSTR lpszIndex);
HRESULT UnRegisterTypeLib();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszIndex`  
 形式の文字列"\\\N"で、N はタイプ ライブラリのリソースの整数のインデックス。  
  
### <a name="remarks"></a>コメント  
 システム レジストリからタイプ ライブラリに関する情報を削除します。 モジュールのインスタンスに複数のタイプ ライブラリが含まれている場合は、このメソッドの最初のバージョンを使用して、どのタイプ ライブラリを使用するかを指定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
## <a name="see-also"></a>関連項目  
 [_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)   
 [クラスの概要](../../atl/atl-class-overview.md)

