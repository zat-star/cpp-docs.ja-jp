---
title: "CAtlBaseModule クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAtlBaseModule
- ATL.CAtlBaseModule
- CAtlBaseModule
dev_langs:
- C++
helpviewer_keywords:
- CAtlBaseModule class
ms.assetid: 55ade80c-9b0c-4c51-933e-2158436c1096
caps.latest.revision: 18
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
ms.openlocfilehash: 4897f6cf7e12a18401720ad663c90491bb0e599d
ms.lasthandoff: 02/24/2017

---
# <a name="catlbasemodule-class"></a>CAtlBaseModule クラス
このクラスは、すべての ATL プロジェクトでインスタンス化します。  
  
## <a name="syntax"></a>構文  
  
```
class CAtlBaseModule : public _ATL_BASE_MODULE
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlBaseModule::CAtlBaseModule](#catlbasemodule)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlBaseModule::AddResourceInstance](#addresourceinstance)|格納されているハンドルの一覧に、リソースのインスタンスを追加します。|  
|[CAtlBaseModule::GetHInstanceAt](#gethinstanceat)|指定したリソースのインスタンスへのハンドルを返します。|  
|[CAtlBaseModule::GetModuleInstance](#getmoduleinstance)|モジュールのインスタンスを返す、`CAtlBaseModule`オブジェクトです。|  
|[CAtlBaseModule::GetResourceInstance](#getresourceinstance)|リソース インスタンスを返し、`CAtlBaseModule`オブジェクトです。|  
|[CAtlBaseModule::RemoveResourceInstance](#removeresourceinstance)|格納されているハンドルの一覧から、リソースのインスタンスを削除します。|  
|[CAtlBaseModule::SetResourceInstance](#setresourceinstance)|リソース インスタンスを設定、`CAtlBaseModule`オブジェクトです。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlBaseModule::m_bInitFailed](#m_binitfailed)|モジュールの初期化が失敗したかどうかを示す変数。|  
  
## <a name="remarks"></a>コメント  
 インスタンス`CAtlBaseModule`名前付き _AtlBaseModule がモジュールのインスタンスへのハンドル、リソース (既定では、1 つだけ) を含むモジュールと主要なリソースを提供するモジュールへのハンドルの配列へのハンドルを含むすべての ATL プロジェクトに存在します。 `CAtlBaseModule`複数のスレッドから安全にアクセスします。  
  
 このクラスは廃止された置換[CComModule](../../atl/reference/ccommodule-class.md) ATL の以前のバージョンで使用されるクラス  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)  
  
 `CAtlBaseModule`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcore.h  
  
##  <a name="a-nameaddresourceinstancea--catlbasemoduleaddresourceinstance"></a><a name="addresourceinstance"></a>CAtlBaseModule::AddResourceInstance  
 格納されているハンドルの一覧に、リソースのインスタンスを追加します。  
  
```
bool AddResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hInst`  
 追加するリソースのインスタンス。  
  
### <a name="return-value"></a>戻り値  
 リソースが正常にあれば true を返す、追加 false それ以外の場合。  
  
##  <a name="a-namecatlbasemodulea--catlbasemodulecatlbasemodule"></a><a name="catlbasemodule"></a>CAtlBaseModule::CAtlBaseModule  
 コンストラクターです。  
  
```
CAtlBaseModule() throw();
```  
  
### <a name="remarks"></a>コメント  
 `CAtlBaseModule` を作成します。  
  
##  <a name="a-namegethinstanceata--catlbasemodulegethinstanceat"></a><a name="gethinstanceat"></a>CAtlBaseModule::GetHInstanceAt  
 指定したリソースのインスタンスへのハンドルを返します。  
  
```
HINSTANCE GetHInstanceAt(int i) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *i*  
 リソースのインスタンスの数。  
  
### <a name="return-value"></a>戻り値  
 対応するリソース インスタンスが存在しない場合は、リソースのインスタンス、または NULL にハンドルを返します。  
  
##  <a name="a-namegetmoduleinstancea--catlbasemodulegetmoduleinstance"></a><a name="getmoduleinstance"></a>CAtlBaseModule::GetModuleInstance  
 モジュールのインスタンスを返す、`CAtlBaseModule`オブジェクトです。  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>戻り値  
 モジュールのインスタンスを返します。  
  
##  <a name="a-namegetresourceinstancea--catlbasemodulegetresourceinstance"></a><a name="getresourceinstance"></a>CAtlBaseModule::GetResourceInstance  
 リソースのインスタンスを返します。  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>戻り値  
 リソースのインスタンスを返します。  
  
##  <a name="a-namembinitfaileda--catlbasemodulembinitfailed"></a><a name="m_binitfailed"></a>CAtlBaseModule::m_bInitFailed  
 モジュールの初期化が失敗したかどうかを示す変数。  
  
```
static bool m_bInitFailed;
```  
  
### <a name="remarks"></a>コメント  
 モジュールが初期化されて、false の初期化に失敗した場合に true を返します。  
  
##  <a name="a-nameremoveresourceinstancea--catlbasemoduleremoveresourceinstance"></a><a name="removeresourceinstance"></a>CAtlBaseModule::RemoveResourceInstance  
 格納されているハンドルの一覧から、リソースのインスタンスを削除します。  
  
```
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hInst`  
 削除するリソースのインスタンス。  
  
### <a name="return-value"></a>戻り値  
 リソースがあった場合、false を正常に削除されたそれ以外の場合は true を返します。  
  
##  <a name="a-namesetresourceinstancea--catlbasemodulesetresourceinstance"></a><a name="setresourceinstance"></a>CAtlBaseModule::SetResourceInstance  
 リソース インスタンスを設定、`CAtlBaseModule`オブジェクトです。  
  
```
HINSTANCE SetResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hInst`  
 リソースの新しいインスタンス。  
  
### <a name="return-value"></a>戻り値  
 更新されたリソースのインスタンスを返します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [モジュール クラス](../../atl/atl-module-classes.md)

