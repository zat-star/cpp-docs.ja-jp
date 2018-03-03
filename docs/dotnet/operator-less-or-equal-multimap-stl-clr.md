---
title: "演算子&lt;= (multimap) (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::multimap::operator<=
dev_langs:
- C++
helpviewer_keywords:
- operator<= member [STL/CLR]
ms.assetid: f23cdacd-fb1b-4e87-8e32-497226841871
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8d03e989735cabe53d365e2ae81fa11fdb5268a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="operatorlt-multimap-stlclr"></a>演算子&lt;= (multimap) (STL/CLR)
以下の一覧の比較できます。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Key,  
    typename Mapped>  
    bool operator<=(multimap<Key, Mapped>% left,  
        multimap<Key, Mapped>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 左へ  
 比較する左のコンテナー。  
  
 右  
 比較する右のコンテナー。  
  
## <a name="remarks"></a>コメント  
 演算子関数を返します`!(right < left)`です。 テストするために使用するかどうか`left`後に順序付けされていない`right`要素によって比較対象の要素が 2 つの multimaps の場合。  
  
## <a name="example"></a>例  
  
```  
// cliext_multimap_operator_le.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultimap c2;   
    c2.insert(Mymultimap::make_value(L'a', 1));   
    c2.insert(Mymultimap::make_value(L'b', 2));   
    c2.insert(Mymultimap::make_value(L'd', 4));   
  
// display contents " [a 1] [b 2] [d 4]"   
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] <= [a b c] is {0}",   
        c1 <= c1);   
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",   
        c2 <= c1);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
 [a 1] [b 2] [d 4]  
[a b c] <= [a b c] is True  
[a b d] <= [a b c] is False  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext マップ/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [演算子 = = (multimap) (STL/CLR)](../dotnet/operator-equality-multimap-stl-clr.md)   
 [operator! = (multimap) (STL/CLR)](../dotnet/operator-inequality-multimap-stl-clr.md)   
 [演算子\<(multimap) (STL/CLR)](../dotnet/operator-less-than-multimap-stl-clr.md)   
 [operator > = (multimap) (STL/CLR)](../dotnet/operator-greater-or-equal-multimap-stl-clr.md)   
 [operator> (multimap) (STL/CLR)](../dotnet/operator-greater-than-multimap-stl-clr.md)