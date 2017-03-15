---
title: "completion_future クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amprt/Concurrency::completion_future
dev_langs:
- C++
ms.assetid: 1303c62e-546d-4b02-a578-251ed3fc0b6b
caps.latest.revision: 8
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
ms.openlocfilehash: a9a77c3cf3c183021b70789b0e17a6b8ad8d786c
ms.lasthandoff: 02/24/2017

---
# <a name="completionfuture-class"></a>completion_future クラス
C ++. AMP の非同期操作に対応するフューチャを表します。  
  
### <a name="syntax"></a>構文  
  
```  
class completion_future;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[completion_future コンス トラクター](#ctor)|`completion_future` クラスの新しいインスタンスを初期化します。|  
|[~ completion_future デストラクター](#dtor)|`completion_future` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[get メソッド](#get)|関連する非同期操作が完了するまで待機します。|  
|[then メソッド](#then)|関連する非同期操作の実行が終了するときに、実行される `completion_future` オブジェクトにコールバック関数オブジェクトを継承します。|  
|[to_task メソッド](#to_task)|関連する非同期操作に対応する `task` オブジェクトを返します。|  
|[有効なメソッド](#valid)|オブジェクトが非同期操作に関連するかどうかを示すブール値を取得します。|  
|[wait メソッド](#wait)|関連する非同期操作が完了するまでブロックします。|  
|[wait_for メソッド](#wait_for)|関連する非同期操作が完了するまで、または `_Rel_time` で指定された時間が経過するまで、ブロックします。|  
|[wait_until メソッド](#wait_until)|関連する非同期操作が完了するまで、または現在の時間が `_Abs_time` によって指定された値を超過するまで、ブロックします。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[演算子 std::shared_future\<void > 演算子](#operator_shared_future)|`completion_future` オブジェクトを `std::shared_future` オブジェクトに暗黙的に変換します。|  
|[operator = 演算子](#operator_eq)|指定された `completion_future` オブジェクトの内容をこのオブジェクトにコピーします。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `completion_future`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** concurrency  


## <a name="a-namectora-completionfuture"></a><a name="ctor"></a>completion_future 

`completion_future` クラスの新しいインスタンスを初期化します。  
  
### <a name="syntax"></a>構文  
  
```  
completion_future();  
  
completion_future(  
    const completion_future& _Other );  
  
completion_future(  
    completion_future&& _Other );  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 `completion_future`オブジェクトをコピーまたは移動します。  
  
### <a name="overloads-list"></a>オーバーロードの一覧  
  
|名前|説明|  
|----------|-----------------|  
|`completion_future();`|新しいインスタンスを初期化、`completion_future`クラス|  
|`completion_future(const completion_future& _Other);`|新しいインスタンスを初期化、`completion_future`クラス コンス トラクターをコピーしています。|  
|`completion_future(completion_future&& _Other);`|新しいインスタンスを初期化、`completion_future`クラス コンス トラクターを移動しています。|  
  
## <a name="a-namegeta-get"></a><a name="get"></a>取得 

関連する非同期操作が完了するまで待機します。 非同期の操作中にいずれかが発生した場合は、ストアドの例外をスローします。  
  
### <a name="syntax"></a>構文  
  
```  
void get() const;  
```  
  
## <a name="a-nameoperatorsharedfuturea-operator-stdsharedfuturevoid"></a><a name="operator_shared_future"></a>演算子 std::shared_future<void> 

`completion_future` オブジェクトを `std::shared_future` オブジェクトに暗黙的に変換します。  
  
### <a name="syntax"></a>構文  
  
```  
operator std::shared_future<void>() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `std::shared_future` オブジェクト。  
  
## <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>演算子 = 

指定された `completion_future` オブジェクトの内容をこのオブジェクトにコピーします。  
  
### <a name="syntax"></a>構文  
  
```  
completion_future&  operator= (const completion_future& _Other );    
completion_future&  operator= (completion_future&& _Other );  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 コピーするオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 この `completion_future` オブジェクトへの参照。  
  
