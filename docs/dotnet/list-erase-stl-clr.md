---
title: "list::erase (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::list::erase
dev_langs:
- C++
helpviewer_keywords:
- erase member [STL/CLR]
ms.assetid: 78705058-1e83-441d-b267-d4fb56451c0b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 54595b61ddd21ccd81cf4f2846224789861cb480
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="listerase-stlclr"></a>list::erase (STL/CLR)
指定した位置にある要素を削除します。  
  
## <a name="syntax"></a>構文  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>パラメーター  
 先頭  
 消去する範囲の開始しています。  
  
 last  
 消去する範囲の終了。  
  
 where  
 消去する要素。  
  
## <a name="remarks"></a>コメント  
 最初のメンバー関数によって示される、被制御シーケンスの要素を削除する`where`です。 それを使用するには 1 つの要素を削除します。  
  
 2 番目のメンバー関数は、範囲 [`first`, `last`) の被制御シーケンスの要素を削除します。 これを使用するには 0 個以上の連続する要素を削除します。  
  
 両方のメンバー関数が、削除された要素の後に残る最初の要素を指定する反復子を返しますまたは[list::end (STL/CLR)](../dotnet/list-end-stl-clr.md) `()`このような要素が存在しない場合。  
  
 要素を消去するには、ときに要素のコピーの数は消去の終了と、シーケンスの最も近い最後の要素の数に比例します。 (シーケンスの先頭または末尾にある 1 つまたは複数の要素を消去するには、ときに要素のコピーは発生しません。)  
  
## <a name="example"></a>例  
  
```  
// cliext_list_erase.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.push_back(L'd');   
    c1.push_back(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    cliext::list<wchar_t>::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
erase(begin()) = b  
 b c d e  
erase(begin(), end()-1) = e  
size() = 1  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext/一覧 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::clear (STL/CLR)](../dotnet/list-clear-stl-clr.md)