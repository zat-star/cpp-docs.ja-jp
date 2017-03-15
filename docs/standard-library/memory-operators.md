---
title: "&lt;memory&gt; 演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::operator!=
- memory/std::operator>
- memory/std::operator>=
- memory/std::operator<
- memory/std::operator<=
- memory/std::operator<<
- memory/std::operator==
ms.assetid: 257e3ba9-c4c2-4ae8-9b11-b156ba9c28de
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 28baed4badda4f2c1d7e5b20235fe8d40c2a7195
ms.openlocfilehash: 50cfd9e09a7534ea7c615ebf6b0c781806013965
ms.lasthandoff: 02/24/2017

---
# <a name="ltmemorygt-operators"></a>&lt;memory&gt; 演算子
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;&lt;](#operator_lt__lt_)|[operator&lt;=](#operator_lt__eq)|  
|[operator==](#operator_eq_eq)|  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a>  operator!=  
 オブジェクト間の不等性をテストします。  
  
```  
template <class Type, class Other>  
bool operator!=(
    const allocator<Type>& left,  
    const allocator<Other>& right) throw();

template <class T, class Del1, class U, class Del2>  
bool operator!=(
    const unique_ptr<T, Del1>& left,  
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>  
bool operator!=(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` left`  
 不等性をテストする一方のオブジェクト。  
  
 ` right`  
 不等性をテストする一方のオブジェクト。  
  
 `Ty1`  
 左辺の共有ポインターによって制御される型。  
  
 `Ty2`  
 右辺の共有ポインターによって制御される型。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが等しくない場合は **true**、オブジェクトが等しい場合は **false**。  
  
### <a name="remarks"></a>コメント  
 1 つ目のテンプレートの演算子は、false を返します。 (すべての既定のアロケーターは等価です。)  
  
 2 番目と&3; 番目のテンプレート演算子は `!(`` left` `==` ` right``)` を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// memory_op_me.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   allocator<double> Alloc;  
   vector <char>:: allocator_type v1Alloc;  
  
   if ( Alloc != v1Alloc )  
      cout << "The allocator objects Alloc & v1Alloc not are equal."  
           << endl;  
   else  
      cout << "The allocator objects Alloc & v1Alloc are equal."  
           << endl;  
}  
```  
  
```Output  
The allocator objects Alloc & v1Alloc are equal.  
```  
  
### <a name="example"></a>例  
  
```cpp  
// std__memory__operator_ne.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
int main()   
    {   
    std::shared_ptr<int> sp0(new int(0));   
    std::shared_ptr<int> sp1(new int(0));   
  
    std::cout << "sp0 != sp0 == " << std::boolalpha   
        << (sp0 != sp0) << std::endl;   
    std::cout << "sp0 != sp1 == " << std::boolalpha   
        << (sp0 != sp1) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
sp0 != sp0 == false  
sp0 != sp1 == true  
```  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a>  operator==  
 オブジェクト同士が等しいかどうかをテストします。  
  
```  
template <class Type, class Other>  
bool operator==(
    const allocator<Type>& left,  
    const allocator<Other>& right) throw();

template <class Ty1, class Del1, class Ty2, class Del2>  
bool operator==(
    const unique_ptr<Ty1, Del1>& left,  
    const unique_ptr<Ty2, Del2>& right);

template <class Ty1, class Ty2>  
bool operator==(
    const shared_ptr<Ty1>& left;,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` left`  
 等しいかどうかをテストするオブジェクト。  
  
 ` right`  
 等しいかどうかをテストするオブジェクト。  
  
 `Ty1`  
 左辺の共有ポインターによって制御される型。  
  
 `Ty2`  
 右辺の共有ポインターによって制御される型。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが等しい場合は `true`、オブジェクトが等しくない場合は `false`。  
  
### <a name="remarks"></a>コメント  
 1 つ目のテンプレート演算子は true を返します。 (すべての既定のアロケーターは等価です。)  
  
 2 番目と&3; 番目のテンプレート演算子は ` left.get() ==  right.get()` を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// memory_op_eq.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   allocator<char> Alloc;  
   vector <int>:: allocator_type v1Alloc;  
  
   allocator<char> cAlloc(Alloc);   
   allocator<int> cv1Alloc(v1Alloc);  
  
   if ( cv1Alloc == v1Alloc )  
      cout << "The allocator objects cv1Alloc & v1Alloc are equal."  
           << endl;  
   else  
      cout << "The allocator objects cv1Alloc & v1Alloc are not equal."  
           << endl;  
  
   if ( cAlloc == Alloc )  
      cout << "The allocator objects cAlloc & Alloc are equal."  
           << endl;  
   else  
      cout << "The allocator objects cAlloc & Alloc are not equal."  
           << endl;  
}  
```  
  
```Output  
The allocator objects cv1Alloc & v1Alloc are equal.  
The allocator objects cAlloc & Alloc are equal.  
```  
  
### <a name="example"></a>例  
  
```cpp  
// std__memory__operator_eq.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
int main()   
    {   
    std::shared_ptr<int> sp0(new int(0));   
    std::shared_ptr<int> sp1(new int(0));   
  
    std::cout << "sp0 == sp0 == " << std::boolalpha   
        << (sp0 == sp0) << std::endl;   
    std::cout << "sp0 == sp1 == " << std::boolalpha   
        << (sp0 == sp1) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
sp0 == sp0 == true  
sp0 == sp1 == false  
```  
  
##  <a name="a-nameoperatorgteqa--operatorgt"></a><a name="operator_gt__eq"></a>  operator&gt;=  
 1 つ目のオブジェクトが&2; つ目のオブジェクト以上であるかをテストします。  
  
```  
template <class T, class Del1, class U, class Del2>  
bool operator>=(
    const unique_ptr<T, Del1>& left,  
    const unique_ptr<U, Del2>& right);

template <class Ty1, class Ty2>  
bool operator>=(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` left`  
 比較するオブジェクトの&1; つ。  
  
 ` right`  
 比較するオブジェクトの&1; つ。  
  
 `Ty1`  
 左辺の共有ポインターによって制御される型。  
  
 `Ty2`  
 右辺の共有ポインターによって制御される型。  
  
### <a name="remarks"></a>コメント  
 このテンプレート演算子は ` left``.get() >=`` right``.get()` を返します。  
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a>  operator&lt;  
 1 番目のオブジェクトが&2; 番目のオブジェクトより小さいかどうかをテストします。  
  
```  
template <class T, class Del1, class U, class Del2>  
bool operator<(
    const unique_ptr<T, Del1>& left,  
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>  
bool operator<(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` left`  
 比較するオブジェクトの&1; つ。  
  
 ` right`  
 比較するオブジェクトの&1; つ。  
  
 `Ty1`  
 左辺のポインターによって制御される型。  
  
 `Ty2`  
 右辺のポインターによって制御される型。  
  
##  <a name="a-nameoperatorlteqa--operatorlt"></a><a name="operator_lt__eq"></a>  operator&lt;=  
 1 番目のオブジェクトが&2; 番目のオブジェクト以下であるかどうかをテストします。  
  
```  
template <class T, class Del1, class U, class Del2>  
bool operator<=(
    const unique_ptr<T, Del1>& left,  
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>  
bool operator<=(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` left`  
 比較するオブジェクトの&1; つ。  
  
 ` right`  
 比較するオブジェクトの&1; つ。  
  
 `Ty1`  
 左辺の共有ポインターによって制御される型。  
  
 `Ty2`  
 右辺の共有ポインターによって制御される型。  
  
### <a name="remarks"></a>コメント  
 このテンプレート演算子は ` left``.get() <=`` right``.get()` を返します。  
  
##  <a name="a-nameoperatorgta--operatorgt"></a><a name="operator_gt_"></a>  operator&gt;  
 1 番目のオブジェクトが&2; 番目のオブジェクトより大きいかどうかをテストします。  
  
```  
template <class Ty1, class Del1, class Ty2, class Del2>  
bool operator>(
    const unique_ptr<Ty1, Del1>& left,  
    const unique_ptr<Ty2&, Del2gt;& right);

template <class Ty1, class Ty2>  
bool operator>(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` left`  
 比較するオブジェクトの&1; つ。  
  
 ` right`  
 比較するオブジェクトの&1; つ。  
  
 `Ty1`  
 左辺の共有ポインターによって制御される型。  
  
 `Ty2`  
 右辺の共有ポインターによって制御される型。  
  
##  <a name="a-nameoperatorltlta--operatorltlt"></a><a name="operator_lt__lt_"></a>  operator&lt;&lt;  
共有ポインターをストリームに書き込みます。  
  
```  
template <class Elem, class Tr, class Ty>  
std::basic_ostream<Elem, Tr>& operator<<(std::basic_ostream<Elem, Tr>& out,  
    shared_ptr<Ty>& sp);
```  
  
### <a name="parameters"></a>パラメーター  
 `Elem`  
 ストリーム要素の型。  
  
 `Tr`  
 ストリーム要素の特性の型。  
  
 `Ty`  
 共有ポインターによって制御される型。  
  
 `out`  
 出力ストリーム。  
  
 `sp`  
 共有ポインター。  
  
### <a name="remarks"></a>コメント  
 このテンプレート関数は `out << sp.get()` を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// std__memory__operator_sl.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
int main()   
    {   
    std::shared_ptr<int> sp0(new int(5));   
  
    std::cout << "sp0 == " << sp0 << " (varies)" << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
sp0 == 3f3040 (varies)  
```  
  
## <a name="see-also"></a>関連項目  
 [\<memory>](../standard-library/memory.md)


