---
title: "add_pointer クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- add_pointer
- type_traits/std::add_pointer
dev_langs:
- C++
helpviewer_keywords:
- add_pointer class
- add_pointer
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
caps.latest.revision: 22
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
ms.openlocfilehash: 008f19421575b8a930498a615642fdfdad99b7b6
ms.lasthandoff: 02/24/2017

---
# <a name="addpointer-class"></a>add_pointer クラス
指定された型から型へのポインターを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class T>  
struct add_pointer;  
 
template <class T>
using add_pointer_t = typename add_pointer<T>::type;  
```  
  
#### <a name="parameters"></a>パラメーター  
*T*  
変更する型。  
  
## <a name="remarks"></a>コメント  
メンバー typedef `type` は、`remove_reference<T>::type*` と同じ型を指定します。 別名 `add_pointer_t` は、メンバー typedef `type` にアクセスするショートカットです。  
  
参照からポインターを作成することは無効であるため、`add_pointer` は型へのポインターを作成する前に、指定された型から参照を削除します (存在する場合)。 その結果、型が参照であるかどうかを気にすることなく、型を `add_pointer` で使用できます。  
  
## <a name="example"></a>例  
次の例では、型の `add_pointer` がその型へのポインターと同じであることを示します。  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
{   
    std::add_pointer_t<int> *p = (int **)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_pointer_t<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
add_pointer_t<int> == int *  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)   
 [remove_pointer クラス](../standard-library/remove-pointer-class.md)

