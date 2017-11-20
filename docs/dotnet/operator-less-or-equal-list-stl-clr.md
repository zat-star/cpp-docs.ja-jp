---
title: "演算子&lt;= (リスト) (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::operator<=
dev_langs: C++
helpviewer_keywords: operator<= member [STL/CLR]
ms.assetid: af677e20-f529-4055-b101-af9728bc090b
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3a8a28eaf627300041812937982bf3a24232271e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="operatorlt-list-stlclr"></a>演算子&lt;= (リスト) (STL/CLR)
以下の一覧の比較できます。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value>  
    bool operator<=(list<Value>% left,  
        list<Value>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 左へ  
 比較する左のコンテナー。  
  
 右  
 比較する右のコンテナー。  
  
## <a name="remarks"></a>コメント  
 演算子関数を返します`!(right < left)`です。 テストするために使用するかどうか`left`後に順序付けされていない`right`と 2 つのリストは、要素で要素を比較します。  
  
## <a name="example"></a>例  
  
```  
// cliext_list_operator_le.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::list<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] <= [a b c] is {0}",   
        c1 <= c1);   
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",   
        c2 <= c1);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] <= [a b c] is True  
[a b d] <= [a b c] is False  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/一覧 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [演算子 = = (リスト) (STL/CLR)](../dotnet/operator-equality-list-stl-clr.md)   
 [operator! = (リスト) (STL/CLR)](../dotnet/operator-inequality-list-stl-clr.md)   
 [演算子\<(リスト) (STL/CLR)](../dotnet/operator-less-than-list-stl-clr.md)   
 [operator > = (リスト) (STL/CLR)](../dotnet/operator-greater-or-equal-list-stl-clr.md)   
 [operator> (list) (STL/CLR)](../dotnet/operator-greater-than-list-stl-clr.md)