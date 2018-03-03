---
title: "collection_adapter::size (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::collection_adapter::size
dev_langs:
- C++
helpviewer_keywords:
- size member [STL/CLR]
ms.assetid: 71866719-9e29-4572-bfb9-60321f2937c5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 670b91a1b01f3234cf3a41b89498994836691fc4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="collectionadaptersize-stlclr"></a>collection_adapter::size (STL/CLR)
要素の数をカウントします。  
  
## <a name="syntax"></a>構文  
  
```  
size_type size();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数は、被制御シーケンスの長さを返します。 特殊化で定義されていない`IEnumerable`または`IEnumerable<Value>`です。  
  
## <a name="example"></a>例  
  
```  
// cliext_collection_adapter_size.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
    Mycoll c1(%d6x);   
  
// display initial contents " x x x x x x"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 x x x x x x  
size() = 6  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext アダプター/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)