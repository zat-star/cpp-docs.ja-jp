---
title: "vector::assign (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::assign
dev_langs: C++
helpviewer_keywords: assign member [STL/CLR]
ms.assetid: 945e2048-6c61-4701-b13c-8241cbee3fa1
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 37f2f75e6274748cc3289dffd42e4debff96fc91
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="vectorassign-stlclr"></a>vector::assign (STL/CLR)
すべての要素を置換します。  
  
## <a name="syntax"></a>構文  
  
```  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 count  
 挿入する要素の数。  
  
 先頭  
 挿入する範囲の開始しています。  
  
 last  
 挿入する範囲の終了。  
  
 右  
 列挙型を挿入します。  
  
 val  
 挿入する要素の値です。  
  
## <a name="remarks"></a>コメント  
 最初のメンバー関数では、被制御シーケンスを置き換えますの繰り返しで`count`値の要素`val`です。 使用する要素をコンテナーを格納するのに、同じ値を持ちます。  
  
 場合`InIt`整数型の場合は、2 番目のメンバー関数の動作と同じ`assign((size_type)first, (value_type)last)`です。 それ以外の場合、シーケンスを被制御シーケンスを置き換えます [`first`、 `last`)。 使用すると被制御シーケンスのコピーを別のシーケンス。  
  
 3 番目のメンバー関数は、列挙子によって指定されたシーケンスに、被制御シーケンスを置き換えます`right`です。 これを使用するには、被制御シーケンスの列挙子によって説明されているシーケンスのコピーを作成します。  
  
## <a name="example"></a>例  
  
```  
// cliext_vector_assign.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::vector<wchar_t> c2;   
    c2.assign(6, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an iterator range   
    c2.assign(c1.begin(), c1.end() - 1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an enumeration   
    c2.assign(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
x x x x x x  
a b  
a b c  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext/vector >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [ベクトル (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector::operator= (STL/CLR)](../dotnet/vector-operator-assign-stl-clr.md)