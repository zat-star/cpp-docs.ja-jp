---
title: "collection_adapter::value_type (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::collection_adapter::value_type
dev_langs:
- C++
helpviewer_keywords:
- value_type member [STL/CLR]
ms.assetid: 4a77ec36-6113-4ec3-86a2-ea24d96605c1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d4cf6b22ab5b08bc1ac2746f7b0ed7e5f98e79b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="collectionadaptervaluetype-stlclr"></a>collection_adapter::value_type (STL/CLR)
要素の型。  
  
## <a name="syntax"></a>構文  
  
```  
typedef Value value_type;  
```  
  
## <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーターのシノニム`Value`、それ以外の場合のシノニムがある特殊化; に存在する場合`System::Object^`です。  
  
## <a name="example"></a>例  
  
```  
// cliext_collection_adapter_value_type.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
    Mycoll c1(%d1);   
  
// display contents " a b c" using value_type   
    for (Mycoll::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   // store element in value_type object   
        Mycoll::value_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext アダプター/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)   
 [collection_adapter::reference (STL/CLR)](../dotnet/collection-adapter-reference-stl-clr.md)