---
title: "&lt;hash_set&gt; 演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 403d8e4e-0b3f-43fb-bc5a-8100c4f331c5
caps.latest.revision: 13
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 031904042e81f5ec9c8b54bbc3e2bfa9e9a365cf
ms.lasthandoff: 02/24/2017

---
# <a name="lthashsetgt-operators"></a>&lt;hash_set&gt; 演算子
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator!= (hash_multiset)](#operator_neq__hash_multiset_)|[operator==](#operator_eq_eq)|  
|[operator== (hash_multiset)](#operator_eq_eq__hash_multiset_)|  
  
##  <a name="operator_neq"></a>  operator!=  
  
> [!NOTE]
>  この API は、互換性のために残されています。 代わりに、[unordered_set クラス](../standard-library/unordered-set-class.md)を使用してください。  
  
 演算子の左辺の hash_set オブジェクトが右辺の hash_set オブジェクトと等しくないかどうかを調べます。  
  
```  
bool operator!=(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 `hash_set` 型のオブジェクト。  
  
 `right`  
 `hash_set` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 hash_sets が等しくない場合は **true**、hash_sets が等しい場合は **false**。  
  
### <a name="remarks"></a>コメント  
 hash_set オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの hash_sets は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。  
  
 Visual C++ .NET 2003 では、[<hash_map>](../standard-library/hash-map.md) ヘッダー ファイルと [<hash_set>](../standard-library/hash-set.md) ヘッダー ファイルのメンバーは、std 名前空間に存在しなくなりましたが、stdext 名前空間に移動されました。 詳細については、「[The stdext 名前空間](../standard-library/stdext-namespace.md)」をご覧ください。  
  
### <a name="example"></a>例  
  
```cpp  
// hash_set_op_ne.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   using namespace stdext;  
   hash_set <int> hs1, hs2, hs3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hs1.insert ( i );  
      hs2.insert ( i * i );  
      hs3.insert ( i );  
   }  
  
   if ( hs1 != hs2 )  
      cout << "The hash_sets hs1 and hs2 are not equal." << endl;  
   else  
      cout << "The hash_sets hs1 and hs2 are equal." << endl;  
  
   if ( hs1 != hs3 )  
      cout << "The hash_sets hs1 and hs3 are not equal." << endl;  
   else  
      cout << "The hash_sets hs1 and hs3 are equal." << endl;  
}  
```  
  
```Output  
The hash_sets hs1 and hs2 are not equal.  
The hash_sets hs1 and hs3 are equal.  
```  
  
##  <a name="operator_eq_eq"></a>  operator==  
  
> [!NOTE]
>  この API は、互換性のために残されています。 代わりに、[unordered_set クラス](../standard-library/unordered-set-class.md)を使用してください。  
  
 演算子の左辺の hash_set オブジェクトが右辺の hash_set オブジェクトと等しいかどうかを調べます。  
  
```  
bool operator!==(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 `hash_set` 型のオブジェクト。  
  
 `right`  
 `hash_set` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 演算子の左辺の hash_set が演算子の右辺の hash_set と等しい場合は **true**、それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 hash_set オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの hash_sets は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。  
  
 Visual C++ .NET 2003 では、[<hash_map>](../standard-library/hash-map.md) ヘッダー ファイルと [<hash_set>](../standard-library/hash-set.md) ヘッダー ファイルのメンバーは、std 名前空間に存在しなくなりましたが、stdext 名前空間に移動されました。 詳細については、「[The stdext 名前空間](../standard-library/stdext-namespace.md)」をご覧ください。  
  
### <a name="example"></a>例  
  
```cpp  
// hash_set_op_eq.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_set <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i );  
   }  
  
   if ( s1 == s2 )  
      cout << "The hash_sets s1 and s2 are equal." << endl;  
   else  
      cout << "The hash_sets s1 and s2 are not equal." << endl;  
  
   if ( s1 == s3 )  
      cout << "The hash_sets s1 and s3 are equal." << endl;  
   else  
      cout << "The hash_sets s1 and s3 are not equal." << endl;  
}  
```  
  
```Output  
The hash_sets s1 and s2 are not equal.  
The hash_sets s1 and s3 are equal.  
```  
  
##  <a name="operator_neq__hash_multiset_"></a>  operator!= (hash_multiset)  
  
> [!NOTE]
>  この API は、互換性のために残されています。 代わりに、[unordered_set クラス](../standard-library/unordered-set-class.md)を使用してください。  
  
 演算子の左側の hash_multiset オブジェクトが右側の hash_multiset オブジェクトと等しくないかどうかをテストします。  
  
```  
bool operator!=(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 `hash_multiset` 型のオブジェクト。  
  
 `right`  
 `hash_multiset` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 hash_multisets が等しくない場合は **true**、hash_multisets が等しい場合は **false**。  
  
### <a name="remarks"></a>コメント  
 hash_multiset オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの hash_multisets は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。  
  
 Visual C++ .NET 2003 では、[<hash_map>](../standard-library/hash-map.md) ヘッダー ファイルと [<hash_set>](../standard-library/hash-set.md) ヘッダー ファイルのメンバーは、std 名前空間に存在しなくなりましたが、stdext 名前空間に移動されました。 詳細については、「[The stdext 名前空間](../standard-library/stdext-namespace.md)」をご覧ください。  
  
### <a name="example"></a>例  
  
```cpp  
// hashset_op_ne.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hs1, hs2, hs3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hs1.insert ( i );  
      hs2.insert ( i * i );  
      hs3.insert ( i );  
   }  
  
   if ( hs1 != hs2 )  
      cout << "The hash_multisets hs1 and hs2 are not equal." << endl;  
   else  
      cout << "The hash_multisets hs1 and hs2 are equal." << endl;  
  
   if ( hs1 != hs3 )  
      cout << "The hash_multisets hs1 and hs3 are not equal." << endl;  
   else  
      cout << "The hash_multisets hs1 and hs3 are equal." << endl;  
}  
```  
  
```Output  
The hash_multisets hs1 and hs2 are not equal.  
The hash_multisets hs1 and hs3 are equal.  
```  
  
##  <a name="operator_eq_eq__hash_multiset_"></a>  operator== (hash_multiset)  
  
> [!NOTE]
>  この API は、互換性のために残されています。 代わりに、[unordered_set クラス](../standard-library/unordered-set-class.md)を使用してください。  
  
 演算子の左側の hash_multiset オブジェクトが右側の hash_multiset オブジェクトと等しいかどうかをテストします。  
  
```  
bool operator!==(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 `hash_multiset` 型のオブジェクト。  
  
 `right`  
 `hash_multiset` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 演算子の左辺の hash_multiset が演算子の右辺の hash_multiset と等しい場合は **true**、それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 hash_multiset オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの hash_multisets は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。  
  
 Visual C++ .NET 2003 では、[<hash_map>](../standard-library/hash-map.md) ヘッダー ファイルと [<hash_set>](../standard-library/hash-set.md) ヘッダー ファイルのメンバーは、std 名前空間に存在しなくなりましたが、stdext 名前空間に移動されました。 詳細については、「[The stdext 名前空間](../standard-library/stdext-namespace.md)」をご覧ください。  
  
### <a name="example"></a>例  
  
```cpp  
// hash_multiset_op_eq.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i );  
   }  
  
   if ( s1 == s2 )  
      cout << "The hash_multisets s1 and s2 are equal." << endl;  
   else  
      cout << "The hash_multisets s1 and s2 are not equal." << endl;  
  
   if ( s1 == s3 )  
      cout << "The hash_multisets s1 and s2 are equal." << endl;  
   else  
      cout << "The hash_multisets s1 and s2 are not equal." << endl;  
}  
```  
  
```Output  
The hash_multisets s1 and s2 are not equal.  
The hash_multisets s1 and s2 are equal.  
```  
  
## <a name="see-also"></a>関連項目  
 [<hash_set>](../standard-library/hash-set.md)


