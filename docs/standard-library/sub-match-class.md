---
title: "sub_match クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sub_match
- regex/std::sub_match
- regex/std::sub_match::matched
- regex/std::sub_match::compare
- regex/std::sub_match::length
- regex/std::sub_match::str
- regex/std::sub_match::difference_type
- regex/std::sub_match::iterator
- regex/std::sub_match::value_type
dev_langs:
- C++
helpviewer_keywords:
- sub_match class
ms.assetid: 804e2b9e-d16a-4c4c-ac60-024e0b2dd0e8
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 12d12497fa96d7cf4185ad3664908a56be1078c9
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="submatch-class"></a>sub_match クラス
サブマッチを記述します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class BidIt>  
class sub_match  
 : public std::pair<BidIt, BidIt> {  
public:  
    bool matched;  
    int compare(const sub_match& right) const;  
    int compare(const basic_string<value_type>& right) const;   
    int compare(const value_type *right) const;   
    difference_type length() const;  
    operator basic_string<value_type>() const;
    basic_string<value_type> str() const;
  
    // typedefs
    typedef typename iterator_traits<BidIt>::value_type value_type;  
    typedef typename iterator_traits<BidIt>::difference_type difference_type;  
    typedef BidIt iterator;  
 };  
```  
  
#### <a name="parameters"></a>パラメーター  
 `BidIt`  
 サブマッチ用の反復子の型。  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスへの呼び出しで、キャプチャ グループに一致する文字のシーケンスを指定するオブジェクトを記述する[regex_match](../standard-library/regex-functions.md#regex_match)または[regex_search](../standard-library/regex-functions.md#regex_search)です。 [match_results Class](../standard-library/match-results-class.md) 型のオブジェクトは、検索に使用された正規表現内のキャプチャ グループごとに 1 つずつ、これらのオブジェクトの配列を保持します。  
  
 キャプチャ グループがオブジェクトのデータ メンバーと一致しなかった場合は、 `matched` が false を保持し、2 つの反復子の `first` と `second` (ベース `std::pair`から継承) が等しくなります。 キャプチャ グループが一致した場合は、 `matched` が true を保持し、反復子 `first` がキャプチャ グループと一致したターゲット シーケンスの最初の文字を指し、反復子 `second` がキャプチャ グループと一致したターゲット シーケンスの最後の文字の 1 つ先の位置を指します。 長さ 0 の一致の場合は、メンバー `matched` が true を保持し、2 つの反復子が等しくなり、両方が一致した位置を指します。  
  
 長さ 0 の一致は、キャプチャ グループが 1 つのアサーションのみまたは 0 回の繰り返しが許可される 1 つの繰り返しのみで構成されている場合に発生します。 例:  
  
 "^" は、ターゲット シーケンス "a" と一致します。キャプチャ グループ 0 に対応する `sub_match` オブジェクトは、両方がシーケンスの最初の文字を指す反復子を保持します。  
  
 "b(a*)b" は、ターゲット シーケンス "bb" と一致します。キャプチャ グループ 1 に対応する `sub_match` オブジェクトは、両方がシーケンスの 2 つ目の文字を指す反復子を保持します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<regex>  
  
 **名前空間:** std  
  
##  <a name="compare"></a>  sub_match::compare  
 サブマッチをシーケンスと比較します。  
  
```  
int compare(const sub_match& right) const;
int compare(const basic_string<value_type>& str) const;
int compare(const value_type *ptr) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 比較するサブマッチ。  
  
 `str`  
 比較対象の文字列。  
  
 `ptr`  
 null で終わる比較対象のシーケンス。  
  
