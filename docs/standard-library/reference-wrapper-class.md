---
title: "reference_wrapper クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- functional/std::reference_wrapper
- type_traits/std::reference_wrapper
- xrefwrap/std::reference_wrapper
- type_traits/std::reference_wrapper::get
- type_traits/std::reference_wrapper::operator()
- functional/std::reference_wrapper::result_type
- functional/std::reference_wrapper::type
- functional/std::reference_wrapper::get
- functional/std::reference_wrapper::operator()
dev_langs: C++
helpviewer_keywords:
- std::reference_wrapper [C++]
- std::reference_wrapper [C++]
- std::reference_wrapper [C++], result_type
- std::reference_wrapper [C++], type
- std::reference_wrapper [C++], get
ms.assetid: 90b8ed62-e6f1-44ed-acc7-9619bd58865a
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 87608912712f201d4731deac53d7a59fdddf41d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="referencewrapper-class"></a>reference_wrapper クラス
参照をラップします。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Ty>  
class reference_wrapper  
{  
public:  
    typedef Ty type;  
 
    reference_wrapper(Ty&) noexcept;
    operator Ty&() const noexcept;
    Ty& get() const noexcept;

    template <class... Types> 
    auto operator()(Types&&... args) const ->
        decltype(std::invoke(get(), std::forward<Types>(args)...));
 
private:  
    Ty *ptr; // exposition only  
};  
```  
  
## <a name="remarks"></a>コメント  
`reference_wrapper<Ty>` は、構築可能で、オブジェクトまたは `Ty` 型の関数への参照の周りの割り当て可能なラッパーのコピーであり、その型のオブジェクトを指すポインターを保持します。 `reference_wrapper` を使用して参照を標準コンテナーに格納できるほか、`std::bind` への参照によってオブジェクトを渡すことができます。  
  
`Ty` 型は、オブジェクトの種類または関数の型である必要があります。それ以外の場合はコンパイル時に静的アサートに失敗します。  
  
ヘルパー関数 [std::ref](functional-functions.md#ref) および [std::cref](functional-functions.md#cref) は、`reference_wrapper` オブジェクトの作成に使用できます。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[reference_wrapper](#reference_wrapper)|`reference_wrapper` を構築します。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[result_type](#result_type)|ラップされた参照の弱い結果型。|  
|[type](#type)|ラップされた参照の型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[get](#get)|ラップされた参照を取得します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[reference_wrapper::operator Ty&amp;](#op_ty_amp)|ラップされた参照へのポインターを取得します。|  
|[reference_wrapper::operator()](#op_call)|ラップされた参照を呼び出します。|  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<functional>  
  
 **名前空間:** std  
  
##  <a name="get"></a>  reference_wrapper::get  
 ラップされた参照を取得します。  
  
```  
Ty& get() const noexcept;
```  
  
### <a name="remarks"></a>コメント  
このメンバー関数はラップされた参照を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// std__functional__reference_wrapper_get.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int main() {   
    int i = 1;   
    std::reference_wrapper<int> rwi(i);   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "rwi = " << rwi << std::endl;   
    rwi.get() = -1;   
    std::cout << "i = " << i << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
rwi = 1  
i = -1  
```  
  
##  <a name="op_ty_amp"></a>  reference_wrapper::operator Ty&amp;  
 ラップされた参照を取得します。  
  
```  
operator Ty&() const noexcept;
```  
  
### <a name="remarks"></a>コメント  
 このメンバー演算子は、 `*ptr`を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// std__functional__reference_wrapper_operator_cast.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int main() {   
    int i = 1;   
    std::reference_wrapper<int> rwi(i);   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "(int)rwi = " << (int)rwi << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
(int)rwi = 1  
```  
  
##  <a name="op_call"></a>  reference_wrapper::operator()  
 ラップされた参照を呼び出します。  
  
```  
template <class... Types>  
auto operator()(Types&&... args);
```  
  
### <a name="parameters"></a>パラメーター  
 `Types`  
 引数リストの型。  
  
 `args`  
 引数リスト。  
  
### <a name="remarks"></a>コメント  
 テンプレート メンバー `operator()` は `std::invoke(get(), std::forward<Types>(args)...)` を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// std__functional__reference_wrapper_operator_call.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    std::reference_wrapper<int (int)> rwi(neg);   
  
    std::cout << "rwi(3) = " << rwi(3) << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
rwi(3) = -3  
```  
  
##  <a name="reference_wrapper"></a>  reference_wrapper::reference_wrapper  
 `reference_wrapper` を構築します。  
  
```  
reference_wrapper(Ty& val) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `Ty`  
 ラップする型。  
  
 `val`  
 ラップする値。  
  
### <a name="remarks"></a>コメント  
 このコンストラクターは、`ptr` の格納された値を `&val` に設定します。  
  
### <a name="example"></a>例  
  
```cpp  
// std__functional__reference_wrapper_reference_wrapper.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    int i = 1;   
    std::reference_wrapper<int> rwi(i);   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "rwi = " << rwi << std::endl;   
    rwi.get() = -1;   
    std::cout << "i = " << i << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
rwi = 1  
i = -1  
```  
  
##  <a name="result_type"></a>  reference_wrapper::result_type  
 ラップされた参照の弱い結果型。  
  
```  
typedef R result_type;  
```  
  
### <a name="remarks"></a>コメント  
 `result_type` typedef は、ラップされた関数の弱い結果型のシノニムです。 この typedef は、関数型に対してのみ意味があります。  
  
### <a name="example"></a>例  
  
```cpp  
// std__functional__reference_wrapper_result_type.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    typedef std::reference_wrapper<int (int)> Mywrapper;   
    Mywrapper rwi(neg);   
    Mywrapper::result_type val = rwi(3);   
  
    std::cout << "val = " << val << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
val = -3  
```  
  
##  <a name="type"></a>  reference_wrapper::type  
 ラップされた参照の型。  
  
```  
typedef Ty type;  
```  
  
### <a name="remarks"></a>コメント  
 この typedef は、テンプレート引数 `Ty` のシノニムです。  
  
### <a name="example"></a>例  
  
```cpp  
// std__functional__reference_wrapper_type.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    int i = 1;   
    typedef std::reference_wrapper<int> Mywrapper;   
    Mywrapper rwi(i);   
    Mywrapper::type val = rwi.get();   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "rwi = " << val << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
rwi = 1  
```  
  
## <a name="see-also"></a>参照  
 [cref](../standard-library/functional-functions.md#cref)   
 [ref](../standard-library/functional-functions.md#ref)

