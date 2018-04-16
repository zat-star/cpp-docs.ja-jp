---
title: "CAtlAutoThreadModuleT クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 082214794b2caa66e8be1127c664e0ffec18a394
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="catlautothreadmodulet-class"></a>CAtlAutoThreadModuleT クラス
このクラスは、スレッド プール、アパートメント モデルの COM サーバーを実装するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, 
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>  
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 COM サーバーを実装するクラスです。  
  
 `ThreadAllocator`  
 スレッドの選択を管理するクラスです。 既定値は[CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)です。  
  
 `dwWait`  
 タイムアウト間隔をミリ秒単位で指定します。 既定値は、無限で、決してメソッドのタイムアウト間隔が経過するとします。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|この静的関数は動的に計算し、プロセッサの数に基づいて、EXE モジュールのスレッドの最大数を返します。|  
  
## <a name="remarks"></a>コメント  
 クラス[残さ](../../atl/reference/catlautothreadmodule-class.md)から派生した`CAtlAutoThreadModuleT`スレッド プール、アパートメント モデルの COM サーバーを実装するためにします。 不使用のクラスが置き換えられます[は](../../atl/reference/ccomautothreadmodule-class.md)します。  
  
> [!NOTE]
>  既定値として、DLL にこのクラスが使用されない必要があります`dwWait`無限の値、DLL を読み込むときにデッドロックが発生します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IAtlAutoThreadModule`  
  
 `CAtlAutoThreadModuleT`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlbase.h  
  
##  <a name="getdefaultthreads"></a>CAtlAutoThreadModuleT::GetDefaultThreads  
 この静的関数は動的に計算し、プロセッサの数に基づいて、EXE モジュールのスレッドの最大数を返します。  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>戻り値  
 EXE モジュールで作成されるスレッドの数。  
  
### <a name="remarks"></a>コメント  
 スレッドの数を計算するための別の方法を使用する場合は、このメソッドをオーバーライドします。 既定では、スレッドの数は、プロセッサの数に基づきます。  
  
## <a name="see-also"></a>参照  
 [IAtlAutoThreadModule クラス](../../atl/reference/iatlautothreadmodule-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [IAtlAutoThreadModule クラス](../../atl/reference/iatlautothreadmodule-class.md)   
 [モジュール クラス](../../atl/atl-module-classes.md)