### <a name="remarks"></a>コメント  
 1 つ目のメンバー関数は、一致するシーケンス `[first, second)` と一致したシーケンス `[right.first, right.second)` とを比較します。 2 つ目のメンバー関数は、一致するシーケンス `[first, second)` と文字シーケンス `[right.begin(), right.end())` とを比較します。 3 つ目のメンバー関数は、一致するシーケンス `[first, second)` と文字シーケンス `[right, right + std::char_traits<value_type>::length(right))` とを比較します。  
  
 各関数から返される値は次のとおりです。  
  
 負の値。一致するシーケンス内の最初に異なる値が、オペランド シーケンス内の対応する要素よりも小さい場合 (`std::char_traits<value_type>::compare` で判断)、または両者のプレフィックスが共通していても、ターゲット シーケンスの方が長い場合は、負の値が返されます。  
  
 ゼロ。両者の要素がすべて等しく、長さも同じである場合は、ゼロが返されます。  
  
 正の値。それ以外の場合は、正の値が返されます。  
  
### <a name="example"></a>例  
  
```cpp  
// std__regex__sub_match_compare.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "matched == " << std::boolalpha   
        << sub.matched << std::endl;   
    std::cout << "length == " << sub.length() << std::endl;   
  
    std::csub_match::difference_type dif = std::distance(sub.first, sub.second);   
    std::cout << "difference == " << dif << std::endl;   
  
    std::csub_match::iterator first = sub.first;   
    std::csub_match::iterator last = sub.second;   
    std::cout << "range == " << std::string(first, last)   
        << std::endl;   
    std::cout << "string == " << sub << std::endl;   
  
    std::csub_match::value_type *ptr = "aab";   
    std::cout << "compare(\"aab\") == "   
        << sub.compare(ptr) << std::endl;   
    std::cout << "compare(string) == "   
        << sub.compare(std::string("AAA")) << std::endl;   
    std::cout << "compare(sub) == "   
        << sub.compare(sub) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
matched == true  
length == 3  
difference == 3  
range == aaa  
string == aaa  
compare("aab") == -1  
compare(string) == 1  
compare(sub) == 0  
```  
  
##  <a name="difference_type"></a>  sub_match::difference_type  
 反復子の差の型です。  
  
```  
typedef typename iterator_traits<BidIt>::difference_type difference_type;  
```  
  
### <a name="remarks"></a>コメント  
 typedef は、`iterator_traits<BidIt>::difference_type` の同意語です。  
  
### <a name="example"></a>例  
  
```cpp  
// std__regex__sub_match_difference_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "matched == " << std::boolalpha   
        << sub.matched << std::endl;   
    std::cout << "length == " << sub.length() << std::endl;   
  
    std::csub_match::difference_type dif = std::distance(sub.first, sub.second);   
    std::cout << "difference == " << dif << std::endl;   
  
    std::csub_match::iterator first = sub.first;   
    std::csub_match::iterator last = sub.second;   
    std::cout << "range == " << std::string(first, last)   
        << std::endl;   
    std::cout << "string == " << sub << std::endl;   
  
    std::csub_match::value_type *ptr = "aab";   
    std::cout << "compare(\"aab\") == "   
        << sub.compare(ptr) << std::endl;   
    std::cout << "compare(string) == "   
        << sub.compare(std::string("AAA")) << std::endl;   
    std::cout << "compare(sub) == "   
        << sub.compare(sub) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
matched == true  
length == 3  
difference == 3  
range == aaa  
string == aaa  
compare("aab") == -1  
compare(string) == 1  
compare(sub) == 0  
```  
  
##  <a name="iterator"></a>  sub_match::iterator  
 反復子の型。  
  
```  
typedef BidIt iterator;  
```  
  
### <a name="remarks"></a>コメント  
 この typedef は、テンプレート型引数 `Bidit` のシノニムです。  
  
### <a name="example"></a>例  
  
