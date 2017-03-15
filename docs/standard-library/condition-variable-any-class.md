---
title: "condition_variable_any クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- condition_variable/std::condition_variable_any
dev_langs:
- C++
ms.assetid: d8afe5db-1561-4ec2-8e85-21ea03ee4321
caps.latest.revision: 15
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: a04164eb30bdb0403f131d64a31b9c7d9cb5656f
ms.lasthandoff: 02/24/2017

---
# <a name="conditionvariableany-class"></a>condition_variable_any クラス
`condition_variable_any` 型を持つイベントを待機するには、クラス `mutex` を使用します。  
  
## <a name="syntax"></a>構文  
  
```
class condition_variable_any;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[condition_variable_any::condition_variable_any コンストラクター](#condition_variable_any__condition_variable_any_constructor)|`condition_variable_any` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[condition_variable_any::notify_all](#condition_variable_any__notify_all_method)|`condition_variable_any` オブジェクトを待機しているすべてのスレッドのブロックを解除します。|  
|[condition_variable_any::notify_one](#condition_variable_any__notify_one_method)|`condition_variable_any` オブジェクトを待機しているスレッドの&1; つのブロックを解除します。|  
|[condition_variable_any::wait](#condition_variable_any__wait_method)|スレッドをブロックします。|  
|[condition_variable_any::wait_for](#condition_variable_any__wait_for_method)|スレッドをブロックし、スレッドがブロック解除されるまでの時間間隔を設定します。|  
|[condition_variable_any::wait_until](#condition_variable_any__wait_until_method)|スレッドをブロックし、スレッドがブロック解除される最大の時刻を設定します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** condition_variable  
  
 **名前空間:** std  
  
##  <a name="a-nameconditionvariableanyconditionvariableanyconstructora--conditionvariableanyconditionvariableany-constructor"></a><a name="condition_variable_any__condition_variable_any_constructor"></a>  condition_variable_any::condition_variable_any コンストラクター  
 `condition_variable_any` オブジェクトを構築します。  
  
```
condition_variable_any();
```  
  
### <a name="remarks"></a>コメント  
 十分なメモリが使用できない場合、コンストラクターは `not_enough_memory` エラー コードがある [system_error](../standard-library/system-error-class.md) オブジェクトをスローします。 他のリソースをいくつか使用できないためにオブジェクトが構築できない場合、コンストラクターは `system_error` エラー コードがある `resource_unavailable_try_again` オブジェクトをスローします。  
  
##  <a name="a-nameconditionvariableanynotifyallmethoda--conditionvariableanynotifyall"></a><a name="condition_variable_any__notify_all_method"></a>  condition_variable_any::notify_all  
 `condition_variable_any` オブジェクトを待機しているすべてのスレッドのブロックを解除します。  
  
```
void notify_all() noexcept;
```  
  
##  <a name="a-nameconditionvariableanynotifyonemethoda--conditionvariableanynotifyone"></a><a name="condition_variable_any__notify_one_method"></a>  condition_variable_any::notify_one  
 `condition_variable_any` オブジェクトを待機しているスレッドの&1; つのブロックを解除します。  
  
```
void notify_one() noexcept;
```  
  
##  <a name="a-nameconditionvariableanywaitmethoda--conditionvariableanywait"></a><a name="condition_variable_any__wait_method"></a>  condition_variable_any::wait  
 スレッドをブロックします。  
  
```
template <class Lock>  
void wait(Lock& Lck);

template <class Lock, class Predicate>
void wait(Lock& Lck, Predicate Pred);
```  
  
### <a name="parameters"></a>パラメーター  
 `Lck`  
 任意の型の `mutex` オブジェクト。  
  
 `Pred`  
 `true` または `false` を返す任意の式。  
  
### <a name="remarks"></a>コメント  
 最初のメソッドは `condition_variable_any` オブジェクトが [notify_one](../standard-library/condition-variable-class.md#condition_variable__notify_one_method) または [notify_all](../standard-library/condition-variable-class.md#condition_variable__notify_all_method) への呼び出しによって通知されるまでブロックします。 また、擬似的に開始することもできます。  
  
 実際には、2 つ目のメソッドは次のコードを実行します。  
  
```
while (!Pred())
    wait(Lck);
