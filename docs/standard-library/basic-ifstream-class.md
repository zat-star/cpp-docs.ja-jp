---
title: "basic_ifstream クラス |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- basic_ifstream
- fstream/std::basic_ifstream
- fstream/std::basic_ifstream::close
- fstream/std::basic_ifstream::is_open
- fstream/std::basic_ifstream::open
- fstream/std::basic_ifstream::rdbuf
- fstream/std::basic_ifstream::swap
dev_langs:
- C++
helpviewer_keywords:
- basic_ifstream class
ms.assetid: 366cd9a7-efc4-4b7f-ba10-c8271e47ffcf
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.openlocfilehash: e1027f916c8ab40a8e1040c3e1da47e5c15a3ae1
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="basicifstream-class"></a>basic_ifstream クラス
`Elem` 型の要素を含む [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> クラスのストリーム バッファーからの要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを記述します。この型の特性は、`Tr` クラスによって決定されます。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_ifstream : public basic_istream<Elem, Tr>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Elem`  
 ファイル バッファーの基本要素。  
  
 `Tr`  
 ファイル バッファーの基本要素の特徴 (通常は `char_traits`< `Elem`>)。  
  
## <a name="remarks"></a>コメント  
 このオブジェクトは、クラス `basic_filebuf`< `Elem`, `Tr`> のオブジェクトを格納します。  
  
## <a name="example"></a>例  
 次の例は、ファイルからテキストを読み取る方法を示しています。  
  
```  
// basic_ifstream_class.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ifstream ifs("basic_ifstream_class.txt");  
    if (!ifs.bad())  
    {  
        // Dump the contents of the file to cout.  
        cout << ifs.rdbuf();  
        ifs.close();  
    }  
}  
```  
  
## <a name="input-basicifstreamclasstxt"></a>入力: basic_ifstream_class.txt  
  
```  
This is the contents of basic_ifstream_class.txt.  
```  
  
## <a name="output"></a>出力  
  
```  
This is the contents of basic_ifstream_class.txt.  
```  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[basic_ifstream](#basic_ifstream)|`basic_ifstream` オブジェクトの新しいインスタンスを初期化します。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[close](#close)|ファイルを閉じます。|  
|[is_open](#is_open)|ファイルが開いているかどうかを判断します。|  
|[open](#open)|ファイルを開きます。|  
|[rdbuf](#rdbuf)|格納されたストリーム バッファーのアドレスを返します。|  
|[swap](#swap)|この `basic_ifstream` の内容を、指定された `basic_ifstream` の内容と交換します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator=](#op_eq)|このストリーム オブジェクトの内容を割り当てます。 これは、`rvalue` が関係する移動代入で、コピーを残しません。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<fstream>  
  
 **名前空間:** std  
  
##  <a name="basic_ifstream"></a>  basic_ifstream::basic_ifstream  
 `basic_ifstream` 型のオブジェクトを構築します。  
  
```  
basic_ifstream();

explicit basic_ifstream(
    const char* _Filename,  
    ios_base::openmode _Mode = ios_base::in,  
    int _Prot = (int)ios_base::_Openprot);

explicit basic_ifstream(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode = ios_base::in,  
    int _Prot = (int)ios_base::_Openprot);

