---
title: "ostrstream クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ostrstream
- strstream/std::ostrstream::freeze
- strstream/std::ostrstream::pcount
- strstream/std::ostrstream::rdbuf
- strstream/std::ostrstream::str
dev_langs:
- C++
helpviewer_keywords:
- ostrstream class
ms.assetid: e2e34679-b266-4728-a8e1-8eda5d400e46
caps.latest.revision: 20
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
ms.openlocfilehash: 2ed85552778f3bbf7346001e4dd4c858177ce49b
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="ostrstream-class"></a>ostrstream クラス
クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーへの、要素とエンコードされたオブジェクトの挿入を制御するオブジェクトを表します。  
  
## <a name="syntax"></a>構文  
  
```
class ostrstream : public ostream
```  
  
## <a name="remarks"></a>コメント  
 このオブジェクトは、クラス `strstreambuf` のオブジェクトを格納します。  
  
> [!NOTE]
>  このクラスは使用されていません。 代わりに、[ostringstream](../standard-library/sstream-typedefs.md#ostringstream) または [wostringstream](../standard-library/sstream-typedefs.md#wostringstream) を使用することを検討します。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[ostrstream](#ostrstream)|`ostrstream` 型のオブジェクトを構築します。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[freeze](#freeze)|ストリーム バッファーの操作により、ストリーム バッファーを使用不可にします。|  
|[pcount](#pcount)|被制御シーケンスに書き込まれる要素の数を返します。|  
|[rdbuf](#rdbuf)|ストリームの関連付けられた `strstreambuf` オブジェクトへのポインターを返します。|  
|[str](#str)|[freeze](../standard-library/strstreambuf-class.md#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<strstream>  
  
 **名前空間:** std  
  
##  <a name="freeze"></a>  ostrstream::freeze  
 ストリーム バッファーの操作により、ストリーム バッファーを使用不可にします。  
  
```
void freeze(bool _Freezeit = true);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Freezeit`  
 ストリームを停止させるかどうか示す `bool`。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は [rdbuf](#rdbuf) -> [freeze](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit*) を呼び出します。  
  
### <a name="example"></a>例  
  **freeze**の使用例は、[strstream::freeze](../standard-library/strstreambuf-class.md#freeze) をご覧ください。  
  
##  <a name="ostrstream"></a>  ostrstream::ostrstream  
 `ostrstream` 型のオブジェクトを構築します。  
  
```
ostrstream();

ostrstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::out);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptr`  
 バッファー。  
  
 `count`  
 バッファーのサイズ (バイト単位)。  
  
 `_Mode`  
 バッファーの入出力モード。 詳細については、[ios_base::openmode](../standard-library/ios-base-class.md#openmode) をご覧ください。  
  
### <a name="remarks"></a>コメント  
 両方のコンストラクターは、[ostream](../standard-library/ostream-typedefs.md#ostream)(**sb**) を呼び出すことにより基本クラスを初期化します。ここで、**sb** は [strstreambuf](../standard-library/strstreambuf-class.md) 型の格納されているオブジェクトです。 最初のコンストラクターはまた、`strstreambuf` を呼び出して **sb** を初期化します。 2 番目のコンストラクターは、次のどちらかの方法で基本クラスを初期化します。  
  
-   `_Mode` & **ios_base::app**== 0 の場合、`ptr` は `count` 要素の配列の最初の要素を指定する必要があり、コンストラクターは `strstreambuf`(`ptr`, `count`, `ptr`) を呼び出します。  
  
-   それ以外の場合、`ptr` は count 要素の配列の最初の要素を指定する必要があります。この count 要素は C 文字列を含み、最初の要素が `ptr` によって指定されるものです。そしてコンストラクターは `strstreambuf`(`ptr`, `count`, `ptr` + `strlen`(`ptr`)) を呼び出します。  
  
##  <a name="pcount"></a>  ostrstream::pcount  
 被制御シーケンスに書き込まれる要素の数を返します。  
  
```
streamsize pcount() const;
```  
  
### <a name="return-value"></a>戻り値  
 被制御シーケンスに書き込まれる要素の数。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、[rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount) を返します。  
  
### <a name="example"></a>例  
  `pcount` の使用例は、[strstream::pcount](../standard-library/strstreambuf-class.md#pcount) をご覧ください。  
  
##  <a name="rdbuf"></a>  ostrstream::rdbuf  
 ストリームの関連付けられた strstreambuf オブジェクトへのポインターを返します。  
  
```
strstreambuf *rdbuf() const
```  
  
### <a name="return-value"></a>戻り値  
 ストリームの関連付けられた strstreambuf オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は **pointer** 型の格納されたストリーム バッファーのアドレスを [strstreambuf](../standard-library/strstreambuf-class.md) に返します。  
  
### <a name="example"></a>例  
  `rdbuf` の使用例は、[strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) をご覧ください。  
  
##  <a name="str"></a>  ostrstream::str  
 [freeze](../standard-library/strstreambuf-class.md#freeze) を呼び出し、被制御シーケンスの先頭へのポインターを返します。  
  
```
char *str();
```  
  
### <a name="return-value"></a>戻り値  
 被制御シーケンスの先頭へのポインター。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、[rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str) を返します。  
  
### <a name="example"></a>例  
  **str** の使用例は、[strstream::str](../standard-library/strstreambuf-class.md#str) をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [ostream](../standard-library/ostream-typedefs.md#ostream)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../standard-library/iostream-programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)




