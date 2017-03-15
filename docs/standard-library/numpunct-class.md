---
title: "numpunct クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xlocnum/std::numpunct"
  - "std::numpunct"
  - "numpunct"
  - "std.numpunct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "numpunct クラス"
ms.assetid: 73fb93cc-ac11-4c98-987c-bfa6267df596
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# numpunct クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

数値とブール式の書式設定および区切りに関する情報を表すために使用される、`CharType` 型のシーケンスを表すロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス。  
  
## <a name="syntax"></a>構文  
  
```  
template <class CharType>  
class numpunct : public locale::facet;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `CharType`  
 ロケールの文字をエンコードするためにプログラム内で使用される型。  
  
## <a name="remarks"></a>コメント  
 すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。 一意な正の値を格納する、格納されている値にアクセスする最初の試行 **id。**  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[numpunct](#numpunct__numpunct)|`numpunct` 型のオブジェクトのコンストラクター。|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[char_type](#numpunct__char_type)|ロケールによって使用される文字を表すために使用される型。|  
|[string_type](#numpunct__string_type)|`CharType` 型の文字を格納する文字列を表す型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[decimal_point](#numpunct__decimal_point)|小数点として使用するロケール固有の要素を返します。|  
|[do_decimal_point](#numpunct__do_decimal_point)|小数点として使用するロケール固有の要素を返すために呼び出されるプロテクト仮想メンバー関数。|  
|[do_falsename](#numpunct__do_falsename)|`false` 値のテキスト表現として使用する文字列を返すために呼び出されるプロテクト仮想メンバー関数。|  
|[do_grouping](#numpunct__do_grouping)|小数点の左側の数字をグループ化する方法を決定するロケール固有の規則を返すために呼び出されるプロテクト仮想メンバー関数。|  
|[do_thousands_sep](#numpunct__do_thousands_sep)|桁区切り記号として使用するロケール固有の要素を返すために呼び出されるプロテクト仮想メンバー関数。|  
|[do_truename](#numpunct__do_truename)|`true` 値のテキスト表現として使用する文字列を返すために呼び出されるプロテクト仮想メンバー関数。|  
|[falsename](#numpunct__falsename)|`false` 値のテキスト表現として使用する文字列を返します。|  
|[グループ化](#numpunct__grouping)|小数点の左側の数字をグループ化する方法を決定するロケール固有の規則を返します。|  
|[thousands_sep](#numpunct__thousands_sep)|桁区切り記号として使用するロケール固有の要素を返します。|  
|[truename](#numpunct__truename)|`true` 値のテキスト表現として使用する文字列を返します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \< ロケール>  
  
 **名前空間:** std  
  
##  <a name="a-namenumpunctchartypea-numpunctchartype"></a><a name="numpunct__char_type"></a>  numpunct::char_type  
 ロケールによって使用される文字を表すために使用される型。  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>コメント  
 型は、テンプレート パラメーターのシノニム **CharType します。**  
  
##  <a name="a-namenumpunctdecimalpointa-numpunctdecimalpoint"></a><a name="numpunct__decimal_point"></a>  numpunct::decimal_point  
 小数点として使用するロケール固有の要素を返します。  
  
```  
CharType decimal_point() const;
```  
  
### <a name="return-value"></a>戻り値  
 小数点として使用する場合は、ロケール固有の要素  
  
### <a name="remarks"></a>コメント  
 メンバー関数を返します [do_decimal_point](#numpunct__do_decimal_point)します。  
  
### <a name="example"></a>例  
  
```  
// numpunct_decimal_point.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const numpunct <char> &npunct =   
   use_facet <numpunct <char> >( loc);  
   cout << loc.name( ) << " decimal point "<<   
   npunct.decimal_point( ) << endl;  
   cout << loc.name( ) << " thousands separator "   
   << npunct.thousands_sep( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 decimal point ,  
German_Germany.1252 thousands separator .  
```  
  
##  <a name="a-namenumpunctdodecimalpointa-numpunctdodecimalpoint"></a><a name="numpunct__do_decimal_point"></a>  numpunct::do_decimal_point  
 小数点として使用するロケール固有の要素を返すために呼び出されるプロテクト仮想メンバー関数。  
  
```  
virtual CharType do_decimal_point() const;
```  
  
### <a name="return-value"></a>戻り値  
 小数点として使用する場合は、ロケール固有の要素  
  
### <a name="example"></a>例  
  例を参照してください [decimal_point](#numpunct__decimal_point), が仮想メンバー関数ある場合、 `decimal_point`です。  
  
##  <a name="a-namenumpunctdofalsenamea-numpunctdofalsename"></a><a name="numpunct__do_falsename"></a>  numpunct::do_falsename  
 プロテクト仮想メンバー関数が値のテキスト表現として使用するためのシーケンスを返す **false**します。  
  
```  
virtual string_type do_falsename() const;
```  
  
### <a name="return-value"></a>戻り値  
 値のテキスト表現として使用するシーケンスを含む文字列 **false**します。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、文字列値を表すためには、"false"を返します。 **false** すべてのロケールにします。  
  
### <a name="example"></a>例  
  例を参照してください [falsename](#numpunct__falsename), が仮想メンバー関数ある場合、 `falsename`です。  
  
##  <a name="a-namenumpunctdogroupinga-numpunctdogrouping"></a><a name="numpunct__do_grouping"></a>  numpunct::do_grouping  
 小数点の左側の数字をグループ化する方法を決定するロケール固有の規則を返すために呼び出されるプロテクト仮想メンバー関数。  
  
```  
virtual string do_grouping() const;
```  
  
### <a name="return-value"></a>戻り値  
 数字が小数点の左側にグループ化方法を決定する場合は、ロケール固有の規則  
  
### <a name="remarks"></a>コメント  
 このプロテクト仮想メンバー関数は、小数点の左側の数字をグループ化する方法を決定するロケール固有の規則を返します。 同じですが、エンコーディング **lconv::grouping**します。  
  
### <a name="example"></a>例  
  例を参照してください [をグループ化](#numpunct__grouping), が仮想メンバー関数ある場合、 **をグループ化**します。  
  
##  <a name="a-namenumpunctdothousandssepa-numpunctdothousandssep"></a><a name="numpunct__do_thousands_sep"></a>  numpunct::do_thousands_sep  
 桁区切り記号として使用するロケール固有の要素を返すために呼び出されるプロテクト仮想メンバー関数。  
  
```  
virtual CharType do_thousands_sep() const;
```  
  
### <a name="return-value"></a>戻り値  
 桁区切り記号として使用するロケール固有の要素を返します。  
  
### <a name="remarks"></a>コメント  
 プロテクト仮想メンバー関数は、型のロケール固有の要素を返す **CharType** 、小数点の左側の桁区切り記号として使用します。  
  
### <a name="example"></a>例  
  例を参照してください [thousands_sep](#numpunct__thousands_sep), が仮想メンバー関数ある場合、 `thousands_sep`です。  
  
##  <a name="a-namenumpunctdotruenamea-numpunctdotruename"></a><a name="numpunct__do_truename"></a>  numpunct::do_truename  
 プロテクト仮想メンバー関数の値のテキスト表現として使用する文字列を返すために呼び出される **true**します。  
  
```  
virtual string_type do_truename() const;
```  
  
### <a name="remarks"></a>コメント  
 値のテキスト表現として使用する文字列 **true**します。  
  
 すべてのロケールには、文字列値を表すためには、"true"が返されます。 **true**します。  
  
### <a name="example"></a>例  
  例を参照してください [truename](#numpunct__truename), が仮想メンバー関数ある場合、 `truename`です。  
  
##  <a name="a-namenumpunctfalsenamea-numpunctfalsename"></a><a name="numpunct__falsename"></a>  numpunct::falsename  
 値のテキスト表現として使用する文字列を返す **false**します。  
  
```  
string_type falsename() const;
```  
  
### <a name="return-value"></a>戻り値  
 シーケンスを含む文字列 **CharType**値のテキスト表現として使用する s **false**します。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、文字列値を表すためには、"false"を返します。 **false** すべてのロケールにします。  
  
 メンバー関数を返します [do_falsename](#numpunct__do_falsename)します。  
  
### <a name="example"></a>例  
  
```  
// numpunct_falsename.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "English" );  
  
   const numpunct <char> &npunct = use_facet <numpunct <char> >( loc );  
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;  
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;  
  
   locale loc2( "French" );  
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >(loc2);  
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;  
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;  
}  
```  
  
```Output  
English_United States.1252 truename true  
English_United States.1252 falsename false  
French_France.1252 truename true  
French_France.1252 falsename false  
```  
  
##  <a name="a-namenumpunctgroupinga-numpunctgrouping"></a><a name="numpunct__grouping"></a>  numpunct::grouping  
 小数点の左側の数字をグループ化する方法を決定するロケール固有の規則を返します。  
  
```  
string grouping() const;
```  
  
### <a name="return-value"></a>戻り値  
 数字が小数点の左側にグループ化方法を決定する場合は、ロケール固有の規則  
  
### <a name="remarks"></a>コメント  
 メンバー関数を返します [do_grouping](#numpunct__do_grouping)します。  
  
### <a name="example"></a>例  
  
```  
// numpunct_grouping.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany");  
  
   const numpunct <char> &npunct =   
       use_facet < numpunct <char> >( loc );  
   for (unsigned int i = 0; i < npunct.grouping( ).length( ); i++)  
   {  
      cout << loc.name( ) << " international grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(npunct.grouping ( )[i])   
           << endl;  
   }  
}  
```  
  
```Output  
German_Germany.1252 international grouping:  
 the 0th group to the left of the radix character is of size 3  
