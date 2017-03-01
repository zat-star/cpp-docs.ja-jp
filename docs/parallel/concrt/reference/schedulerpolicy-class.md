---
title: "SchedulerPolicy クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::SchedulerPolicy
- concrtrm/concurrency::SchedulerPolicy
dev_langs:
- C++
helpviewer_keywords:
- SchedulerPolicy class
ms.assetid: bcebf51a-65f8-45a3-809b-d1ff93527dc4
caps.latest.revision: 22
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
ms.openlocfilehash: 68707be387590cf04745d5a53872558d7af8da8c
ms.lasthandoff: 02/24/2017

---
# <a name="schedulerpolicy-class"></a>SchedulerPolicy クラス
`SchedulerPolicy` クラスには、ポリシー要素ごとに&1; つずつ、スケジューラ インスタンスの動作を制御するキーと値のペアのセットが含まれています。  
  
## <a name="syntax"></a>構文  
  
```
class SchedulerPolicy;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[SchedulerPolicy コンス トラクター](#ctor)|オーバーロードされます。 新しいスケジューラ ポリシーを構築しの値を設定[ポリシー キー](concurrency-namespace-enums.md)同時実行ランタイム スケジューラおよびリソース マネージャーでサポートされています。|  
|[~ SchedulerPolicy デストラクター](#dtor)|スケジューラ ポリシーを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[GetPolicyValue メソッド](#getpolicyvalue)|`key` パラメーターとして指定されるポリシー キーの値を取得します。|  
|[SetConcurrencyLimits メソッド](#setconcurrencylimits)|`MinConcurrency` オブジェクトに対して、`MaxConcurrency` ポリシーおよび `SchedulerPolicy` ポリシーを同時に設定します。|  
|[SetPolicyValue メソッド](#setpolicyvalue)|`key` パラメーターとして指定されるポリシー キーの値を設定し、古い値を返します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator = 演算子](#operator_eq)|別のスケジューラ ポリシーからスケジューラ ポリシーを割り当てます。|  
  
## <a name="remarks"></a>コメント  
 使用して制御できるポリシーの詳細については、`SchedulerPolicy`を参照してください[PolicyElementKey 列挙体](concurrency-namespace-enums.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `SchedulerPolicy`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h, concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namegetpolicyvaluea-getpolicyvalue"></a><a name="getpolicyvalue"></a>GetPolicyValue 

 `key` パラメーターとして指定されるポリシー キーの値を取得します。  
  
```
unsigned int GetPolicyValue(PolicyElementKey key) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 値を取得するポリシーのキー。  
  
### <a name="return-value"></a>戻り値  
 キーが指定された場合、`key`パラメーターがサポートされている、キーのポリシーの値にキャスト、`unsigned int`です。  
  
### <a name="remarks"></a>コメント  
 メソッドがスローされます[invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md)キーがポリシーに無効にします。  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>演算子 = 

 別のスケジューラ ポリシーからスケジューラ ポリシーを割り当てます。  
  
```
SchedulerPolicy& operator= (const SchedulerPolicy& _RhsPolicy);
```  
  
### <a name="parameters"></a>パラメーター  
 `_RhsPolicy`  
 このポリシーを割り当てるポリシー。  
  
### <a name="return-value"></a>戻り値  
 スケジューラ ポリシーへの参照。  
  
### <a name="remarks"></a>コメント  
 通常、新しいスケジューラ ポリシーを定義する最も簡単な方法は、既存のポリシーをコピーし、それを `SetPolicyValue` メソッドまたは `SetConcurrencyLimits` メソッドを使用して変更することです。  
  
##  <a name="a-namectora-schedulerpolicy"></a><a name="ctor"></a>SchedulerPolicy 

 新しいスケジューラ ポリシーを構築しの値を設定[ポリシー キー](concurrency-namespace-enums.md)同時実行ランタイム スケジューラおよびリソース マネージャーでサポートされています。  
  
