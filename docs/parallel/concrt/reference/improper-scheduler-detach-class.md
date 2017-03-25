---
title: "improper_scheduler_detach クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach::improper_scheduler_detach
dev_langs:
- C++
helpviewer_keywords:
- improper_scheduler_detach class
ms.assetid: 30132102-c900-4951-a470-b63b4e3aa2d2
caps.latest.revision: 19
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 0975354279c2a7e35524890498d9d7ebab1c18d3
ms.lasthandoff: 03/17/2017

---
# <a name="improperschedulerdetach-class"></a>improper_scheduler_detach クラス
このクラスは、`CurrentScheduler::Detach` オブジェクトの `Attach` メソッドによってスケジューラにアタッチされていないコンテキストで `Scheduler` メソッドが呼び出された場合にスローされる例外を表します。  
  
## <a name="syntax"></a>構文  
  
```
class improper_scheduler_detach : public std::exception;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[improper_scheduler_detach](#ctor)|オーバーロードされます。 `improper_scheduler_detach` オブジェクトを構築します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `improper_scheduler_detach`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a>improper_scheduler_detach 

 `improper_scheduler_detach` オブジェクトを構築します。  
  
```
explicit _CRTIMP improper_scheduler_detach(_In_z_ const char* _Message) throw();

improper_scheduler_detach() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [Scheduler クラス](scheduler-class.md)

