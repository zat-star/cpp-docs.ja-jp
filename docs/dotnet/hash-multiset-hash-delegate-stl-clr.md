---
title: hash_multiset::hash_delegate (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- cliext::hash_multiset::hash_delegate
dev_langs:
- C++
helpviewer_keywords:
- hash_delegate member [STL/CLR]
ms.assetid: 61ccfdfb-6a3c-40aa-902f-49e004a31a75
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6451dcd954e85e539a007778214923ea377196dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="hashmultisethashdelegate-stlclr"></a>hash_multiset::hash_delegate (STL/CLR)
指定したキーに一致する要素を検索します。  
  
## <a name="syntax"></a>構文  
  
```  
hasher^ hash_delegate();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数では、キーの値を整数に変換するために使用されるデリゲートを返します。 キーのハッシュに使用するとします。  
  
## <a name="example"></a>例  
  
```  
// cliext_hash_multiset_hash_delegate.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    Myhash_multiset::hasher^ myhash = c1.hash_delegate();   
  
    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));   
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
hash(L'a') = 1616896120  
hash(L'b') = 570892832  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset::hasher (STL/CLR)](../dotnet/hash-multiset-hasher-stl-clr.md)