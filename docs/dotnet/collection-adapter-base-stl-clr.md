---
title: "collection_adapter::base (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::collection_adapter::base
dev_langs:
- C++
helpviewer_keywords:
- base member [STL/CLR]
ms.assetid: 44928046-3fda-4974-817f-bc61a6f11b9f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 920235952f57bf82c6d8607b9732592053941b9c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="collectionadapterbase-stlclr"></a>collection_adapter::base (STL/CLR)
ラップされた BCL インターフェイスを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
Coll^ base();  
```  
  
## <a name="remarks"></a>コメント  
 メンバー関数では、格納された BCL インターフェイス ハンドルを返します。  
  
## <a name="example"></a>例  
  
```  
// cliext_collection_adapter_base.cpp   
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
  
    System::Console::WriteLine("base() same = {0}", c1.base() == %c1);   
    return (0);   
    }  
  
```  
  
```Output  
 x x x x x x  
base() same = True  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext アダプター/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)