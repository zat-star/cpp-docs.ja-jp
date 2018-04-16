---
title: "Deferrableeventargs::invokeallfinished メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 86b45205-3edb-4134-9cd0-ed7a7b4c3b1a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0ca021d66c615bfec84b8f08df8474eeb20709e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="deferrableeventargsinvokeallfinished-method"></a>DeferrableEventArgs::InvokeAllFinished メソッド
遅延イベントを処理するすべての処理が完了したことを示すために呼び出されます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
void InvokeAllFinished()  
```  
  
## <a name="remarks"></a>コメント  
 イベント ソース呼び出しの後にこのメソッドを呼び出す必要があります[InvokeAll](../windows/eventsource-invokeall-method.md)です。 このメソッドを呼び出すことで、さらに遅延が取られることを回避し、遅延が取られなかった場合は、完了ハンドラーの実行を強制します。  
  
 コード例は、次を参照してください。 [DeferrableEventArgs クラス](../windows/deferrableeventargs-class.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [DeferrableEventArgs クラス](../windows/deferrableeventargs-class.md)   
 [EventSource::InvokeAll メソッド](../windows/eventsource-invokeall-method.md)