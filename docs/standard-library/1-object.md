---
title: "_1 オブジェクト |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _1
- std::_1
- functional/std::_1
dev_langs:
- C++
helpviewer_keywords:
- _1 object
ms.assetid: 30c3c480-ff31-4708-94be-7d0d65f243c9
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 86978cd4549f0672dac7cad0e4713380ea189c27
ms.openlocfilehash: ce86a87e5f22b27c5b1d7eeeeb4edcbcac8e15c7
ms.contentlocale: ja-jp
ms.lasthandoff: 04/18/2017

---
# <a name="1-object"></a>_1 オブジェクト
置き換え可能な引数のプレースホルダーです。  
  
## <a name="syntax"></a>構文  
  
```  
namespace placeholders {  
    extern unspecified _1,
    _2, ... _M  
 } // namespace placeholders (within std)  
```  
  
## <a name="remarks"></a>コメント  
 オブジェクト`_1, _2, ... _M`プレース ホルダーは、最初に、2 番目、…、によって返されるオブジェクトへの関数呼び出しでそれぞれの m 番目の引数を指定する[バインド](../standard-library/functional-functions.md#bind)です。 bind 式が評価されるときに N 番目の引数が挿入される場所を指定するには、`_N` を使用します。  
  
 この実装では、`M` の値は 20 です。  
  
## <a name="example"></a>例  
  
```cpp  
// std__functional_placeholder.cpp   
// compile with: /EHsc   
#include <functional>   
#include <algorithm>   
#include <iostream>   
  
using namespace std::placeholders;   
  
void square(double x)   
    {   
    std::cout << x << "^2 == " << x * x << std::endl;   
    }   
  
void product(double x, double y)   
    {   
    std::cout << x << "*" << y << " == " << x * y << std::endl;   
    }   
  
int main()   
    {   
    double arg[] = {1, 2, 3};   
  
    std::for_each(&arg[0], &arg[3], square);   
    std::cout << std::endl;   
  
    std::for_each(&arg[0], &arg[3], std::bind(product, _1, 2));   
    std::cout << std::endl;   
  
    std::for_each(&arg[0], &arg[3], std::bind(square, _1));   
  
    return (0);   
    }  
  
```  
  
```Output  
1^2 == 1  
2^2 == 4  
3^2 == 9  
  
1*2 == 2  
2*2 == 4  
3*2 == 6  
  
1^2 == 1  
2^2 == 4  
3^2 == 9  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<functional>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [バインド](../standard-library/functional-functions.md#bind)   
 [is_placeholder クラス](../standard-library/is-placeholder-class.md)

