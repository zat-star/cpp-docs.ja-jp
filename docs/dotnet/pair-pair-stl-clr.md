---
title: "pair::pair (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::pair::pair
dev_langs: C++
helpviewer_keywords: pair member [STL/CLR]
ms.assetid: 188035f3-bd37-4b46-96dd-5ceb9a16df79
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6b2382161ae1a4acf8cb79f017a39daf51826b4d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="pairpair-stlclr"></a>pair::pair (STL/CLR)
組オブジェクトを構築します。  
  
## <a name="syntax"></a>構文  
  
```  
pair();  
pair(pair<Coll>% right);  
pair(pair<Coll>^ right);  
pair(Value1 val1, Value2 val2);  
```  
  
#### <a name="parameters"></a>パラメーター  
 右  
 格納するペア。  
  
 val1  
 最初の値を格納します。  
  
 val2  
 2 番目の値を格納します。  
  
## <a name="remarks"></a>コメント  
 : コンス トラクター  
  
 `pair();`  
  
 構築された既定値を持つストアドのペアを初期化します。  
  
 : コンス トラクター  
  
 `pair(pair<Value1, Value2>% right);`  
  
 初期化ストアド ペアを持つ`right.` [pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md)と`right.` [pair::second (STL/CLR)](../dotnet/pair-second-stl-clr.md)です。  
  
 `pair(pair<Value1, Value2>^ right);`  
  
 初期化ストアド ペアを持つ`right->` [pair::first (STL/CLR)](../dotnet/pair-first-stl-clr.md)と`right>` [pair::second (STL/CLR)](../dotnet/pair-second-stl-clr.md)です。  
  
 : コンス トラクター  
  
 `pair(Value1 val1, Value2 val2);`  
  
 初期化ストアドのペアを持つ`val1`と`val2`です。  
  
## <a name="example"></a>例  
  
```  
// cliext_pair_construct.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
// construct an empty container   
    cliext::pair<wchar_t, int> c1;   
    System::Console::WriteLine("[{0}, {1}]",   
        c1.first == L'\0' ? "\\0" : "??", c1.second);   
  
// construct with a pair of values   
    cliext::pair<wchar_t, int> c2(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
// construct by copying another pair   
    cliext::pair<wchar_t, int> c3(c2);   
    System::Console::WriteLine("[{0}, {1}]", c3.first, c3.second);   
  
// construct by copying a pair handle   
    cliext::pair<wchar_t, int> c4(%c3);   
    System::Console::WriteLine("[{0}, {1}]", c4.first, c4.second);   
  
    return (0);   
    }  
  
```  
  
```Output  
[\0, 0]  
[x, 3]  
[x, 3]  
[x, 3]  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext ユーティリティ/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [pair (STL/CLR)](../dotnet/pair-stl-clr.md)