---
title: "&lt;ostream&gt; 関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
caps.latest.revision: 15
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 44708461657101b1ddad7db76f1c3c8d4df07f3a
ms.lasthandoff: 02/24/2017

---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt; 関数
||||  
|-|-|-|  
|[swap](#swap)|[endl](#endl)|[ends](#ends)|  
|[flush](#flush)|  
  
##  <a name="a-nameendla--endl"></a><a name="endl"></a>  endl  
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
 マニピュレーターが `Ostr` **.**[put](../standard-library/basic-ostream-class.md#basic_ostream__put)( `Ostr`**.** [widen](../standard-library/basic-ios-class.md#basic_ios__widen)( **'\n'**)) を呼び出してから、`Ostr`**.**[flush](../standard-library/basic-ostream-class.md#basic_ostream__flush) を呼び出します。 `Ostr` を返します。  
  
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
  
##  <a name="a-nameendsa--ends"></a><a name="ends"></a>  ends  
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
 マニピュレーターが `Ostr` **.**[put](../standard-library/basic-ostream-class.md#basic_ostream__put)( `Elem`( **'\0'**)) を呼び出します。 `Ostr.` を返します。  
  
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
  
##  <a name="a-nameflusha--flush"></a><a name="flush"></a>  flush  
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
 マニピュレーターが `Ostr` **.**[flush](../standard-library/basic-ostream-class.md#basic_ostream__flush) を呼び出します。 `Ostr` を返します。  
  
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
  
##  <a name="a-nameswapa--swap"></a><a name="swap"></a>  swap  
 2 つの `basic_ostream` オブジェクトの値を交換します。  
  
```  
template <class Elem, class Tr>  
void swap(
    basic_ostream<Elem, Tr>& left,  
    basic_ostream<Elem, Tr>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` left`  
 `basic_ostream` オブジェクトへの左辺値参照。  
  
 ` right`  
 `basic_ostream` オブジェクトへの左辺値参照。  
  
### <a name="remarks"></a>コメント  
 テンプレート関数 `swap` は、` left.swap(`` right``)` を実行します。  
  
## <a name="see-also"></a>関連項目  
 [\<ostream>](../standard-library/ostream.md)


