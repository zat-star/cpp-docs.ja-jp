---
title: "is_trivially_assignable クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- type_traits/std::is_trivially_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: d37d4c827a082f7db179d4fb7014cba371103e71
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

---
# <a name="istriviallyassignable-class"></a>is_trivially_assignable クラス
`From` 型の値を `To` 型に普通に代入できるかどうかをテストします  
  
## <a name="syntax"></a>構文  
  
```
template <class To, class From>  
struct is_trivially_assignable;
```  
  
#### <a name="parameters"></a>パラメーター  
 目的  
 代入を受け取るオブジェクトの型。  
  
 提供元  
 値を渡すオブジェクトの型。  
  
## <a name="remarks"></a>コメント  
 式 `declval<To>() = declval<From>()` は正しい形式である必要があり、トリビアルでない演算を必要としないことがコンパイラに判明している必要があります。 `From` と `To` の両方とも完全な型、`void`、または不明なバインドの配列にする必要があります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)




