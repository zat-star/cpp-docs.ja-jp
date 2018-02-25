---
title: "is_integral クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_integral
dev_langs:
- C++
helpviewer_keywords:
- is_integral class
- is_integral
ms.assetid: fe9279d0-4495-4e88-bf23-153cc6602397
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 992726f3b1d94b0ed4065c3fc2bb8bf54497a36b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="isintegral-class"></a>is_integral クラス
型が整数かどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Ty>  
struct is_integral;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Ty`  
 照会する型。  
  
## <a name="remarks"></a>コメント  
 型 `Ty` が整数型の 1 つ、または整数型の 1 つの `cv-qualified` 形式である場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。  
  
 整数型は、`bool`、`char`、`unsigned char`、`signed char`、`wchar_t`、`short`、`unsigned short`、`int`、`unsigned int`、`long`、`unsigned long` のいずれかです。 さらに、それらを提供するコンパイラの場合、整数の型は `long long`、`unsigned long long`、`__int64`、`unsigned __int64` のいずれかにすることもできます。  
  
## <a name="example"></a>例  
  
```cpp  
// std__type_traits__is_integral.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_integral<trivial> == " << std::boolalpha   
        << std::is_integral<trivial>::value << std::endl;   
    std::cout << "is_integral<int> == " << std::boolalpha   
        << std::is_integral<int>::value << std::endl;   
    std::cout << "is_integral<float> == " << std::boolalpha   
        << std::is_integral<float>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_integral<trivial> == false  
is_integral<int> == true  
is_integral<float> == false  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_enum クラス](../standard-library/is-enum-class.md)   
 [is_floating_point クラス](../standard-library/is-floating-point-class.md)
