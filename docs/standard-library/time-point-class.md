---
title: "time_point クラス |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::time_point
- chrono/std::chrono::time_point::time_point
- chrono/std::chrono::time_point::max
- chrono/std::chrono::time_point::min
- chrono/std::chrono::time_point::time_since_epoch
dev_langs:
- C++
ms.assetid: 18be1e52-57b9-489a-8a9b-f58894f0aaad
caps.latest.revision: 10
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 1c4d02cf83401e6a6dce3fa079d43dea0fce6270
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="timepoint-class"></a>time_point クラス
`time_point` では、時点を表す型について記述します。 これは、テンプレート引数 `Clock` によって表される新しいエポック以降の経過時間を格納する [duration](../standard-library/duration-class.md) 型のオブジェクトを保持します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Clock,  
    class Duration = typename Clock::duration>  
class time_point;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`time_point::clock`|テンプレート パラメーター `Clock` のシノニム。|  
|`time_point::duration`|テンプレート パラメーター `Duration` のシノニム。|  
|`time_point::period`|入れ子にされた型の名前 `duration::period` のシノニム。|  
|`time_point::rep`|入れ子にされた型の名前 `duration::rep` のシノニム。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[time_point](#time_point)|`time_point` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[max](#max)|`time_point::ref` の上限を指定します。|  
|[min](#min)|`time_point::ref` の下限を指定します。|  
|[time_since_epoch](#time_since_epoch)|格納された `duration` の値を返します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[time_point::operator+=](#op_add_eq)|指定した値を格納された期間に加算します。|  
|[time_point::operator-=](#operator-_eq)|指定した値を格納された期間から減算します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<chrono >  
  
 **名前空間:** std::chrono  
  
##  <a name="max"></a>time_point::max
 `time_point::ref` 型の値の上限の境界を返す静的メソッドです。  
  
```  
static constexpr time_point max();
```  
  
### <a name="return-value"></a>戻り値  
 実際には、`time_point(duration::max())` を返します。  
  
##  <a name="min"></a>time_point::min
 `time_point::ref` 型の値の下限の境界を返す静的メソッドです。  
  
```  
static constexpr time_point min();
```  
  
### <a name="return-value"></a>戻り値  
 実際には、`time_point(duration::min())` を返します。  
  
##  <a name="op_add_eq"></a>  time_point::operator+=  
 指定した値を格納された [duration](../standard-library/duration-class.md) 値に加算します。  
  
```  
time_point& operator+=(const duration& Dur);
```  
  
### <a name="parameters"></a>パラメーター  
 `Dur`  
 `duration` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 加算が実行された後の `time_point` オブジェクト。  
  
##  <a name="time_point__operator-_eq"></a>  time_point::operator-=  
 指定された値を格納された [duration](../standard-library/duration-class.md) 値から減算します。  
  
```  
time_point& operator-=(const duration& Dur);
```  
  
### <a name="parameters"></a>パラメーター  
 `Dur`  
 `duration` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 減算が実行された後の `time_point` オブジェクト。  
  
##  <a name="time_point"></a>  time_point::time_point コンストラクター  
 `time_point` オブジェクトを構築します。  
  
```  
constexpr time_point();

constexpr explicit time_point(const duration& Dur);

template <class Duration2>  
constexpr time_point(const time_point<clock, Duration2>& Tp);
```  
  
### <a name="parameters"></a>パラメーター  
 `Dur`  
 [duration](../standard-library/duration-class.md) オブジェクト。  
  
 `Tp`  
 `time_point` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 最初のコンストラクターは、格納されている `duration` 値が [duration::zero](../standard-library/duration-class.md#zero) と等しいオブジェクトを構築します。  
  
 2 番目のコンストラクターは、格納されている duration 値が `Dur` と等しいオブジェクトを構築します。 `is_convertible<Duration2, duration>` が *true を保持*しない限り、2 番目のコンストラクターはオーバーロードの解決に関与しません。 詳細については、「[<type_traits>](../standard-library/type-traits.md)」を参照してください。  
  
 3 番目のコンストラクターは、`duration` を使用してその `Tp.time_since_epoch()` 値を初期化します。  
  
##  <a name="time_since_epoch"></a>time_point::time_since_epoch
 格納されている [duration](../standard-library/duration-class.md) 値を取得します。  
  
```  
constexpr duration time_since_epoch() const;
```  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)