```cpp  
// std__regex__sub_match_iterator.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "matched == " << std::boolalpha   
        << sub.matched << std::endl;   
    std::cout << "length == " << sub.length() << std::endl;   
  
    std::csub_match::difference_type dif = std::distance(sub.first, sub.second);   
    std::cout << "difference == " << dif << std::endl;   
  
    std::csub_match::iterator first = sub.first;   
    std::csub_match::iterator last = sub.second;   
    std::cout << "range == " << std::string(first, last)   
        << std::endl;   
    std::cout << "string == " << sub << std::endl;   
  
    std::csub_match::value_type *ptr = "aab";   
    std::cout << "compare(\"aab\") == "   
        << sub.compare(ptr) << std::endl;   
    std::cout << "compare(string) == "   
        << sub.compare(std::string("AAA")) << std::endl;   
    std::cout << "compare(sub) == "   
        << sub.compare(sub) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
matched == true  
length == 3  
difference == 3  
range == aaa  
string == aaa  
compare("aab") == -1  
compare(string) == 1  
compare(sub) == 0  
```  
  
##  <a name="length"></a>  sub_match::length  
 サブマッチの長さを返します。  
  
```  
difference_type length() const;
```  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、一致するシーケンスの長さを返します。または、一致するシーケンスが存在しない場合、0 を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// std__regex__sub_match_length.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "matched == " << std::boolalpha   
        << sub.matched << std::endl;   
    std::cout << "length == " << sub.length() << std::endl;   
  
    std::csub_match::difference_type dif = std::distance(sub.first, sub.second);   
    std::cout << "difference == " << dif << std::endl;   
  
    std::csub_match::iterator first = sub.first;   
    std::csub_match::iterator last = sub.second;   
    std::cout << "range == " << std::string(first, last)   
        << std::endl;   
    std::cout << "string == " << sub << std::endl;   
  
    std::csub_match::value_type *ptr = "aab";   
    std::cout << "compare(\"aab\") == "   
        << sub.compare(ptr) << std::endl;   
    std::cout << "compare(string) == "   
        << sub.compare(std::string("AAA")) << std::endl;   
    std::cout << "compare(sub) == "   
        << sub.compare(sub) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
matched == true  
length == 3  
difference == 3  
range == aaa  
string == aaa  
compare("aab") == -1  
compare(string) == 1  
compare(sub) == 0  
```  
  
##  <a name="matched"></a>  sub_match::matched  
 一致が成功したかどうかを示します。  
  
```  
bool matched;  
```  
  
### <a name="remarks"></a>コメント  
 このメンバーは、 `true` に関連付けられているキャプチャ グループが、正規表現の一致に含まれていた場合にのみ、 `*this` を保持します。  
  
### <a name="example"></a>例  
  
```cpp  
// std__regex__sub_match_matched.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "matched == " << std::boolalpha   
        << sub.matched << std::endl;   
    std::cout << "length == " << sub.length() << std::endl;   
  
    std::csub_match::difference_type dif = std::distance(sub.first, sub.second);   
    std::cout << "difference == " << dif << std::endl;   
  
    std::csub_match::iterator first = sub.first;   
    std::csub_match::iterator last = sub.second;   
    std::cout << "range == " << std::string(first, last)   
        << std::endl;   
    std::cout << "string == " << sub << std::endl;   
  
    std::csub_match::value_type *ptr = "aab";   
    std::cout << "compare(\"aab\") == "   
        << sub.compare(ptr) << std::endl;   
    std::cout << "compare(string) == "   
        << sub.compare(std::string("AAA")) << std::endl;   
    std::cout << "compare(sub) == "   
        << sub.compare(sub) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
