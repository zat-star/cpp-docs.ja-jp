---
title: "set::count (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::set::Count
dev_langs: C++
helpviewer_keywords: count member [STL/CLR]
ms.assetid: 78855f8c-3de5-4d3e-800b-0bbea5e829dd
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 847154691aa7919b708c36777d2016494c72d21b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="setcount-stlclr"></a>set::count (STL/CLR)
指定したキーに一致する要素の数を検索します。  
  
## <a name="syntax"></a>構文  
  
```  
size_type count(key_type key);  
```  
  
#### <a name="parameters"></a>パラメーター  
 key  
 検索対象のキー値。  
  
## <a name="remarks"></a>コメント  
 メンバー関数と同じ順序付けする被制御シーケンスの要素の数を返します`key`です。 それを使用して、指定したキーと一致する、被制御シーケンスの現在の要素の数を決定します。  
  
## <a name="example"></a>例  
  
```  
// cliext_set_count.cpp   
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
  
    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));   
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));   
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
count(L'A') = 0  
count(L'b') = 1  
count(L'C') = 0  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext と set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [設定 (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set::equal_range (STL/CLR)](../dotnet/set-equal-range-stl-clr.md)