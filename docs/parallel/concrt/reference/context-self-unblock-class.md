---
title: "context_self_unblock クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- context_self_unblock
- CONCRT/concurrency::context_self_unblock
- CONCRT/concurrency::context_self_unblock::context_self_unblock
dev_langs: C++
helpviewer_keywords: context_self_unblock class
ms.assetid: 9601cd28-4f40-4c2e-89ab-747068956331
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0478e018aadd0e8e73da3691d2b9bf6974569f23
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="contextselfunblock-class"></a>context_self_unblock クラス
このクラスは、同じコンテキストから `Unblock` オブジェクトの `Context` メソッドが呼び出された場合にスローされる例外を表します。 これは、特定のコンテキストがそれ自体のブロックを解除しようとしたことを示します。  
  
## <a name="syntax"></a>構文  
  
```  
class context_self_unblock : public std::exception;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[context_self_unblock](#ctor)|オーバーロードされます。 `context_self_unblock` オブジェクトを構築します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `context_self_unblock`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a>context_self_unblock 

 `context_self_unblock` オブジェクトを構築します。  
  
```  
explicit _CRTIMP context_self_unblock(_In_z_ const char* _Message) throw();

 
context_self_unblock() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  
## <a name="see-also"></a>参照  
 [concurrency 名前空間](concurrency-namespace.md)
