---
title: aligned_union Class | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- aligned_union
- type_traits/std::aligned_union
dev_langs:
- C++
helpviewer_keywords:
- aligned_union
ms.assetid: 9931a44d-3a67-4f29-a0f6-d47a7cf560ac
caps.latest.revision: 10
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
ms.openlocfilehash: d6ecefd7d6877bc65bbf6f5542ae6b7f318a9d27
ms.lasthandoff: 02/24/2017

---
# <a name="alignedunion-class"></a>aligned_union クラス
共用体型を格納するのに十分な大きさと適切に配置された POD 型と必要なサイズを提供します。  
  
## <a name="syntax"></a>構文  
  
```  
template <std::size_t Len, class... Types>  
struct aligned_union;  
 
template <std::size_t Len, class... Types>  
using aligned_union_t = typename aligned_union<Len, Types...>::type;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Len`  
 共用体内の最大の型に関するアラインメント値を指定します。  
  
 `Types`  
 基になる共用体内の個別の型。  
  
## <a name="remarks"></a>コメント  
 テンプレート クラスを使用して、初期化されていない記憶域に共用体を格納するために必要なサイズと配置を取得します。 メンバー typedef `type` は、`Types` にリストされたすべての型を格納するのに適した POD 型を指定します。最小サイズは `Len` です。 型 `std::size_t` の静的メンバー `alignment_value` には、`Types` にリストされているすべての型に必要な最も厳格な配置が含まれます。  
  
## <a name="example"></a>例  
 次の例は、共用体を配置するため、`aligned_union` を使用して配置されたスタック バッファーを割り当てる方法を示しています。  
  
```  
// std__type_traits__aligned_union.cpp  
#include <iostream>  
#include <type_traits>  
  
union U_type  
{  
    int i;  
    float f;  
    double d;  
    U_type(float e) : f(e) {}  
};  
  
typedef std::aligned_union<16, int, float, double>::type aligned_U_type;  
  
int main()  
{  
    // allocate memory for a U_type aligned on a 16-byte boundary  
    aligned_U_type au;  
    // do placement new in the aligned memory on the stack  
    U_type* u = new (&au) U_type(1.0f);  
    if (nullptr != u)  
    {  
        std::cout << "value of u->i is " << u->i << std::endl;  
        // must clean up placement objects manually!  
        u->~U_type();  
    }  
}  
```  
  
```Output  
value of u->i is 1065353216  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)   
 [alignment_of クラス](../standard-library/alignment-of-class.md)

