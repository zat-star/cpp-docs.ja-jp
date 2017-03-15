---
title: "condition_variable クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- condition_variable/std::condition_variable
dev_langs:
- C++
ms.assetid: 80b1295c-b73d-4d46-b664-6e183f2eec1b
caps.latest.revision: 16
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
ms.openlocfilehash: 6ba1c9aae256029cc35f1815dbc7bfd3503254dc
ms.lasthandoff: 02/24/2017

---
# <a name="conditionvariable-class"></a>condition_variable クラス
`condition_variable` 型の `mutex` がある場合に、イベントを待機するために `unique_lock<mutex>` クラスを使用します。 この型のオブジェクトは [condition_variable_any<unique_lock\<mutex>>](../standard-library/condition-variable-any-class.md) 型のオブジェクトより優れたパフォーマンスを実現することがあります。  
  
## <a name="syntax"></a>構文  
  
```
class condition_variable;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[condition_variable::condition_variable コンストラクター](#condition_variable__condition_variable_constructor)|`condition_variable` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[condition_variable::native_handle メソッド](#condition_variable__native_handle_method)|condition_variable ハンドルを表す実装固有の型を返します。|  
|[condition_variable::notify_all](#condition_variable__notify_all_method)|`condition_variable` オブジェクトを待機しているすべてのスレッドのブロックを解除します。|  
|[condition_variable::notify_one](#condition_variable__notify_one_method)|`condition_variable` オブジェクトを待機しているスレッドの&1; つのブロックを解除します。|  
|[condition_variable::wait](#condition_variable__wait_method)|スレッドをブロックします。|  
|[condition_variable::wait_for](#condition_variable__wait_for_method)|スレッドをブロックし、スレッドがブロック解除されるまでの時間間隔を設定します。|  
|[condition_variable::wait_until](#condition_variable__wait_until_method)|スレッドをブロックし、スレッドがブロック解除される最大の時刻を設定します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** condition_variable  
  
 **名前空間:** std  
  
##  <a name="a-nameconditionvariableconditionvariableconstructora--conditionvariableconditionvariable-constructor"></a><a name="condition_variable__condition_variable_constructor"></a>  condition_variable::condition_variable コンストラクター  
 `condition_variable` オブジェクトを構築します。  
  
```
condition_variable();
```  
  
### <a name="remarks"></a>コメント  
 十分なメモリが使用できない場合、コンストラクターは `not_enough_memory` エラー コードがある [system_error](../standard-library/system-error-class.md) オブジェクトをスローします。 他のリソースをいくつか使用できないためにオブジェクトが構築できない場合、コンストラクターは `system_error` エラー コードがある `resource_unavailable_try_again` オブジェクトをスローします。  
  
##  <a name="a-nameconditionvariablenativehandlemethoda--conditionvariablenativehandle"></a><a name="condition_variable__native_handle_method"></a>  condition_variable::native_handle  
 condition_variable ハンドルを表す実装固有の型を返します。  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>戻り値  
 `native_handle_type` は、同時実行ランタイムの内部データ構造へのポインターとして定義されます。  
  
##  <a name="a-nameconditionvariablenotifyallmethoda--conditionvariablenotifyall"></a><a name="condition_variable__notify_all_method"></a>  condition_variable::notify_all  
 `condition_variable` オブジェクトを待機しているすべてのスレッドのブロックを解除します。  
  
```
void notify_all() noexcept;
```  
  
##  <a name="a-nameconditionvariablenotifyonemethoda--conditionvariablenotifyone"></a><a name="condition_variable__notify_one_method"></a>  condition_variable::notify_one  
 `condition_variable` オブジェクトを待機しているスレッドの&1; つのブロックを解除します。  
  
```
void notify_one() noexcept;
```  
  
##  <a name="a-nameconditionvariablewaitmethoda--conditionvariablewait"></a><a name="condition_variable__wait_method"></a>  condition_variable::wait  
 スレッドをブロックします。  
  
```
void wait(unique_lock<mutex>& Lck);

