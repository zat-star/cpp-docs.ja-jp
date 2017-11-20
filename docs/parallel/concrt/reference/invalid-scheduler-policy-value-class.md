---
title: "invalid_scheduler_policy_value クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: concrt/concurrency::invalid_scheduler_policy_value
dev_langs: C++
helpviewer_keywords: invalid_scheduler_policy_value class
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dc8d6a06d578169cb60bc757c1719b7028e12b06
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="invalidschedulerpolicyvalue-class"></a>invalid_scheduler_policy_value クラス
このクラスは、`SchedulerPolicy` オブジェクトのポリシー キーがそのキーの無効な値に設定された場合にスローされる例外を表します。  
  
## <a name="syntax"></a>構文  
  
```
class invalid_scheduler_policy_value : public std::exception;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[invalid_scheduler_policy_value](invalid-scheduler-policy-thread-specification-class.md#ctor|オーバーロードされます。 `invalid_scheduler_policy_value` オブジェクトを構築します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `invalid_scheduler_policy_value`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
    
##  <a name="ctor"></a>invalid_scheduler_policy_value 

 `invalid_scheduler_policy_value` オブジェクトを構築します。  
  
```
explicit _CRTIMP invalid_scheduler_policy_value(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_value() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  

## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [SchedulerPolicy クラス](schedulerpolicy-class.md)