```    
  
##  <a name="a-nameconditionvariableanywaitformethoda--conditionvariableanywaitfor"></a><a name="condition_variable_any__wait_for_method"></a>  condition_variable_any::wait_for  
 スレッドをブロックし、スレッドがブロック解除されるまでの時間間隔を設定します。  
  
```
template <class Lock, class Rep, class Period>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time);

template <class Lock, class Rep, class Period, class Predicate>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time, Predicate Pred);
```  
  
### <a name="parameters"></a>パラメーター  
 `Lck`  
 任意の型の `mutex` オブジェクト。  
  
 `Rel_time`  
 スレッドが開始するまでの時間の長さを指定する `chrono::duration` オブジェクト。  
  
 `Pred`  
 `true` または `false` を返す任意の式。  
  
### <a name="return-value"></a>戻り値  
 `cv_status::timeout` が経過したときに待機が終了した場合、最初のメソッドは `Rel_time` を返します。 それ以外の場合、メソッドは `cv_status::no_timeout` を返します。  
  
 2 番目のメソッドは、`Pred` の値を返します。  
  
### <a name="remarks"></a>コメント  
 最初のメソッドは `condition_variable_any` オブジェクトが [notify_one](../standard-library/condition-variable-class.md#condition_variable__notify_one_method) または [notify_all](../standard-library/condition-variable-class.md#condition_variable__notify_all_method) への呼び出しによって通知されるか、時間間隔 `Rel_time` が経過するまでブロックします。 また、擬似的に開始することもできます。  
  
 実際には、2 つ目のメソッドは次のコードを実行します。  
  
```cpp  
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```  
  
##  <a name="a-nameconditionvariableanywaituntilmethoda--conditionvariableanywaituntil"></a><a name="condition_variable_any__wait_until_method"></a>  condition_variable_any::wait_until  
 スレッドをブロックし、スレッドがブロック解除される最大の時刻を設定します。  
  
```
template <class Lock, class Clock, class Duration>
void wait_until(Lock& Lck, const chrono::time_point<Clock, Duration>& Abs_time);

template <class Lock, class Clock, class Duration, class Predicate>
void wait_until(
    Lock& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time,
    Predicate Pred);

template <class Lock>
void wait_until(Lock Lck, const xtime* Abs_time);

template <class Lock, class Predicate>
void wait_until(
    Lock Lck,
    const xtime* Abs_time,
    Predicate Pred);
```  
  
### <a name="parameters"></a>パラメーター  
 `Lck`  
 ミューテックス オブジェクト。  
  
 `Abs_time`  
 [chrono::time_point](../standard-library/time-point-class.md) オブジェクト。  
  
 `Pred`  
 `true` または `false` を返す任意の式。  
  
### <a name="return-value"></a>戻り値  
 `cv_status` が経過すると待機が終了する場合に、`cv_status::timeout` 型の戻り値の `Abs_time` を返すメソッド。 それ以外の場合、メソッドは `cv_status::no_timeout` を返します。  
  
 `bool` の `Pred` 戻り値を返すメソッド。  
  
### <a name="remarks"></a>コメント  
 最初のメソッドは `condition_variable` オブジェクトが [notify_one](../standard-library/condition-variable-class.md#condition_variable__notify_one_method) または [notify_all](../standard-library/condition-variable-class.md#condition_variable__notify_all_method) への呼び出しによって通知されるか、`Abs_time` までブロックします。 また、擬似的に開始することもできます。  
  
 実際には、2 つ目のメソッドは次のコードを実行します。  
  
```
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```  
  
 3 つ目のメソッドと&4; つ目のメソッドは、`xtime` 型のオブジェクトへのポインターを使用して、`chrono::time_point` オブジェクトを置き換えます。 `xtime` オブジェクトは、シグナルを待機する時間の最大値を指定します。  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [<condition_variable>](../standard-library/condition-variable.md)




