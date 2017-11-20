---
title: "&lt;thread&gt; 関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- thread/std::get_id
- thread/std::sleep_for
- thread/std::sleep_until
- thread/std::swap
- thread/std::yield
ms.assetid: bb1aa1ef-fe3f-4e2c-8b6e-e22dbf2f5a19
caps.latest.revision: "12"
manager: ghogen
helpviewer_keywords:
- std::get_id [C++]
- std::sleep_for [C++]
- std::sleep_until [C++]
- std::swap [C++]
- std::yield [C++]
ms.openlocfilehash: dd073f48eb926e8fec0017f63ab77a91eb65acff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ltthreadgt-functions"></a>&lt;thread&gt; 関数
||||  
|-|-|-|  
|[get_id](#get_id)|[sleep_for](#sleep_for)|[sleep_until](#sleep_until)|  
|[swap](#swap)|[yield](#yield)|  
  
##  <a name="get_id"></a>  get_id  
 現在の実行スレッドを一意に識別します。  
  
```  
thread::id this_thread::get_id() noexcept;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の実行のスレッドを一意に識別する [thread::id](../standard-library/thread-class.md) 型のオブジェクト。  
  
##  <a name="sleep_for"></a>  sleep_for  
 呼び出し元のスレッドをブロックします。  
  
```  
template <class Rep,  
class Period>  
inline void sleep_for(const chrono::duration<Rep, Period>& Rel_time);
```  
  
### <a name="parameters"></a>パラメーター  
 `Rel_time`  
 期間を指定する [duration](../standard-library/duration-class.md) オブジェクト。  
  
### <a name="remarks"></a>コメント  
 関数は、少なくとも、`Rel_time` で指定された時間、呼び出し元のスレッドをブロックします。 この関数では、例外がスローされません。  
  
##  <a name="sleep_until"></a>  sleep_until  
 少なくとも指定された時間まで、呼び出し元スレッドをブロックします。  
  
```  
template <class Clock, class Duration>  
void sleep_until(const chrono::time_point<Clock, Duration>& Abs_time);

void sleep_until(const xtime *Abs_time);
```  
  
### <a name="parameters"></a>パラメーター  
 `Abs_time`  
 特定の時点を表します。  
  
### <a name="remarks"></a>コメント  
 この関数では、例外がスローされません。  
  
##  <a name="swap"></a>  swap  
 2 つの `thread` オブジェクトの状態を交換します。  
  
```  
void swap(thread& Left, thread& Right) noexcept;  
```  
  
### <a name="parameters"></a>パラメーター  
 `Left`  
 左側の `thread` オブジェクト。  
  
 `Right`  
 右側の `thread` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 関数は `Left.swap(Right)` を呼び出します。  
  
##  <a name="yield"></a>  yield  
 現在のスレッドが通常引き続き実行される場合であっても、他のスレッドを実行するようオペレーティング システムに通知します。  
  
```  
inline void yield() noexcept;  
```  
  
## <a name="see-also"></a>関連項目  
 [\<thread>](../standard-library/thread.md)

