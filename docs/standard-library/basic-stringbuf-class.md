---
title: "basic_stringbuf クラス |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- basic_stringbuf
- sstream/std::basic_stringbuf
- sstream/std::basic_stringbuf::allocator_type
- sstream/std::basic_stringbuf::char_type
- sstream/std::basic_stringbuf::int_type
- sstream/std::basic_stringbuf::off_type
- sstream/std::basic_stringbuf::pos_type
- sstream/std::basic_stringbuf::traits_type
- sstream/std::basic_stringbuf::overflow
- sstream/std::basic_stringbuf::pbackfail
- sstream/std::basic_stringbuf::seekoff
- sstream/std::basic_stringbuf::seekpos
- sstream/std::basic_stringbuf::str
- sstream/std::basic_stringbuf::underflow
dev_langs:
- C++
helpviewer_keywords:
- basic_stringbuf class
ms.assetid: 40c85f9e-42a5-4a65-af5c-23c8e3bf8113
caps.latest.revision: 28
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
ms.openlocfilehash: b8d19f4cd76690c52dd6a69df04240944c151f67
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="basicstringbuf-class"></a>basic_stringbuf クラス
文字の特徴がクラス `Tr` によって決まる型 `Elem` の要素の、配列オブジェクトに格納されている要素のシーケンスとの間での転送を制御するストリーム バッファーについて説明します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Elem, class Tr = char_traits<Elem>,   
    class Alloc = allocator<Elem>>  
class basic_stringbuf : public basic_streambuf<Elem, Tr>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Alloc`  
 アロケーター クラス。  
  
 `Elem`  
 文字列の基本要素の型。  
  
 `Tr`  
 文字列の基本要素に特化した文字の特徴。  
  
## <a name="remarks"></a>コメント  
 シーケンスでの変更に応じて、オブジェクトの割り当て、拡張、解放が行われます。  
  
 クラス basic_stringbuf<`Elem`, `Tr`, `Alloc`> のオブジェクトは、コンストラクターの引数 `ios_base::`[openmode](../standard-library/ios-base-class.md#openmode) のコピーをその `stringbuf` モード **mode** として格納します。  
  
-   `mode & ios_base::in` が 0 でない場合は、入力バッファーにアクセスできます。 詳細については、「[basic_streambuf クラス](../standard-library/basic-streambuf-class.md)」を参照してください。  
  
-   `mode & ios_base::out` が 0 でない場合は、出力バッファーにアクセスできます。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[basic_stringbuf](#basic_stringbuf)|`basic_stringbuf` 型のオブジェクトを構築します。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|この型は、テンプレート パラメーター `Alloc`のシノニムです。|  
|[char_type](#char_type)|型名を `Elem` テンプレート パラメーターに関連付けます。|  
|[int_type](#int_type)|`basic_filebuf` のスコープ内のこの型を、`Tr` スコープ内の同じ名前の型と同等にします。|  
|[off_type](#off_type)|`basic_filebuf` のスコープ内のこの型を、`Tr` スコープ内の同じ名前の型と同等にします。|  
|[pos_type](#pos_type)|`basic_filebuf` のスコープ内のこの型を、`Tr` スコープ内の同じ名前の型と同等にします。|  
|[traits_type](#traits_type)|型名を `Tr` テンプレート パラメーターに関連付けます。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[overflow](#overflow)|いっぱいのバッファーに新しい文字が挿入されたときに呼び出すことができる、プロテクト仮想関数。|  
|[pbackfail](#pbackfail)|プロテクト仮想メンバー関数が要素を入力バッファーに戻そうと試み、その要素を現在の要素に (次のポインターによって指されるように) します。|  
|[seekoff](#seekoff)|プロテクト仮想メンバー関数が、制御されているストリームの現在の位置を変更しようと試みます。|  
|[seekpos](#seekpos)|プロテクト仮想メンバー関数が、制御されているストリームの現在の位置を変更しようと試みます。|  
|[str](#str)|文字列バッファー内のテキストを設定または取得します。書き込み位置は変更しません。|  
|swap||  
|[underflow](#underflow)|入力ストリームから現在の要素を抽出するプロテクト仮想メンバー関数。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<sstream>  
  
 **名前空間:** std  
  
##  <a name="allocator_type"></a>  basic_stringbuf::allocator_type  
 この型は、テンプレート パラメーター `Alloc`のシノニムです。  
  
```  
typedef Alloc allocator_type;  
```  
  
##  <a name="basic_stringbuf"></a>  basic_stringbuf::basic_stringbuf  
 `basic_stringbuf` 型のオブジェクトを構築します。  
  
```  
basic_stringbuf(
    ios_base::openmode _Mode = ios_base::in | ios_base::out);

