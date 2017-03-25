---
title: "invalid_oversubscribe_operation クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation::invalid_oversubscribe_operation
dev_langs:
- C++
helpviewer_keywords:
- invalid_oversubscribe_operation class
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
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
ms.openlocfilehash: 9263fd2bf7d4cfa3b1b8542b8a0bf8d2a3969326
ms.lasthandoff: 03/17/2017

---
# <a name="invalidoversubscribeoperation-class"></a>invalid_oversubscribe_operation クラス
このクラスは、`Context::Oversubscribe` パラメーターが `_BeginOversubscription` に設定された `false` メソッドを事前に呼び出さずに、`Context::Oversubscribe` パラメーターが `_BeginOversubscription` に設定された `true` メソッドを呼び出した場合にスローされる例外を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class invalid_oversubscribe_operation : public std::exception;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[invalid_oversubscribe_operation](#ctor)|オーバーロードされます。 `invalid_oversubscribe_operation` オブジェクトを構築します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `invalid_oversubscribe_operation`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a>invalid_oversubscribe_operation 

 `invalid_oversubscribe_operation` オブジェクトを構築します。  
  
```  
explicit _CRTIMP invalid_oversubscribe_operation(_In_z_ const char* _Message) throw();

 
invalid_oversubscribe_operation() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)

