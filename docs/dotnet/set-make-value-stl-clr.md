---
title: "set::make_value (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::set::make_value
dev_langs: C++
helpviewer_keywords: make_value member [STL/CLR]
ms.assetid: 2f71515e-7de1-4139-a68e-72ff2a96aa4a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 92f86df6e90ce8bfaabc5482b2f4801bf79f4b44
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="setmakevalue-stlclr"></a>set::make_value (STL/CLR)
値オブジェクトを構築します。  
  
## <a name="syntax"></a>構文  
  
```  
static value_type make_value(key_type key);  
```  
  
#### <a name="parameters"></a>パラメーター  
 key  
 使用するキー値。  
  
## <a name="remarks"></a>コメント  
 メンバー関数を返します、`value_type`オブジェクト キーを持つ`key`します。 他のいくつかのメンバー関数で使用するために適切なオブジェクトの作成に使用するとします。  
  
## <a name="example"></a>例  
  
```  
// cliext_set_make_value.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(Myset::make_value(L'a'));   
    c1.insert(Myset::make_value(L'b'));   
    c1.insert(Myset::make_value(L'c'));   
  
// display contents " a b c"   
    for each (Myset::value_type elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext と set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [設定 (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set::key_type (STL/CLR)](../dotnet/set-key-type-stl-clr.md)   
 [set::value_type (STL/CLR)](../dotnet/set-value-type-stl-clr.md)