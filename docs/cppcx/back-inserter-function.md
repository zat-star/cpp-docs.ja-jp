---
title: "back_inserter 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::back_inserter
dev_langs:
- C++
helpviewer_keywords:
- back_inserter Function
ms.assetid: 91476338-5548-44b7-bc7e-2150f4fbe31a
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: de0d6a54931cc3133a7a882002c278b4b1506aec
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="backinserter-function"></a>back_inserter 関数
指定されたコレクションの末尾に要素を挿入するために使用される反復子を返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
template <typename T>
Platform::BackInsertIterator<T>   
    back_inserter(IVector<T>^ v);  
  
template<typename T>  
Platform::BackInsertIterator<T>   
   back_inserter(IObservableVector<T>^ v);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 テンプレート型パラメーター。  
  
 `v`  
 基になるコレクションへのアクセスを提供するインターフェイス ポインター。  
  
### <a name="return-value"></a>戻り値  
 反復子。  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Windows::Foundation::Collections  
  
## <a name="see-also"></a>参照  
 [:Foundation Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)