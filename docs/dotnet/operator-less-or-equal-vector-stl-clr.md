---
title: "演算子&lt;= (ベクトル) (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::operator<=
dev_langs: C++
helpviewer_keywords: operator<= member [STL/CLR]
ms.assetid: d4f9d0ba-1fa3-4895-aef4-c9f9a06dbe05
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1e2b2e9cc116c06cb1f0c91d093566fa8ac77eac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="operatorlt-vector-stlclr"></a>演算子&lt;= (ベクトル) (STL/CLR)
以下のベクターの比較できます。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value>  
    bool operator<=(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 左へ  
 比較する左のコンテナー。  
  
 右  
 比較する右のコンテナー。  
  
## <a name="remarks"></a>コメント  
 演算子関数を返します`!(right < left)`です。 テストするために使用するかどうか`left`後に順序付けされていない`right`要素によって比較対象の要素が 2 つのベクトルの場合。  
  
## <a name="example"></a>例  
  
```  
// cliext_vector_operator_le.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
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
 **ヘッダー:** \<cliext/vector >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [ベクトル (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [演算子 = = (ベクトル) (STL/CLR)](../dotnet/operator-equality-vector-stl-clr.md)   
 [operator! = (ベクトル) (STL/CLR)](../dotnet/operator-inequality-vector-stl-clr.md)   
 [演算子\<(ベクトル) (STL/CLR)](../dotnet/operator-less-than-vector-stl-clr.md)   
 [operator > = (ベクトル) (STL/CLR)](../dotnet/operator-greater-or-equal-vector-stl-clr.md)   
 [operator> (vector) (STL/CLR)](../dotnet/operator-greater-than-vector-stl-clr.md)