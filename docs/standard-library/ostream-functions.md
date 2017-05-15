---
title: "&lt;ostream&gt; 関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ostream/std::swap
- ostream/std::endl
- ostream/std::ends
- ostream/std::flush
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
caps.latest.revision: 15
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 89eebd013c08f52175e5e4038b501d4ce572e55a
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt; 関数
||||  
|-|-|-|  
|[swap](#swap)|[endl](#endl)|[ends](#ends)|  
|[flush](#flush)|  
  
##  <a name="endl"></a>  endl  
 行を終了し、バッファーをフラッシュします。  
  
```  
template class<Elem, Tr> basic_ostream<Elem, Tr>& endl(basic_ostream<Elem, Tr>& Ostr);
```  
  
### <a name="parameters"></a>パラメーター  
 `Elem`  
 要素型。  
  
 `Ostr`  
 `basic_ostream` 型のオブジェクト。  
  
 `Tr`  
 文字の特徴 (traits)。  
  
### <a name="return-value"></a>戻り値  
 `basic_ostream` 型のオブジェクト。  
  
### <a name="remarks"></a>コメント  
 マニピュレーターが `Ostr` **.**[put](../standard-library/basic-ostream-class.md#put)( `Ostr`**.** [widen](../standard-library/basic-ios-class.md#widen)( **'\n'**)) を呼び出してから、`Ostr`**.**[flush](../standard-library/basic-ostream-class.md#flush) を呼び出します。 `Ostr` を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// ostream_endl.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout << "testing" << endl;  
}  
```  
  
```Output  
testing  
```  
  
##  <a name="ends"></a>  ends  
 文字列を終了します。  
  
```  
template class<Elem, Tr> basic_ostream<Elem, Tr>& ends(basic_ostream<Elem, Tr>& Ostr);
```  
  
### <a name="parameters"></a>パラメーター  
 `Elem`  
 要素型。  
  
 `Ostr`  
 `basic_ostream` 型のオブジェクト。  
  
 `Tr`  
 文字の特徴 (traits)。  
  
### <a name="return-value"></a>戻り値  
 `basic_ostream` 型のオブジェクト。  
  
### <a name="remarks"></a>コメント  
 マニピュレーターが `Ostr` **.**[put](../standard-library/basic-ostream-class.md#put)( `Elem`( **'\0'**)) を呼び出します。 `Ostr.` を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// ostream_ends.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout << "a";  
   cout << "b" << ends;  
   cout << "c" << endl;  
}  
```  
  
```Output  
ab c  
```  
  
##  <a name="flush"></a>  flush  
 バッファーをフラッシュします。  
  
```  
template class<Elem, Tr> basic_ostream<Elem, Tr>& flush(basic_ostream<Elem, Tr>& Ostr);
```  
  
### <a name="parameters"></a>パラメーター  
 `Elem`  
 要素型。  
  
 `Ostr`  
 `basic_ostream` 型のオブジェクト。  
  
 `Tr`  
 文字の特徴 (traits)。  
  
### <a name="return-value"></a>戻り値  
 `basic_ostream` 型のオブジェクト。  
  
### <a name="remarks"></a>コメント  
 マニピュレーターが `Ostr` **.**[flush](../standard-library/basic-ostream-class.md#flush) を呼び出します。 `Ostr` を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// ostream_flush.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout << "testing" << flush;  
}  
```  
  
```Output  
testing  
```  
  
##  <a name="swap"></a>  swap  
 2 つの `basic_ostream` オブジェクトの値を交換します。  
  
```  
template <class Elem, class Tr>  
void swap(
    basic_ostream<Elem, Tr>& left,  
    basic_ostream<Elem, Tr>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 `basic_ostream` オブジェクトへの左辺値参照。  
  
 `right`  
 `basic_ostream` オブジェクトへの左辺値参照。  
  
### <a name="remarks"></a>コメント  
 テンプレート関数 `swap` は、`left.swap(right)` を実行します。  
  
## <a name="see-also"></a>関連項目  
 [\<ostream>](../standard-library/ostream.md)


