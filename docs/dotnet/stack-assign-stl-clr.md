---
title: "stack::assign (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::stack::assign
dev_langs:
- C++
helpviewer_keywords:
- assign member [STL/CLR]
ms.assetid: 18cc35ad-23cf-4a5a-adae-d967dc5d6980
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 240a7776fd60cb9917e195b89f72c135ce7454f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="stackassign-stlclr"></a>stack::assign (STL/CLR)
すべての要素を置換します。  
  
## <a name="syntax"></a>構文  
  
```  
void assign(stack<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 右  
 コンテナーのアダプターを挿入します。  
  
## <a name="remarks"></a>コメント  
 このメンバー関数を割り当てます`right.get_container()`を基になるコンテナーにします。 使用する、スタックのすべての内容を変更します。  
  
## <a name="example"></a>例  
  
```  
// cliext_stack_assign.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign a repetition of values   
    Mystack c2;   
    c2.assign(c1);   
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
 **ヘッダー:** \<cliext/stack >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [スタック (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [stack::operator= (STL/CLR)](../dotnet/stack-operator-assign-stl-clr.md)