```  
  
##  <a name="a-namenumpunctnumpuncta-numpunctnumpunct"></a><a name="numpunct__numpunct"></a>  numpunct::numpunct  
 `numpunct` 型のオブジェクトのコンストラクター。  
  
```  
explicit numpunct(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Refs`  
 オブジェクトのメモリ管理の種類を指定するために使用する整数値です。  
  
### <a name="remarks"></a>コメント  
 ような値、 `_Refs` パラメーターとその重要性は。  
  
-   0: オブジェクトの有効期間はそれを含むロケールで管理します。  
  
-   1: オブジェクトの有効期間を手動で管理する必要があります。  
  
-   \> 0: これらの値が定義されていません。  
  
 直接例することはできません、デストラクターが保護されているためです。  
  
 コンス トラクターは、そのベース オブジェクトと **ロケール::**[ファセット](../standard-library/locale-class.md#facet_class)( `_Refs`)。  
  
##  <a name="a-namenumpunctstringtypea-numpunctstringtype"></a><a name="numpunct__string_type"></a>  numpunct::string_type  
 型の文字を含む文字列を表す型 **CharType**します。  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート クラスの特殊化を表します。 [basic_string](../standard-library/basic-string-class.md) オブジェクトを持つには、区切り文字のシーケンスのコピーを格納します。  
  
##  <a name="a-namenumpunctthousandssepa-numpunctthousandssep"></a><a name="numpunct__thousands_sep"></a>  numpunct::thousands_sep  
 桁区切り記号として使用するロケール固有の要素を返します。  
  
```  
CharType thousands_sep() const;
```  
  
### <a name="return-value"></a>戻り値  
 1000 単位として使用するロケール固有の要素の区切り記号。  
  
### <a name="remarks"></a>コメント  
 メンバー関数を返します [do_thousands_sep](#numpunct__do_thousands_sep)します。  
  
### <a name="example"></a>例  
  
```  
// numpunct_thou_sep.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const numpunct <char> &npunct =   
   use_facet < numpunct < char > >( loc );  
   cout << loc.name( ) << " decimal point "<<   
   npunct.decimal_point( ) << endl;  
   cout << loc.name( ) << " thousands separator "   
   << npunct.thousands_sep( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 decimal point ,  
German_Germany.1252 thousands separator .  
```  
  
##  <a name="a-namenumpuncttruenamea-numpuncttruename"></a><a name="numpunct__truename"></a>  numpunct::truename  
 値のテキスト表現として使用する文字列を返す **true**します。  
  
```  
string_type falsename() const;
```  
  
### <a name="return-value"></a>戻り値  
 値のテキスト表現として使用する文字列 **true**します。  
  
### <a name="remarks"></a>コメント  
 メンバー関数を返します [do_truename](#numpunct__do_truename)します。  
  
 すべてのロケールには、文字列値を表すためには、"true"が返されます。 **true**します。  
  
### <a name="example"></a>例  
  
```  
// numpunct_truename.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "English" );  
  
   const numpunct < char> &npunct = use_facet <numpunct <char> >( loc );  
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;  
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;  
  
   locale loc2("French");  
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >( loc2 );  
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;  
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;  
}  
```  
  
```Output  
English_United States.1252 truename true  
English_United States.1252 falsename false  
French_France.1252 truename true  
French_France.1252 falsename false  
```  
  
## <a name="see-also"></a>「  
 [\< ロケール>](../standard-library/locale.md)   
 [facet クラス](../standard-library/locale-class.md#facet_class)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