basic_stringbuf(
    const basic_string<Elem, Tr, Alloc>& str,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Mode`  
 [ios_base::openmode](../standard-library/ios-base-class.md#openmode) の列挙値のうちの 1 つ。  
  
 `str`  
 [basic_string](../standard-library/basic-string-class.md) 型のオブジェクト。  
  
### <a name="remarks"></a>コメント  
 最初のコンストラクターは、入力バッファーと出力バッファーを制御するすべてのポインターに Null ポインターを格納します。 詳細については、[basic_streambuf クラス](../standard-library/basic-streambuf-class.md)の「コメント」セクションを参照してください。 `_Mode` も stringbuf モードとして格納します。 詳細については、[basic_stringbuf クラス](../standard-library/basic-stringbuf-class.md)の「コメント」セクションを参照してください。  
  
 2 番目のコンストラクターは、文字列オブジェクト `str` によって制御されるシーケンスのコピーを割り当てます。 `_Mode & ios_base::in` が 0 以外の場合、シーケンスの先頭から読み取りを開始するように入力バッファーを設定します。 `_Mode & ios_base::out` が 0 以外の場合、シーケンスの先頭から書き込みを開始するように出力バッファーを設定します。 `_Mode` も stringbuf モードとして格納します。 詳細については、[basic_stringbuf クラス](../standard-library/basic-stringbuf-class.md)の「コメント」セクションを参照してください。  
  
##  <a name="char_type"></a>  basic_stringbuf::char_type  
 型名を **Elem** テンプレート パラメーターに関連付けます。  
  
```  
typedef Elem char_type;  
```  
  
##  <a name="int_type"></a>  basic_stringbuf::int_type  
 **Tr** スコープ内のこの型を、basic_filebuf スコープ内の同じ名前の型と同等にします。  
  
```  
typedef typename traits_type::int_type int_type;  
```  
  
##  <a name="off_type"></a>  basic_stringbuf::off_type  
 **Tr** スコープ内のこの型を、basic_filebuf スコープ内の同じ名前の型と同等にします。  
  
```  
typedef typename traits_type::off_type off_type;  
```  
  
##  <a name="overflow"></a>  basic_stringbuf::overflow  
 いっぱいのバッファーに新しい文字が挿入されたときに呼び出すことができる、プロテクト仮想関数。  
  
```  
virtual int_type overflow(int_type _Meta = traits_type::eof());
```  
  
### <a name="parameters"></a>パラメーター  
 `_Meta`  
 バッファーまたは **traits_type::eof** に挿入する文字。  
  
### <a name="return-value"></a>戻り値  
 関数が失敗すると、**traits_type::eof** が返されます。 それ以外の場合は、**traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*) を返します。  
  
### <a name="remarks"></a>コメント  
 _ *Meta* が**traits_type::**[eof](../standard-library/char-traits-struct.md#eof) と等しくない場合、プロテクト仮想メンバー関数は、要素 **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(\_ *Meta*) を出力バッファーに挿入しようとします。 これはさまざまな方法で行うことができます。  
  
-   書き込み位置が使用可能な場合は、書き込み位置に要素を格納し、出力バッファーのネクスト ポインターをインクリメントできます。  
  
-   新しい記憶域または追加の記憶域を出力バッファーに割り当てることで、書き込み位置を使用可能にすることができます。 このように出力バッファーを拡張すると、関連付けられているすべての入力バッファーも拡張されます。  
  
##  <a name="pbackfail"></a>  basic_stringbuf::pbackfail  
 プロテクト仮想メンバー関数が要素を入力バッファーに戻そうと試み、その要素を現在の要素に (次のポインターによって指されるように) します。  
  
```  
virtual int_type pbackfail(int_type _Meta = traits_type::eof());
```  
  
### <a name="parameters"></a>パラメーター  
 `_Meta`  
 バッファーまたは **traits_type::eof** に挿入する文字。  
  
### <a name="return-value"></a>戻り値  
 関数が失敗すると、**traits_type::eof** が返されます。 それ以外の場合は、**traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*) を返します。  
  
### <a name="remarks"></a>コメント  
 `_Meta` が **traits_type::**[eof](../standard-library/char-traits-struct.md#eof) と等しい場合、プッシュ バックする要素は、実質的に、現在の要素の前に既にストリームにある要素になります。 それ以外の場合、その要素が **byte** = **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(_ *Meta*) で置き換えられます。 この関数は、さまざまな方法で要素を戻すことができます。  
  
-   戻り位置が使用可能であり、格納されている要素が byte に等しい場合、入力バッファーのネクスト ポインターをデクリメントできます。  
  
-   戻り位置が使用可能で、stringbuf モードでシーケンスの変更が許可されている (**mode & ios_base::out** が 0 以外) 場合は、この関数は byte を戻り位置に格納し、入力バッファーのネクスト ポインターをデクリメントできます。  
  
##  <a name="pos_type"></a>  basic_stringbuf::pos_type  
 **Tr** スコープ内のこの型を、basic_filebuf スコープ内の同じ名前の型と同等にします。  
  
```  
typedef typename traits_type::pos_type pos_type;  
```  
  
##  <a name="seekoff"></a>  basic_stringbuf::seekoff  
 プロテクト仮想メンバー関数が、制御されているストリームの現在の位置を変更しようと試みます。  
  
```  
virtual pos_type seekoff(
    off_type _Off,  
    ios_base::seekdir _Way,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Off`  
 シークする `_Way` の相対位置。 詳細については、「[basic_stringbuf::off_type](#off_type)」を参照してください。  
  
 `_Way`  
 オフセット演算の開始位置。 有効値については、「[ios_base::seekdir](../standard-library/ios-base-class.md#seekdir)」を参照してください。  
  
 `_Mode`  
 ポインター位置のモードを指定します。 既定では、読み取り位置および書き込み位置を変更できます。 詳細については、「[ios_base::openmode](../standard-library/ios-base-class.md#openmode)」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 新しい位置または無効なストリーム位置を返します。  
  
### <a name="remarks"></a>コメント  
 クラス `basic_stringbuf<Elem, Tr, Alloc>` のオブジェクトの場合、ストリームの位置はストリーム オフセットのみで構成されます。 オフセット ゼロは、被制御シーケンスの最初の要素を指定します。  
  
 新しい位置は、次のように決定されます。  
  
-   `_Way` == `ios_base::beg` の場合、新しい位置はストリームの先頭と `_Off` です。  
  
-   `_Way` == `ios_base::cur` の場合、新しい位置は現在のストリームの位置と `_Off` です。  
  
-   `_Way` == `ios_base::end` の場合、新しい位置はストリームの最後と `_Off` です。  
  
 `_Mode & ios_base::in` が 0 以外の場合、関数は入力バッファー内の次に読み取る位置を変更します。 `_Mode & ios_base::out` が 0 以外の場合、関数は出力バッファー内の次に書き込む位置を変更します。 影響を受けるストリームの場合、そのバッファーが存在する必要があります。 配置操作を正常に完了するためには、結果のストリームの位置が被制御シーケンス内になければなりません。 関数が両方のストリームの位置に影響する場合、`_Way` は必ず `ios_base::beg` または `ios_base::end` になり、両方のストリームは同じ要素に配置されます。 それ以外の場合 (またはどちらも位置も影響を受けない場合)、配置操作は失敗します。  
  
 関数がいずれかまたは両方のストリームの位置の変更に成功すると、結果のストリームの位置が返されます。 それ以外の場合は、失敗し、無効なストリームの位置が返されます。  
  
##  <a name="seekpos"></a>  basic_stringbuf::seekpos  
 プロテクト仮想メンバー関数が、制御されているストリームの現在の位置を変更しようと試みます。  
  
```  
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Sp`  
 シークする位置。  
  
 `_Mode`  
 ポインター位置のモードを指定します。 既定では、読み取り位置および書き込み位置を変更できます。  
  
### <a name="return-value"></a>戻り値  
 関数がいずれかまたは両方のストリームの位置の変更に成功すると、結果のストリームの位置が返されます。 それ以外の場合は、失敗し、無効なストリームの位置が返されます。 ストリームの位置が無効であることを確認するには、戻り値と `pos_type(off_type(-1))` を比較します。  
  
### <a name="remarks"></a>コメント  
 クラス basic_stringbuf< **Elem**, **Tr**, `Alloc`> のオブジェクトの場合、ストリームの位置はストリーム オフセットのみで構成されます。 オフセット ゼロは、被制御シーケンスの最初の要素を指定します。 新しい位置は、_ *Sp* によって判断されます。  
  
 **mode & ios_base::in** が 0 以外の場合、関数は入力バッファー内の次に読み取る位置を変更します。 **mode & ios_base::out** が 0 以外の場合、関数は出力バッファー内の次に書き込む位置を変更します。 影響を受けるストリームの場合、そのバッファーが存在する必要があります。 配置操作を正常に完了するためには、結果のストリームの位置が被制御シーケンス内になければなりません。 それ以外の場合 (またはどちらも位置も影響を受けない場合)、配置操作は失敗します。  
  
##  <a name="str"></a>  basic_stringbuf::str  
 文字列バッファー内のテキストを設定または取得します。書き込み位置は変更しません。  
  
```  
basic_string<Elem, Tr, Alloc> str() const;
void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Newstr`  
 新しい文字列。  
  
### <a name="return-value"></a>戻り値  
 制御されたシーケンスが **\*this** によって制御されるシーケンスのコピーである、クラス [basic_string](../standard-library/basic-string-class.md)\< **Elem**, **Tr**, Alloc **>,** のオブジェクトを返します。  
  
### <a name="remarks"></a>コメント  
 最初のメンバー関数は、制御されたシーケンスが **\*this** によって制御されるシーケンスのコピーである、クラス basic_string< **Elem**, **Tr**, `Alloc`> のオブジェクトを返します。 コピーされるシーケンスは、stored stringbuf モードによって異なります。  
  
-   **mode & ios_base::out** が 0 以外で、出力バッファーが存在する場合、シーケンスは全体の出力バッファー (`pbase` で始まる [epptr](../standard-library/basic-streambuf-class.md#epptr) - [pbase](../standard-library/basic-streambuf-class.md#pbase) 要素) になります。  
  
-   **mode & ios_base::in** が 0 以外で、入力バッファーが存在する場合、シーケンスは全体の入力バッファー (`eback` で始まる [egptr](../standard-library/basic-streambuf-class.md#egptr) - [eback](../standard-library/basic-streambuf-class.md#eback) 要素) になります。  
  
-   それ以外の場合、コピーされたシーケンスは空になります。  
  
 2 番目のメンバー関数は、**\*this** によって現在制御されている任意のシーケンスの割り当てを解除します。 その後、`_Newstr` によって制御されるシーケンスのコピーを割り当てます。 **mode & ios_base::in** が 0 以外の場合、シーケンスの先頭から読み取りを開始するように入力バッファーを設定します。 **mode & ios_base::out** が 0 以外の場合、シーケンスの先頭から書き込みを開始するように出力バッファーを設定します。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_stringbuf_str.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <sstream>  
  
using namespace std;  
  
int main( )   
{  
   basic_string<char> i( "test" );  
   stringstream ss;  
  
   ss.rdbuf( )->str( i );  
   cout << ss.str( ) << endl;  
  
   ss << "z";  
   cout << ss.str( ) << endl;  
  
   ss.rdbuf( )->str( "be" );  
   cout << ss.str( ) << endl;  
}  
```  
  
```Output  
test  
zest  
be  
```  
  
##  <a name="traits_type"></a>  basic_stringbuf::traits_type  
 型名を **Tr** テンプレート パラメーターに関連付けます。  
  
```  
typedef Tr traits_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター **Tr** のシノニムです。  
  
##  <a name="underflow"></a>  basic_stringbuf::underflow  
 入力ストリームから現在の要素を抽出するプロテクト仮想関数。  
  
```  
virtual int_type underflow();
```  
  
### <a name="return-value"></a>戻り値  
 関数が失敗すると、**traits_type::**[eof](../standard-library/char-traits-struct.md#eof) が返されます。 それ以外の場合、変換された入力ストリームの現在の要素が返されます。  
  
### <a name="remarks"></a>コメント  
 プロテクト仮想メンバー関数は、現在の要素 **byte** を入力バッファーから抽出しようとし、現在のストリームの位置を進め、**traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( **byte**) として要素を返します。 これは 1 つの方法で実行可能です。読み取り位置が使用可能な場合は、読み取り位置に格納されている要素として **byte** を使用し、入力バッファーの次のポインターを進めます。  
  
##  <a name="swap"></a>  basic_streambuf::swap  
 この文字列バッファーと別の文字列バッファーの内容を交換します。  
  
```  
void basic_stringbuf<T>::swap(basic_stringbuf& other)  
```  
  
### <a name="parameters"></a>パラメーター  
 `other`  
 この basic_stringbuf により内容が交換される basic_stringbuf 。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="op_eq"></a>  basic_stringbuf::operator=  
 演算子の右側にある basic_stringbuf の内容を、左側の basic_stringbuf に割り当てます。  
  
```  
basic_stringbuf& basic_stringbuf:: operator=(const basic_stringbuf& other)  
```  
  
### <a name="parameters"></a>パラメーター  
 `other`  
 内容が演算子の左側にある stringbuf に割り当てられる、ロケールの特徴を含む basic_stringbuf。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../standard-library/iostream-programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)


