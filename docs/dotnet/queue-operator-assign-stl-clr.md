---
title: "queue::operator = (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::queue::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= member [STL/CLR]
ms.assetid: 826c335a-5680-498c-b57d-e7bc93a914be
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fd49e14e259d78e5df566c0c2e722ae85bbdf272
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="queueoperator-stlclr"></a>queue::operator= (STL/CLR)
被制御シーケンスを置き換えます。  
  
## <a name="syntax"></a>構文  
  
```  
queue <Value, Container>% operator=(queue <Value, Container>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 右  
 コピーするコンテナーのアダプターです。  
  
## <a name="remarks"></a>コメント  
 メンバー演算子コピー`right`オブジェクトを返します`*this`です。 これを使用して、被制御シーケンスを `right` の被制御シーケンスのコピーと置き換えます。  
  
## <a name="example"></a>例  
  
```  
// cliext_queue_operator_as.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myqueue c2;   
    c2 = c1;   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext/キュー >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [キュー (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [queue::assign (STL/CLR)](../dotnet/queue-assign-stl-clr.md)