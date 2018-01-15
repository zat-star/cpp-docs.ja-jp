---
title: "Eventsource::invokeall メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::EventSource::InvokeAll
dev_langs: C++
helpviewer_keywords: InvokeAll method
ms.assetid: 1506618f-0421-4428-a4d0-4ea2b10a3bf6
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 45835b6929ae73559c427d374430b64e7ff21a61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="eventsourceinvokeall-method"></a>EventSource::InvokeAll メソッド
現在関連付けられている各イベント ハンドラーを呼び出します[EventSource](../windows/eventsource-class.md)オブジェクトの指定した引数型と引数を使用します。  
  
## <a name="syntax"></a>構文  
  
```  
void InvokeAll();  
template <  
   typename T0  
>  
void InvokeAll(  
   T0arg0  
);  
template <  
   typename T0,  
   typename T1  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6,  
   typename T7  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6,  
   T7arg7  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6,  
   typename T7,  
   typename T8  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6,  
   T7arg7,  
   T8arg8  
);  
template <  
   typename T0,  
   typename T1,  
   typename T2,  
   typename T3,  
   typename T4,  
   typename T5,  
   typename T6,  
   typename T7,  
   typename T8,  
   typename T9  
>  
void InvokeAll(  
   T0arg0,  
   T1arg1,  
   T2arg2,  
   T3arg3,  
   T4arg4,  
   T5arg5,  
   T6arg6,  
   T7arg7,  
   T8arg8,  
   T9arg9  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T0`  
 0 番目のイベント ハンドラーの引数の型。  
  
 `T1`  
 最初のイベント ハンドラーの引数の型。  
  
 `T2`  
 2 番目のイベント ハンドラーの引数の型。  
  
 `T3`  
 3 番目のイベント ハンドラーの引数の型。  
  
 `T4`  
 4 番目のイベント ハンドラーの引数の型。  
  
 `T5`  
 5 番目のイベント ハンドラーの引数の型。  
  
 `T6`  
 6 番目のイベント ハンドラーの引数の型。  
  
 `T7`  
 7 番目のイベント ハンドラーの引数の型。  
  
 `T8`  
 8 番目のイベント ハンドラーの引数の型。  
  
 `T9`  
 9 番目のイベント ハンドラーの引数の型。  
  
 `arg0`  
 0 番目のイベント ハンドラーの引数。  
  
 `arg1`  
 最初のイベント ハンドラーの引数。  
  
 `arg2`  
 2 番目のイベント ハンドラーの引数。  
  
 `arg3`  
 3 番目のイベント ハンドラーの引数。  
  
 `arg4`  
 4 番目のイベント ハンドラーの引数。  
  
 `arg5`  
 5 番目のイベント ハンドラーの引数。  
  
 `arg6`  
 6 番目のイベント ハンドラーの引数。  
  
 `arg7`  
 7 番目のイベント ハンドラーの引数。  
  
 `arg8`  
 8 番目のイベント ハンドラーの引数。  
  
 `arg9`  
 9 番目のイベント ハンドラーの引数。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>参照
 [EventSource クラス](../windows/eventsource-class.md)