---
title: "invalid_operation クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- invalid_operation
- CONCRT/concurrency::invalid_operation
- CONCRT/concurrency::invalid_operation::invalid_operation
dev_langs:
- C++
helpviewer_keywords:
- invalid_operation class
ms.assetid: 26ba07dc-fcdf-44cb-b748-a31d35205b52
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
ms.openlocfilehash: 85821bbbe62fe5da93165065cb6f17ae4e938f4e
ms.lasthandoff: 03/17/2017

---
# <a name="invalidoperation-class"></a>invalid_operation クラス
このクラスは、同時実行ランタイムによってスローされる他の例外の種類によって正確に記述されない無効な操作を実行しようとした場合にスローされる例外を表します。  
  
## <a name="syntax"></a>構文  
  
```
class invalid_operation : public std::exception;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[invalid_operation](#ctor)|オーバーロードされます。 `invalid_operation` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 通常、この例外がスローされる条件については、それぞれのメソッドにドキュメント化されています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `invalid_operation`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a>invalid_operation 

 `invalid_operation` オブジェクトを構築します。  
  
```
explicit _CRTIMP invalid_operation(_In_z_ const char* _Message) throw();

invalid_operation() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)

