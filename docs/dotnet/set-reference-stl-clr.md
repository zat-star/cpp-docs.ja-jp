---
title: "set::reference (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::set::reference
dev_langs:
- C++
helpviewer_keywords:
- reference member [STL/CLR]
ms.assetid: 6bd102cb-5bea-4544-ae17-f10b2a73229e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d71133d0ab3b91f8339f4b6ab4b36a1fe58f08ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="setreference-stlclr"></a>set::reference (STL/CLR)
要素への参照の型です。  
  
## <a name="syntax"></a>構文  
  
```  
typedef value_type% reference;  
```  
  
## <a name="remarks"></a>コメント  
 この型は、要素への参照を表します。  
  
## <a name="example"></a>例  
  
```  
// cliext_set_reference.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    Myset::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        {   // get a reference to an element   
        Myset::reference ref = *it;   
        System::Console::Write(" {0}", ref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext と set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [設定 (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set::const_reference (STL/CLR)](../dotnet/set-const-reference-stl-clr.md)   
 [set::value_type (STL/CLR)](../dotnet/set-value-type-stl-clr.md)