```
SchedulerPolicy();

SchedulerPolicy(
    size_t _PolicyKeyCount,
 ...);

SchedulerPolicy(
    const SchedulerPolicy& _SrcPolicy);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PolicyKeyCount`  
 `_PolicyKeyCount` パラメーターの後に続くキーと値のペアの数。  
  
 `_SrcPolicy`  
 コピー元のポリシー。  
  
### <a name="remarks"></a>コメント  
 最初のコンストラクターでは、すべてのポリシーが既定値に初期化される新しいスケジューラ ポリシーを作成します。  
  
 2 番目のコンストラクターでは、名前付きパラメーター スタイルの初期化を使用する新しいスケジューラ ポリシーを作成します。 `_PolicyKeyCount` パラメーターの後の値は、キーと値のペアとして渡されます。 このコンストラクターで指定されていないポリシー キーには既定値が設定されます。 このコンス トラクターが例外をスローする[invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md)、 [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)または[invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md)します。  
  
 3 番目のコンストラクターはコピー コンストラクターです。 通常、新しいスケジューラ ポリシーを定義する最も簡単な方法は、既存のポリシーをコピーし、それを `SetPolicyValue` メソッドまたは `SetConcurrencyLimits` メソッドを使用して変更することです。  
  
##  <a name="a-namedtora-schedulerpolicy"></a><a name="dtor"></a>~ SchedulerPolicy 

 スケジューラ ポリシーを破棄します。  
  
```
~SchedulerPolicy();
```  
  
##  <a name="a-namesetconcurrencylimitsa-setconcurrencylimits"></a><a name="setconcurrencylimits"></a>SetConcurrencyLimits 

 `MinConcurrency` オブジェクトに対して、`MaxConcurrency` ポリシーおよび `SchedulerPolicy` ポリシーを同時に設定します。  
  
```
void SetConcurrencyLimits(
    unsigned int _MinConcurrency,
    unsigned int _MaxConcurrency = MaxExecutionResources);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MinConcurrency`  
 値、`MinConcurrency`ポリシー キー。  
  
 `_MaxConcurrency`  
 値、`MaxConcurrency`ポリシー キー。  
  
### <a name="remarks"></a>コメント  
 メソッドがスローされます[invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md)の値が指定されている場合、`MinConcurrency`ポリシーが指定よりも大きい、`MaxConcurrency`ポリシーです。  
  
 メソッドをスローすることも[invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)に他の無効な値です。  
  
##  <a name="a-namesetpolicyvaluea-setpolicyvalue"></a><a name="setpolicyvalue"></a>SetPolicyValue 

 `key` パラメーターとして指定されるポリシー キーの値を設定し、古い値を返します。  
  
```
unsigned int SetPolicyValue(
    PolicyElementKey key,
    unsigned int value);
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 値を設定するポリシーのキー。  
  
 `value`  
 ポリシー キーに設定する値。  
  
### <a name="return-value"></a>戻り値  
 キーが指定された場合、`key`パラメーターがサポートされている、キーのポリシーの古い値がキャスト、`unsigned int`です。  
  
### <a name="remarks"></a>コメント  
 メソッドがスローされます[invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md)無効なポリシー キーまたはレジストリでは、その値を設定できませんポリシー キー、`SetPolicyValue`メソッドです。  
  
 メソッドがスローされます[invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)で指定されたキーがサポートされていない値に対して、`key`パラメーター。  
  
 このメソッドは設定できないことに注意してください、`MinConcurrency`または`MaxConcurrency`ポリシーです。 これらの値を設定するには、使用、 [SetConcurrencyLimits](#setconcurrencylimits)メソッドです。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [PolicyElementKey 列挙型](concurrency-namespace-enums.md)   
 [CurrentScheduler クラス](currentscheduler-class.md)   
 [Scheduler クラス](scheduler-class.md)   
 [タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




