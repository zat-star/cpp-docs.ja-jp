---
title: "&lt;bitset&gt; 演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84fe6a13-6f6e-4cdc-bf8f-6f65ab1134d4
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 2a1f1c21cdcd42e7e8d33eb6405297fc88635d87
ms.lasthandoff: 02/24/2017

---
# <a name="ltbitsetgt-operators"></a>&lt;bitset&gt; 演算子
||||  
|-|-|-|  
|[operator&amp;](#operator_amp_)|[operator&gt;&gt;](#operator_gt__gt_)|[operator&lt;&lt;](#operator_lt__lt_)|  
|[operator_xor](#operator_xor)|[operator_or](#operator_or)|  
  
##  <a name="a-nameoperatorampa--operatoramp"></a><a name="operator_amp_"></a>  operator&amp;  
 2 つのビットセット間でビットごとの `AND` を実行します。  
  
```  
template <size_t size>  
bitset<size>  
operator&(
    const bitset<size>& left,  
    const bitset<size>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` left`  
 それぞれの要素が `AND` でビットごとに結合される&2; つのビットセットのうちの最初。  
  
 ` right`  
 それぞれの要素が `AND` でビットごとに結合される&2; つの valarray のうちの&2; つ目。  
  
### <a name="return-value"></a>戻り値  
 要素が ` left` と ` right` の該当要素で `AND` 演算を実行した結果であるビットセット。  
  
### <a name="example"></a>例  
  
```cpp  
// bitset_and.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
#include <string>  
  
using namespace std;  
  
int main()  
{  
   bitset<4> b1 ( string("0101") );  
   bitset<4> b2 ( string("0011") );  
   bitset<4> b3 = b1 & b2;  
   cout << "bitset 1: " << b1 << endl;  
   cout << "bitset 2: " << b2 << endl;  
   cout << "bitset 3: " << b3 << endl;  
}  
```  
  
```Output  
bitset 1: 0101  
bitset 2: 0011  
bitset 3: 0001  
```  
  
##  <a name="a-nameoperatorltlta--operatorltlt"></a><a name="operator_lt__lt_"></a>  演算子&lt;&lt;  
 ビット シーケンスのテキスト表現を出力ストリームに挿入します。  
  
```  
 
template <class CharType, class Traits, size_t N>  
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& ostr,  
    const bitset<N>& 
    right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 文字列として出力ストリームに挿入する型 **bitset\<N>** のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 **ostr** のビット シーケンスのテキスト表現。  
  
### <a name="remarks"></a>コメント  
 このテンプレート関数は **operator<<** をオーバーロードし、最初に文字列に変換することなく、ビットセットを書き込みます。 このテンプレート関数は、実質的に次の内容を実行します。  
  
 **ostr** << _ *Right*. [to_string](https://msdn.microsoft.com/library/2f93c55z.aspx) < **CharType**, **Traits**, **allocator**\< **CharType**> > ( )  
  
### <a name="example"></a>例  
  
```cpp  
// bitset_op_insert.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
#include <string>  
  
int main( )  
{  
   using namespace std;  
  
   bitset<5> b1 ( 9 );  
  
   // bitset inserted into output stream directly  
   cout << "The ordered set of bits in the bitset<5> b1(9)"  
        << "\n can be output with the overloaded << as: ( "  
        << b1 << " )" << endl;  
  
   // Compare converting bitset to a string before  
   // inserting it into the output steam  
   string s1;  
   s1 =  b1.template to_string<char,   
      char_traits<char>, allocator<char> >( );  
   cout << "The string returned from the bitset b1"  
        << "\n by the member function to_string( ) is: "  
        << s1 << "." << endl;  
}  
```  
  
##  <a name="a-nameoperatorgtgta--operatorgtgt"></a><a name="operator_gt__gt_"></a>  演算子&gt;&gt;  
 ビット文字の文字列をビットセットに読み込みます。  
  
```  
 
template <class CharType, class Traits, size_t Bits>  
basic_istream<CharType, Traits>& operator>> (
    basic_istream<CharType, Traits>& 
_Istr,  
    bitset<N>& 
    right);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Istr`  
 ビットセットに挿入する入力ストリームに入力される文字列。  
  
 ` right`  
 入力ストリームからビットを受け取るビットセット。  
  
### <a name="return-value"></a>戻り値  
 このテンプレート関数は文字列 `_Istr` を返します。  
  
### <a name="remarks"></a>コメント  
 このテンプレート関数は **operator>>** をオーバーロードし、ビットセット _ *Right* に値ビットセット (`str`) を格納します。`str` は `_Istr` から抽出された型 [basic_string](https://msdn.microsoft.com/library/syxtdd4f.aspx) < **CharType**, **Traits**, **allocator**\< **CharType**> > **&** のオブジェクトです。  
  
 このテンプレート関数は `_Istr` から要素を抽出し、次の状態になるまでそれをビットセットに挿入します。  
  
-   すべてのビット要素が入力ストリームから抽出され、ビットセットに格納されています。  
  
-   ビットセットが入力ストリームからのビットでいっぱいになっています。  
  
-   0 でも 1 でもない入力要素に遭遇しました。  
  
### <a name="example"></a>例  
  
```cpp  
#include <bitset>  
#include <iostream>  
#include <string>  
  
using namespace std;  
int main()  
{  
  
   bitset<5> b1;  
   cout << "Enter string of (0 or 1) bits for input into bitset<5>.\n"  
        << "Try bit string of length less than or equal to 5,\n"  
        << " (for example: 10110): ";  
   cin >>  b1;  
  
   cout << "The ordered set of bits entered from the "  
        << "keyboard\n has been input into bitset<5> b1 as: ( "  
        << b1 << " )" << endl;  
  
   // Truncation due to longer string of bits than length of bitset  
   bitset<2> b3;  
   cout << "Enter string of bits (0 or 1) for input into bitset<2>.\n"  
        << " Try bit string of length greater than 2,\n"  
        << " (for example: 1011): ";  
   cin >>  b3;  
  
   cout << "The ordered set of bits entered from the "  
        << "keyboard\n has been input into bitset<2> b3 as: ( "  
        << b3 << " )" << endl;  
  
   // Flushing the input stream  
   char buf[100];  
   cin.getline(&buf[0], 99);  
  
   // Truncation with non-bit value  
   bitset<5> b2;  
   cout << "Enter a string for input into  bitset<5>.\n"  
        << " that contains a character than is NOT a 0 or a 1,\n "  
        << " (for example: 10k01): ";  
   cin >>  b2;  
  
   cout << "The string entered from the keyboard\n"  
        << " has been input into bitset<5> b2 as: ( "  
        << b2 << " )" << endl;  
}  
```  
  
##  <a name="a-nameoperatorxora--operatorxor"></a><a name="operator_xor"></a>  operator_xor  
 2 つのビットセット間でビットごとの `EXCLUSIVE-OR` を実行します。  
  
```  
template <size_t size>  
bitset<size>  
operator^(
    const bitset<size>& left,  
    const bitset<size>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` left`  
 それぞれの要素が `EXCLUSIVE-OR` でビットごとに結合される&2; つのビットセットのうちの最初。  
  
 ` right`  
 それぞれの要素が `EXCLUSIVE-OR` でビットごとに結合される&2; つの valarray のうちの&2; つ目。  
  
### <a name="return-value"></a>戻り値  
 要素が ` left` と ` right` の該当要素で `EXCLUSIVE-OR` 演算を実行した結果であるビットセット。  
  
### <a name="example"></a>例  
  
```cpp  
// bitset_xor.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
#include <string>  
  
using namespace std;  
  
int main()  
{  
   bitset<4> b1 ( string("0101") );  
   bitset<4> b2 ( string("0011") );  
   bitset<4> b3 = b1 ^ b2;  
   cout << "bitset 1: " << b1 << endl;  
   cout << "bitset 2: " << b2 << endl;  
   cout << "bitset 3: " << b3 << endl;  
}  
```  
  
```Output  
bitset 1: 0101  
bitset 2: 0011  
bitset 3: 0110  
```  
  
##  <a name="a-nameoperatorora--operatoror"></a><a name="operator_or"></a>  operator_or  
 2 つのビットセット間でビットごとの `OR` を実行します。  
  
```  
template <size_t size>  
bitset<size>  
operator|(
    const bitset<size>& left,  
    const bitset<size>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` left`  
 それぞれの要素が `OR` でビットごとに結合される&2; つのビットセットのうちの最初。  
  
 ` right`  
 それぞれの要素が `OR` でビットごとに結合される&2; つの valarray のうちの&2; つ目。  
  
### <a name="return-value"></a>戻り値  
 要素が ` left` と ` right` の該当要素で `OR` 演算を実行した結果であるビットセット。  
  
### <a name="example"></a>例  
  
```cpp  
// bitset_or.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
#include <string>  
  
using namespace std;  
  
int main()  
{  
   bitset<4> b1 ( string("0101") );  
   bitset<4> b2 ( string("0011") );  
   bitset<4> b3 = b1 | b2;  
   cout << "bitset 1: " << b1 << endl;  
   cout << "bitset 2: " << b2 << endl;  
   cout << "bitset 3: " << b3 << endl;  
}  
```  
  
```Output  
bitset 1: 0101  
bitset 2: 0011  
bitset 3: 0111  
```  
  
## <a name="see-also"></a>関連項目  
 [\<bitset>](../standard-library/bitset.md)


