---
title: "CComAutoThreadModule クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoThreadModule
- ATLBASE/ATL::CComAutoThreadModule
- ATLBASE/ATL::CreateInstance
- ATLBASE/ATL::GetDefaultThreads
- ATLBASE/ATL::Init
- ATLBASE/ATL::Lock
- ATLBASE/ATL::Unlock
- ATLBASE/ATL::dwThreadID
- ATLBASE/ATL::m_Allocator
- ATLBASE/ATL::m_nThreads
- ATLBASE/ATL::m_pApartments
dev_langs:
- C++
helpviewer_keywords:
- CComAutoThreadModule class
- apartment model modules
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
caps.latest.revision: 21
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
ms.openlocfilehash: 07aaf6dc7029452fa6822c5f5f1ae09b724ddc8b
ms.lasthandoff: 02/24/2017

---
# <a name="ccomautothreadmodule-class"></a>CComAutoThreadModule クラス
ATL 7.0 の時点で`CComAutoThreadModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class ThreadAllocator = CComSimpleThreadAllocator>  
class CComAutoThreadModule : public CComModule
```  
  
#### <a name="parameters"></a>パラメーター  
 `ThreadAllocator`  
 [in]スレッドの選択を管理するクラスです。 既定値は[CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)します。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CreateInstance](#createinstance)|スレッドを選択し、関連付けられているアパートメントでオブジェクトを作成します。|  
|[GetDefaultThreads](#getdefaultthreads)|(静的)プロセッサの数に基づくモジュールのスレッドの数を動的に計算します。|  
|[Init](#init)|モジュールのスレッドを作成します。|  
|[ロック](#lock)|モジュールと、現在のスレッドのロック カウントをインクリメントします。|  
|[ロックを解除します。](#unlock)|モジュールと、現在のスレッドのロックのカウントをデクリメントします。|  
  
### <a name="data-members"></a>データ メンバー  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[dwThreadID](#dwthreadid)|現在のスレッドの識別子が含まれています。|  
|[m_Allocator](#m_allocator)|スレッドの選択を管理します。|  
|[m_nThreads](#m_nthreads)|モジュールのスレッドの数が含まれています。|  
|[m_pApartments](#m_papartments)|モジュールのアパートメントを管理します。|  
  
## <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このクラスは、置き換えられました、[残さ](../../atl/reference/catlautothreadmodule-class.md)と[不要](../../atl/reference/catlmodule-class.md)クラスを派生します。 次の情報は、ATL の以前のリリースで使用します。  
  
 `CComAutoThreadModule`派生した[CComModule](../../atl/reference/ccommodule-class.md) Exe ファイルおよび Windows サービスのスレッドがプールされているアパートメント モデルの COM サーバーを実装します。 `CComAutoThreadModule`使用して[CComApartment](../../atl/reference/ccomapartment-class.md)モジュール内の各スレッド アパートメントを管理します。  
  
 モジュールからの派生`CComAutoThreadModule`複数アパートメント内でオブジェクトを作成する場合。 含める必要があります、 [DECLARE_CLASSFACTORY_AUTO_THREAD](http://msdn.microsoft.com/library/19d7105e-03e8-4412-9f5e-5384c8a5e18f)を指定するオブジェクトのクラス定義でマクロ[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)クラス ファクトリとして。  
  
 既定では、ATL COM AppWizard (Visual Studio .NET で ATL プロジェクト ウィザード) が継承する、モジュールから`CComModule`します。 使用する`CComAutoThreadModule`、クラス定義を変更します。 例:  
  
 [!code-cpp[NVC_ATL_AxHost&#2;](../../atl/codesnippet/cpp/ccomautothreadmodule-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [不要](../../atl/reference/catlmodule-class.md)  
  
 `IAtlAutoThreadModule`  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 [CComModule](../../atl/reference/ccommodule-class.md)  
  
 `CComAutoThreadModule`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="createinstance"></a>CComAutoThreadModule::CreateInstance  
 ATL 7.0 の時点で`CComAutoThreadModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
HRESULT CreateInstance(
    void* pfnCreateInstance,
    REFIID riid,
    void** ppvObj);
```  
  
### <a name="parameters"></a>パラメーター  
 *pfnCreateInstance*  
 [in]作成者関数へのポインター。  
  
 `riid`  
 [in]要求されたインターフェイスの IID です。  
  
 `ppvObj`  
 [out]によって識別されるインターフェイス ポインターへのポインター`riid`します。 オブジェクトがこのインターフェイスをサポートしていない場合`ppvObj`は NULL に設定します。  
  
### <a name="return-value"></a>戻り値  
 標準的な HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 スレッドを選択し、関連付けられているアパートメントでオブジェクトを作成します。  
  
##  <a name="dwthreadid"></a>CComAutoThreadModule::dwThreadID  
 ATL 7.0 の時点で`CComAutoThreadModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
DWORD dwThreadID;
```  
  
### <a name="remarks"></a>コメント  
 現在のスレッドの識別子が含まれています。  
  
##  <a name="getdefaultthreads"></a>CComAutoThreadModule::GetDefaultThreads  
 ATL 7.0 の時点で`CComAutoThreadModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>戻り値  
 EXE モジュール内に作成するスレッドの数。  
  
### <a name="remarks"></a>コメント  
 この静的関数は、プロセッサの数に基づいて、EXE モジュールのスレッドの最大数を動的に計算します。 既定では、この戻り値が渡される、 [Init](#init)スレッドを作成します。  
  
##  <a name="init"></a>CComAutoThreadModule::Init  
 ATL 7.0 の時点で`CComAutoThreadModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL,
    int nThreads = GetDefaultThreads());
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 [in]オブジェクト マップ エントリの配列へのポインター。  
  
 `h`  
 [in]`HINSTANCE`に渡される**DLLMain**または`WinMain`です。  
  
 `plibid`  
 [in]プロジェクトに関連付けられているタイプ ライブラリの LIBID へのポインター。  
  
 `nThreads`  
 [in]作成されるスレッドの数。 既定では、`nThreads`によって返される値は、 [GetDefaultThreads](#getdefaultthreads)します。  
  
### <a name="remarks"></a>コメント  
 データ メンバーは初期化され、数で指定されたスレッドの作成`nThreads`します。  
  
##  <a name="lock"></a>CComAutoThreadModule::Lock  
 ATL 7.0 の時点で`CComAutoThreadModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
LONG Lock();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役に立たないかテスト可能性のある値。  
  
### <a name="remarks"></a>コメント  
 モジュールと、現在のスレッドのロック カウントをインクリメントを実行します。 `CComAutoThreadModule`モジュールのロック カウントを使用して、クライアントがある場合は、モジュールにアクセスするかどうかを調べます。 現在のスレッドのロック カウントは、統計目的のために使用されます。  
  
##  <a name="m_allocator"></a>CComAutoThreadModule::m_Allocator  
 ATL 7.0 の時点で`CComAutoThreadModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
ThreadAllocator  m_Allocator;
```     
  
### <a name="remarks"></a>コメント  
 スレッドの選択を管理するオブジェクト。 既定では、`ThreadAllocator`クラス テンプレートのパラメーターが[CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)します。  
  
##  <a name="m_nthreads"></a>CComAutoThreadModule::m_nThreads  
 ATL 7.0 の時点で`CComAutoThreadModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
int m_nThreads;
```  
  
### <a name="remarks"></a>コメント  
 EXE モジュール内のスレッドの数が含まれています。 [Init](#init)が呼び出されると、`m_nThreads`に設定されている、`nThreads`パラメーターの値。 各スレッドの関連付けられているアパートメント、 [CComApartment](../../atl/reference/ccomapartment-class.md)オブジェクトです。  
  
##  <a name="m_papartments"></a>CComAutoThreadModule::m_pApartments  
 ATL 7.0 の時点で`CComAutoThreadModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
CComApartment* m_pApartments;
```  
  
### <a name="remarks"></a>コメント  
 配列を指す[CComApartment](../../atl/reference/ccomapartment-class.md)アパートメントにモジュールを管理するそれぞれのオブジェクト。 配列内の要素の数に基づいて、 [m_nThreads](#m_nthreads)メンバーです。  
  
##  <a name="unlock"></a>CComAutoThreadModule::Unlock  
 ATL 7.0 の時点で`CComAutoThreadModule`は今後使用しません。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはです。  
  
```
LONG Unlock();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役に立たないかテスト可能性のある値。  
  
### <a name="remarks"></a>コメント  
 モジュールと、現在のスレッドのロック カウントをデクリメントを実行します。 `CComAutoThreadModule`モジュールのロック カウントを使用して、クライアントがある場合は、モジュールにアクセスするかどうかを調べます。 現在のスレッドのロック カウントは、統計目的のために使用されます。  
  
 モジュールのロック カウントが&0; になったモジュールをアンロードできます。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [モジュール クラス](../../atl/atl-module-classes.md)

