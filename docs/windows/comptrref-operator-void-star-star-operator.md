---
title: "Comptrref::operator void * * 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRef::operator void**
dev_langs: C++
helpviewer_keywords: operator void** operator
ms.assetid: f020045c-9de4-4392-8783-73f0fc0761c6
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a86f36f075dcee9688ee0eeca55e22a6eb7bb6fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comptrrefoperator-void-operator"></a>ComPtrRef::operator void** 演算子
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
operator void**() const;  
```  
  
## <a name="remarks"></a>コメント  
 現在の ComPtrRef オブジェクトを削除するには、ポインター-へのポインター - ComPtrRef オブジェクトによって表されるインターフェイスへのポインターをキャスト`void`、キャスト ポインターを返します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照  
 [ComPtrRef クラス](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)