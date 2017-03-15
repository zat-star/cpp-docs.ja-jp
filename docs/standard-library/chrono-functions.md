---
title: "&lt;chrono&gt; 関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
caps.latest.revision: 10
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 9824bdc37d1ae2d1d3a8e42c727986fd2a194514
ms.lasthandoff: 02/24/2017

---
# <a name="ltchronogt-functions"></a>&lt;chrono&gt; 関数
||||  
|-|-|-|  
|[duration_cast 関数](#duration_cast_function)|[time_point_cast 関数](#time_point_cast_function)|  
  

##  <a name="a-namedurationcastfunctiona--durationcast-function"></a><a name="duration_cast_function"></a>  duration_cast 関数  
 `duration` オブジェクトを指定した型にキャストします。  
  
```  
template <class To, class Rep, class Period>  
constexpr To duration_cast(const duration<Rep, Period>& Dur);
```  
  
### <a name="return-value"></a>戻り値  
 対象の型に収まる必要のある場合、省略された期間 `duration` を表す `To` 型の `Dur` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `To` が `duration` のインスタンス化の場合、この関数はオーバーロードの解決に関与しません。  
  
##  <a name="a-nametimepointcastfunctiona--timepointcast-function"></a><a name="time_point_cast_function">time_point_cast 関数</a>  
 [time_point](../standard-library/time-point-class.md) オブジェクトを指定した型にキャストします。  
  
```  
template <class To, class Clock, class Duration>  
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);
```  
  
### <a name="return-value"></a>戻り値  
 `time_point` 型の継続時間を含む `To` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `To` が [duration](../standard-library/duration-class.md) のインスタンス化ではない限り、この関数はオーバーロードの解決に関与しません。  
  
## <a name="see-also"></a>関連項目  
 [\<chrono>](../standard-library/chrono.md)


