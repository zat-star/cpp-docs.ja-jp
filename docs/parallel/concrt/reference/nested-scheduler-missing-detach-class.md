---
title: "nested_scheduler_missing_detach クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach::nested_scheduler_missing_detach
dev_langs:
- C++
helpviewer_keywords:
- nested_scheduler_missing_detach class
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 7ab8dc3761c6f11529b70ec4d71bbaebdfea0493
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

---
# <a name="nestedschedulermissingdetach-class"></a>nested_scheduler_missing_detach クラス
このクラスは、`CurrentScheduler::Detach` オブジェクトの `Attach` メソッドによって別のスケジューラにアタッチされているコンテキストで `Scheduler` メソッドが呼び出されなかったことを、同時実行ランタイムが検出した場合にスローされる例外を表します。  
  
## <a name="syntax"></a>構文  
  
```
class nested_scheduler_missing_detach : public std::exception;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[nested_scheduler_missing_detach](#ctor)|オーバーロードされます。 `nested_scheduler_missing_detach` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 呼び出して別のスケジューラ内を入れ子にする場合にのみ、この例外がスローされます、`Attach`のメソッド、`Scheduler`既にによって所有されているか、別のスケジューラにアタッチされているコンテキストでのオブジェクト。 同時実行ランタイムは、問題の特定を支援するために、シナリオを検出できるとな場合にこの例外をスローします。 呼び出しを無視していないすべてのインスタンス、`CurrentScheduler::Detach`メソッドがこの例外をスローすることが保証されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `nested_scheduler_missing_detach`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a>nested_scheduler_missing_detach 

 `nested_scheduler_missing_detach` オブジェクトを構築します。  
  
```
explicit _CRTIMP nested_scheduler_missing_detach(_In_z_ const char* _Message) throw();

nested_scheduler_missing_detach() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [Scheduler クラス](scheduler-class.md)

