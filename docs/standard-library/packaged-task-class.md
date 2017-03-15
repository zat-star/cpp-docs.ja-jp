---
title: "packaged_task クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::packaged_task
dev_langs:
- C++
ms.assetid: 0a72cbe3-f22a-4bfe-8e50-dcb268c98780
caps.latest.revision: 9
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
ms.sourcegitcommit: acc0ecd4edaf1e58977dcbdeb483d497a72bc4c8
ms.openlocfilehash: a54b1c9788ef60f63aafafc9125b09c449fde1b0
ms.lasthandoff: 02/24/2017

---
# <a name="packagedtask-class"></a>packaged_task クラス
呼び出しラッパーであり、呼び出しシグネチャが `Ty(ArgTypes...)` である*非同期プロバイダー*を記述します。 その*関連付けられた非同期状態*には、可能性がある結果に加えて呼び出し可能オブジェクトのコピーが保持されます。  
  
## <a name="syntax"></a>構文  
  
```
template <class>
class packaged_task;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[packaged_task::packaged_task コンストラクター](#packaged_task__packaged_task_constructor)|`packaged_task` オブジェクトを構築します。|  
|[packaged_task::~packaged_task デストラクター](#packaged_task___dtorpackaged_task_destructor)|`packaged_task` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[packaged_task::get_future](#packaged_task__get_future_method)|同じ関連付けられた非同期状態の [future](../standard-library/future-class.md) オブジェクトを返します。|  
|[packaged_task::make_ready_at_thread_exit](#packaged_task__make_ready_at_thread_exit_method)|関連付けられた非同期状態に格納された呼び出し可能オブジェクトを呼び出し、戻り値をアトミックに格納します。|  
|[packaged_task::reset](#packaged_task__reset_method)|関連付けられた非同期状態を置き換えます。|  
|[packaged_task::swap](#packaged_task__swap_method)|関連付けられた非同期状態を、指定したオブジェクトのものと交換します。|  
|[packaged_task::valid](#packaged_task__valid_method)|オブジェクトが関連付けられた非同期状態であるかどうかを指定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[packaged_task::operator=](#packaged_task__operator_eq)|関連付けられた非同期状態を、指定されたオブジェクトから転送します。|  
|[packaged_task::operator()](#packaged_task__operator__)|関連付けられた非同期状態に格納された呼び出し可能オブジェクトを呼び出し、戻り値をアトミックに格納し、状態を *ready* に設定します。|  
|[packaged_task::operator bool](#packaged_task__operator_bool)|オブジェクトが関連付けられた非同期状態であるかどうかを指定します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** future  
  
 **名前空間:** std  
  
##  <a name="a-namepackagedtaskgetfuturemethoda--packagedtaskgetfuture"></a><a name="packaged_task__get_future_method"></a>  packaged_task::get_future  
 同じ*関連付けられた非同期状態*の `future<Ty>` 型のオブジェクトを返します。  
  
```
future<Ty> get_future();
```  
  
### <a name="remarks"></a>コメント  
 `packaged_task` オブジェクトが関連付けられた非同期状態ではない場合、このメソッドはエラー コード `no_state` で [future_error](../standard-library/future-error-class.md) をスローします。  
  
 このメソッドが同じ関連付けられた非同期状態の `packaged_task` オブジェクトに対して既に呼び出されている場合、このメソッドはエラー コード `future_already_retrieved` で `future_error` をスローします。  
  
##  <a name="a-namepackagedtaskmakereadyatthreadexitmethoda--packagedtaskmakereadyatthreadexit"></a><a name="packaged_task__make_ready_at_thread_exit_method"></a>  packaged_task::make_ready_at_thread_exit  
 *関連付けられた非同期状態*に格納された呼び出し可能オブジェクトを呼び出し、戻り値をアトミックに格納します。  
  
```
void make_ready_at_thread_exit(ArgTypes... args);
```  
  
### <a name="remarks"></a>コメント  
 `packaged_task` オブジェクトが関連付けられた非同期状態ではない場合、このメソッドはエラー コード `no_state` で [future_error](../standard-library/future-error-class.md) をスローします。  
  
 このメソッドまたは [make_ready_at_thread_exit](#packaged_task__make_ready_at_thread_exit_method) が同じ関連付けられた非同期状態の `packaged_task` オブジェクトに対して既に呼び出されている場合、このメソッドはエラー コード `promise_already_satisfied` で `future_error` をスローします。  
  
 それ以外の場合、この演算子は `INVOKE(fn, args..., Ty)` を呼び出します。ここで、*fn* は関連付けられた非同期状態に格納された呼び出し可能オブジェクトです。 すべての戻り値は、関連付けられた非同期状態の返された結果としてアトミックに格納されます。  
  
 [packaged_task::operator()](#packaged_task__operator__) とは対照的に、呼び出し元のスレッドのスレッド ローカルのオブジェクトがすべて破棄されるまでは、関連付けられた非同期状態は `ready` に設定されません。 通常、関連付けられた非同期状態でブロックされたスレッドは、呼び出し元のスレッドが終了するまでブロック解除されません。  
  
##  <a name="a-namepackagedtaskoperatoreqa--packagedtaskoperator"></a><a name="packaged_task__operator_eq"></a>  packaged_task::operator=  
 *関連付けられた非同期状態*を、指定されたオブジェクトから転送します。  
  
```
packaged_task& operator=(packaged_task&& Right);
```  
  
### <a name="parameters"></a>パラメーター  
 `Right`  
 `packaged_task` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `*this`  
  
### <a name="remarks"></a>コメント  
 操作の後、`Right` に関連付けられた非同期状態は既にありません。  
  
##  <a name="a-namepackagedtaskoperatora--packagedtaskoperator"></a><a name="packaged_task__operator__"></a>  packaged_task::operator()  
 *関連付けられた非同期状態*に格納された呼び出し可能オブジェクトを呼び出し、戻り値をアトミックに格納し、状態を *ready* に設定します。  
  
```
void operator()(ArgTypes... args);
```  
  
### <a name="remarks"></a>コメント  
 `packaged_task` オブジェクトが関連付けられた非同期状態ではない場合、このメソッドはエラー コード `no_state` で [future_error](../standard-library/future-error-class.md) をスローします。  
  
 このメソッドまたは [make_ready_at_thread_exit](#packaged_task__make_ready_at_thread_exit_method) が同じ関連付けられた非同期状態の `packaged_task` オブジェクトに対して既に呼び出されている場合、このメソッドはエラー コード `promise_already_satisfied` で `future_error` をスローします。  
  
 それ以外の場合、この演算子は `INVOKE(fn, args..., Ty)` を呼び出します。ここで、*fn* は関連付けられた非同期状態に格納された呼び出し可能オブジェクトです。 すべての戻り値は、関連付けられた非同期状態の返された結果としてアトミックに格納され、状態が ready に設定されます。 その結果、関連付けられた非同期状態でブロックされているすべてのスレッドがブロック解除されます。  
  
##  <a name="a-namepackagedtaskoperatorboola--packagedtaskoperator-bool"></a><a name="packaged_task__operator_bool"></a>  packaged_task::operator bool  
 オブジェクトが `associated asynchronous state` であるかどうかを指定します。  
  
```
operator bool() const noexcept;
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが関連付けられた非同期状態である場合は `true` を返します。それ以外の場合は `false` を返します。  
  
