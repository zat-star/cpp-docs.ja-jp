---
title: "missing_wait クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
dev_langs:
- C++
helpviewer_keywords:
- missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
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
ms.openlocfilehash: 70b1c77660992b33de2204fd4f4221ed6e957e21
ms.lasthandoff: 03/17/2017

---
# <a name="missingwait-class"></a>missing_wait クラス
このクラスは、`task_group` オブジェクトまたは `structured_task_group` オブジェクトのデストラクターの実行時に、そのオブジェクトにスケジュールされたタスクがまだ存在する場合にスローされる例外を表します。 例外の結果としてのスタック アンワインドによりデストラクターが実行される場合、この例外はスローされません。  
  
## <a name="syntax"></a>構文  
  
```
class missing_wait : public std::exception;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[missing_wait](#ctor)|オーバーロードされます。 `missing_wait` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 例外のフローでない場合はいずれかの呼び出しを担当しています、`wait`または`run_and_wait`のメソッド、`task_group`または`structured_task_group`消滅させるためには、そのオブジェクトを許可する前にオブジェクトです。 ランタイムが呼び出す忘れたを示す値としては、この例外をスロー、`wait`または`run_and_wait`メソッドです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `missing_wait`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a>missing_wait 

 `missing_wait` オブジェクトを構築します。  
  
```
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [task_group クラス](task-group-class.md)   
 [待機](task-group-class.md)   
 [run_and_wait](task-group-class.md)   
 [structured_task_group クラス](structured-task-group-class.md)

