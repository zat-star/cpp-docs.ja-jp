---
title: "uninitialized_object クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amprt/Concurrency::uninitialized_object
dev_langs:
- C++
helpviewer_keywords:
- uninitialized_object class
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 1ff7840ec3ff4ab00b7e13d647c329a892dade42
ms.lasthandoff: 02/24/2017

---
# <a name="uninitializedobject-class"></a>uninitialized_object クラス
初期化されていないオブジェクトが使用される場合にスローされる例外です。  
  
## <a name="syntax"></a>構文  
  
```  
class uninitialized_object : public runtime_exception;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[uninitialized_object のコンス トラクター](#ctor)|`uninitialized_object` クラスの新しいインスタンスを初期化します。|  

  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `runtime_exception`  
  
 `uninitialized_object`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** Concurrency  
## <a name="a-nameuninitializedobjectctora-unsupportedfeature"></a><a name="uninitialized_object__ctor"></a>unsupported_feature 

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

## <a name="see-also"></a>関連項目  
 [同時実行 Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

