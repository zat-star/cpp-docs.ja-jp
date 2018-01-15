---
title: "Makeallocator::allocate メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::MakeAllocator::Allocate
dev_langs: C++
helpviewer_keywords: Allocate method
ms.assetid: a01997bc-4ff1-4ed0-9def-e4aaa15b0598
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e93cd6b5b8b3489fc18e8b083c0fc59589ebd1d8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="makeallocatorallocate-method"></a>MakeAllocator::Allocate メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
__forceinline void* Allocate();  
```  
  
## <a name="return-value"></a>戻り値  
 成功した場合、割り当てられたメモリ; へのポインターそれ以外の場合、`nullptr`です。  
  
## <a name="remarks"></a>コメント  
 メモリが割り当てられ、現在 MakeAllocator オブジェクトに関連付けます。  
  
 割り当てられたメモリのサイズは、現在の MakeAllocator テンプレート パラメーターで指定された型のサイズです。  
  
 開発者は、異なるメモリ割り当てのモデルを実装する Allocate() メソッドのみをオーバーライドする必要があります。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>参照  
 [MakeAllocator クラス](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)