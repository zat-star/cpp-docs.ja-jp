---
title: "extent クラス | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::extent
dev_langs: C++
helpviewer_keywords:
- extent class
- extent
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f7e6f8af90f3c31e2b72524ac2c31a9884e82448
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="extent-class"></a>extent クラス
配列の次元を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Ty, unsigned I = 0>  
struct extent;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Ty`  
 照会する型。  
  
 `I`  
 照会する配列の範囲。  
  
## <a name="remarks"></a>コメント  
 `Ty` が少なくとも `I` 次元の配列型である場合、この型クエリは `I` で指定される次元の要素数を保持します。 `Ty` が配列型ではないか、配列のランク (次元数) が `I` 未満である場合、または `I` がゼロで `Ty` の型が "`U` の不明な範囲の配列" である場合、この型クエリは 0 を保持します。  
  
## <a name="example"></a>例  
  
```cpp  
// std__type_traits__extent.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "extent 0 == "   
        << std::extent<int[5][10]>::value << std::endl;   
    std::cout << "extent 1 == "   
        << std::extent<int[5][10], 1>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
extent 0 == 5  
extent 1 == 10  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)   
 [remove_all_extents クラス](../standard-library/remove-all-extents-class.md)   
 [remove_extent クラス](../standard-library/remove-extent-class.md)
