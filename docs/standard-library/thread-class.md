---
title: "thread クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- thread/std::thread
dev_langs:
- C++
ms.assetid: df249bc7-ff81-4ff9-a6d6-5e3d9a8f56a1
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 848a51faa24498dd1505483894aa47ce959240a7
ms.lasthandoff: 02/24/2017

---
# <a name="thread-class"></a>thread クラス
アプリケーション内の実行スレッドを観察および管理するために使用するオブジェクトを定義します。  
  
## <a name="syntax"></a>構文  
  
```
class thread;
```  
  
## <a name="remarks"></a>コメント  
 アプリケーション内の実行スレッドを観察および管理するために `thread` オブジェクトを使用できます。 既定のコンストラクターを使用して作成されたスレッド オブジェクトは、実行スレッドに関連付けられていません。 呼び出し可能オブジェクトを使用して構築されたスレッド オブジェクトは、新しい実行スレッドを作成し、そのスレッドで呼び出し可能オブジェクトを呼び出します。 スレッド オブジェクトは移動できますが、コピーできません。 したがって、実行スレッドは&1; つのスレッド オブジェクトだけに関連付けることができます。  
  
 すべての実行スレッドに `thread::id` 型の一意の識別子があります。 関数 `this_thread::get_id` は呼び出しスレッドの識別子を返します。 メンバー関数 `thread::get_id` は、スレッド オブジェクトによって管理されるスレッドの識別子を返します。 既定で構築されるスレッド オブジェクトの場合、`thread::get_id` メソッドは、呼び出し時に結合できる実行スレッドに対して、既定で構築されるスレッド オブジェクトすべてで同じで、`this_thread::get_id` によって返される値とは異なる値を持つオブジェクトを返します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-classes"></a>パブリック クラス  
  
