---
title: "IExecutionContext 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IExecutionContext
dev_langs:
- C++
helpviewer_keywords:
- IExecutionContext structure
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 5ad3f21e55371b904ac8a597a7a66d5c5deb8339
ms.lasthandoff: 02/24/2017

---
# <a name="iexecutioncontext-structure"></a>IExecutionContext 構造体
特定の仮想プロセッサで実行でき、協調的にコンテキストを切り替えることができる実行コンテキストへのインターフェイスです。  
  
## <a name="syntax"></a>構文  
  
```
struct IExecutionContext;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Iexecutioncontext::dispatch メソッド](#dispatch)|スレッド プロキシが特定の実行コンテキストの実行を開始するときに呼び出されるメソッド。 スケジューラのメイン ワーカー ルーチンがあります。|  
|[Iexecutioncontext::getid メソッド](#getid)|実行コンテキストの一意の識別子を返します。|  
|[Iexecutioncontext::getproxy メソッド](#getproxy)|このコンテキストを実行しているスレッド プロキシへのインターフェイスを返します。|  
|[Iexecutioncontext::getscheduler メソッド](#getscheduler)|この実行コンテキストが属するスケジューラへのインターフェイスを返します。|  
|[Iexecutioncontext::setproxy メソッド](#setproxy)|この実行コンテキストには、スレッド プロキシを関連付けます。 関連付けられたスレッド プロキシが、コンテキストの実行を開始する前に、このメソッドの権限を呼び出す`Dispatch`メソッドです。|  
  
## <a name="remarks"></a>コメント  
 カスタム スケジューラを同時実行ランタイムのリソース マネージャーでのインターフェイスを実装する場合を実装する必要があります、`IExecutionContext`インターフェイスです。 リソース マネージャーによって作成されたスレッドが実行することにより、スケジューラの代わりの作業を実行、`IExecutionContext::Dispatch`メソッドです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IExecutionContext`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namedispatcha--iexecutioncontextdispatch-method"></a><a name="dispatch"></a>Iexecutioncontext::dispatch メソッド  
 スレッド プロキシが特定の実行コンテキストの実行を開始するときに呼び出されるメソッド。 スケジューラのメイン ワーカー ルーチンがあります。  
  
```
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pDispatchState`  
 この実行コンテキストがディスパッチされる状態へのポインター。 ディスパッチの状態の詳細については、次を参照してください。 [DispatchState](dispatchstate-structure.md)します。  
  
##  <a name="a-namegetida--iexecutioncontextgetid-method"></a><a name="getid"></a>Iexecutioncontext::getid メソッド  
 実行コンテキストの一意の識別子を返します。  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 一意の整数識別子です。  
  
### <a name="remarks"></a>コメント  
 メソッドを使用する必要があります`GetExecutionContextId`を実装するオブジェクトの一意の識別子を取得する、`IExecutionContext`インターフェイス、メソッドにパラメーターとしてインターフェイスを使用する前に、リソース マネージャーでを指定します。 同じ識別子を返す必要が場合に、`GetId`関数が呼び出されます。  
  
 別のソースから取得した識別子は、未定義の動作になる可能性があります。  
  
##  <a name="a-namegetproxya--iexecutioncontextgetproxy-method"></a><a name="getproxy"></a>Iexecutioncontext::getproxy メソッド  
 このコンテキストを実行しているスレッド プロキシへのインターフェイスを返します。  
  
```
virtual IThreadProxy* GetProxy() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 `IThreadProxy` インターフェイス。 呼び出して、実行コンテキストのスレッド プロキシが初期化されていない場合`SetProxy`、関数が返す必要があります`NULL`します。  
  
### <a name="remarks"></a>コメント  
 リソース マネージャーを起動、`SetProxy`実行コンテキストのメソッドで、`IThreadProxy`インターフェイスを入力する前に、パラメーターとして、`Dispatch`メソッドをコンテキストにします。 この引数を格納して呼び出しで返すことが求め`GetProxy()`します。  
  
##  <a name="a-namegetschedulera--iexecutioncontextgetscheduler-method"></a><a name="getscheduler"></a>Iexecutioncontext::getscheduler メソッド  
 この実行コンテキストが属するスケジューラへのインターフェイスを返します。  
  
```
virtual IScheduler* GetScheduler() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 `IScheduler` インターフェイス。  
  
### <a name="remarks"></a>コメント  
 有効な実行コンテキストを初期化するために必要な`IScheduler`インターフェイスのメソッドにパラメーターとして使用する前に、リソース マネージャーでの提供します。  
  
##  <a name="a-namesetproxya--iexecutioncontextsetproxy-method"></a><a name="setproxy"></a>Iexecutioncontext::setproxy メソッド  
 この実行コンテキストには、スレッド プロキシを関連付けます。 関連付けられたスレッド プロキシが、コンテキストの実行を開始する前に、このメソッドの権限を呼び出す`Dispatch`メソッドです。  
  
```
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pThreadProxy`  
 入力されるスレッド プロキシへのインターフェイス、`Dispatch`この実行コンテキストのメソッドです。  
  
### <a name="remarks"></a>コメント  
 パラメーターを保存することを期待されて`pThreadProxy`への呼び出しに戻ると、`GetProxy`メソッドです。 リソース マネージャーは、スレッド プロキシが実行している間に、実行コンテキストに関連付けられているスレッド プロキシが変更されないことを保証、`Dispatch`メソッドです。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [IScheduler 構造体](ischeduler-structure.md)   
 [IThreadProxy 構造体](ithreadproxy-structure.md)

