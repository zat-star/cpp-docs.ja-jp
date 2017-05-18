---
title: "is_bind_expression クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_bind_expression
- functional/std::is_bind_expression
dev_langs:
- C++
helpviewer_keywords:
- is_bind_expression class
ms.assetid: 0715f9e9-2239-4778-a1cf-2c21f49dfd47
caps.latest.revision: 20
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
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 58e5d6db98ff10180d2e1efea973fa7d63386553
ms.contentlocale: ja-jp
ms.lasthandoff: 04/19/2017

---
# <a name="isbindexpression-class"></a>is_bind_expression クラス
`bind` の呼び出しによって型が生成されたかどうかテストします。  
  
## <a name="syntax"></a>構文  
  
template<class Ty>  
struct is_bind_expression {  
   static const bool value;  
   };  
  
## <a name="remarks"></a>コメント  
型 `Ty` が `bind` への呼び出しによって返される型の場合、定数メンバー `value` は true です。それ以外の場合は false です。  
  
## <a name="example"></a>例  
  
```cpp  
// std__functional__is_bind_expression.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
void square(double x)
{
    std::cout << x << "^2 == " << x * x << std::endl;
}

template<class Expr>
void test_for_bind(const Expr&)
{
    std::cout << std::is_bind_expression<Expr>::value << std::endl;
}

int main()
{
    test_for_bind(3.0 * 3.0);
    test_for_bind(std::bind(square, 3));

    return (0);
}  
```  
  
```Output  
0  
1  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<functional>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [bind](../standard-library/functional-functions.md#bind)


