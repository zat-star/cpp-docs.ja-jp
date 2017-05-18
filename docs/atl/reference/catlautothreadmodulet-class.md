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
caps.latest.revision: 20
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
ms.openlocfilehash: 86b35f0a6a3ab43c170ee710838ec9ba0e2fc5b0
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="catlautothreadmodulet-class"></a>CAtlAutoThreadModuleT クラス
このクラスは、スレッドがプールされているアパートメント モデルの COM サーバーを実装するためのメソッドを提供します。  
  
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
 スレッドの選択を管理するクラスです。 既定値は[CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)します。  
  
 `dwWait`  
 タイムアウト間隔をミリ秒単位で指定します。 既定値は、無限で、決してメソッドのタイムアウト間隔が経過するとします。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|この静的関数は動的に計算し、プロセッサの数に基づいて、EXE モジュールのスレッドの最大数を返します。|  
  
## <a name="remarks"></a>コメント  
 クラス[残さ](../../atl/reference/catlautothreadmodule-class.md)から派生した`CAtlAutoThreadModuleT`スレッドがプールされているアパートメント モデルの COM サーバーを実装するためにします。 廃止されたクラスを置き換えるもの[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)します。  
  
> [!NOTE]
>  既定値として、DLL 内でこのクラスが使用されない必要があります`dwWait`無限の値、DLL を読み込むときにデッドロックが発生します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IAtlAutoThreadModule`  
  
 `CAtlAutoThreadModuleT`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="getdefaultthreads"></a>CAtlAutoThreadModuleT::GetDefaultThreads  
 この静的関数は動的に計算し、プロセッサの数に基づいて、EXE モジュールのスレッドの最大数を返します。  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>戻り値  
 EXE モジュール内に作成するスレッドの数。  
  
### <a name="remarks"></a>コメント  
 スレッドの数を計算するため、別の方法を使用する場合は、このメソッドをオーバーライドします。 既定では、スレッドの数をプロセッサの数に基づきます。  
  
## <a name="see-also"></a>関連項目  
 [IAtlAutoThreadModule クラス](../../atl/reference/iatlautothreadmodule-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [IAtlAutoThreadModule クラス](../../atl/reference/iatlautothreadmodule-class.md)   
 [モジュール クラス](../../atl/atl-module-classes.md)

