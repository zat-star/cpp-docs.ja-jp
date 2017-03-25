---
title: "improper_lock クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- improper_lock
- CONCRT/concurrency::improper_lock
- CONCRT/concurrency::improper_lock::improper_lock
dev_langs:
- C++
helpviewer_keywords:
- improper_lock class
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
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
ms.openlocfilehash: 336cd222ee70253954905b1ea01144160eeb2f06
ms.lasthandoff: 03/17/2017

---
# <a name="improperlock-class"></a>improper_lock クラス
このクラスは、ロックが正しく取得されなかった場合にスローされる例外を表します。  
  
## <a name="syntax"></a>構文  
  
```
class improper_lock : public std::exception;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[improper_lock](#ctor)|オーバーロードされます。 `improper_lock exception` を構築します。|  
  
## <a name="remarks"></a>コメント  
 通常、同じコンテキストで再帰的に再入不可能なロックの取得を試みときにこの例外がスローされます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `improper_lock`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a>improper_lock 

 `improper_lock exception` を構築します。  
  
```
explicit _CRTIMP improper_lock(_In_z_ const char* _Message) throw();

improper_lock() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [critical_section クラス](critical-section-class.md)   
 [reader_writer_lock クラス](reader-writer-lock-class.md)

