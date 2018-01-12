---
title: "queue::front_item (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::queue::front_item
dev_langs: C++
helpviewer_keywords: front_item member [STL/CLR]
ms.assetid: 389ab030-4351-48e6-9b03-417f1d3fcb86
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 871bb12f4dcde45b548614efbb552ba1b0d4bc35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="queuefrontitem-stlclr"></a>queue::front_item (STL/CLR)
最初の要素にアクセスします。  
  
## <a name="syntax"></a>構文  
  
```  
property value_type front_item;  
```  
  
## <a name="remarks"></a>コメント  
 プロパティでは、空でない必要があります、被制御シーケンスの最初の要素にアクセスします。 これを使用するには存在することがわかっている場合に、最初の要素を読み書きします。  
  
## <a name="example"></a>例  
  
```  
// cliext_queue_front_item.cpp   
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
  
// inspect last item   
    System::Console::WriteLine("front_item = {0}", c1.front_item);   
  
// alter last item and reinspect   
    c1.front_item = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
front_item = a  
 x b c  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext/キュー >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [キュー (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [queue::back (STL/CLR)](../dotnet/queue-back-stl-clr.md)   
 [queue::back_item (STL/CLR)](../dotnet/queue-back-item-stl-clr.md)   
 [queue::front (STL/CLR)](../dotnet/queue-front-stl-clr.md)   
 [queue::front (STL/CLR)](../dotnet/queue-front-stl-clr.md)