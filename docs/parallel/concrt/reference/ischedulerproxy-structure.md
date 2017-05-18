---
title: "ISchedulerProxy 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::BindContext
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::CreateOversubscriber
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::RequestInitialVirtualProcessors
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::Shutdown
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::SubscribeCurrentThread
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::UnbindContext
dev_langs:
- C++
helpviewer_keywords:
- ISchedulerProxy structure
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 3dd95150022ad94f50b456c84f7dacd2d3cef7c5
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

---
# <a name="ischedulerproxy-structure"></a>ISchedulerProxy 構造体
スケジューラは、このインターフェイスを使用して同時実行ランタイムのリソース マネージャーと通信して、リソース割り当てをネゴシエートします。  
  
## <a name="syntax"></a>構文  
  
```
struct ISchedulerProxy;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Ischedulerproxy::bindcontext](#bindcontext)|いずれかで関連付けられていない場合は、スレッド プロキシを実行コンテキストを関連付けます。|  
|[Ischedulerproxy::createoversubscriber](#createoversubscriber)|既存の実行リソースに関連付けられているハードウェア スレッドに新しい仮想プロセッサ ルートを作成します。|  
|[Ischedulerproxy::requestinitialvirtualprocessors](#requestinitialvirtualprocessors)|仮想プロセッサ ルートの最初の割り当てを要求します。 すべての仮想プロセッサ ルートでは、スケジューラの作業を実行できる&1; つのスレッドを実行する機能を表します。|  
|[Ischedulerproxy::shutdown](#shutdown)|スケジューラがシャット ダウンしているリソース マネージャーに通知します。 これは、結果、リソース マネージャーは、スケジューラに付与されるすべてのリソースを直ちに解放します。|  
|[Ischedulerproxy::subscribecurrentthread](#subscribecurrentthread)|このスケジューラに関連付けられた、リソース マネージャーで、現在のスレッドを登録します。|  
|[Ischedulerproxy::unbindcontext](#unbindcontext)|指定された実行コンテキストのスレッド プロキシの関連付けを解除、`pContext`パラメーター、スレッド プロキシ ファクトリの空きプールに返します。 このメソッドを使用してバインドされた実行コンテキストにのみ呼び出すことが、 [ischedulerproxy::bindcontext](#bindcontext)メソッド中でまだ開始されていないと、`pContext`のパラメーター、 [ithreadproxy::switchto](ithreadproxy-structure.md#switchto)メソッドの呼び出しです。|  
  
## <a name="remarks"></a>コメント  
 リソース マネージャーに渡して、`ISchedulerProxy`インターフェイスを使用して登録するすべてのスケジューラを[iresourcemanager::registerscheduler](iresourcemanager-structure.md#registerscheduler)メソッドです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ISchedulerProxy`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="bindcontext"></a>Ischedulerproxy::bindcontext メソッド  
 いずれかで関連付けられていない場合は、スレッド プロキシを実行コンテキストを関連付けます。  
  
```
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pContext`  
 実行コンテキストに関連付けるスレッド プロキシへのインターフェイス。  
  
