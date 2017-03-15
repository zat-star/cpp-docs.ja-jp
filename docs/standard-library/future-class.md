---
title: "future クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::future
dev_langs:
- C++
ms.assetid: 495e82c3-5341-4e37-87dd-b40107fbdfb6
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 6de4fecd3f5f65ac48cbb49f2ed4f874f4283487
ms.lasthandoff: 02/24/2017

---
# <a name="future-class"></a>future クラス
*非同期のリターン オブジェクト*を記述します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Ty>
class future;
```  
  
## <a name="remarks"></a>コメント  
 各標準*非同期プロバイダー*は、このテンプレートのインスタンス化の型を持つオブジェクトを返します。 `future` オブジェクトは、関連付けられている非同期プロバイダーへのアクセスのみを提供します。 同じ非同期プロバイダーに関連付けられている複数の非同期リターン オブジェクトが必要な場合は、`future` オブジェクトを [shared_future](../standard-library/shared-future-class.md) オブジェクトにコピーします。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[future::future コンストラクター](#future__future_constructor)|`future` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[future::get](#future__get_method)|関連付けられた非同期状態に格納されている結果を取得します。|  
|[future::share](#future__share_method)|オブジェクトを `shared_future` に変換します。|  
|[future::valid](#future__valid_method)|オブジェクトが空でないかどうかを指定します。|  
|[future::wait](#future__wait_method)|関連付けられた非同期状態が準備できるまで、現在のスレッドをブロックします。|  
|[future::wait_for](#future__wait_for_method)|関連付けられた非同期状態が準備できるまで、または指定した時間が経過するまでブロックします。|  
|[future::wait_until](#future__wait_until_method)|関連付けられた非同期状態が準備できるまで、または指定した時点までブロックします。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[future::operator=](#future__operator_eq)|指定したオブジェクトから関連付けられた非同期状態を転送します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** future  
  
 **名前空間:** std  
  
##  <a name="a-namefuturefutureconstructora--futurefuture-constructor"></a><a name="future__future_constructor"></a>  future::future コンストラクター  
 `future` オブジェクトを構築します。  
  
```
future() noexcept;
future(future&& Other) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `Other`  
 `future` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 1 つ目のコンストラクターは、関連付けられた非同期状態がない `future` オブジェクトを構築します。  
  
 2 つ目のコンストラクターは、`future` オブジェクトを構築し、`Other` から関連付けられた非同期状態を転送します。 `Other` に関連付けられた非同期状態は既にありません。  
  
##  <a name="a-namefuturegetmethoda--futureget"></a><a name="future__get_method"></a>  future::get  
 関連付けられた非同期状態に格納されている結果を取得します。  
  
```
Ty get();
```  
  
### <a name="return-value"></a>戻り値  
 結果が例外の場合は、そのメソッドが再スローします。 それ以外の場合、結果が返されます。  
  
### <a name="remarks"></a>コメント  
 結果を取得する前に、このメソッドは、関連付けられた非同期状態が準備できるまで、現在のスレッドをブロックします。  
  
 部分的特殊化 `future<Ty&>` では、格納されている値は、実質的には非同期プロバイダーに戻り値として渡されたオブジェクトへの参照です。  
  
 特殊化 `future<void>` には格納されている値がないため、このメソッドは `void` を返します。  
  
 その他の特殊化では、メソッドは、格納されている値からその戻り値を移動します。 そのため、このメソッドを&1; 回だけ呼び出します。  
  
##  <a name="a-namefutureoperatoreqa--futureoperator"></a><a name="future__operator_eq"></a>  future::operator=  
 関連付けられた非同期状態から、指定したオブジェクトを転送します。  
  
```
future& operator=(future&& Right) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `Right`  
 `future` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `*this`  
  
### <a name="remarks"></a>コメント  
 転送の後、`Right` に関連付けられた非同期状態は既にありません。  
  
##  <a name="a-namefuturesharemethoda--futureshare"></a><a name="future__share_method"></a>  future::share  
 オブジェクトを [shared_future](../standard-library/shared-future-class.md) オブジェクトに変換します。  
  
```
shared_future<Ty> share();
```  
  
### <a name="return-value"></a>戻り値  
 `shared_future(move(*this))`  
  
##  <a name="a-namefuturevalidmethoda--futurevalid"></a><a name="future__valid_method"></a>  future::valid  
 オブジェクトが関連付けられた非同期状態であるかどうかを指定します。  
  
```
bool valid() noexcept;
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが関連付けられた非同期状態である場合は `true` を返します。それ以外の場合は `false` を返します。  
  
##  <a name="a-namefuturewaitmethoda--futurewait"></a><a name="future__wait_method"></a>  future::wait  
 関連付けられた非同期状態が *ready* になるまで、現在のスレッドをブロックします。  
  
```cpp  
void wait() const;
```  
  
### <a name="remarks"></a>コメント  
 関連付けられている非同期状態は、非同期プロバイダーが戻り値を格納した場合か例外を格納した場合のみ *ready* になります。  
  
##  <a name="a-namefuturewaitformethoda--futurewaitfor"></a><a name="future__wait_for_method"></a>  future::wait_for  
 関連付けられた非同期状態が *ready* になるまで、または指定した時間が経過するまでブロックします。  
  
```
template <class Rep, class Period>
future_status wait_for(const chrono::duration<Rep, Period>& Rel_time) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `Rel_time`  
 スレッドがブロックする最大の時間間隔を指定する [chrono::duration](../standard-library/duration-class.md) オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 呼び出し側に戻る理由を示す [future_status](../standard-library/future-enums.md#future_status_enumeration)。  
  
### <a name="remarks"></a>コメント  
 関連付けられている非同期状態は、非同期プロバイダーが戻り値を格納した場合か例外を格納した場合のみ準備完了になります。  
  
##  <a name="a-namefuturewaituntilmethoda--futurewaituntil"></a><a name="future__wait_until_method"></a>  future::wait_until  
 関連付けられた非同期状態が *ready* になるまで、または指定した時点後まで現在のスレッドをブロックします。  
  
```cpp  
template <class Clock, class Duration>
future_status wait_until(const chrono::time_point<Clock, Duration>& Abs_time) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `Abs_time`  
 スレッドがブロックを解除できる時間を指定する [chrono::time_point](../standard-library/time-point-class.md) オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 呼び出し側に戻る理由を示す [future_status](../standard-library/future-enums.md#future_status_enumeration)。  
  
### <a name="remarks"></a>コメント  
 関連付けられている非同期状態は、非同期プロバイダーが戻り値を格納した場合か例外を格納した場合のみ *ready* になります。  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<future>](../standard-library/future.md)




