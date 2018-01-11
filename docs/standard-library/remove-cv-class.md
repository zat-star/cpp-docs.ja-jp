---
title: "remove_cv クラス |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::remove_cv
dev_langs: C++
helpviewer_keywords:
- remove_cv class
- remove_cv
ms.assetid: 8502602a-1c80-479c-84e0-33bd1d6496d6
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 335d3d5cc2efef9a0a3f3e2642988dc44c3aa067
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="removecv-class"></a>remove_cv クラス
型から非 const/volatile 型を作成します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class T>  
struct remove_cv;  
 
template <class T>  
using remove_cv_t = typename remove_cv<T>::type;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 変更する型。  
  
## <a name="remarks"></a>コメント  
 `remove_cv<T>` のインスタンスは、`T1` の形式が `T`、`const T1`、または `volatile T1` である場合は、修飾型 `const volatile T1` を保持します。それ以外の場合は、`T` を保持します。  
  
## <a name="example"></a>例  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    int *p = (std::remove_cv_t<const volatile int> *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "remove_cv_t<const volatile int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
```  
  
```Output  
remove_cv_t<const volatile int> == int  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [<type_traits>](../standard-library/type-traits.md)   
 [remove_const クラス](../standard-library/remove-const-class.md)   
 [remove_volatile クラス](../standard-library/remove-volatile-class.md)