basic_ifstream(basic_ifstream&& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Filename`  
 開くファイルの名前。  
  
 `_Mode`  
 [ios_base::openmode](../standard-library/ios-base-class.md#openmode) の列挙値のうちの 1 つ。  
  
 `_Prot`  
 [_fsopen、_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md) の `shflag` パラメーターと同等の既定のファイル保護。  
  
### <a name="remarks"></a>コメント  
 最初のコンストラクターは、[basic_istream](../standard-library/basic-istream-class.md)( `sb`) を呼び出すことで基底クラスを初期化します。ここで、`sb` はクラス [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> の格納されているオブジェクトです。 また、`basic_filebuf`< `Elem`, `Tr`> を呼び出すことで `sb` の初期化もします。  
  
 2 番目と 3 番目のコンストラクターは、`basic_istream`( `sb`) を呼び出すことで基底クラスを初期化します。 また、`sb` も、[basic_filebuf](../standard-library/basic-filebuf-class.md#basic_filebuf)< `Elem`, `Tr`> を呼び出した後に `sb`. [open](../standard-library/basic-filebuf-class.md#open)( `_Filename`, `_Mode` &#124; `ios_base::in`) を呼び出すことで初期化します。 後者の関数が Null ポインターを返す場合、コンストラクターは **setstate**( `failbit`). を呼び出します。  
  
 4 番目のコンストラクターは、右辺値参照として扱われる `right` のコンテンツでオブジェクトを初期化します。  
  
### <a name="example"></a>例  
  次の例は、ファイルからテキストを読み取る方法を示しています。 ファイルを作成するには、[basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) の例を参照してください。  
  
```  
// basic_ifstream_ctor.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ifstream ifs("basic_ifstream_ctor.txt");  
    if (!ifs.bad())  
    {  
        // Dump the contents of the file to cout.  
        cout << ifs.rdbuf();  
        ifs.close();  
    }  
}  
```  
  
##  <a name="close"></a>  basic_ifstream::close  
 ファイルを閉じます。  
  
```  
void close();
```  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、[rdbuf](#rdbuf) **->** [close](../standard-library/basic-filebuf-class.md#close) を呼び出します。  
  
### <a name="example"></a>例  
  **close** の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。  
  
##  <a name="is_open"></a>  basic_ifstream::is_open  
 ファイルが開いているかどうかを判断します。  
  
```  
bool is_open() const;
```  
  
### <a name="return-value"></a>戻り値  
 ファイルが開いている場合は **true**、それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、[rdbuf](#rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#is_open) を返します。  
  
### <a name="example"></a>例  
  `is_open` の使用例については、「[basic_filebuf::is_open](../standard-library/basic-filebuf-class.md#is_open)」を参照してください。  
  
##  <a name="open"></a>  basic_ifstream::open  
 ファイルを開きます。  
  
```  
void open(
    const char* _Filename,  
    ios_base::openmode _Mode = ios_base::in,  
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,  
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode = ios_base::in,  
    int _Prot = (int)ios_base::_Openprot);

void open(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Filename`  
 開くファイルの名前。  
  
 `_Mode`  
 [ios_base::openmode](../standard-library/ios-base-class.md#openmode) の列挙値のうちの 1 つ。  
  
 `_Prot`  
 [_fsopen、_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md) の `shflag` パラメーターと同等の既定のファイル保護。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、[rdbuf](#rdbuf) **->** [open](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode` &#124; **ios_base::in**) を呼び出します。 オープンに失敗すると、関数は ios_base::failure 例外をスローできる [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**) を呼び出します。  
  
### <a name="example"></a>例  
  **open** の使用例については、「[basic_filebuf::open](../standard-library/basic-filebuf-class.md#open)」を参照してください。  
  
##  <a name="op_eq"></a>  basic_ifstream::operator=  
 このストリーム オブジェクトの内容を割り当てます。 これは、右辺値が関係する移動代入で、コピーを残しません。  
  
```  
basic_ifstream& operator=(basic_ifstream&& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 `basic_ifstream` オブジェクトへの右辺値参照。  
  
### <a name="return-value"></a>戻り値  
 `*this` を返します。  
  
### <a name="remarks"></a>コメント  
 メンバー演算子により、右辺値の参照として扱われる `right` の内容を使用して、オブジェクトの内容が置き換えられます。 詳細については、「[左辺値と右辺値](../cpp/lvalues-and-rvalues-visual-cpp.md)」を参照してください。  
  
##  <a name="rdbuf"></a>  basic_ifstream::rdbuf  
 格納されたストリーム バッファーのアドレスを返します。  
  
```  
basic_filebuf<Elem, Tr> *rdbuf() const 
```  
  
### <a name="return-value"></a>戻り値  
 格納されているストリーム バッファーを表す [basic_filebuf](../standard-library/basic-filebuf-class.md) オブジェクトへのポインター。  
  
### <a name="example"></a>例  
  `rdbuf` の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。  
  
##  <a name="swap"></a>  basic_ifstream::swap  
 2 つの `basic_ifstream` オブジェクトの内容を交換します。  
  
```  
void swap(basic_ifstream& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 別のストリーム バッファーへの参照。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、`right` の内容を、このオブジェクトの内容と交換します。  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../standard-library/iostream-programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)



