---
title: "is_nothrow_assignable クラス | Microsoft Docs"
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
- is_nothrow_assignable
- type_traits/std::is_nothrow_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 8f7cfa4eafda6061e503b5b8495d64c29a19eda8
ms.lasthandoff: 02/24/2017

---
# <a name="isnothrowassignable-class"></a>is_nothrow_assignable クラス
`From` 型の値を `To` 型に代入できるかどうか、および代入でスローしないことが判明しているかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class To, class From>  
struct is_nothrow_assignable;
```  
  
#### <a name="parameters"></a>パラメーター  
 目的  
 代入を受け取るオブジェクトの型。  
  
 提供元  
 値を渡すオブジェクトの型。  
  
## <a name="remarks"></a>コメント  
 式 `declval<To>() = declval<From>()` は正しい形式である必要があり、スローしないことがコンパイラに判明している必要があります。 `From` と `To` の両方とも完全な型、`void`、または不明なバインドの配列にする必要があります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)




