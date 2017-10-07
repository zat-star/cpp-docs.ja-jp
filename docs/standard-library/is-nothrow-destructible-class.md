---
title: "is_nothrow_destructible クラス | Microsoft Docs"
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
- type_traits/std::is_nothrow_destructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_destructible
ms.assetid: 0bbd8a28-e312-4d72-bd28-aac027f974d3
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 857d37d89ff61dd7e6f0768796024565b03c920f
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

---
# <a name="isnothrowdestructible-class"></a>is_nothrow_destructible クラス
型が破棄可能で、デストラクタ―がスローしないとコンパイラに判明しているかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
struct is_nothrow_destructible;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 照会する型。  
  
## <a name="remarks"></a>コメント  
 型 `T` が破棄可能な型で、デストラクタ―がスローしないとコンパイラに判明している場合、型述語のインスタンスは true を保持します。 それ以外の場合、false を保持します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)




