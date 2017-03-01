---
title: "task_canceled クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::task_canceled
dev_langs:
- C++
helpviewer_keywords:
- task_canceled class
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
caps.latest.revision: 11
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: dcf930c7efd1a7d7b015919b2009440045dd18fe
ms.lasthandoff: 02/24/2017

---
# <a name="taskcanceled-class"></a>task_canceled クラス
このクラスは、現在のタスクを強制的に取り消すために PPL タスク レイヤーによってスローされる例外を表します。 によってもスローされます、`get()`メソッドを[タスク](/visualstudio/extensibility/debugger/task-class-internal-members)、取り消されたタスクに対してです。  
  
## <a name="syntax"></a>構文  
  
```
class task_canceled : public std::exception;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[task_canceled コンス トラクター](#ctor)|オーバーロードされます。 `task_canceled` オブジェクトを構築します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `task_canceled`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namectora-taskcanceled"></a><a name="ctor"></a>task_canceled 

 `task_canceled` オブジェクトを構築します。  
  
```
explicit _CRTIMP task_canceled(_In_z_ const char* _Message) throw();

task_canceled() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)