|名前|説明|  
|----------|-----------------|  
|[thread::id クラス](#thread__id_class)|関連するスレッドを一意に識別します。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[thread::thread コンストラクター](#thread__thread_constructor)|`thread` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[thread::detach メソッド](#thread__detach_method)|`thread` オブジェクトから関連するスレッドをデタッチします。|  
|[thread::get_id メソッド](#thread__get_id_method)|関連付けられたスレッドの一意の識別子を返します。|  
|[thread::hardware_concurrency メソッド](#thread__hardware_concurrency_method)|静的。 ハードウェア スレッド コンテキストの数の見積もりを返します。|  
|[thread::join メソッド](#thread__join_method)|関連のスレッドが完了するまでブロックします。|  
|[thread::joinable メソッド](#thread__joinable_method)|関連付けられたスレッドが結合可能かどうかを指定します。|  
|[thread::native_handle メソッド](#thread__native_handle_method)|スレッド ハンドルを表す実装固有の型を返します。|  
|[thread::swap メソッド](#thread__swap_method)|オブジェクトの状態を指定した `thread` オブジェクトと交換します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[thread::operator=](#thread__operator_eq)|スレッドを現在の `thread` オブジェクトと関連付けます。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** thread  
  
 **名前空間:** std  
  
##  <a name="a-namethreaddetachmethoda--threaddetach-method"></a><a name="thread__detach_method"></a>  thread::detach メソッド  
 関連するスレッドをデタッチします。 オペレーティング システムは、終了時にスレッド リソースを解放することが必要になります。  
  
```
void detach();
```  
  
### <a name="remarks"></a>コメント  
 `detach` を呼び出した後、後続の [get_id](#thread__get_id_method) 呼び出しによって [id](#thread__id_class) が返されます。  
  
 呼び出し元のオブジェクトに関連付けられているスレッドが結合可能でない場合、関数は、エラー コード `invalid_argument` で [system_error](../standard-library/system-error-class.md) をスローします。  
  
 呼び出し元のオブジェクトに関連付けられているスレッドが無効な場合、関数は、エラー コード `no_such_process` で `system_error` をスローします。  
  
##  <a name="a-namethreadgetidmethoda--threadgetid-method"></a><a name="thread__get_id_method"></a>  thread::get_id メソッド  
 関連付けられたスレッドの一意の識別子を返します。  
  
```
id get_id() const noexcept;
```  
  
### <a name="return-value"></a>戻り値  
 関連付けられたスレッドを一意に識別する [thread::id](#thread__id_class) オブジェクト、またはオブジェクトに関連付けられているスレッドがない場合は `thread::id()`。  
  
##  <a name="a-namethreadhardwareconcurrencymethoda--threadhardwareconcurrency-method"></a><a name="thread__hardware_concurrency_method"></a>  thread::hardware_concurrency メソッド  
 ハードウェア スレッド コンテキストの数の見積もりを返す静的メソッド。  
  
```
static unsigned int hardware_concurrency() noexcept;
```  
  
### <a name="return-value"></a>戻り値  
 ハードウェア スレッド コンテキストの数の見積もり。 値を計算できない場合や、値が適切に定義されていない場合、このメソッドは 0 を返します。  
  
##  <a name="a-namethreadidclassa--threadid-class"></a><a name="thread__id_class"></a>  thread::id クラス  
 プロセス内の各実行スレッドの一意の識別子を提供します。  
  
```
class thread::id {
    id() noexcept;
};
```  
  
### <a name="remarks"></a>コメント  
 既定のコンストラクターは、既存のスレッドのオブジェクトについて、`thread::id` オブジェクトに等しいオブジェクトを作成しません。  
  
 既定で構築される `thread::id` オブジェクトは等しいものになります。  
  
##  <a name="a-namethreadjoinmethoda--threadjoin-method"></a><a name="thread__join_method"></a>  thread::join メソッド  
 呼び出し元のオブジェクトに関連付けられている実行スレッドが完了するまでブロックします。  
  
```
void join();
```  
  
### <a name="remarks"></a>コメント  
 呼び出しが成功すると、呼び出し元のオブジェクトの後続の [get_id](#thread__get_id_method) 呼び出しは、既存のどのスレッドの `thread::id` にも等しくない既定の [thread::id](#thread__id_class) を返します。呼び出しが成功しなかった場合、`get_id` によって返される値は変更されません。  
  
##  <a name="a-namethreadjoinablemethoda--threadjoinable-method"></a><a name="thread__joinable_method"></a>  thread::joinable メソッド  
 関連付けられたスレッドが*結合可能*かどうかを指定します。  
  
```
bool joinable() const noexcept;
```  
  
### <a name="return-value"></a>戻り値  
 関連付けられたスレッドが*結合可能*な場合は `true`、それ以外の場合は `false`。  
  
### <a name="remarks"></a>コメント  
 `get_id() != id()` の場合、スレッド オブジェクトは*結合可能*です。  
  
##  <a name="a-namethreadnativehandlemethoda--threadnativehandle-method"></a><a name="thread__native_handle_method"></a>  thread::native_handle メソッド  
 スレッド ハンドルを表す実装固有の型を返します。 スレッド ハンドルは、実装固有の方法で使用できます。  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>戻り値  
 `native_handle_type` は、`void *` としてキャストされる Win32 `HANDLE` と定義されます。  
  
##  <a name="a-namethreadoperatoreqa--threadoperator"></a><a name="thread__operator_eq"></a>  thread::operator=  
 指定したオブジェクトのスレッドを現在のオブジェクトに関連付けます。  
  
```
thread& operator=(thread&& Other) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `Other`  
 `thread` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `*this`  
  
### <a name="remarks"></a>コメント  
 メソッドは、呼び出し元のオブジェクトが結合可能である場合、デタッチを呼び出します。  
  
 関連付けが行われると、`Other` が既定で構築される状態に設定されます。  
  
##  <a name="a-namethreadswapmethoda--threadswap-method"></a><a name="thread__swap_method"></a>  thread::swap メソッド  
 オブジェクトの状態を、指定された `thread` オブジェクトの状態と交換します。  
  
```
void swap(thread& Other) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `Other`  
 `thread` オブジェクト。  
  
##  <a name="a-namethreadthreadconstructora--threadthread-constructor"></a><a name="thread__thread_constructor"></a>  thread::thread コンストラクター  
 `thread` オブジェクトを構築します。  
  
```
thread() noexcept;
template <class Fn, class... Args>
explicit thread(Fn&& F, Args&&... A);

thread(thread&& Other) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `F`  
 スレッドによって実行されるアプリケーション定義関数。  
  
 `A`  
 `F` に渡す引数のリスト。  
  
 `Other`  
 既存の `thread` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 最初のコンストラクターは、実行スレッドに関連付けられていないオブジェクトを構築します。 構築されたオブジェクトの `get_id` への呼び出しによって返される値は `thread::id()` です。  
  
 2 番目のコンストラクターは、新しい実行スレッドに関連付けられているオブジェクトを構築し、[\<functional>](../standard-library/functional.md) で定義されている擬似関数 `INVOKE` を実行します。 新しいスレッドを開始するのに十分なリソースがない場合、関数は、エラー コード `resource_unavailable_try_again` で [system_error](../standard-library/system-error-class.md) オブジェクトをスローします。 `F` への呼び出しが、キャッチされない例外で終了する場合、[terminate](../standard-library/exception-functions.md#terminate) が呼び出されます。  
  
 3 番目のコンストラクターは、`Other` に関連付けられているスレッドに関連付けられているオブジェクトを構築します。 `Other` は既定で構築される状態に設定されます。  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<thread>](../standard-library/thread.md)




