---
title: "add_rvalue_reference クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::add_rvalue_reference
- add_rvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- add_rvalue_reference Class
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
caps.latest.revision: 11
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: faa8014788d12841df6a0822ec7fe379198f06d1
ms.contentlocale: ja-jp
ms.lasthandoff: 04/19/2017

---
# <a name="addrvaluereference-class"></a>add_rvalue_reference クラス
テンプレート パラメーターがオブジェクトまたは関数の型の場合に、その右辺値参照型を作成します。 それ以外の場合、参照縮小のセマンティクスのため、型はテンプレート パラメーターと同じです。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template <class T>
struct add_rvalue_reference;

template <class T>
using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;
```  
  
#### <a name="parameters"></a>パラメーター  
 T  
 変更する型。  
  
## <a name="remarks"></a>コメント  
 `add_rvalue_reference` クラスには `type` という名前のメンバーがあります。これはテンプレート パラメーター `T` への右辺値参照の型の別名です。 参照縮小のセマンティクスは、非オブジェクトおよび非関数型 `T` では、`T&&` は `T` を意味します。 たとえば、`T` が左辺値参照型の場合、`add_rvalue_reference<T>::type` は右辺値参照ではなく左辺値参照型です。  
  
 便宜上、<type_traits> はヘルパー テンプレート `add_rvalue_reference_t` (`add_rvalue_reference` の `type` メンバーの別名) を定義します。  
  
## <a name="example"></a>例  
 このコード例では、static_assert を使用して、右辺値参照型を `add_rvalue_reference` と`add_rvalue_reference_t` を使用して作成する方法、および左辺値参照型での `add_rvalue_reference` の結果を右辺値参照ではなく左辺値参照型に縮小する方法を示します。  
  
```cpp  
// ex_add_rvalue_reference.cpp  
// Build by using: cl /EHsc /W4 ex_add_rvalue_reference.cpp  
#include <type_traits>   
#include <iostream>   
#include <string>  
  
using namespace std;  
int main()  
{  
    static_assert(is_same<add_rvalue_reference<string>::type, string&&>::value,   
        "Expected add_rvalue_reference_t<string> to be string&&");  
    static_assert(is_same<add_rvalue_reference_t<string*>, string*&&>::value,   
        "Expected add_rvalue_reference_t<string*> to be string*&&");  
    static_assert(is_same<add_rvalue_reference<string&>::type, string&>::value,   
        "Expected add_rvalue_reference_t<string&> to be string&");  
    static_assert(is_same<add_rvalue_reference_t<string&&>, string&&>::value,   
        "Expected add_rvalue_reference_t<string&&> to be string&&");  
    cout << "All static_assert tests of add_rvalue_reference passed." << endl;  
    return 0;  
}  
  
/*Output:  
All static_assert tests of add_rvalue_reference passed.  
*/  
```  
  
## <a name="requirements"></a>要件  
 ヘッダー: <type_traits> 名前空間: std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)   
 [add_lvalue_reference クラス](../standard-library/add-lvalue-reference-class.md)   
 [is_rvalue_reference クラス](../standard-library/is-rvalue-reference-class.md)

