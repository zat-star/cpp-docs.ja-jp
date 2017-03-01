---
title: "&lt;future&gt; 関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e3acc1e-736a-42dc-ade2-b2fe69aa96bc
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 57a9e0ba45c363d126ef44dc80eeb13d72b3733d
ms.lasthandoff: 02/24/2017

---
# <a name="ltfuturegt-functions"></a>&lt;future&gt; 関数
||||  
|-|-|-|  
|[async](#async_function)|[future_category](#future_category_function)|[make_error_code](#make_error_code_function)|  
|[make_error_condition](#make_error_condition_function)|[swap](#swap_function)|  
  
##  <a name="a-nameasyncfunctiona--async"></a><a name="async_function"></a>  async  
 *非同期プロバイダー*を表します。  
  
```
template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(Fn&& fn, ArgTypes&&... args);

template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(launch policy, Fn&& fn, ArgTypes&&... args);
```  
  
### <a name="parameters"></a>パラメーター  
 `policy`  
 [launch](../standard-library/future-enums.md#launch_enumeration) の値。  
  
### <a name="remarks"></a>コメント  
 省略形の定義:  
  
|||  
|-|-|  
|*dfn*|`decay_copy(forward<Fn>(fn))` の呼び出しの結果。|  
|*dargs*|`decay_copy(forward<ArgsTypes>(args…))` の呼び出しの結果。|  
|*Ty*|型 `result_of<Fn(ArgTypes…)>::type`。|  
  
 1 番目のテンプレート関数は、`async(launch::any, fn, args…)` を返します。  
  
 2 番目の関数は `future<Ty>` オブジェクトを返し、その*関連付けられた非同期状態*は、結果、*dfn* および *dargs* の値、実行の個別のスレッドを管理するためのスレッド オブジェクトを保持します。  
  
 `decay<Fn>::type` が launch 以外の型でない限り、2 番目の関数はオーバーロードの解決に関与しません。  
  
 `policy` が `launch::any` であれば、関数は `launch::async` か `launch::deferred` を選択できます。 この実装では、関数は `launch::async` を使用しています。  
  
 `policy` が `launch::async` であれば、関数は `INVOKE(dfn, dargs..., Ty)` を評価するスレッドを作成します。 関数はスレッドの作成後、結果を待たずに戻ります。 システムが新しいスレッドを開始できない場合、関数はエラー コードが `resource_unavailable_try_again` である [system_error](../standard-library/system-error-class.md) をスローします。  
  
 `policy` が `launch::deferred` である場合、関数は関連付けられた非同期状態を*遅延関数*の保持中としてマークして戻ります。 関連付けられた非同期状態が実際に準備完了になるまで待機する、時間指定のない関数への初めての呼び出しでは、`INVOKE(dfn, dargs..., Ty)` を評価することによって遅延関数が呼び出されます。  
  
 いずれの場合も、`future` オブジェクトの関連付けられた非同期状態は、`INVOKE(dfn, dargs…, Ty)` の評価が完了するまでは、例外がスローされても正常に制御が戻っても、*ready* には設定されません。 関連付けられた非同期状態の結果は、例外がスローされた場合の例外か、評価から返された値です。  
  
> [!NOTE]
>  `std::async` で開始されたタスクにアタッチされた `future` (または最後の [shared_future](../standard-library/shared-future-class.md)) の場合、タスクが完了していないと、デストラクターがブロックします。つまり、スレッドがまだ `.get()` または `.wait()` を呼び出しておらず、タスクがまだ実行中の場合、デストラクターによってブロックされます。 `future` から取得された `std::async` がローカル スコープ外に移動される場合、それを使う他のコードでは、共有状態が準備完了になることをデストラクターがブロックする場合があることに注意する必要があります。  
  
 擬似関数 `INVOKE` は [\<functional>](../standard-library/functional.md) で定義されています。  
  
##  <a name="a-namefuturecategoryfunctiona--futurecategory"></a><a name="future_category_function"></a>  future_category  
 `future` オブジェクトに関連するエラーの特性を設定する [error_category](../standard-library/error-category-class.md) オブジェクトへの参照を返します。  
  
```
const error_category& future_category() noexcept;
```  
  
##  <a name="a-namemakeerrorcodefunctiona--makeerrorcode"></a><a name="make_error_code_function"></a>  make_error_code  
 [future](../standard-library/future-class.md) エラーを特徴付ける [error_category](../standard-library/error-category-class.md) オブジェクトと共に、[error_code](../standard-library/error-code-class.md) を作成します。  
  
```
inline error_code make_error_code(future_errc Errno) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `Errno`  
 報告されたエラーを識別する [future_errc](../standard-library/future-enums.md#future_errc_enumeration) の値。  
  
### <a name="return-value"></a>戻り値  
 `error_code(static_cast<int>(Errno), future_category());`  
  
##  <a name="a-namemakeerrorconditionfunctiona--makeerrorcondition"></a><a name="make_error_condition_function"></a>  make_error_condition  
 [future](../standard-library/future-class.md) エラーを特徴付ける [error_category](../standard-library/error-category-class.md) オブジェクトと共に、[error_condition](../standard-library/error-condition-class.md) を作成します。  
  
```
inline error_condition make_error_condition(future_errc Errno) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `Errno`  
 報告されたエラーを識別する [future_errc](../standard-library/future-enums.md#future_errc_enumeration) の値。  
  
### <a name="return-value"></a>戻り値  
 `error_condition(static_cast<int>(Errno), future_category());`  
  
##  <a name="a-nameswapfunctiona--swap"></a><a name="swap_function"></a>  swap  
 *関連付けられた非同期状態*を、`promise` オブジェクト間で交換します。  
  
```
template <class Ty>
void swap(promise<Ty>& Left, promise<Ty>& Right) noexcept;

template <class Ty, class... ArgTypes>
void swap(packaged_task<Ty(ArgTypes...)>& Left, packaged_task<Ty(ArgTypes...)>& Right) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `Left`  
 左側の `promise` オブジェクト。  
  
 `Right`  
 右側の `promise` オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [\<future>](../standard-library/future.md)




