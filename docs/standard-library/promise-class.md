---
title: "promise クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::promise
dev_langs:
- C++
ms.assetid: 2931558c-d94a-4ba1-ac4f-20bf7b6e23f9
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: ad79ecc3497182a451ef85ea53c8ec5603fdca69
ms.lasthandoff: 02/24/2017

---
# <a name="promise-class"></a>promise クラス
*非同期プロバイダー*を記述します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Ty>
class promise;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[promise::promise コンストラクター](#promise__promise_constructor)|`promise` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[promise::get_future](#promise__get_future_method)|この約束に関連付けられている [future](../standard-library/future-class.md) を返します。|  
|[promise::set_exception](#promise__set_exception_method)|この約束の結果をアトミックに設定して、例外を示します。|  
|[promise::set_exception_at_thread_exit](#promise__set_exception_at_thread_exit_method)|この約束の結果をアトミックに設定して例外を示し、現在のスレッドのすべてのスレッド ローカルのオブジェクトが破棄された後にのみ通知を配信します (通常はスレッド終了時)。|  
|[promise::set_value](#promise__set_value_method)|この約束の結果をアトミックに設定して、値を示します。|  
|[promise::set_value_at_thread_exit](#promise__set_value_at_thread_exit_method)|この約束の結果をアトミックに設定して値を示し、現在のスレッドのすべてのスレッド ローカルのオブジェクトが破棄された後にのみ通知を配信します (通常はスレッド終了時)。|  
|[promise::swap](#promise__swap_method)|この promise の*関連付けられた非同期状態*を、指定した promise オブジェクトの状態と交換します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[promise::operator=](#promise__operator_eq)|この約束オブジェクトの共有状態の割り当て。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `promise`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** future  
  
 **名前空間:** std  
  
##  <a name="a-namepromisegetfuturemethoda--promisegetfuture"></a><a name="promise__get_future_method"></a>  promise::get_future  
 この promise と同じ*関連付けられた非同期状態*の [future](../standard-library/future-class.md) オブジェクトを返します。  
  
```
future<Ty> get_future();
```  
  
### <a name="remarks"></a>コメント  
 promise オブジェクトが空の場合、このメソッドは `no_state` の [error_code](../standard-library/error-code-class.md) を持つ [future_error](../standard-library/future-error-class.md) をスローします。  
  
 このメソッドが同じ関連付けられた非同期状態を持つ約束オブジェクトに対して既に呼び出されている場合、メソッドは `future_error` の `error_code` を持つ `future_already_retrieved` をスローします。  
  
##  <a name="a-namepromiseoperatoreqa--promiseoperator"></a><a name="promise__operator_eq"></a>  promise::operator=  
 指定した `promise` オブジェクトから*関連付けられた非同期状態*を転送します。  
  
```
promise& operator=(promise&& Other) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `Other`  
 `promise` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `*this`  
  
### <a name="remarks"></a>コメント  
 この演算子は `Other` から関連付けられた非同期状態を転送します。 転送後、`Other` は*空*になります。  
  
##  <a name="a-namepromisepromiseconstructora--promisepromise-constructor"></a><a name="promise__promise_constructor"></a>  promise::promise コンストラクター  
 `promise` オブジェクトを構築します。  
  
```
promise();
template <class Alloc>
promise(allocator_arg_t, const Alloc& Al);
promise(promise&& Other) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `Al`  
 メモリ割り当て。 詳細については、「[\<allocators>](../standard-library/allocators-header.md)」をご覧ください。  
  
 `Other`  
 `promise` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 1 つ目のコンストラクターは、*空の*`promise` オブジェクトを構築します。  
  
 2 つ目のコンストラクターは、空の `promise` オブジェクトを構築して、`Al` をメモリの割り当てに使用します。  
  
 3 つ目のコンストラクターは、`promise` オブジェクトを構築し、関連付けられた非同期状態を `Other` から転送し、`Other` を空のままにします。  
  
##  <a name="a-namepromisesetexceptionmethoda--promisesetexception"></a><a name="promise__set_exception_method"></a>  promise::set_exception  
 アトミックに例外をこの `promise` オブジェクトの結果として格納し、*関連付けられた非同期状態*を*準備完了*に設定します。  
  
```
void set_exception(exception_ptr Exc);
```  
  
### <a name="parameters"></a>パラメーター  
 `Exc`  
 このメソッドにより例外結果として格納されている [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)。  
  
### <a name="remarks"></a>コメント  
 `promise` オブジェクトに関連付けられた非同期状態がない場合、このメソッドは `no_state` のエラー コードを持つ [future_error](../standard-library/future-error-class.md) をスローします。  
  
 `set_exception`、[set_exception_at_thread_exit](#promise__set_exception_at_thread_exit_method)、[set_value](#promise__set_value_method)、または [set_value_at_thread_exit](#promise__set_value_at_thread_exit_method) が同じ関連付けられた非同期状態を持つ `promise` オブジェクトに対して呼び出されている場合、このメソッドは `promise_already_satisfied` のエラー コードを持つ `future_error` をスローします。  
  
 このメソッドの結果として、関連付けられた非同期状態に対してブロックされているすべてのスレッドのブロックが解除されます。  
  
##  <a name="a-namepromisesetexceptionatthreadexitmethoda--promisesetexceptionatthreadexit"></a><a name="promise__set_exception_at_thread_exit_method"></a>  promise::set_exception_at_thread_exit  
 この `promise` の結果をアトミックに設定して例外を示し、現在のスレッドのすべてのスレッド ローカルのオブジェクトが破棄された後にのみ通知を配信します (通常はスレッド終了時)。  
  
```
void set_exception_at_thread_exit(exception_ptr Exc);
```  
  
### <a name="parameters"></a>パラメーター  
 `Exc`  
 このメソッドにより例外結果として格納されている [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr)。  
  
### <a name="remarks"></a>コメント  
 promise オブジェクトに*関連付けられた非同期状態*がない場合、このメソッドは `no_state` のエラー コードを持つ [future_error](../standard-library/future-error-class.md) をスローします。  
  
 [set_exception](#promise__set_exception_method)、`set_exception_at_thread_exit`、[set_value](#promise__set_value_method)、または [set_value_at_thread_exit](#promise__set_value_at_thread_exit_method) が同じ関連付けられた非同期状態を持つ `promise` オブジェクトに対して既に呼び出されている場合、このメソッドは `promise_already_satisfied` のエラー コードを持つ `future_error` をスローします。  
  
 [set_exception](#promise__set_exception_method) とは対照的に、このメソッドでは、関連付けられた非同期状態は、現在のスレッドのすべてのスレッド ローカルのオブジェクトが破棄されるまでは準備完了に設定されません。 通常、関連付けられた非同期状態に対してブロックされたスレッドは、現在のスレッドが終了するまでブロック解除されません。  
  
##  <a name="a-namepromisesetvaluemethoda--promisesetvalue"></a><a name="promise__set_value_method"></a>  promise::set_value  
 アトミックに値をこの `promise` オブジェクトの結果として格納し、*関連付けられた非同期状態* を*準備完了*に設定します。  
  
```
void promise::set_value(const Ty& Val);
void promise::set_value(Ty&& Val);
void promise<Ty&>::set_value(Ty& Val);
void promise<void>::set_value();
```  
  
### <a name="parameters"></a>パラメーター  
 `Val`  
 結果として格納される値。  
  
### <a name="remarks"></a>コメント  
 `promise` オブジェクトに関連付けられた非同期状態がない場合、このメソッドは `no_state` のエラー コードを持つ [future_error](../standard-library/future-error-class.md) をスローします。  
  
 [set_exception](#promise__set_exception_method)、[set_exception_at_thread_exit](#promise__set_exception_at_thread_exit_method)、`set_value`、または [set_value_at_thread_exit](#promise__set_value_at_thread_exit_method) が同じ関連付けられた非同期状態の `promise` オブジェクトに対して呼び出されている場合、このメソッドは `promise_already_satisfied` のエラー コードを持つ `future_error` をスローします。  
  
 このメソッドの結果として、関連付けられた非同期状態に対してブロックされているすべてのスレッドのブロックが解除されます。  
  
 最初のメソッドは、`Val` が関連付けられた非同期状態にコピーされたときにスローされるすべての例外もスローします。 この状況では、関連付けられた非同期状態は準備完了に設定されません。  
  
 2 番目のメソッドは、`Val` が関連付けられた非同期状態に移動されたときにスローされるすべての例外もスローします。 この状況では、関連付けられた非同期状態は準備完了に設定されません。  
  
 部分的特殊化 `promise<Ty&>` の場合、格納されている値は、実際には `Val` への参照です。  
  
 特殊化 `promise<void>` の場合、格納されている値は存在しません。  
  
##  <a name="a-namepromisesetvalueatthreadexitmethoda--promisesetvalueatthreadexit"></a><a name="promise__set_value_at_thread_exit_method"></a>  promise::set_value_at_thread_exit  
 アトミックにこの `promise` オブジェクトの結果として値を格納します。  
  
```
void promise::set_value_at_thread_exit(const Ty& Val);
void promise::set_value_at_thread_exit(Ty&& Val);
void promise<Ty&>::set_value_at_thread_exit(Ty& Val);
void promise<void>::set_value_at_thread_exit();
```  
  
### <a name="parameters"></a>パラメーター  
 `Val`  
 結果として格納される値。  
  
### <a name="remarks"></a>コメント  
 promise オブジェクトに*関連付けられた非同期状態*がない場合、このメソッドは `no_state` のエラー コードを持つ [future_error](../standard-library/future-error-class.md) をスローします。  
  
 [set_exception](#promise__set_exception_method)、[set_exception_at_thread_exit](#promise__set_exception_at_thread_exit_method)、[set_value](#promise__set_value_method)、または `set_value_at_thread_exit` が同じ関連付けられた非同期状態の `promise` オブジェクトに対して呼び出されている場合、このメソッドは `promise_already_satisfied` のエラー コードを持つ `future_error` をスローします。  
  
 `set_value` とは対照的に、関連付けられた非同期状態は、現在のスレッドのスレッド ローカルのオブジェクトがすべて破棄されるまでは準備完了に設定されません。 通常、関連付けられた非同期状態に対してブロックされたスレッドは、現在のスレッドが終了するまでブロック解除されません。  
  
 最初のメソッドは、`Val` が関連付けられた非同期状態にコピーされたときにスローされるすべての例外もスローします。  
  
 2 番目のメソッドは、`Val` が関連付けられた非同期状態に移動されたときにスローされるすべての例外もスローします。  
  
 部分的特殊化 `promise<Ty&>` の場合、格納されている値は、事実上 `Val` への参照です。  
  
 特殊化 `promise<void>` の場合、格納されている値は存在しません。  
  
##  <a name="a-namepromiseswapmethoda--promiseswap"></a><a name="promise__swap_method"></a>  promise::swap  
 この約束オブジェクトに*関連付けられた非同期状態*を指定したオブジェクトのものと交換します。  
  
```
void swap(promise& Other) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `Other`  
 `promise` オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)




 


