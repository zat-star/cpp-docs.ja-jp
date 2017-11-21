---
title: "hash_set::iterator (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_set::iterator
dev_langs: C++
helpviewer_keywords: iterator member [STL/CLR]
ms.assetid: b75fc54f-6a9e-4ce8-a168-988afe7fe7e5
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 26890eb168726e651bb7324fddcd089eb3846616
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="hashsetiterator-stlclr"></a>hash_set::iterator (STL/CLR)
被制御シーケンスの反復子の型です。  
  
## <a name="syntax"></a>構文  
  
```  
typedef T1 iterator;  
```  
  
## <a name="remarks"></a>コメント  
 この型が指定されていない型のオブジェクトを表します`T1`被制御シーケンスの双方向反復子として使用されることができます。  
  
## <a name="example"></a>例  
  
```  
// cliext_hash_set_iterator.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    Myhash_set::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" {0}", *it);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)   
 [hash_set::const_iterator (STL/CLR)](../dotnet/hash-set-const-iterator-stl-clr.md)