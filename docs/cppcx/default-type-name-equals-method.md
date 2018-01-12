---
title: "既定値:: (type_name)::equals メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/Platform::Object::Equals
dev_langs: C++
ms.assetid: 4450f835-06fc-4758-8d0a-72cf00007873
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bd5fcdbb71c1555d06e094f5e08f9da795f0d5a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="defaulttypenameequals-method"></a>default::(type_name)::Equals メソッド
指定したオブジェクトが、現在のオブジェクトと等しいかどうかを判断します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
  
bool Equals(  
    Object^ obj  
)  
```  
  
### <a name="parameters"></a>パラメーター  
 obj  
 比較対象のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが等しい場合は`true` 。それ以外の場合は `false`。  
  
### <a name="requirements"></a>必要条件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** 既定  
  
 **ヘッダー:** vccorlib.h  
  
## <a name="see-also"></a>参照  
 [default 名前空間](../cppcx/default-namespace.md)