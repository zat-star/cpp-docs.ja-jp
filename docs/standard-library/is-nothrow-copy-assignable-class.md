---
title: "is_nothrow_copy_assignable クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37964edce6b8b6370302a29c76e80386e54ab5a4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="isnothrowcopyassignable-class"></a>is_nothrow_copy_assignable クラス
スローしないことがコンパイラに判明しているコピー代入演算子が型にあるかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>
struct is_nothrow_copy_assignable;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 照会する型。  
  
## <a name="remarks"></a>コメント  
 `is_nothrow_assignable<T&, const T&>` が true を保持する場合に、参照型 `T` に対して型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_nothrow_assignable クラス](../standard-library/is-nothrow-assignable-class.md)   