### <a name="remarks"></a>コメント  
 通常、 [ithreadproxy::switchto](ithreadproxy-structure.md#switchto)メソッドでは、スレッド プロキシは要求時に実行コンテキストにバインドします。 、ただし、状況によってがいることを確認するには、事前にコンテキストにバインドする必要がある、`SwitchTo`メソッドが既にバインドされているコンテキストに切り替わります。 これは、UMS スケジュール コンテキストのメモリを割り当てるメソッドを呼び出すことができない場合であり、スレッド プロキシを工場出荷時の空きプールでスレッド プロキシがすぐに使用できない場合に、メモリの割り当てスレッド プロキシをバインド必要があります。  
  
 `invalid_argument`場合にスローされますが、パラメーター`pContext`プロパティ値を持つ`NULL`です。  
  
##  <a name="createoversubscriber"></a>Ischedulerproxy::createoversubscriber メソッド  
 既存の実行リソースに関連付けられているハードウェア スレッドに新しい仮想プロセッサ ルートを作成します。  
  
```
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pExecutionResource`  
 `IExecutionResource`オーバーサブスク ライブするハードウェア スレッドを表すインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 `IVirtualProcessorRoot` インターフェイス。  
  
### <a name="remarks"></a>コメント  
 スケジューラが一定期間の特定のハードウェア スレッドをオーバーサブスク ライブするときに、このメソッドを使用します。 完了すると、仮想プロセッサ ルートとする必要がありますに戻す、リソース マネージャーを呼び出して、[削除](iexecutionresource-structure.md#remove)メソッドを`IVirtualProcessorRoot`インターフェイスです。  
  
 既存の仮想プロセッサ ルートを oversubscribe でも、`IVirtualProcessorRoot`インターフェイスから継承、`IExecutionResource`インターフェイスです。  
  
##  <a name="requestinitialvirtualprocessors"></a>Ischedulerproxy::requestinitialvirtualprocessors メソッド  
 仮想プロセッサ ルートの最初の割り当てを要求します。 すべての仮想プロセッサ ルートでは、スケジューラの作業を実行できる&1; つのスレッドを実行する機能を表します。  
  
```
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `doSubscribeCurrentThread`  
 現在のスレッドを購読し、リソースの割り当て時に考慮するかどうか。  
  
### <a name="return-value"></a>戻り値  
 `IExecutionResource`インターフェイスの現在のスレッドの場合、パラメーター`doSubscribeCurrentThread`プロパティ値を持つ`true`です。 値の場合`false`、メソッドが返す`NULL`します。  
  
### <a name="remarks"></a>コメント  
 スケジューラは作業を実行する前に、リソース マネージャーからの仮想プロセッサ ルートを要求するのにこのメソッドを使用してください。 リソース マネージャーは、スケジューラのポリシーへのアクセスを使用して[ischeduler::getpolicy](ischeduler-structure.md#getpolicy)ポリシー キーの値を使用して`MinConcurrency`、`MaxConcurrency`と`TargetOversubscriptionFactor`を最初に、スケジューラに割り当てるハードウェア スレッドの数とすべてのハードウェア スレッドを作成する数の仮想プロセッサ ルートを決定します。 スケジューラ ポリシーを使用して、スケジューラの初期の割り当てを決定する方法の詳細については、次を参照してください。 [PolicyElementKey](concurrency-namespace-enums.md)します。  
  
 リソース マネージャーによってスケジューラにメソッドを呼び出すことによってリソースが割り当てられます。 [ischeduler::addvirtualprocessors](ischeduler-structure.md#addvirtualprocessors)仮想プロセッサ ルートの一覧です。 メソッドは、このメソッドが戻る前に、スケジューラにコールバックとして呼び出されます。  
  
 スケジューラが、パラメーターを設定して、現在のスレッドのサブスクリプションを要求されるかどうか`doSubscribeCurrentThread`に`true`、メソッドが戻る、`IExecutionResource`インターフェイスです。 使用して、後で、サブスクリプションを終了する必要があります、 [iexecutionresource::remove](iexecutionresource-structure.md#remove)メソッドです。  
  
 ハードウェア スレッドが選択されているかを判断する場合、リソース マネージャーはプロセッサ ノード アフィニティを最適化しようとします。 現在のスレッドのサブスクリプションが要求されると場合、は、このスケジューラに割り当てられた作業に参加しているつもりの現在のスレッドを示す値を勧めします。 このような場合は、割り当てられた仮想プロセッサ ルートは、現在のスレッドが可能であれば、実行するプロセッサ ノードに配置されます。  
  
 スレッドをサブスクライブは、基になるハードウェア スレッドのサブスクリプション レベルを&1; ずつ増加します。 サブスクリプションが終了した場合に、サブスクリプション レベルを&1; つ消費します。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)します。  
  
##  <a name="shutdown"></a>Ischedulerproxy::shutdown メソッド  
 スケジューラがシャット ダウンしているリソース マネージャーに通知します。 これは、結果、リソース マネージャーは、スケジューラに付与されるすべてのリソースを直ちに解放します。  
  
```
virtual void Shutdown() = 0;
```  
  
### <a name="remarks"></a>コメント  
 すべて`IExecutionContext`インターフェイスのメソッドを使用して外部のスレッドの購読の結果として受信したスケジューラ`ISchedulerProxy::RequestInitialVirtualProcessors`または`ISchedulerProxy::SubscribeCurrentThread`をリソース マネージャーを返す必要があるを使用して`IExecutionResource::Remove`スケジューラでは、自身をシャット ダウンする前にします。  
  
 いずれかの仮想プロセッサ ルートが非アクティブ化、スケジューラがあった場合は、それらをアクティブ化する必要がありますを使用して[ivirtualprocessorroot::activate](ivirtualprocessorroot-structure.md#activate)のままにして実行するスレッド プロキシがあると、`Dispatch`メソッドを呼び出す前に、ディスパッチする実行コンテキストのうち`Shutdown`スケジューラのプロキシにします。  
  
 スケジューラへの呼び出しによって付与リソース マネージャーを個別に返すすべての仮想プロセッサ ルートがする必要はありません、`Remove`メソッドすべての仮想プロセッサ ルートはシャット ダウン時にリソース マネージャーに返されるためです。  
  
##  <a name="subscribecurrentthread"></a>Ischedulerproxy::subscribecurrentthread メソッド  
 このスケジューラに関連付けられた、リソース マネージャーで、現在のスレッドを登録します。  
  
```
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 `IExecutionResource`ランタイムの現在のスレッドを表すインターフェイスです。  
  
### <a name="remarks"></a>コメント  
 リソース マネージャーで、スケジューラ、およびその他のスケジューラにリソースを割り当てているときに、現在のスレッドを考慮する場合は、このメソッドを使用します。 作業に参加するスレッドの計画は、スケジューラがリソース マネージャーからを受け取る仮想プロセッサ ルートと、スケジューラ キューに置かれたときに特に便利です。 リソース マネージャーでは、情報を使用して、システム上のハードウェア スレッドの不要なオーバー サブスクリプションを防止します。  
  
 リソース マネージャーにこのメソッドを使用して受信した実行リソースを返す必要があるを使用して、 [iexecutionresource::remove](iexecutionresource-structure.md#remove)メソッドです。 呼び出すスレッド、`Remove`メソッドは以前と呼ばれている同じスレッドである必要があります、`SubscribeCurrentThread`メソッドです。  
  
 スレッドをサブスクライブは、基になるハードウェア スレッドのサブスクリプション レベルを&1; ずつ増加します。 サブスクリプションが終了した場合に、サブスクリプション レベルを&1; つ消費します。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)します。  
  
##  <a name="unbindcontext"></a>Ischedulerproxy::unbindcontext メソッド  
 指定された実行コンテキストのスレッド プロキシの関連付けを解除、`pContext`パラメーター、スレッド プロキシ ファクトリの空きプールに返します。 このメソッドを使用してバインドされた実行コンテキストにのみ呼び出すことが、 [ischedulerproxy::bindcontext](#bindcontext)メソッド中でまだ開始されていないと、`pContext`のパラメーター、 [ithreadproxy::switchto](ithreadproxy-structure.md#switchto)メソッドの呼び出しです。  
  
```
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pContext`  
 スレッド プロキシとの関連付けを解除する実行コンテキスト。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [IScheduler 構造体](ischeduler-structure.md)   
 [IThreadProxy 構造体](ithreadproxy-structure.md)   
 [IVirtualProcessorRoot 構造体](ivirtualprocessorroot-structure.md)   
 [IResourceManager 構造体](iresourcemanager-structure.md)

