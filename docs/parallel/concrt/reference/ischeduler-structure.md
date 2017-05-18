---
title: "IScheduler 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IScheduler
- CONCRTRM/concurrency::IScheduler
- CONCRTRM/concurrency::IScheduler::IScheduler::AddVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::GetId
- CONCRTRM/concurrency::IScheduler::IScheduler::GetPolicy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyBusy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyIdle
- CONCRTRM/concurrency::IScheduler::IScheduler::RemoveVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::Statistics
dev_langs:
- C++
helpviewer_keywords:
- IScheduler structure
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
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
ms.openlocfilehash: 24305fbdded1709ec51270b3a29a239b345a5679
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

---
# <a name="ischeduler-structure"></a>IScheduler 構造体
作業スケジューラの抽象化のインターフェイスです。 同時実行ランタイムのリソース マネージャーは、このインターフェイスを使用して作業スケジューラと通信します。  
  
## <a name="syntax"></a>構文  
  
```
struct IScheduler;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Ischeduler::addvirtualprocessors](#addvirtualprocessors)|使用のため、仮想プロセッサ ルートのセットをスケジューラに提供します。 各`IVirtualProcessorRoot`インターフェイスはスケジューラのための作業を実行できる&1; つのスレッドを実行する権限を表します。|  
|[Ischeduler::getid](#getid)|スケジューラの一意の識別子を返します。|  
|[Ischeduler::getpolicy](#getpolicy)|スケジューラのポリシーのコピーを返します。 スケジューラ ポリシーの詳細については、次を参照してください。 [SchedulerPolicy](schedulerpolicy-class.md)します。|  
|[Ischeduler::notifyresourcesexternallybusy](#notifyresourcesexternallybusy)|ハードウェア スレッドが、配列内の仮想プロセッサ ルートのセットによって表されるこのスケジューラに通知`ppVirtualProcessorRoots`他のスケジューラによって使用されているようになりました。|  
|[Ischeduler::notifyresourcesexternallyidle](#notifyresourcesexternallyidle)|ハードウェア スレッドが、配列内の仮想プロセッサ ルートのセットによって表されるこのスケジューラに通知`ppVirtualProcessorRoots`他のスケジューラによって使用されていません。|  
|[Ischeduler::removevirtualprocessors](#removevirtualprocessors)|このスケジューラに以前割り当てられた仮想プロセッサ ルートの削除を開始します。|  
|[Ischeduler::statistics](#statistics)|タスクの到着から完了率、およびスケジューラのキューの長さの変更に関連する情報を提供します。|  
  
## <a name="remarks"></a>コメント  
 リソース マネージャーとの通信を行うカスタム スケジューラを実装する場合は、実装を提供する必要があります、`IScheduler`インターフェイスです。 このインターフェイスは、1 つの側のスケジューラとリソース マネージャー間の通信の双方向チャネルです。 もう一方の端がによって表される、`IResourceManager`と`ISchedulerProxy`リソース マネージャーでは実装されているインターフェイス。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IScheduler`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="addvirtualprocessors"></a>Ischeduler::addvirtualprocessors メソッド  
 使用のため、仮想プロセッサ ルートのセットをスケジューラに提供します。 各`IVirtualProcessorRoot`インターフェイスはスケジューラのための作業を実行できる&1; つのスレッドを実行する権限を表します。  
  
```
virtual void AddVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `ppVirtualProcessorRoots`  
 配列`IVirtualProcessorRoot`スケジューラに追加されている仮想プロセッサを表すインターフェイスのルートです。  
  
 `count`  
 数`IVirtualProcessorRoot`配列内のインターフェイスです。  
  
### <a name="remarks"></a>コメント  
 リソース マネージャーを起動、`AddVirtualProcessor`スケジューラの仮想プロセッサ ルートの最初のセットを許可するメソッドです。 スケジューラ間でリソースのバランスを再調整するときに、仮想プロセッサ ルートをスケジューラに追加するメソッドを呼び出すことこともできます。  
  
##  <a name="getid"></a>Ischeduler::getid メソッド  
 スケジューラの一意の識別子を返します。  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 一意の整数識別子です。  
  
### <a name="remarks"></a>コメント  
 使用する必要があります、 [GetSchedulerId](concurrency-namespace-functions.md)を実装するオブジェクトの一意の識別子を取得する関数、`IScheduler`インターフェイス、メソッドにパラメーターとしてインターフェイスを使用する前に、リソース マネージャーでの提供します。 同じ識別子を返す必要が場合に、`GetId`関数が呼び出されます。  
  
 別のソースから取得した識別子は、未定義の動作になる可能性があります。  
  
##  <a name="getpolicy"></a>Ischeduler::getpolicy メソッド  
 スケジューラのポリシーのコピーを返します。 スケジューラ ポリシーの詳細については、次を参照してください。 [SchedulerPolicy](schedulerpolicy-class.md)します。  
  
```
virtual SchedulerPolicy GetPolicy() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 スケジューラのポリシーのコピー。  
  
