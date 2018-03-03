---
title: "hash_set::rbegin (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::hash_set::rbegin
dev_langs:
- C++
helpviewer_keywords:
- rbegin member [STL/CLR]
ms.assetid: 1f2ff4ed-8557-40cf-8e61-816563acc43e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 33caee5f46436f7f2176d237c10744c66f4113b3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="hashsetrbegin-stlclr"></a>hash_set::rbegin (STL/CLR)
反転被制御シーケンスの先頭を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
reverse_iterator rbegin();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数では、最後の要素または空のシーケンスの先頭を越えた、被制御シーケンスの指定、逆順反復子を返します。 したがって、これを指定、`beginning`反転シーケンスのです。 指定する反復子を取得するために使用、`current`被制御シーケンスの長さを変更した場合、逆の順序で表示される、被制御シーケンスですがその状態の先頭は変更できます。  
  
## <a name="example"></a>例  
  
```  
// cliext_hash_set_rbegin.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    Myhash_set::reverse_iterator rit = c1.rbegin();   
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
 **ヘッダー:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set::begin (STL/CLR)](../dotnet/hash-set-begin-stl-clr.md)   
 [hash_set::end (STL/CLR)](../dotnet/hash-set-end-stl-clr.md)   
 [hash_set::rend (STL/CLR)](../dotnet/hash-set-rend-stl-clr.md)