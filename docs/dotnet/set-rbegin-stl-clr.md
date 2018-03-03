---
title: "set::rbegin (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::set::rbegin
dev_langs:
- C++
helpviewer_keywords:
- rbegin member [STL/CLR]
ms.assetid: b9da72dc-0b75-489e-b179-74c27a4bcfb7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e7ee4e2be7058bdb6ed83264de1425da8003c274
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="setrbegin-stlclr"></a>set::rbegin (STL/CLR)
反転被制御シーケンスの先頭を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
reverse_iterator rbegin();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数では、最後の要素または空のシーケンスの先頭を越えた、被制御シーケンスの指定、逆順反復子を返します。 したがって、これを指定、`beginning`反転シーケンスのです。 指定する反復子を取得するために使用、`current`被制御シーケンスの長さを変更した場合、逆の順序で表示される、被制御シーケンスですがその状態の先頭は変更できます。  
  
## <a name="example"></a>例  
  
```  
// cliext_set_rbegin.cpp   
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
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    Myset::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*rbegin() = c  
*++rbegin() = b  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext と set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [設定 (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set::begin (STL/CLR)](../dotnet/set-begin-stl-clr.md)   
 [set::end (STL/CLR)](../dotnet/set-end-stl-clr.md)   
 [set::rend (STL/CLR)](../dotnet/set-rend-stl-clr.md)