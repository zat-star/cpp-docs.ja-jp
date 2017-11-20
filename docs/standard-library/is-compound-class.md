---
title: "is_compound クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_compound
dev_langs: C++
helpviewer_keywords:
- is_compound class
- is_compound
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 570a67a3b18bd9d2bf7652d604f1e4e3156664de
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="iscompound-class"></a>is_compound クラス
指定した型が基本型でないかどうかを調べます。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Ty>  
struct is_compound;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Ty`  
 照会する型。  
  
## <a name="remarks"></a>コメント  
 `Ty` の型が基本型である場合、型述語のインスタンスは `false` を保持します (つまり、[is_fundamental](../standard-library/is-fundamental-class.md)`<Ty>` は `true` を保持します)。それ以外の場合は、`true` を保持します。 したがって、`Ty` が配列型、関数型、`void` またはオブジェクトや関数へのポインター、参照、クラス、共用体、列挙体、非静的クラス メンバーへのポインター、または、これらのいずれかの *cv で修飾された*形式である場合、述語は `true` を保持します。  
  
## <a name="example"></a>例  
  
```cpp  
// std__type_traits__is_compound.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_compound<trivial> == " << std::boolalpha   
        << std::is_compound<trivial>::value << std::endl;   
    std::cout << "is_compound<int[]> == " << std::boolalpha   
        << std::is_compound<int[]>::value << std::endl;   
    std::cout << "is_compound<int()> == " << std::boolalpha   
        << std::is_compound<int()>::value << std::endl;   
    std::cout << "is_compound<int&> == " << std::boolalpha   
        << std::is_compound<int&>::value << std::endl;   
    std::cout << "is_compound<void *> == " << std::boolalpha   
        << std::is_compound<void *>::value << std::endl;   
    std::cout << "is_compound<int> == " << std::boolalpha   
        << std::is_compound<int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_compound<trivial> == true  
is_compound<int[]> == true  
is_compound<int()> == true  
is_compound<int&> == true  
is_compound<void *> == true  
is_compound<int> == false  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_class クラス](../standard-library/is-class-class.md)