matched == true  
length == 3  
difference == 3  
range == aaa  
string == aaa  
compare("aab") == -1  
compare(string) == 1  
compare(sub) == 0  
```  
  
##  <a name="op_basic_string_lt_value_type_gt"></a>  sub_match::operator basic_string&lt;value_type&gt;  
 サブマッチを文字列にキャストします。  
  
```  
operator basic_string<value_type>() const;
```  
  
### <a name="remarks"></a>コメント  
 このメンバー演算子は、 `str()`を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// std__regex__sub_match_operator_str.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "matched == " << std::boolalpha   
        << sub.matched << std::endl;   
    std::cout << "length == " << sub.length() << std::endl;   
  
    std::csub_match::difference_type dif = std::distance(sub.first, sub.second);   
    std::cout << "difference == " << dif << std::endl;   
  
    std::csub_match::iterator first = sub.first;   
    std::csub_match::iterator last = sub.second;   
    std::cout << "range == " << std::string(first, last)   
        << std::endl;   
    std::cout << "string == " << sub << std::endl;   
  
    std::csub_match::value_type *ptr = "aab";   
    std::cout << "compare(\"aab\") == "   
        << sub.compare(ptr) << std::endl;   
    std::cout << "compare(string) == "   
        << sub.compare(std::string("AAA")) << std::endl;   
    std::cout << "compare(sub) == "   
        << sub.compare(sub) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
matched == true  
length == 3  
difference == 3  
range == aaa  
string == aaa  
compare("aab") == -1  
compare(string) == 1  
compare(sub) == 0  
```  
  
##  <a name="str"></a>  sub_match::str  
 サブマッチを文字列に変換します。  
  
```  
basic_string<value_type> str() const;
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、`basic_string<value_type>(first, second)` を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// std__regex__sub_match_str.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "matched == " << std::boolalpha   
        << sub.matched << std::endl;   
    std::cout << "length == " << sub.length() << std::endl;   
  
    std::csub_match::difference_type dif = std::distance(sub.first, sub.second);   
    std::cout << "difference == " << dif << std::endl;   
  
    std::csub_match::iterator first = sub.first;   
    std::csub_match::iterator last = sub.second;   
    std::cout << "range == " << std::string(first, last)   
        << std::endl;   
    std::cout << "string == " << sub << std::endl;   
  
    std::csub_match::value_type *ptr = "aab";   
    std::cout << "compare(\"aab\") == "   
        << sub.compare(ptr) << std::endl;   
    std::cout << "compare(string) == "   
        << sub.compare(std::string("AAA")) << std::endl;   
    std::cout << "compare(sub) == "   
        << sub.compare(sub) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
matched == true  
length == 3  
difference == 3  
range == aaa  
string == aaa  
compare("aab") == -1  
compare(string) == 1  
compare(sub) == 0  
```  
  
##  <a name="value_type"></a>  sub_match::value_type  
 要素の型。  
  
```  
typedef typename iterator_traits<BidIt>::value_type value_type;  
```  
  
### <a name="remarks"></a>コメント  
 typedef は、`iterator_traits<BidIt>::value_type` の同意語です。  
  
### <a name="example"></a>例  
  
```cpp  
// std__regex__sub_match_value_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::csub_match sub = mr[1];   
    std::cout << "matched == " << std::boolalpha   
        << sub.matched << std::endl;   
    std::cout << "length == " << sub.length() << std::endl;   
  
    std::csub_match::difference_type dif = std::distance(sub.first, sub.second);   
    std::cout << "difference == " << dif << std::endl;   
  
    std::csub_match::iterator first = sub.first;   
    std::csub_match::iterator last = sub.second;   
    std::cout << "range == " << std::string(first, last)   
        << std::endl;   
    std::cout << "string == " << sub << std::endl;   
  
    std::csub_match::value_type *ptr = "aab";   
    std::cout << "compare(\"aab\") == "   
        << sub.compare(ptr) << std::endl;   
    std::cout << "compare(string) == "   
        << sub.compare(std::string("AAA")) << std::endl;   
    std::cout << "compare(sub) == "   
        << sub.compare(sub) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
matched == true  
length == 3  
difference == 3  
range == aaa  
string == aaa  
compare("aab") == -1  
compare(string) == 1  
compare(sub) == 0  
```  
  
## <a name="see-also"></a>関連項目  
 [\<regex>](../standard-library/regex.md)   
 [sub_match](../standard-library/sub-match-class.md)

