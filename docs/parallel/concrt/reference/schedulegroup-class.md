---
title: "ScheduleGroup クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::ScheduleGroup
dev_langs:
- C++
helpviewer_keywords:
- ScheduleGroup class
ms.assetid: 86d380ff-f2e8-411c-b1a8-22bd3079824a
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
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 424b2f53f39bce57c85e44f0df54928acdac399a
ms.lasthandoff: 02/24/2017

---
# <a name="schedulegroup-class"></a>ScheduleGroup クラス
スケジュール グループの抽象化を表します。 スケジュール グループは、(別のグループに移動する前に同じグループ内の別のタスクを実行することで) 一時的に、または (同じ NUMA ノードまたは物理ソケットの同じグループ内の複数の項目を実行することにより) 空間的に、短い間隔でスケジュールするとメリットがある関連作業のセットを編成します。  
  
## <a name="syntax"></a>構文  
  
```
class ScheduleGroup;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[~ ScheduleGroup デストラクター](#dtor)||  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Id メソッド](#id)|スケジュール グループが属するスケジューラ内で一意のスケジュール グループの識別子を返します。|  
|[Reference メソッド](#reference)|スケジュール グループの参照カウントをインクリメントします。|  
|[Release メソッド](#release)|スケジュール グループの参照カウントをデクリメントします。|  
|[ScheduleTask メソッド](#scheduletask)|スケジュール グループ内の軽量タスクをスケジュールします。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ScheduleGroup`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-nameida-id"></a><a name="id"></a>Id 

 スケジュール グループが属するスケジューラ内で一意のスケジュール グループの識別子を返します。  
  
```
virtual unsigned int Id() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 グループが属するスケジューラ内で一意では、スケジュール グループの識別子です。  
  
##  <a name="a-nameoperatordeletea-operator-delete"></a><a name="operator_delete"></a>delete 演算子 

 A`ScheduleGroup`オブジェクトが破棄される内部的に、ランタイムによってに対するすべての外部参照が離されるとします。 明示的に削除できません。  
  
```
void operator delete(
    void* _PObject);

void operator delete(
    void* _PObject,
    int,
 const char *,
    int);
```    
  
### <a name="parameters"></a>パラメーター  
 `_PObject`  
 削除するオブジェクトへのポインター。  
  
##  <a name="a-namereferencea-reference"></a><a name="reference"></a>参照 

 スケジュール グループの参照カウントをインクリメントします。  
  
```
virtual unsigned int Reference() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 新たにインクリメントされた参照カウントします。  
  
### <a name="remarks"></a>コメント  
 これは、スケジュール グループの構成の有効期間を管理に通常使用します。 スケジュール グループの参照カウントがゼロになるスケジュール グループは、ランタイムによって削除されます。 いずれかを使用して作成されたスケジュール グループ、 [currentscheduler::createschedulegroup](currentscheduler-class.md#createschedulegroup)メソッド、または[scheduler::createschedulegroup](scheduler-class.md#createschedulegroup)メソッドの最初の参照カウントは&1; です。  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>リリース 

 スケジュール グループの参照カウントをデクリメントします。  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 新たにデクリメントされた参照カウントします。  
  
### <a name="remarks"></a>コメント  
 これは、スケジュール グループの構成の有効期間を管理に通常使用します。 スケジュール グループの参照カウントがゼロになるスケジュール グループは、ランタイムによって削除されます。 呼び出した後、`Release`メソッド作成を削除する時期の特定の数の参照カウントと配置を使用してその他の参照、`Reference`メソッド、さらに、スケジュール グループを使用することはできません。 これを行うとすると、未定義の動作が発生します。  
  
 スケジュール グループは、特定のスケジューラ インスタンスに関連付けられます。 スケジュール グループへのすべての参照が解放されること、スケジューラに対するすべての参照を公開前に、おそれがあるため、後者でスケジューラが破棄されていることを確認する必要があります。 それ以外の場合の結果で未定義の動作を実行します。  
  
##  <a name="a-namedtora-schedulegroup"></a><a name="dtor"></a>~ ScheduleGroup 

```
virtual ~ScheduleGroup();
```  
  
##  <a name="a-namescheduletaska-scheduletask"></a><a name="scheduletask"></a>ScheduleTask 

 スケジュール グループ内の軽量タスクをスケジュールします。  
  
```
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Proc`  
 軽量タスクの本体を実行するために実行する関数へのポインター。  
  
 `_Data`  
 タスクの本体にパラメーターとして渡されるデータへの void ポインター。  
  
### <a name="remarks"></a>コメント  
 呼び出す、`ScheduleTask`メソッドは、タスクの実行後に適切なタイミングで、ランタイムによって削除されるスケジュール グループの参照カウントを暗黙的に設定します。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [CurrentScheduler クラス](currentscheduler-class.md)   
 [Scheduler クラス](scheduler-class.md)   
 [タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