##  <a name="notifyresourcesexternallybusy"></a>Ischeduler::notifyresourcesexternallybusy メソッド  
 ハードウェア スレッドが、配列内の仮想プロセッサ ルートのセットによって表されるこのスケジューラに通知`ppVirtualProcessorRoots`他のスケジューラによって使用されているようになりました。  
  
```
virtual void NotifyResourcesExternallyBusy(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `ppVirtualProcessorRoots`  
 配列`IVirtualProcessorRoot`を他のスケジューラになっている使用中のハードウェア スレッドに関連付けられているインターフェイス。  
  
 `count`  
 数`IVirtualProcessorRoot`配列内のインターフェイスです。  
  
### <a name="remarks"></a>コメント  
 特定のハードウェア スレッドの同時に複数のスケジューラに割り当てることができます。 この理由の&1; つがないことは十分なハードウェア スレッド リソースを共有せずにすべてのスケジューラの最小の同時実行制御を満たすために、システム上にできます。 別の方法としては、リソースが所有しているスケジューラは使用しないときに、非アクティブ化してそのハードウェア スレッド上のすべての仮想プロセッサ ルートを使用して他のスケジューラに割り当てられる一時的です。  
  
 ハードウェア スレッドのサブスクリプション レベルがサブスクライブしているスレッドの数で示され、そのハードウェア スレッドに関連付けられている仮想プロセッサ ルートをアクティブにします。 特定のスケジューラの観点からは、ハードウェア スレッドの外部のサブスクリプション レベルは、その他のスケジューラが関与するサブスクリプションの部分です。 ハードウェア スレッドの外部のサブスクリプション レベルが正の値にゼロから離れるときに、スケジューラにリソースが外部でビジー状態である通知が送信されます。  
  
 スケジューラ ポリシーをこの方法による通知の送信先のみ位置の値、`MinConcurrency`ポリシー キーの値と等しく、`MaxConcurrency`ポリシー キー。 スケジューラ ポリシーの詳細については、次を参照してください。 [SchedulerPolicy](schedulerpolicy-class.md)します。  
  
 通知に対して認定されるスケジューラを取得初期通知のセットが作成されるときにだけに割り当てられているリソースが外部でビジー状態かアイドル状態かどうかを示すことです。  
  
##  <a name="notifyresourcesexternallyidle"></a>Ischeduler::notifyresourcesexternallyidle メソッド  
 ハードウェア スレッドが、配列内の仮想プロセッサ ルートのセットによって表されるこのスケジューラに通知`ppVirtualProcessorRoots`他のスケジューラによって使用されていません。  
  
```
virtual void NotifyResourcesExternallyIdle(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `ppVirtualProcessorRoots`  
 配列`IVirtualProcessorRoot`を他のスケジューラがアイドル状態になるハードウェア スレッドに関連付けられているインターフェイス。  
  
 `count`  
 数`IVirtualProcessorRoot`配列内のインターフェイスです。  
  
### <a name="remarks"></a>コメント  
 特定のハードウェア スレッドの同時に複数のスケジューラに割り当てることができます。 この理由の&1; つがないことは十分なハードウェア スレッド リソースを共有せずにすべてのスケジューラの最小の同時実行制御を満たすために、システム上にできます。 別の方法としては、リソースが所有しているスケジューラは使用しないときに、非アクティブ化してそのハードウェア スレッド上のすべての仮想プロセッサ ルートを使用して他のスケジューラに割り当てられる一時的です。  
  
 ハードウェア スレッドのサブスクリプション レベルがサブスクライブしているスレッドの数で示され、そのハードウェア スレッドに関連付けられている仮想プロセッサ ルートをアクティブにします。 特定のスケジューラの観点からは、ハードウェア スレッドの外部のサブスクリプション レベルは、その他のスケジューラが関与するサブスクリプションの部分です。 ハードウェア スレッドの外部のサブスクリプション レベルが以前の正の値からゼロになると、スケジューラにリソースが外部でビジー状態である通知が送信されます。  
  
 スケジューラ ポリシーをこの方法による通知の送信先のみ位置の値、`MinConcurrency`ポリシー キーの値と等しく、`MaxConcurrency`ポリシー キー。 スケジューラ ポリシーの詳細については、次を参照してください。 [SchedulerPolicy](schedulerpolicy-class.md)します。  
  
 通知に対して認定されるスケジューラを取得初期通知のセットが作成されるときにだけに割り当てられているリソースが外部でビジー状態かアイドル状態かどうかを示すことです。  
  
##  <a name="removevirtualprocessors"></a>Ischeduler::removevirtualprocessors メソッド  
 このスケジューラに以前割り当てられた仮想プロセッサ ルートの削除を開始します。  
  
```
virtual void RemoveVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `ppVirtualProcessorRoots`  
 配列`IVirtualProcessorRoot`を削除する仮想プロセッサ ルートを表すインターフェイスです。  
  
 `count`  
 数`IVirtualProcessorRoot`配列内のインターフェイスです。  
  
### <a name="remarks"></a>コメント  
 リソース マネージャーを起動、`RemoveVirtualProcessors`スケジューラからの仮想プロセッサ ルートのセットを実行するメソッドです。 呼び出す、スケジューラが期待どおり、[削除](iexecutionresource-structure.md#remove)仮想プロセッサ ルートで完了すると、各インターフェイスのメソッドです。 使用しないでください、`IVirtualProcessorRoot`インターフェイスが起動したら、`Remove`メソッドをします。  
  
 パラメーター`ppVirtualProcessorRoots`インターフェイスの配列を指します。 削除する仮想プロセッサ ルートのセット間のルートがアクティブ化されていないを使用してすぐに返される、`Remove`メソッドです。 アクティブになったいずれかの処理を実行中または非アクティブ化されているし、は、到着する作業を待機しているルートを非同期に返される必要があります。 スケジューラは、仮想プロセッサ ルートをできるだけ早く削除するすべての試行を行う必要があります。 仮想プロセッサ ルートの削除が遅れると、スケジューラ内でオーバー サブスクリプションを意図的でない可能性があります。  
  
##  <a name="statistics"></a>Ischeduler::statistics メソッド  
 タスクの到着から完了率、およびスケジューラのキューの長さの変更に関連する情報を提供します。  
  
```
virtual void Statistics(
    _Out_ unsigned int* pTaskCompletionRate,
    _Out_ unsigned int* pTaskArrivalRate,
    _Out_ unsigned int* pNumberOfTasksEnqueued) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pTaskCompletionRate`  
 このメソッドに最後に呼び出した後、スケジューラによって完了したタスクの数。  
  
 `pTaskArrivalRate`  
 このメソッドに最後に呼び出した後に、スケジューラ内で到着したタスクの数。  
  
 `pNumberOfTasksEnqueued`  
 すべてのスケジューラ キュー内のタスクの合計数。  
  
### <a name="remarks"></a>コメント  
 このメソッドには、スケジューラの統計情報を収集するために、リソース マネージャーでは呼び出されます。 ここで収集された統計情報は、動的なフィードバック アルゴリズムが適切にスケジューラに他のリソースを割り当てる場合およびリソースを解除する場合を判断するには使用されます。 スケジューラによって提供される値は、オプティミスティックできるあり、現在の数を正確に反映する必ずしも必要はありません。  
  
 リソース マネージャーで、スケジューラとリソース マネージャーに登録された他のスケジューラ間でリソースのバランスをとる方法を特定するタスクや到着としてなどについてのフィードバックを使用する場合は、このメソッドを実装する必要があります。 統計情報を収集しないように選択する場合は、ポリシーのキーを設定できます`DynamicProgressFeedback`値`DynamicProgressFeedbackDisabled`Manager が、スケジューラでは、このメソッドを呼び出せませんスケジューラのポリシー、およびリソースにします。  
  
 統計情報がない場合は、リソース マネージャーは、リソース割り当てと移行意思決定を行う、ハードウェア スレッドのサブスクリプション レベルを使用します。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)します。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [SchedulerPolicy クラス](schedulerpolicy-class.md)   
 [IExecutionContext 構造体](iexecutioncontext-structure.md)   
 [IThreadProxy 構造体](ithreadproxy-structure.md)   
 [IVirtualProcessorRoot 構造体](ivirtualprocessorroot-structure.md)   
 [IResourceManager 構造体](iresourcemanager-structure.md)

