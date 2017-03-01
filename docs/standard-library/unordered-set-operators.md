---
title: "&lt;unordered_set&gt; 演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8653eea6-12f2-4dd7-aa2f-db38a71599a0
caps.latest.revision: 7
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: da5fe91f5306080ce10c72d8cc1908b6952135c3
ms.lasthandoff: 02/24/2017

---
# <a name="ltunorderedsetgt-operators"></a>&lt;unordered_set&gt; operators
|||||  
|-|-|-|-|  
|[operator!=](#operator_neq)|[operator==](#operator_eq_eq)|[operator!=](#operator_neq_unordered_multiset)|[operator==](#operator_eq_eq_unordered_multiset)|  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a>  operator!=  
 演算子の左側にある [unordered_set](../standard-library/unordered-set-class.md) オブジェクトが、右側にある unordered_set オブジェクトと等しくないかどうかをテストします。  
  
```
bool operator!=(const unordered_set <Key, Hash, Pred, Allocator>& left, const unordered_set <Key, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 `unordered_set` 型のオブジェクト。  
  
 `right`  
 `unordered_set` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 unordered_sets が等しくない場合 `true` で、等しい場合は `false` です。  
  
### <a name="remarks"></a>コメント  
 unordered_set オブジェクト間の比較は、要素を任意の順序で格納することによる影響を受けません。 同じ数の要素が存在しており、一方のコンテナー内の要素がもう一方のコンテナー内の要素の並べ替えである場合、2 つの unordered_set は等しくなります。 それ以外の場合は等しくありません。  
  
### <a name="example"></a>例  
  
```cpp  
// unordered_set_ne.cpp   
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_set>   
#include <iostream>   
#include <ios>  
  
int main()   
{   
    using namespace std;  
  
    unordered_set<char> c1, c2, c3;  
  
    c1.insert('a');   
    c1.insert('b');   
    c1.insert('c');   
  
    c2.insert('c');   
    c2.insert('a');   
    c2.insert('d');   
  
    c3.insert('c');   
    c3.insert('a');   
    c3.insert('b');   
  
   cout << boolalpha;  
   cout << "c1 != c2: " << (c1 != c2) << endl;   
   cout << "c1 != c3: " << (c1 != c3) << endl;   
   cout << "c2 != c3: " << (c2 != c3) << endl;   
  
    return (0);   
}  
  
```  
  
 **出力:**  
  
 `c1 != c2: true`  
  
 `c1 != c3: false`  
  
 `c2 != c3: true`  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a>  operator==  
 演算子の左側にある [unordered_set](../standard-library/unordered-set-class.md) オブジェクトが、右側にある unordered_set オブジェクトと等しいかどうかをテストします。  
  
```
bool operator==(const unordered_set <Key, Hash, Pred, Allocator>& left, const unordered_set <Key, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 `unordered_set` 型のオブジェクト。  
  
 `right`  
 `unordered_set` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 unordered_sets が等しい場合 `true` で、等しくない場合は `false` です。  
  
### <a name="remarks"></a>コメント  
 unordered_set オブジェクト間の比較は、要素を任意の順序で格納することによる影響を受けません。 同じ数の要素が存在しており、一方のコンテナー内の要素がもう一方のコンテナー内の要素の並べ替えである場合、2 つの unordered_set は等しくなります。 それ以外の場合は等しくありません。  
  
### <a name="example"></a>例  
  
```cpp  
// unordered_set_eq.cpp   
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_set>   
#include <iostream>   
#include <ios>  
  
int main()   
{   
    using namespace std;  
  
    unordered_set<char> c1, c2, c3;  
  
    c1.insert('a');   
    c1.insert('b');   
    c1.insert('c');   
  
    c2.insert('c');   
    c2.insert('a');   
    c2.insert('d');   
  
    c3.insert('c');   
    c3.insert('a');   
    c3.insert('b');   
  
   cout << boolalpha;  
   cout << "c1 == c2: " << (c1 == c2) << endl;   
   cout << "c1 == c3: " << (c1 == c3) << endl;   
   cout << "c2 == c3: " << (c2 == c3) << endl;   
  
    return (0);   
}  
  
```  
  
 **出力:**  
  
 `c1 == c2: false`  
  
 `c1 == c3: true`  
  
 `c2 == c3: false`  
  
##  <a name="a-nameoperatornequnorderedmultiseta--operator"></a><a name="operator_neq_unordered_multiset"></a>  operator!=  
 演算子の左側の [unordered_multiset](../standard-library/unordered-multiset-class.md) オブジェクトが右側の unordered_multiset オブジェクトと等しくないかどうかをテストします。  
  
```
bool operator!=(const unordered_multiset <Key, Hash, Pred, Allocator>& left, const unordered_multiset <Key, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 `unordered_multiset` 型のオブジェクト。  
  
 `right`  
 `unordered_multiset` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 unordered_multisets が等しくない場合 `true` で、等しい場合は `false` です。  
  
### <a name="remarks"></a>コメント  
 unordered_multiset オブジェクト間の比較は、要素を任意の順序で格納することによる影響を受けません。 同じ数の要素が存在しており、一方のコンテナー内の要素がもう一方のコンテナー内の要素の並べ替えである場合、2 つの unordered_multisets は等しくなります。 それ以外の場合は等しくありません。  
  
### <a name="example"></a>例  
  
```cpp  
// unordered_multiset_ne.cpp   
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_set>   
#include <iostream>   
#include <ios>  
  
int main()   
{   
    using namespace std;  
  
    unordered_multiset<char> c1, c2, c3;  
  
    c1.insert('a');   
    c1.insert('b');   
    c1.insert('c');   
    c1.insert('c');   
  
    c2.insert('c');   
    c2.insert('c');   
    c2.insert('a');   
    c2.insert('d');   
  
    c3.insert('c');   
    c3.insert('c');   
    c3.insert('a');   
    c3.insert('b');   
  
   cout << boolalpha;  
   cout << "c1 != c2: " << (c1 != c2) << endl;   
   cout << "c1 != c3: " << (c1 != c3) << endl;   
   cout << "c2 != c3: " << (c2 != c3) << endl;   
  
    return (0);   
}  
  
```  
  
 **出力:**  
  
 `c1 != c2: true`  
  
 `c1 != c3: false`  
  
 `c2 != c3: true`  
  
##  <a name="a-nameoperatoreqequnorderedmultiseta--operator"></a><a name="operator_eq_eq_unordered_multiset"></a>  operator==  
 演算子の左側の [unordered_multiset](../standard-library/unordered-multiset-class.md) オブジェクトが右側の unordered_multiset オブジェクトと等しいかどうかをテストします。  
  
```
bool operator==(const unordered_multiset <Key, Hash, Pred, Allocator>& left, const unordered_multiset <Key, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 `unordered_multiset` 型のオブジェクト。  
  
 `right`  
 `unordered_multiset` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 unordered_multisets が等しい場合 `true` で、等しくない場合は `false` です。  
  
### <a name="remarks"></a>コメント  
 unordered_multiset オブジェクト間の比較は、要素を任意の順序で格納することによる影響を受けません。 同じ数の要素が存在しており、一方のコンテナー内の要素がもう一方のコンテナー内の要素の並べ替えである場合、2 つの unordered_multisets は等しくなります。 それ以外の場合は等しくありません。  
  
### <a name="example"></a>例  
  
```cpp  
// unordered_multiset_eq.cpp   
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_set>   
#include <iostream>   
#include <ios>  
  
int main()   
{   
    using namespace std;  
  
    unordered_multiset<char> c1, c2, c3;  
  
    c1.insert('a');   
    c1.insert('b');   
    c1.insert('c');   
    c1.insert('c');   
  
    c2.insert('c');   
    c2.insert('c');   
    c2.insert('a');   
    c2.insert('d');   
  
    c3.insert('c');   
    c3.insert('c');   
    c3.insert('a');   
    c3.insert('b');   
  
   cout << boolalpha;  
   cout << "c1 == c2: " << (c1 == c2) << endl;   
   cout << "c1 == c3: " << (c1 == c3) << endl;   
   cout << "c2 == c3: " << (c2 == c3) << endl;   
  
    return (0);   
}  
  
```  
  
 **出力:**  
  
 `c1 == c2: false`  
  
 `c1 == c3: true`  
  
 `c2 == c3: false`  
  
## <a name="see-also"></a>関連項目  
 [<unordered_set>](../standard-library/unordered-set.md)