##  <a name="a-namepackagedtaskpackagedtaskconstructora--packagedtaskpackagedtask-constructor"></a><a name="packaged_task__packaged_task_constructor"></a>  packaged_task::packaged_task コンストラクター  
 `packaged_task` オブジェクトを構築します。  
  
```
packaged_task() noexcept;
packaged_task(packaged_task&& Right) noexcept;
template <class Fn>
   explicit packaged_task(Fn&& fn);

template <class Fn, class Alloc>
   explicit packaged_task(
      allocator_arg_t, const Alloc& alloc, Fn&& fn);
```  
  
### <a name="parameters"></a>パラメーター  
 `Right`  
 `packaged_task` オブジェクト。  
  
 `alloc`  
 メモリ割り当て。 詳細については、「[\<allocators>](../standard-library/allocators-header.md)」を参照してください。  
  
 `fn`  
 関数オブジェクトを指定します。  
  
### <a name="remarks"></a>コメント  
 1 つ目のコンストラクターは、*関連付けられた非同期状態*がない `packaged_task` オブジェクトを構築します。  
  
 2 つ目のコンストラクターは、`packaged_task` オブジェクトを構築し、`Right` から関連付けられた非同期状態を転送します。 操作の後、`Right` に関連付けられた非同期状態は既にありません。  
  
 3 つ目のコンストラクターは、関連付けられた非同期状態に格納された `packaged_task` のコピーを持つ `fn` オブジェクトを構築します。  
  
 4 つ目のコンストラクターは、関連付けられた非同期状態に格納された `packaged_task` のコピーを持つ `fn` オブジェクトを構築し、メモリ割り当てのために `alloc` を使用します。  
  
##  <a name="a-namepackagedtaskdtorpackagedtaskdestructora--packagedtaskpackagedtask-destructor"></a><a name="packaged_task___dtorpackaged_task_destructor"></a>  packaged_task::~packaged_task デストラクター  
 `packaged_task` オブジェクトを破棄します。  
  
```
~packaged_task();
```  
  
### <a name="remarks"></a>コメント  
 *関連付けられた非同期状態*が*準備完了*ではない場合、デストラクターは、関連付けられた非同期状態の結果としてエラー コード `broken_promise` で [future_error](../standard-library/future-error-class.md) 例外を格納し、関連付けられた非同期状態でブロックされているすべてのスレッドがブロック解除されます。  
  
##  <a name="a-namepackagedtaskresetmethoda--packagedtaskreset"></a><a name="packaged_task__reset_method"></a>  packaged_task::reset  
 新しい*関連付けられた非同期状態*を使用して、既存の関連付けられた非同期状態を置き換えます。  
  
```
void reset();
```  
  
### <a name="remarks"></a>コメント  
 実際には、このメソッドは `*this = packaged_task(move(fn))` を実行します。ここで、*fn* は、このオブジェクトの関連付けられた非同期状態に格納された関数オブジェクトです。 そのため、オブジェクトの状態が削除され、[get_future](#packaged_task__get_future_method)、[operator()](#packaged_task__operator__)、および [make_ready_at_thread_exit](#packaged_task__make_ready_at_thread_exit_method) を新しく構築されたオブジェクトでのように呼び出すことができます。  
  
##  <a name="a-namepackagedtaskswapmethoda--packagedtaskswap"></a><a name="packaged_task__swap_method"></a>  packaged_task::swap  
 関連付けられた非同期状態を、指定したオブジェクトのものと交換します。  
  
```
void swap(packaged_task& Right) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `Right`  
 `packaged_task` オブジェクト。  
  
##  <a name="a-namepackagedtaskvalidmethoda--packagedtaskvalid"></a><a name="packaged_task__valid_method"></a>  packaged_task::valid  
 オブジェクトが `associated asynchronous state` であるかどうかを指定します。  
  
```
bool valid() const;
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが関連付けられた非同期状態である場合は `true` を返します。それ以外の場合は `false` を返します。  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<future>](../standard-library/future.md)




