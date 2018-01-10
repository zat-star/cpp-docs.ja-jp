---
title: "invalid_scheduler_policy_thread_specification クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: concrt/concurrency::invalid_scheduler_policy_thread_specification
dev_langs: C++
helpviewer_keywords: invalid_scheduler_policy_thread_specification class
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 82c53e760d09ecdcc39f50b30d68a6c0b5290c4a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="invalidschedulerpolicythreadspecification-class"></a>invalid_scheduler_policy_thread_specification クラス
このクラスは、`SchedulerPolicy` オブジェクトの同時実行数の限度を設定する際に、`MinConcurrency` キーに指定された値が `MaxConcurrency` キーの値よりも小さい場合にスローされる例外を表します。  
  
## <a name="syntax"></a>構文  
  
```
class invalid_scheduler_policy_thread_specification : public std::exception;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[invalid_scheduler_policy_thread_specification](無効です-スケジューラ-ポリシーの値-class.md #ctor|オーバーロードされます。 `invalid_scheduler_policy_value` オブジェクトを構築します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `invalid_scheduler_policy_thread_specification`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
##  <a name="ctor"></a>invalid_scheduler_policy_thread_specification 

 `invalid_scheduler_policy_value` オブジェクトを構築します。  
  
```
explicit _CRTIMP invalid_scheduler_policy_thread_specification(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_thread_specification() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  

## <a name="see-also"></a>参照  
 [同時実行 Namespace](concurrency-namespace.md)   
 [SchedulerPolicy クラス](schedulerpolicy-class.md)
