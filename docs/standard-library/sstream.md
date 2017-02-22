---
title: "&lt;sstream&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<sstream>"
  - "std::<sstream>"
  - "<sstream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sstream ヘッダー"
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# &lt;sstream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

割り当てられた配列オブジェクトに格納されているシーケンスのストリーム入出力操作をサポートするテンプレート クラスを定義します。  無限シーケンスは、テンプレート クラス [basic\_string](../standard-library/basic-string-class.md)オブジェクトとして簡単に変換されます。  
  
## 構文  
  
```  
namespace std {  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_stringbuf;  
typedef basic_stringbuf<char> stringbuf;  
typedef basic_stringbuf<wchar_t> wstringbuf;  
  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_istringstream;  
typedef basic_istringstream<char> istringstream;  
typedef basic_istringstream<wchar_t> wistringstream;  
  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_ostringstream;  
typedef basic_ostringstream<char> ostringstream;  
typedef basic_ostringstream<wchar_t> wostringstream;  
  
template<class CharType,  
    class Traits = char_traits<CharType>,  
    class Allocator = allocator<CharType> >  
    class basic_stringstream;  
typedef basic_stringstream<char> stringstream;  
typedef basic_stringstream<wchar_t> wstringstream;  
  
        // TEMPLATE FUNCTIONS  
template<class CharType, class Traits, class Allocator>  
    void swap(  
        basic_stringbuf<CharType, Traits, Allocator>& _Left,  
        basic_stringbuf<CharType, Traits, Allocator>& _Right  
    );   
template<class CharType, class Traits, class Allocator>  
    void swap(  
        basic_istringstream<CharType, Traits, Allocator>& _Left,  
        basic_istringstream<CharType, Traits, Allocator>& _Right  
    );  
template<class CharType, class Traits, class Allocator>  
    void swap(  
        basic_ostringstream<CharType, Traits, Allocator>& _Left,  
        basic_ostringstream<CharType, Traits, Allocator>& _Right  
    );  
template<class CharType, class Traits, class Allocator>  
    void swap (  
        basic_stringstream<CharType, Traits, Allocator>& _Left,  
        basic_stringstream<CharType, Traits, Allocator>& _Right  
    );  
}  // namespace std  
  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`_Left`|`sstream` オブジェクトへの参照。|  
|`_Right`|`sstream` オブジェクトへの参照。|  
  
## 解説  
 型 `char *` オブジェクトはオーバーフローに [\<strstream\>](../standard-library/strstream.md) の機能を使用できます。  ただし、`<strstream>` は推奨されておらず、`<sstream>` の使用を推奨します。  
  
### Typedef  
  
|||  
|-|-|  
|[istringstream](../Topic/istringstream.md)|`char` テンプレート パラメーターを特化型 `basic_istringstream` を作成します。|  
|[ostringstream](../Topic/ostringstream.md)|`char` テンプレート パラメーターを特化型 `basic_ostringstream` を作成します。|  
|[stringbuf](../Topic/stringbuf.md)|`char` テンプレート パラメーターを特化型 `basic_stringbuf` を作成します。|  
|[stringstream](../Topic/stringstream.md)|`char` テンプレート パラメーターを特化型 `basic_stringstream` を作成します。|  
|[wistringstream](../Topic/wistringstream.md)|`wchar_t` テンプレート パラメーターを特化型 `basic_istringstream` を作成します。|  
|[wostringstream](../Topic/wostringstream.md)|`wchar_t` テンプレート パラメーターを特化型 `basic_ostringstream` を作成します。|  
|[wstringbuf](../Topic/wstringbuf.md)|`wchar_t` テンプレート パラメーターを特化型 `basic_stringbuf` を作成します。|  
|[wstringstream](../Topic/wstringstream.md)|`wchar_t` テンプレート パラメーターを特化型 `basic_stringstream` を作成します。|  
  
### マニピュレーター  
  
|||  
|-|-|  
|[swap](../Topic/%3Csstream%3E%20swap.md)|`sstream` 2 の二つのオブジェクトの値を交換します。|  
  
### クラス  
  
|||  
|-|-|  
|[basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)|型の特性を **Tr**クラスにおける、型 **Elem**要素の送信を制御する Array オブジェクトに格納されている要素のシーケンスとしてストリーム バッファーを記述します。|  
|[basic\_istringstream](../standard-library/basic-istringstream-class.md)|オブジェクトは、クラス [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<**Elem**、**Tr**、型の特性を **Tr**クラスによって決定され、要素が `Alloc`のアロケーター クラスによって割り当てられた型 **Elem**要素で `Alloc`\>ストリーム バッファーからの要素とエンコードされたオブジェクトのコントロールの抽出記述します。|  
|[basic\_ostringstream](../standard-library/basic-ostringstream-class.md)|クラス [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<**Elem**、**Tr**、型の特性を **Tr**クラスによって決定され、要素が `Alloc`のアロケーター クラスによって割り当てられた型 **Elem**要素で `Alloc`\>ストリーム バッファーにオブジェクトを、要素とエンコードされたオブジェクトのコントロールの挿入を記述します。|  
|[basic\_stringstream](../standard-library/basic-stringstream-class.md)|クラス [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<**Elem**、**Tr**、型の特性を **Tr**クラスによって決定され、要素が `Alloc`のアロケーター クラスによって割り当てられた型 **Elem**要素で `Alloc`\>ストリームのバッファーを使用してオブジェクトを、要素とエンコードされたオブジェクトのコントロールの挿入および抽出記述します。|  
  
## 必要条件  
  
-   **ヘッダー:** の \<sstream\>  
  
-   **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)