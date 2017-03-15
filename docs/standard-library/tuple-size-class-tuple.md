---
title: "tuple_size クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tuple_size
- std::tuple_size
- utility/std::tuple_size
dev_langs:
- C++
helpviewer_keywords:
- tuple_size Class
ms.assetid: 73852fc5-eb68-41f1-8379-465cedc2314a
caps.latest.revision: 23
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
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: f0ae102852f1db46b68d86438e20ce9645535d19
ms.lasthandoff: 02/24/2017

---
# <a name="tuplesize-class"></a>tuple_size クラス
`tuple` を含む要素の数を報告します。  
  
## <a name="syntax"></a>構文  
  
```  
// TEMPLATE STRUCT tuple_size  
template <class Tuple>  
   struct tuple_size;  
  
// number of elements in array  
template <class Elem, size_t Size>  
   struct tuple_size<array<Elem, Size>>  
      : integral_constant<size_t, Size>; 
  
// size of pair
template <class T1, class T2>
   struct tuple_size<pair<T1, T2>> 
      : integral_constant<size_t, 2>

// size of tuple  
template <class... Types>  
   struct tuple_size<tuple<Types...>>  
      : integral_constant<size_t, sizeof...(Types)>;  
  
// size of const tuple  
template <class Tuple>  
   struct tuple_size<const Tuple>;  
  
// size of volatile tuple  
template <class Tuple>  
   struct tuple_size<volatile Tuple>;  
  
// size of const volatile tuple  
template <class Tuple>  
   struct tuple_size<const volatile Tuple>;   
```  
  
#### <a name="parameters"></a>パラメーター  
*Tuple*  
組の型。 
  
*Elem*  
配列要素の型。 
  
*Size*  
配列のサイズ。 
  
*T1*  
ペアの最初のメンバーの型。 
  
*T2*  
ペアの&2; 番目のメンバーの型。 
  
*型*  
タプル要素の型。 
  
  
## <a name="remarks"></a>コメント  
テンプレート クラスは、組型 `value` の範囲を値として持つ整数定数式であるメンバー `Tuple`を持ちます。  
  
配列のテンプレート特殊化には、配列のサイズである `Size` を値として持つ整数定数式であるメンバー `value` が含まれます。  
  
ペアのテンプレート特殊化には、2 を値として持つ整数定数式であるメンバー `value` が含まれます。  
  
## <a name="example"></a>例  
  
```cpp  
#include <tuple>   
#include <iostream>  
  
using namespace std;  
  
typedef tuple<int, double, int, double> MyTuple;  
int main()  
{  
    MyTuple c0(0, 1.5, 2, 3.7);  
  
    // display contents " 0 1 2 3"   
    cout << " " << get<0>(c0);  
    cout << " " << get<1>(c0);  
    cout << " " << get<2>(c0);  
    cout << " " << get<3>(c0) << endl;  
  
    // display size " 4"   
    cout << " " << tuple_size<MyTuple>::value << endl;  
}  
```  
  
```Output  
 0 1.5 2 3.7  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<tuple>  
 **ヘッダー:** \<array> (配列の特殊化用)  
 **ヘッダー:** \<utility> (ペアの特殊化用)  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [\<tuple>](../standard-library/tuple.md)   
 [タプル](../standard-library/tuple-class.md)  
 [tuple_element クラス](../standard-library/tuple-element-class-tuple.md)

