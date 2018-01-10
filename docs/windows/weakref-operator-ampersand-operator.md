---
title: "Weakref::operator&amp;演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::WeakRef::operator&
dev_langs: C++
helpviewer_keywords: operator& operator
ms.assetid: 900afb73-3801-4d08-9b41-2e6a62011ccd
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 787712a857740afad539c0e44c450c6762aeb48f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="weakrefoperatoramp-operator"></a>Weakref::operator&amp;演算子
現在の WeakRef オブジェクトを表す ComPtrRef オブジェクトを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&() throw()  
```  
  
## <a name="return-value"></a>戻り値  
 現在の WeakRef オブジェクトを表す ComPtrRef オブジェクトです。  
  
## <a name="remarks"></a>コメント  
 これは、コード内で使用するものではありませんを内部ヘルパー演算子です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [WeakRef クラス](../windows/weakref-class.md)