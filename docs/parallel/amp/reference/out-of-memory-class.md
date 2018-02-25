---
title: "out_of_memory クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- out_of_memory
- AMPRT/out_of_memory
- AMPRT/Concurrency::out_of_memory::out_of_memory
dev_langs:
- C++
helpviewer_keywords:
- out_of_memory class
ms.assetid: 3aa7e682-8f13-4ae6-9188-31fb423956e4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 88f143493aec70d6176436e6acaee7944fa142ad
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="outofmemory-class"></a>out_of_memory クラス
システムまたはデバイスのメモリ不足のためにメソッドが失敗した場合にスローされる例外。  
  
## <a name="syntax"></a>構文  
  
```  
class out_of_memory : public runtime_exception;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[out_of_memory コンス トラクター](#ctor)|`out_of_memory` クラスの新しいインスタンスを初期化します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** Concurrency  
## <a name="ctor"></a> out_of_memory 

 クラスの新しいインスタンスを初期化します。  
  
### <a name="syntax"></a>構文  
  
```  
explicit out_of_memory(  
    const char * _Message ) throw();  
  
out_of_memory () throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明。  
  
### <a name="return-value"></a>戻り値  
 `out_of_memory` クラスの新しいインスタンス。  
  
  
## <a name="see-also"></a>参照  
 [Concurrency 名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
