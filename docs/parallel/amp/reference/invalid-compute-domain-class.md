---
title: "invalid_compute_domain クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- invalid_compute_domain
- AMPRT/invalid_compute_domain
- AMPRT/Concurrency::invalid_compute_domain::invalid_compute_domain
dev_langs:
- C++
helpviewer_keywords:
- invalid_compute_domain class
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf8393e3af29c09376d4213bcdcec7642a593081
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="invalidcomputedomain-class"></a>invalid_compute_domain クラス
ランタイムがで指定された計算ドメインを使用して、カーネルを起動できない場合にスローされる例外、 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)呼び出しサイトです。  

  
## <a name="syntax"></a>構文  
  
```  
class invalid_compute_domain : public runtime_exception;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[invalid_compute_domain コンス トラクター](#ctor)|`invalid_compute_domain` クラスの新しいインスタンスを初期化します。|  

  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `runtime_exception`  
  
 `invalid_compute_domain`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** Concurrency  

## <a name="ctor"></a> invalid_compute_domain 

クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
explicit invalid_compute_domain(  
    const char * _Message ) throw();  
  
invalid_compute_domain() throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明。  
  
### <a name="return-value"></a>戻り値  
 `invalid_compute_domain` クラスのインスタンス。  
    
## <a name="see-also"></a>参照  
 [Concurrency 名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