## <a name="overloads-list"></a>オーバーロードの一覧  
  
|名前|説明|  
|----------|-----------------|  
|`completion_future& operator=(const completion_future& _Other);`|指定した内容をコピー`completion_future`オブジェクトのディープ コピーを使用してこの&1; つにします。|  
|`completion_future& operator=(completion_future&& _Other);`|指定した内容をコピー`completion_future`オブジェクトを移動代入を使用して、この&1; つにします。|  
  
## <a name="a-namethena-then"></a><a name="then"></a>そうしたら 

関連する非同期操作の実行が終了するときに、実行される `completion_future` オブジェクトにコールバック関数オブジェクトを継承します。  
  
### <a name="syntax"></a>構文  
  
```  
template <typename _Functor>  
void then(const _Functor & _Func ) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Functor`  
 コールバック ファンクタ。  
  
 `_Func`  
 コールバック関数オブジェクト。  
  
## <a name="a-nametotaska-totask"></a><a name="to_task"></a>to_task 

関連する非同期操作に対応する `task` オブジェクトを返します。  
  
### <a name="syntax"></a>構文  
  
```  
concurrency::task<void> to_task() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`task`関連する非同期操作に対応するオブジェクト。  
  
## <a name="a-namevalida-valid"></a><a name="valid"></a>有効です 

オブジェクトが、非同期操作に関連付けられているかどうかを示すブール値を取得します。  
  
### <a name="syntax"></a>構文  
  
```  
bool valid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `true`オブジェクトが、非同期操作; に関連付けられている場合それ以外の場合、`false`です。  
  
## <a name="a-namewaita-wait"></a><a name="wait"></a>待機 

関連する非同期操作が完了するまでブロックします。  
  
### <a name="syntax"></a>構文  
  
```  
void wait() const;  
```  
  
## <a name="a-namewaitfora-waitfor"></a><a name="wait_for"></a>wait_for 

関連する非同期操作が完了するまで、または `_Rel_time` で指定された時間が経過するまで、ブロックします。  
  
### <a name="syntax"></a>構文  
  
```  
template <  
    class _Rep,  
    class _Period  
>  
std::future_status::future_status wait_for(  
    const std::chrono::duration< _Rep, _Period>& _Rel_time ) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rep`  
 タイマー刻みの数を表す演算型。  
  
 `_Period`  
 タイマー刻みごとに経過する秒数を表す std::ratio。  
  
 `_Rel_time`  
 操作が完了するまでの最大待機時間。  
  
### <a name="return-value"></a>戻り値  
 戻り値:  
  
-   関連する非同期操作が実行されていない場合、`std::future_status::deferred`。  
  
-   関連する非同期操作が終了した場合、`std::future_status::ready`。  
  
-   指定した期間が経過した場合、`std::future_status::timeout`。  
  
## <a name="a-namewaituntila-waituntil"></a><a name="wait_until"></a>wait_until 

関連する非同期操作が完了するまで、または現在の時間が `_Abs_time` によって指定された値を超過するまで、ブロックします。  
  
### <a name="syntax"></a>構文  
  
```  
template <  
    class _Clock,  
    class _Duration  
>  
std::future_status::future_status wait_until(  
    const std::chrono::time_point< _Clock, _Duration>& _Abs_time ) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Clock`  
 このタイム ポイントが測定されたクロック。  
  
 `_Duration`  
 `_Clock` のエポックの開始からの期間、その後で関数がタイムアウトします。  
  
 `_Abs_time`  
 その後で関数がタイムアウトする時点。  
  
### <a name="return-value"></a>戻り値  
 戻り値:  
  
1.  関連する非同期操作が実行されていない場合、`std::future_status::deferred`。  
  
2.  関連する非同期操作が終了した場合、`std::future_status::ready`。  
  
3.  指定された期間が経過した場合、`std::future_status::timeout`。  
  
## <a name="a-namedtora-completionfuture"></a><a name="dtor"></a>~ completion_future 

`completion_future` オブジェクトを破棄します。  
  
### <a name="syntax"></a>構文  
  
```  
~completion_future();  
```  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

