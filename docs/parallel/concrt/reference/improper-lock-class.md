---
title: "improper_lock クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- improper_lock
- CONCRT/concurrency::improper_lock
- CONCRT/concurrency::improper_lock::improper_lock
dev_langs:
- C++
helpviewer_keywords:
- improper_lock class
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37cf615460cda6d0f33f0431e258cac843f456c4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
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
 通常、同じコンテキストで再帰的に再入不可能なロックの取得を試みが行われたときにこの例外がスローされます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `improper_lock`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a> improper_lock 

 `improper_lock exception` を構築します。  
  
```
explicit _CRTIMP improper_lock(_In_z_ const char* _Message) throw();

improper_lock() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  
## <a name="see-also"></a>参照  
 [同時実行 Namespace](concurrency-namespace.md)   
 [critical_section クラス](critical-section-class.md)   
 [reader_writer_lock クラス](reader-writer-lock-class.md)
