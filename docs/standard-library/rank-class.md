---
title: "rank クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::rank
dev_langs:
- C++
helpviewer_keywords:
- rank class
- rank
ms.assetid: bc9f1b8f-800f-46ca-b6f4-d8579ed5406a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4a2fa8ccbbadb776a91465caa72b596ba0673d4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="rank-class"></a>rank クラス
配列の次元数を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Ty>  
struct rank;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Ty`  
 照会する型。  
  
## <a name="remarks"></a>コメント  
 この型クエリは、配列型 `Ty` の次元数の値を保持します。`Ty` が配列型でない場合は 0 になります。  
  
## <a name="example"></a>例  
  
```cpp  
// std__type_traits__rank.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "rank<int> == "   
        << std::rank<int>::value << std::endl;   
    std::cout << "rank<int[5]> == "   
        << std::rank<int[5]>::value << std::endl;   
    std::cout << "rank<int[5][10]> == "   
        << std::rank<int[5][10]>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
rank<int> == 0  
rank<int[5]> == 1  
rank<int[5][10]> == 2  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)   
 [extent クラス](../standard-library/extent-class.md)
