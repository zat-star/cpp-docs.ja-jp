---
title: "unsupported_feature クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unsupported_feature
- AMPRT/unsupported_feature
- AMPRT/Concurrency::unsupported_feature
dev_langs: C++
helpviewer_keywords: unsupported_feature class
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 967e06e713235e45a018cc32898f3baebdae52d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="unsupportedfeature-class"></a>unsupported_feature クラス
サポートされていない機能が使用される場合にスローされる例外です。  
  
## <a name="syntax"></a>構文  
  
```  
class unsupported_feature : public runtime_exception;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[unsupported_feature コンス トラクター](#ctor)|`unsupported_feature` 例外の新しいインスタンスを構築します。|  

  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `runtime_exception`  
  
 `unsupported_feature`  
  
## <a name="unsupported_feature__ctor"></a>unsupported_feature 

  unsupported_feature 例外の新しいインスタンスを構築します。  
  
### <a name="syntax"></a>構文  
  
```  
explicit unsupported_feature(  
    const char * _Message ) throw();  
  
unsupported_feature() throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明。  
  
### <a name="return-value"></a>戻り値  
 `unsupported_feature` オブジェクト。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** Concurrency  
  
## <a name="see-also"></a>参照  
 [Concurrency 名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
