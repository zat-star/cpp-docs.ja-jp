---
title: "unsupported_feature クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unsupported_feature
- AMPRT/unsupported_feature
- AMPRT/Concurrency::unsupported_feature
dev_langs:
- C++
helpviewer_keywords:
- unsupported_feature class
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
caps.latest.revision: 12
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
ms.openlocfilehash: 191678e0802696e7200945f96dc1f2bbd379cf57
ms.lasthandoff: 02/24/2017

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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** Concurrency  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

