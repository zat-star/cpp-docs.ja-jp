---
title: "is_trivially_destructible クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: type_traits/std::is_trivially_destructible
dev_langs: C++
helpviewer_keywords: is_trivially_destructible
ms.assetid: 3f7a787d-2448-40c5-ac51-a228318e02ce
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 47b734f531e0bc958c41afbef5f5023ca01649cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="istriviallydestructible-class"></a>is_trivially_destructible クラス
型が普通に破棄可能であるかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
struct is_trivially_destructible;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 照会する型。  
  
## <a name="remarks"></a>コメント  
 型 `T` が破棄可能な型であり、デストラクターが自明でない演算を使用しないことがコンパイラに判明している場合、型述語のインスタンスは true を保持します。 それ以外の場合、false を保持します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)



