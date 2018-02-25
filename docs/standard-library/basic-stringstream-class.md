---
title: "basic_stringstream クラス |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- sstream/std::basic_stringstream
- sstream/std::basic_stringstream::allocator_type
- sstream/std::basic_stringstream::rdbuf
- sstream/std::basic_stringstream::str
dev_langs:
- C++
helpviewer_keywords:
- std::basic_stringstream [C++]
- std::basic_stringstream [C++], allocator_type
- std::basic_stringstream [C++], rdbuf
- std::basic_stringstream [C++], str
ms.assetid: 49629814-ca37-45c5-931b-4ff894e6ebd2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f6616f5eadc5291b917d7121f5eebb92baeec8c3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="basicstringstream-class"></a>basic_stringstream クラス
クラス [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> のストリーム バッファーを使用して、要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトを表します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>  
class basic_stringstream : public basic_iostream<Elem, Tr>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Alloc`  
 アロケーター クラス。  
  
 `Elem`  
 文字列の基本要素の型。  
  
 *Tr*  
 文字列の基本要素に特化した文字の特徴。  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスは、**Elem** 型の要素を含むクラス [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> のストリーム バッファーを使用して、要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトについて記述します。Elem 型の特性はクラス **Tr** によって決定され、その要素はクラス `Alloc` のアロケーターによって割り当てられます。 このオブジェクトは、クラス basic_stringbuf< **Elem**, **Tr**, `Alloc`> のオブジェクトを格納します。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[basic_stringstream](#basic_stringstream)|`basic_stringstream` 型のオブジェクトを構築します。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|この型は、テンプレート パラメーター `Alloc` のシノニムです。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[rdbuf](#rdbuf)|型 `pointer` の格納されたストリーム バッファーのアドレスを [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`> に返します。|  
|[str](#str)|文字列バッファー内のテキストを設定または取得します。書き込み位置は変更しません。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<sstream>  
  
 **名前空間:** std  
  
##  <a name="allocator_type"></a>  basic_stringstream::allocator_type  
 この型は、テンプレート パラメーター `Alloc` のシノニムです。  
  
```  
typedef Alloc allocator_type;  
```  
  
##  <a name="basic_stringstream"></a>  basic_stringstream::basic_stringstream  
 `basic_stringstream` 型のオブジェクトを構築します。  
  
```  
explicit basic_stringstream(ios_base::openmode _Mode = ios_base::in | ios_base::out);

explicit basic_stringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Mode`  
 [ios_base::openmode](../standard-library/ios-base-class.md#openmode) の列挙値のうちの 1 つ。  
  
 `str`  
 `basic_string` 型のオブジェクト。  
  
### <a name="remarks"></a>コメント  
 最初のコンストラクターは、[basic_iostream](../standard-library/basic-iostream-class.md)( **sb**) を呼び出すことで基底クラスを初期化します。ここで、**sb** はクラス [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> の格納されているオブジェクトです。 また、basic_stringbuf< **Elem**, **Tr**, `Alloc`>( `_Mode`) を呼び出すことで **sb** の初期化もします。  
  
 2 番目のコンストラクターが basic_iostream( **sb**) を呼び出して基底クラスを初期化します。 また、basic_stringbuf< **Elem**, **Tr**, `Alloc`>(_ *Str*, `_Mode`) を呼び出すことで **sb** の初期化もします。  
  
##  <a name="rdbuf"></a>  basic_stringstream::rdbuf  
 **pointer** 型の格納されたストリーム バッファーのアドレスを [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> に返します。  
  
```  
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```  
  
### <a name="return-value"></a>戻り値  
 basic_stringbuf< **Elem**, **Tr**, `Alloc`> に返す **pointer** 型の格納されたストリーム バッファーのアドレス。  
  
### <a name="example"></a>例  
  `rdbuf` の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。  
  
##  <a name="str"></a>  basic_stringstream::str  
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
 制御されたシーケンスが **\*this** によって制御されるシーケンスのコピーである、クラス [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`> のオブジェクトを返します。  
  
### <a name="remarks"></a>コメント  
 最初のメンバー関数は [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str) を返します。 2 番目のメンバー関数は `rdbuf` -> **str**( `_Newstr`) を呼び出します。  
  
### <a name="example"></a>例  
  **str** の使用例については、「[basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#str)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../standard-library/iostream-programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)

