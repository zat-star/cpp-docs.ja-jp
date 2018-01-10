---
title: "is_assignable クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_assignable
dev_langs: C++
helpviewer_keywords: is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ba99c19328b576900b1c269c24949baa832c8be7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="isassignable-class"></a>is_assignable クラス
`From` 型の値を `To` 型に代入できるかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class To, class From>  
struct is_assignable;
```  
  
#### <a name="parameters"></a>パラメーター  
 目的  
 代入を受け取るオブジェクトの型。  
  
 提供元  
 値を渡すオブジェクトの型。  
  
## <a name="remarks"></a>コメント  
 評価されていない式 `declval<To>() = declval<From>()` は整形式である必要があります。 `From` と `To` の両方とも完全な型、`void`、または不明なバインドの配列にする必要があります。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)