template <class Predicate>
void wait(unique_lock<mutex>& Lck, Predicate Pred);
```  
  
### <a name="parameters"></a>パラメーター  
 `Lck`  
 [unique_lock\<mutex>](../standard-library/unique-lock-class.md) オブジェクト。  
  
 `Pred`  
 `true` または `false` を返す任意の式。  
  
### <a name="remarks"></a>コメント  
 最初のメソッドは `condition_variable` オブジェクトが [notify_one](#condition_variable__notify_one_method) または [notify_all](#condition_variable__notify_all_method) への呼び出しによって通知されるまでブロックします。 また、擬似的に開始することもできます。  
  
 実際には、2 つ目のメソッドは次のコードを実行します。  
  
```cpp  
while(!Pred())
    wait(Lck);
```    
  
##  <a name="a-nameconditionvariablewaitformethoda--conditionvariablewaitfor"></a><a name="condition_variable__wait_for_method"></a>  condition_variable::wait_for  
 スレッドをブロックし、スレッドがブロック解除されるまでの時間間隔を設定します。  
  
```
template <class Rep, class Period>
cv_status wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time);

template <class Rep, class Period, class Predicate>
bool wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time, 
    Predicate Pred);
```  
  
### <a name="parameters"></a>パラメーター  
 `Lck`  
 [unique_lock\<mutex>](../standard-library/unique-lock-class.md) オブジェクト。  
  
 `Rel_time`  
 スレッドが開始するまでの時間の長さを指定する `chrono::duration` オブジェクト。  
  
 `Pred`  
 `true` または `false` を返す任意の式。  
  
### <a name="return-value"></a>戻り値  
 `cv_status::timeout` が経過したときに待機が終了した場合、最初のメソッドは `Rel_time` を返します。 それ以外の場合、メソッドは `cv_status::no_timeout` を返します。  
  
 2 番目のメソッドは、`Pred` の値を返します。  
  
### <a name="remarks"></a>コメント  
 最初のメソッドは `condition_variable` オブジェクトが [notify_one](#condition_variable__notify_one_method) または [notify_all](#condition_variable__notify_all_method) への呼び出しによって通知されるか、時間間隔 `Rel_time` が経過するまでブロックします。 また、擬似的に開始することもできます。  
  
 実際には、2 つ目のメソッドは次のコードを実行します。  
  
```cpp  
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```  
  
##  <a name="a-nameconditionvariablewaituntilmethoda--conditionvariablewaituntil"></a><a name="condition_variable__wait_until_method"></a>  condition_variable::wait_until  
 スレッドをブロックし、スレッドがブロック解除される最大の時刻を設定します。  
  
```
template <class Clock, class Duration>
cv_status wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time);

template <class Clock, class Duration, class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time, 
    Predicate Pred);

cv_status wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time);

template <class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time, 
    Predicate Pred);
```  
  
### <a name="parameters"></a>パラメーター  
 `Lck`  
 [unique_lock\<mutex>](../standard-library/unique-lock-class.md) オブジェクト。  
  
 `Abs_time`  
 [chrono::time_point](../standard-library/time-point-class.md) オブジェクト。  
  
 `Pred`  
 `true` または `false` を返す任意の式。  
  
### <a name="return-value"></a>戻り値  
 `cv_status` が経過すると待機が終了する場合に、`cv_status::timeout` 型の戻り値の `Abs_time` を返すメソッド。 それ以外の場合、メソッドは `cv_status::no_timeout` を返します。  
  
 `bool` の `Pred` 戻り値を返すメソッド。  
  
### <a name="remarks"></a>コメント  
 最初のメソッドは `condition_variable` オブジェクトが [notify_one](#condition_variable__notify_one_method) または [notify_all](#condition_variable__notify_all_method) への呼び出しによって通知されるか、`Abs_time` までブロックします。 また、擬似的に開始することもできます。  
  
 実際には、2 つ目のメソッドは次のコードを実行します。  
  
```cpp  
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```  
  
 3 つ目のメソッドと&4; つ目のメソッドは、`xtime` 型のオブジェクトへのポインターを使用して、`chrono::time_point` オブジェクトを置き換えます。 `xtime` オブジェクトは、シグナルを待機する時間の最大値を指定します。  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [<condition_variable>](../standard-library/condition-variable.md)




