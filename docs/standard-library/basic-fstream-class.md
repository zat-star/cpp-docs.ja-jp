---
title: "basic_fstream クラス |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- basic_fstream
- fstream/std::basic_fstream
- fstream/std::basic_fstream::close
- fstream/std::basic_fstream::is_open
- fstream/std::basic_fstream::open
- fstream/std::basic_fstream::rdbuf
- fstream/std::basic_fstream::swap
dev_langs:
- C++
helpviewer_keywords:
- basic_fstream class
ms.assetid: 8473817e-42a4-430b-82b8-b476c86bcf8a
caps.latest.revision: 24
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
ms.openlocfilehash: f9d52128703d021ba3a880ff899ca71b144e89ec
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="basicfstream-class"></a>basic_fstream クラス
`Elem` 型の要素を含む [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> クラスのストリーム バッファーを使用して要素とエンコードされたオブジェクトを挿入および抽出する際に、この処理を制御するオブジェクトを記述します。この型の特性は、`Tr` クラスによって決定されます。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_fstream : public basic_iostream<Elem, Tr>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Elem`  
 ファイル バッファーの基本要素。  
  
 `Tr`  
 ファイル バッファーの基本要素の特徴 (通常は `char_traits`< `Elem`>)。  
  
## <a name="remarks"></a>コメント  
 このオブジェクトは、クラス `basic_filebuf`< `Elem`, `Tr`> のオブジェクトを格納します。  
  
> [!NOTE]
>  fstream オブジェクトの get ポインターおよび put ポインターは、互いに独立したポインターでは**ありません**。 get ポインターが移動すると、put ポインターも移動します。  
  
## <a name="example"></a>例  
 次の例で、読み取りと書き込みが可能な `basic_fstream` オブジェクトの作成方法を示します。  
  
```  
// basic_fstream_class.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    fstream fs("fstream.txt", ios::in | ios::out | ios::trunc);  
    if (!fs.bad())  
    {  
        // Write to the file.  
        fs << "Writing to a basic_fstream object..." << endl;  
        fs.close();  
  
        // Dump the contents of the file to cout.  
        fs.open("fstream.txt", ios::in);  
        cout << fs.rdbuf();  
        fs.close();  
    }  
}  
```  
  
```Output  
Writing to a basic_fstream object...  
```  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[basic_fstream](#basic_fstream)|`basic_fstream` 型のオブジェクトを構築します。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[close](#close)|ファイルを閉じます。|  
|[is_open](#is_open)|ファイルが開いているかどうかを判断します。|  
|[open](#open)|ファイルを開きます。|  
|[rdbuf](#rdbuf)|pointer 型の格納されたストリーム バッファーのアドレスを [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> に返します。|  
|[swap](#swap)|このオブジェクトの内容を別の `basic_fstream` オブジェクトの内容と交換します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<fstream>  
  
 **名前空間:** std  
  
##  <a name="basic_fstream"></a>  basic_fstream::basic_fstream  
 `basic_fstream` 型のオブジェクトを構築します。  
  
```  
basic_fstream();

explicit basic_fstream(
    const char* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

explicit basic_fstream(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

basic_fstream(basic_fstream&& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Filename`  
 開くファイルの名前。  
  
 `_Mode`  
 [ios_base::openmode](../standard-library/ios-base-class.md#openmode) の列挙値のうちの 1 つ。  
  
 `_Prot`  
 [_fsopen、_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md) の `shflag` パラメーターと同等の既定のファイル保護。  
  
### <a name="remarks"></a>コメント  
 最初のコンストラクターは、[basic_iostream](../standard-library/basic-iostream-class.md)( **sb**) を呼び出すことで基底クラスを初期化します。ここで、**sb** はクラス [basic_filebuf](../standard-library/basic-filebuf-class.md)\< **Elem**, **Tr**> の格納されているオブジェクトです。 また、`basic_filebuf`\< **Elem**, **Tr**> を呼び出すことで **sb** の初期化もします。  
  
 2 番目と 3 番目のコンストラクターは、`basic_iostream`( **sb**) を呼び出すことで基底クラスを初期化します。 また、`basic_filebuf`\< **Elem**, **Tr**> とその後に **sb.**[open](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode`) を呼び出すことで **sb** を初期化します。 後者の関数が Null ポインターを返す場合、コンストラクターは [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**) を呼び出します。  
  
 4 番目のコンストラクターは、右辺値参照として扱われる `right` のコンテンツでオブジェクトを初期化します。  
  
### <a name="example"></a>例  
  `basic_fstream` の使用例については、「[streampos](../standard-library/ios-typedefs.md#streampos)」を参照してください。  
  
##  <a name="close"></a>  basic_fstream::close  
 ファイルを閉じます。  
  
```  
void close();
```  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、[rdbuf](#rdbuf)**->** [close](../standard-library/basic-filebuf-class.md#close) を呼び出します。  
  
### <a name="example"></a>例  
  **close** の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。  
  
##  <a name="is_open"></a>  basic_fstream::is_open  
 ファイルが開いているかどうかを判断します。  
  
```  
bool is_open() const;
```  
  
### <a name="return-value"></a>戻り値  
 ファイルが開いている場合は **true**、それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、[rdbuf](#rdbuf)**->**[is_open](../standard-library/basic-filebuf-class.md#is_open) を返します。  
  
### <a name="example"></a>例  
  `is_open` の使用例については、「[basic_filebuf::is_open](../standard-library/basic-filebuf-class.md#is_open)」を参照してください。  
  
##  <a name="open"></a>  basic_fstream::open  
 ファイルを開きます。  
  
```  
void open(
    const char* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,  
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out,  
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
 メンバー関数は、[rdbuf](#rdbuf) **->** [open](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode`) を呼び出します。 その関数が Null ポインターを返す場合、関数は [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**) を呼び出します。  
  
### <a name="example"></a>例  
  **open** の使用例については、「[basic_filebuf::open](../standard-library/basic-filebuf-class.md#open)」を参照してください。  
  
##  <a name="op_eq"></a>  basic_fstream::operator=  
 指定したストリーム オブジェクトからコンテンツをこのオブジェクトに割り当てます。 これは、コピーを残さない右辺値を伴う移動代入です。  
  
```  
basic_fstream& operator=(basic_fstream&& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 `basic_fstream` オブジェクトへの左辺値参照。  
  
### <a name="return-value"></a>戻り値  
 `*this` を返します。  
  
### <a name="remarks"></a>コメント  
 メンバー演算子により、右辺値の参照として扱われる `right` の内容を使用して、オブジェクトの内容が置き換えられます。  
  
##  <a name="rdbuf"></a>  basic_fstream::rdbuf  
 pointer 型の格納されたストリーム バッファーのアドレスを [basic_filebuf](../standard-library/basic-filebuf-class.md)\< **Elem**, **Tr**> に返します。  
  
```  
basic_filebuf<Elem, Tr> *rdbuf() const 
```  
  
### <a name="return-value"></a>戻り値  
 格納されたストリーム バッファーのアドレス。  
  
### <a name="example"></a>例  
  `rdbuf` の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。  
  
##  <a name="swap"></a>  basic_fstream::swap  
 2 つの `basic_fstream` オブジェクトの内容を交換します。  
  
```  
void swap(basic_fstream& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 `basic_fstream` オブジェクトへの `lvalue` 参照。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、このオブジェクトの内容と `right` の内容を交換します。  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../standard-library/iostream-programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)


