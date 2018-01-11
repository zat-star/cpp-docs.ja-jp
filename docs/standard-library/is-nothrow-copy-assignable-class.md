---
title: "is_nothrow_copy_assignable クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_nothrow_copy_assignable
dev_langs: C++
helpviewer_keywords: is_nothrow_copy_assignable
ms.assetid: baa8abd6-4f53-489f-abba-8d5d5c53bbbc
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1fe17d40b104c1ae06ac8158db79925c0731d3ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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





