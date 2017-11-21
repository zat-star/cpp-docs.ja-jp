---
title: "binder1st (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::binder1st
dev_langs: C++
helpviewer_keywords: binder1st function [STL/CLR]
ms.assetid: a989c9cc-a485-45d9-bd19-519018e6974b
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ae786f50700d59c5f4a24ed0ec7de1c11718f352
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="binder1st-stlclr"></a>binder1st (STL/CLR)
このテンプレート クラスは、引数が 1 つファンクタを記述、呼び出されると、そのストアドの 2 つの引数ファンクタ ストアド最初の引数と 2 番目の指定された引数で呼び出されますが返されます。 使用するそのストアド ファンクタの観点から、関数オブジェクトを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Fun>  
    ref class binder1st  
    { // wrap operator()  
public:  
    typedef Fun stored_function_type;  
    typedef typename Fun::first_argument_type first_argument_type;  
    typedef typename Fun::second_argument_type second_argument_type;  
    typedef typename Fun:result_type result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        second_argument_type, result_type>  
        delegate_type;  
  
    binder1st(Fun% functor, first_argument_type left);  
    binder1st(binder1st<Arg>% right);  
  
    result_type operator()(second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### <a name="parameters"></a>パラメーター  
 楽しい  
 ストアド ファンクタの型。  
  
## <a name="member-functions"></a>メンバー関数  
  
|型定義|説明|  
|---------------------|-----------------|  
|delegate_type|汎用デリゲートの型。|  
|first_argument_type|ファンクタ最初の引数の型。|  
|result_type|ファンクタ結果の型。|  
|second_argument_type|ファンクタ 2 番目の引数の型。|  
|stored_function_type|ファンクタの型。|  
  
|メンバー|説明|  
|------------|-----------------|  
|binder1st|ファンクタを構築します。|  
  
|演算子|説明|  
|--------------|-----------------|  
|演算子 ()|必要な関数を計算します。|  
|演算子 delegate_type^()|デリゲートにファンクタをキャストします。|  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスでは、2 つの引数ファンクターと最初の引数を格納する引数が 1 つファンクタについて説明します。 このメンバー演算子を定義する`operator()`ストアドの最初の引数と 2 番目の引数が指定されたストアド ファンクターを呼び出すときの結果が返されるオブジェクトが関数として呼び出されたとき、ようにことです。  
  
 型が関数の引数として、オブジェクトを渡すことができますも`delegate_type^`適切に変換されます。  
  
## <a name="example"></a>例  
  
```  
// cliext_binder1st.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::minus<int> sub_op;   
    cliext::binder1st<cliext::minus<int> > subfrom3(sub_op, 3);   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        subfrom3);   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        bind1st(sub_op, 3));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
-1 0  
-1 0  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/機能 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [bind1st (STL/CLR)](../dotnet/bind1st-stl-clr.md)