---
title: "&lt;vector&gt; 演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 1d14f312-6f59-4ec7-88ae-95f89a558823
caps.latest.revision: 13
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 14308c0789851af423fd687f88acfe9177d89aff
ms.lasthandoff: 02/24/2017

---
# <a name="ltvectorgt-operators"></a>&lt;vector&gt; 演算子
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;=](#operator_lt__eq)|[operator==](#operator_eq_eq)|  
  
##  <a name="operator_neq"></a>  operator!=  
 演算子の左側のオブジェクトが右側のオブジェクトと等しくないかどうかを調べます。  
  
```  
bool operator!=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 **vector** 型のオブジェクト。  
  
 `right`  
 **vector** 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 vector が等しくない場合は **true**。vector が等しい場合は **false**。  
  
### <a name="remarks"></a>コメント  
 2 つの vector は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。  
  
### <a name="example"></a>例  
  
```cpp  
// vector_op_ne.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
     v2.push_back( 2 );  
  
   if ( v1 != v2 )  
      cout << "Vectors not equal." << endl;  
   else  
      cout << "Vectors equal." << endl;  
}  
```  
  
```Output  
Vectors not equal.  
```  
  
##  <a name="operator_lt_"></a>  operator&lt;  
 演算子の左側のオブジェクトが右側のオブジェクトより小さいかどうかを調べます。  
  
```  
bool operator<(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 **vector** 型のオブジェクト。  
  
 `right`  
 **vector** 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 演算子の左辺の vector が演算子の右辺の vector より小さい場合は **true**、それ以外の場合は **false**。  
  
### <a name="example"></a>例  
  
```cpp  
// vector_op_lt.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   v1.push_back( 4 );  
  
   v2.push_back( 1 );  
   v2.push_back( 3 );  
  
   if ( v1 < v2 )  
      cout << "Vector v1 is less than vector v2." << endl;  
   else  
      cout << "Vector v1 is not less than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is less than vector v2.  
```  
  
##  <a name="operator_lt__eq"></a>  operator&lt;=  
 演算子の左側のオブジェクトが右側のオブジェクト以下かどうかを調べます。  
  
```  
bool operator<=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 **vector** 型のオブジェクト。  
  
 `right`  
 **vector** 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 演算子の左辺の vector が演算子の右辺の vector 以下の場合は **true**、それ以外の場合は **false**。  
  
### <a name="example"></a>例  
  
```cpp  
// vector_op_le.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   v1.push_back( 4 );  
  
   v2.push_back( 1 );  
   v2.push_back( 3 );  
  
   if ( v1 <= v2 )  
      cout << "Vector v1 is less than or equal to vector v2." << endl;  
   else  
      cout << "Vector v1 is greater than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is less than or equal to vector v2.  
```  
  
##  <a name="operator_eq_eq"></a>  operator==  
 演算子の左側のオブジェクトが右側のオブジェクトと等しいかどうかを調べます。  
  
```  
bool operator==(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 **vector** 型のオブジェクト。  
  
 `right`  
 **vector** 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 演算子の左辺の vector が演算子の右辺の vector と等しい場合は **true**、それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 2 つの vector は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。  
  
### <a name="example"></a>例  
  
```cpp  
// vector_op_eq.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v2.push_back( 1 );  
  
   if ( v1 == v2 )  
      cout << "Vectors equal." << endl;  
   else  
      cout << "Vectors not equal." << endl;  
}  
```  
  
```Output  
Vectors equal.  
```  
  
##  <a name="operator_gt_"></a>  operator&gt;  
 演算子の左側のオブジェクトが右側のオブジェクトより大きいかどうかを調べます。  
  
```  
bool operator>(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 **vector** 型のオブジェクト。  
  
 `right`  
 **vector** 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 演算子の左辺の vector が演算子の右辺の vector より大きい場合は **true**、それ以外の場合は **false**。  
  
### <a name="example"></a>例  
  
```cpp  
// vector_op_gt.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 3 );  
   v1.push_back( 1 );  
  
   v2.push_back( 1 );  
   v2.push_back( 2 );  
   v2.push_back( 2 );  
  
   if ( v1 > v2 )  
      cout << "Vector v1 is greater than vector v2." << endl;  
   else  
      cout << "Vector v1 is not greater than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is greater than vector v2.  
```  
  
##  <a name="operator_gt__eq"></a>  operator&gt;=  
 演算子の左側のオブジェクトが右側のオブジェクト以上であるかどうかを調べます。  
  
```  
bool operator>=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 **vector** 型のオブジェクト。  
  
 `right`  
 **vector** 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 演算子の左辺の vector が演算子の右辺の vector 以上の場合は **true**、それ以外の場合は **false**。  
  
### <a name="example"></a>例  
  
```cpp  
// vector_op_ge.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 3 );  
   v1.push_back( 1 );  
  
     v2.push_back( 1 );  
   v2.push_back( 2 );  
   v2.push_back( 2 );  
  
   if ( v1 >= v2 )  
      cout << "Vector v1 is greater than or equal to vector v2." << endl;  
   else  
      cout << "Vector v1 is less than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is greater than or equal to vector v2.  
```  
  
## <a name="see-also"></a>関連項目  
 [\<vector>](../standard-library/vector.md)


