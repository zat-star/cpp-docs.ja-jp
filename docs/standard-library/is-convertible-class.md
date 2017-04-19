---
title: "is_convertible クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_convertible
- type_traits/std::is_convertible
dev_langs:
- C++
helpviewer_keywords:
- is_convertible class
- is_convertible
ms.assetid: 75614008-1894-42ea-bd57-974399628536
caps.latest.revision: 19
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 381fa9297dd9fad3efd84078a000fea65af0abfd
ms.lasthandoff: 02/24/2017

---
# <a name="isconvertible-class"></a>is_convertible クラス
一方の型をもう一方の型に変換できるかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```  
template <class From, class To>  
struct is_convertible;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `From`  
 変換前の型。  
  
 `Ty`  
 変換後の型。  
  
## <a name="remarks"></a>コメント  
 `To to = from;` という式が正しい形式である場合、型述語のインスタンスは true を保持します (`from` は型 `From` のオブジェクト)。  
  
## <a name="example"></a>例  
  
```cpp  
// std__type_traits__is_convertible.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_convertible<trivial, int> == " << std::boolalpha   
        << std::is_convertible<trivial, int>::value << std::endl;   
    std::cout << "is_convertible<trivial, trivial> == " << std::boolalpha   
        << std::is_convertible<trivial, trivial>::value << std::endl;   
    std::cout << "is_convertible<char, int> == " << std::boolalpha   
        << std::is_convertible<char, int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_convertible<trivial, int> == false  
is_convertible<trivial, trivial> == true  
is_convertible<char, int> == true  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_base_of クラス](../standard-library/is-base-of-class.md)

