---
title: "queue::reference (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::queue::reference
dev_langs:
- C++
helpviewer_keywords:
- reference member [STL/CLR]
ms.assetid: cca05237-5b95-4cca-ac21-b786aa8a3c96
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 31768af422052ca9d565a80620d8eb339904590a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="queuereference-stlclr"></a>queue::reference (STL/CLR)
要素への参照の型です。  
  
## <a name="syntax"></a>構文  
  
```  
typedef value_type% reference;  
```  
  
## <a name="remarks"></a>コメント  
 この型は、要素への参照を表します。  
  
## <a name="example"></a>例  
  
```  
// cliext_queue_reference.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify back of queue and redisplay   
    Myqueue::reference ref = c1.back();   
    ref = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b x  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext/キュー >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [キュー (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [queue::const_reference (STL/CLR)](../dotnet/queue-const-reference-stl-clr.md)   
 [queue::value_type (STL/CLR)](../dotnet/queue-value-type-stl-clr.md)