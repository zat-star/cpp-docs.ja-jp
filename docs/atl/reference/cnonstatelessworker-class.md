---
title: "CNonStatelessWorker クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker::RequestType
- ATLUTIL/ATL::CNonStatelessWorker::Execute
- ATLUTIL/ATL::CNonStatelessWorker::Initialize
- ATLUTIL/ATL::CNonStatelessWorker::Terminate
dev_langs:
- C++
helpviewer_keywords:
- CNonStatelessWorker class
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 804b87bf752aac5cecf64cb61b4d53d6269963f2
ms.lasthandoff: 02/24/2017

---
# <a name="cnonstatelessworker-class"></a>CNonStatelessWorker クラス
スレッド プールからの要求を受信し、各要求の作成し、破棄がワーカー オブジェクトに渡します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class Worker>  
class CNonStatelessWorker
```  
  
#### <a name="parameters"></a>パラメーター  
 *作業者*  
 準拠しているワーカー スレッドのクラス、[ワーカー アーキタイプ](../../atl/reference/worker-archetype.md)キューに置かれた要求を処理するのに適した[CThreadPool](../../atl/reference/cthreadpool-class.md)します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CNonStatelessWorker::RequestType](#requesttype)|実装[WorkerArchetype::RequestType](worker-archetype.md#requesttype)します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CNonStatelessWorker::Execute](#execute)|実装[WorkerArchetype::Execute](worker-archetype.md#execute)します。|  
|[CNonStatelessWorker::Initialize](#initialize)|実装[WorkerArchetype::Initialize](worker-archetype.md#initialize)します。|  
|[CNonStatelessWorker::Terminate](#terminate)|実装[WorkerArchetype::Terminate](worker-archetype.md#terminate)します。|  
  
## <a name="remarks"></a>コメント  
 このクラスで使用するための単純なワーカー スレッドは、 [CThreadPool](../../atl/reference/cthreadpool-class.md)します。 このクラスは、独自の要求の処理機能を提供しません。 代わりに、1 つのインスタンスをインスタンス化*ワーカー*&1; 回の要求し、そのインスタンスにそのメソッドの実装のデリゲートします。  
  
 このクラスの利点は、既存のワーカー スレッド クラスの状態モデルを変更する便利な方法が提供されることです。 `CThreadPool`スレッドの有効期間の&1; つのワーカーを作成 worker クラスには、状態が保持している場合は、複数の要求間で保持してはようにします。 そのクラスをラップするだけで、`CNonStatelessWorker`テンプレートで使用する前に`CThreadPool`、作業者とは、単一の要求に制限を保持している状態の有効期間。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  
  
##  <a name="execute"></a>CNonStatelessWorker::Execute  
 実装[WorkerArchetype::Execute](worker-archetype.md#execute)します。  

  
```
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```  
  
### <a name="remarks"></a>コメント  
 このメソッドのインスタンスを作成、*ワーカー*スタックとの呼び出しにクラス[初期化](worker-archetype.md#initialize)そのオブジェクトにします。 初期化が成功した場合、このメソッドも呼び出します[Execute](worker-archetype.md#execute)と[Terminate](worker-archetype.md#terminate)同一のオブジェクトにします。  

  
##  <a name="initialize"></a>CNonStatelessWorker::Initialize  
 実装[WorkerArchetype::Initialize](worker-archetype.md#initialize)します。  
  
```
BOOL Initialize(void* /* pvParam */) throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 このクラス、初期化を行わない`Initialize`します。  
  
##  <a name="requesttype"></a>CNonStatelessWorker::RequestType  
 実装[WorkerArchetype::RequestType](worker-archetype.md#requesttype)します。  
  
```
typedef Worker::RequestType RequestType;
```  
  
### <a name="remarks"></a>コメント  
 このクラスは処理に使用されるクラスと同じ型の作業項目、*ワーカー*テンプレート パラメーター。 参照してください[CNonStatelessWorker 概要](../../atl/reference/cnonstatelessworker-class.md)詳細です。  
  
##  <a name="terminate"></a>CNonStatelessWorker::Terminate  
 実装[WorkerArchetype::Terminate](worker-archetype.md#terminate)します。  
  
```
void Terminate(void* /* pvParam */) throw();
```  
  
### <a name="remarks"></a>コメント  
 このクラス クリーンアップを行わない`Terminate`します。  
  
## <a name="see-also"></a>関連項目  
 [CThreadPool クラス](../../atl/reference/cthreadpool-class.md)   
 [ワーカーのアーキタイプ](../../atl/reference/worker-archetype.md)   
 [クラス](../../atl/reference/atl-classes.md)

