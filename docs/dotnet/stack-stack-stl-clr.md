---
title: "stack::stack (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::stack::stack
dev_langs: C++
helpviewer_keywords: stack member [STL/CLR]
ms.assetid: f1cfb3fe-4d22-41e5-906b-e8faa0bcde9b
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e12c704561cd56ac251479861740c7df205f1e37
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="stackstack-stlclr"></a>stack::stack (STL/CLR)
コンテナー アダプター オブジェクトを構築します。  
  
## <a name="syntax"></a>構文  
  
```  
stack();  
stack(stack<Value, Container>% right);  
stack(stack<Value, Container>^ right);  
explicit stack(container_type% wrapped);  
```  
  
#### <a name="parameters"></a>パラメーター  
 右  
 コピーするオブジェクト。  
  
 ラップされました。  
 使用するラップされたコンテナーです。  
  
## <a name="remarks"></a>コメント  
 : コンス トラクター  
  
 `stack();`  
  
 空のラップされたコンテナーを作成します。 空の初期被制御シーケンスの指定に使用するとします。  
  
 : コンス トラクター  
  
 `stack(stack<Value, Container>% right);`  
  
 ラップされたコンテナーのコピーを作成する`right.get_container()`です。 Stack オブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスを指定するために使用`right`です。  
  
 : コンス トラクター  
  
 `stack(stack<Value, Container>^ right);`  
  
 ラップされたコンテナーのコピーを作成する`right->get_container()`です。 Stack オブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスを指定するために使用`*right`です。  
  
 : コンス トラクター  
  
 `explicit stack(container_type% wrapped);`  
  
 既存のコンテナーを使用して`wrapped`ラップのコンテナーとして。 既存のコンテナーからのスタックを構築するために使用するとします。  
  
## <a name="example"></a>例  
  
```  
// cliext_stack_construct.cpp   
// compile with: /clr   
#include <cliext/stack>   
#include <cliext/vector>   
  
typedef cliext::stack<wchar_t> Mystack;   
typedef cliext::vector<wchar_t> Myvector;   
typedef cliext::stack<wchar_t, Myvector> Mystack_vec;   
int main()   
    {   
// construct an empty container   
    Mystack c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct from an underlying container   
    Myvector v2(5, L'x');   
    Mystack_vec c2(v2);       
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mystack_vec c3(c2);   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container through handle   
    Mystack_vec c4(%c2);   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 x x x x x  
 x x x x x  
 x x x x x  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/stack >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [スタック (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [stack::assign (STL/CLR)](../dotnet/stack-assign-stl-clr.md)   
 [stack::generic_container (STL/CLR)](../dotnet/stack-generic-container-stl-clr.md)   
 [stack::operator= (STL/CLR)](../dotnet/stack-operator-assign-stl-clr.md)