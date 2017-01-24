---
title: "basic_string クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.basic_string"
  - "std::basic_string"
  - "basic_string"
  - "xstring/std::basic_string"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_string クラス"
ms.assetid: a9c3e0a2-39bf-4c8a-b093-9abe30839591
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# basic_string クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`basic_string` テンプレート クラスのオブジェクトによって制御されるシーケンスは C\+\+ の標準文字列クラスで、通常文字列と呼ばれますが、標準 C\+\+ ライブラリ全体で使用される C スタイルの null で終わる文字列と混同しないようにしてください。  標準 C\+\+ 文字列は、比較と連結演算子、反復子、STL アルゴリズム、クラスのアロケーターによって管理されるメモリのコピーおよび割り当てなど、通常の型として文字列の使用を有効にするコンテナーです。  標準 C\+\+ 文字列を C スタイルの null で終わる文字列に変換する場合は、[basic\_string::c\_str](../Topic/basic_string::c_str.md) メンバーを使用します。  
  
## 構文  
  
```  
template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>> class basic_string;  
```  
  
#### パラメーター  
 `CharType`  
 文字列に格納される単一文字のデータ型。  標準 C\+\+ ライブラリでは、`char` 型の要素に型定義 [string](../Topic/string%20\(C++%20STL%20%3Cstring%3E\).md)、`wchar_t` に [wstring](../Topic/wstring.md)、`char16_t` に [u16string](../Topic/u16string.md)、`char32_t` に [u32string](../Topic/u32string.md) を使用した、このテンプレート クラスの特殊化が提供されます。  
  
 `Traits`  
 basic\_string 特化の **CharType** 要素のさまざまな重要なプロパティは、クラス **Traits** によって記述されます。  既定値は `char_traits`\<`CharType`\> です。  
  
 `Allocator`  
 メモリの文字列の割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。  既定値は **allocator**\<`CharType`\> です。  
  
### コンストラクター  
  
|||  
|-|-|  
|[basic\_string](../Topic/basic_string::basic_string.md)|空または特定の文字によって初期化される文字列、または他の文字列オブジェクトまたは C 文字列の全体または一部のコピーである文字列を作成します。|  
  
### Typedef  
  
|||  
|-|-|  
|[allocator\_type](../Topic/basic_string::allocator_type.md)|文字列オブジェクトの `allocator` クラス型を表す型。|  
|[const\_iterator](../Topic/basic_string::const_iterator.md)|文字列内の `const` 要素にアクセスし、読み取ることができるランダム アクセス反復子を提供する型。|  
|[const\_pointer](../Topic/basic_string::const_pointer.md)|文字列内の `const` 要素へのポインターを提供する型。|  
|[const\_reference](../Topic/basic_string::const_reference.md)|読み取りと `const` 操作の実行のために、文字列に格納された `const` 要素への参照を提供する型。|  
|[const\_reverse\_iterator](../Topic/basic_string::const_reverse_iterator.md)|文字列内の任意の `const` 要素を読み取ることができるランダム アクセス反復子を提供する型。|  
|[difference\_type](../Topic/basic_string::difference_type.md)|同じ文字列内の要素を参照する 2 反復子の違いを提供する型。|  
|[iterator](../Topic/basic_string::iterator.md)|文字列内の任意の要素を読み取り、または変更できるランダム アクセス反復子を提供する型。|  
|[npos](../Topic/basic_string::npos.md)|検索機能が失敗したときに「見つかりません」、または「すべての残りの文字」を示す –1 に初期化された符号なし整数値。|  
|[ポインター](../Topic/basic_string::pointer.md)|文字列または文字アレイ内の文字要素へのポインターを提供する型。|  
|[参照](../Topic/basic_string::reference.md)|文字列に格納されている要素への参照を提供する型。|  
|[reverse\_iterator](../Topic/basic_string::reverse_iterator.md)|反転文字列内の要素を読み取り、または変更できるランダム アクセス反復子を提供する型。|  
|[size\_type](../Topic/basic_string::size_type.md)|文字列の要素の数の符号なし整数型。|  
|[traits\_type](../Topic/basic_string::traits_type.md)|文字列に格納されている要素の文字の特徴の型。|  
|[value\_type](../Topic/basic_string::value_type.md)|文字列に格納された文字の型を表す型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[append](../Topic/basic_string::append.md)|文字列の末尾に文字を追加します。|  
|[assign](../Topic/basic_string::assign.md)|文字列の内容に新しい文字の値を割り当てます。|  
|[at](../Topic/basic_string::at.md)|文字列内の指定した位置にある要素への参照を返します。|  
|[back](../Topic/basic_string::back.md)||  
|[begin](../Topic/basic_string::begin.md)|文字列の 1 つ目の要素を示す反復子を返します。|  
|[c\_str](../Topic/basic_string::c_str.md)|C スタイルの null で終わる文字列として、文字列の内容を変換します。|  
|[capacity](../Topic/basic_string::capacity.md)|文字列のメモリ割り当てを増やさずに文字列に格納できる要素の最大数を返します。|  
|[cbegin](../Topic/basic_string::cbegin.md)|文字列の 1 つ目の要素を示す定数反復子を返します。|  
|[cend](../Topic/basic_string::cend.md)|文字列内の最後の要素の次の場所を指す定数反復子を返します。|  
|[clear](../Topic/basic_string::clear.md)|文字列のすべての要素を消去します。|  
|[compare](../Topic/basic_string::compare.md)|2 つの文字列が等しいかどうか、または一方が辞書式に他方よりも小さいかどうかを判断するために、特定の文字列を含む文字列を比較します。|  
|[copy](../Topic/basic_string::copy.md)|コピー元の文字列のインデックス位置からターゲットの文字配列に最大で指定された文字数をコピーします。  使用しないでください。  代わりに、[basic\_string::\_Copy\_s](../Topic/basic_string::_Copy_s.md) を使用してください。|  
|[crbegin](../Topic/basic_string::crbegin.md)|反転文字列内の最初の要素を示す定数反復子を返します。|  
|[crend](../Topic/basic_string::crend.md)|反転文字列内の最後の要素の次の場所を指す定数反復子を返します。|  
|[\_Copy\_s](../Topic/basic_string::_Copy_s.md)|コピー元の文字列のインデックス位置からターゲットの文字配列に最大で指定された文字数をコピーします。|  
|[データ](../Topic/basic_string::data.md)|文字列の内容を文字配列に変換します。|  
|[empty](../Topic/basic_string::empty.md)|文字列に文字が含まれているかどうかをテストします。|  
|[End](../Topic/basic_string::end.md)|文字列内の最後の要素の次の場所を指す反復子を返します。|  
|[erase](../Topic/basic_string::erase.md)|指定した位置から文字列の要素または要素範囲を削除します。|  
|[find](../Topic/basic_string::find.md)|指定された文字シーケンスに一致する部分文字列の最初の出現を文字列で前方に検索します。|  
|[find\_first\_not\_of](../Topic/basic_string::find_first_not_of.md)|指定された文字列の要素ではない最初の文字を文字列で検索します。|  
|[find\_first\_of](../Topic/basic_string::find_first_of.md)|指定された文字列の要素と一致する最初の文字を文字列で検索します。|  
|[find\_last\_not\_of](../Topic/basic_string::find_last_not_of.md)|指定された文字列の要素ではない最後の文字を文字列で検索します。|  
|[find\_last\_of](../Topic/basic_string::find_last_of.md)|指定された文字列の要素である最後の文字を文字列で検索します。|  
|[front](../Topic/basic_string::front.md)|文字列内の最初の要素への参照を返します。|  
|[get\_allocator](../Topic/basic_string::get_allocator.md)|文字列の構築に使用される `allocator` オブジェクトのコピーを返します。|  
|[insert](../Topic/basic_string::insert.md)|指定した位置の文字列に要素、複数の要素、または要素の範囲を挿入します。|  
|[length](../Topic/basic_string::length.md)|文字列内の現在の要素数を返します。|  
|[max\_size](../Topic/basic_string::max_size.md)|文字列が含むことができる最大文字数を返します。|  
|[pop\_back](../Topic/basic_string::pop_back.md)|文字列の最後の要素を消去します。|  
|[push\_back](../Topic/basic_string::push_back.md)|文字列の末尾に要素を追加します。|  
|[rbegin](../Topic/basic_string::rbegin.md)|反転文字列の 1 つ目の要素への反復子を返します。|  
|[rend](../Topic/basic_string::rend.md)|反転文字列内の最後の要素の先を示す反復子を返します。|  
|[replace](../Topic/basic_string::replace.md)|指定された場所の文字列の要素を指定された文字、または他の範囲、文字列、または C 文字列からコピーされた文字で置き換えます。|  
|[reserve](../Topic/basic_string::reserve.md)|文字列のキャパシティを少なくとも指定した数に設定します。|  
|[resize](../Topic/basic_string::resize.md)|要素を必要に応じて追加または削除して、文字列の新しいサイズを指定します。|  
|[rfind](../Topic/basic_string::rfind.md)|指定された文字シーケンスに一致する部分文字列の最初の出現を文字列で後方に検索します。|  
|[shrink\_to\_fit](../Topic/basic_string::shrink_to_fit.md)|文字列の余分なキャパシティを破棄します。|  
|[size](../Topic/basic_string::size.md)|文字列内の現在の要素数を返します。|  
|[substr](../Topic/basic_string::substr.md)|指定された位置から始まる文字列から最大でいくつかの文字の部分文字列をコピーします。|  
|[swap](../Topic/basic_string::swap.md)|2 つの文字列の内容を交換します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \+\=](../Topic/basic_string::operator+=.md)|文字列に文字を追加します。|  
|[operator \=](../Topic/basic_string::operator=.md)|文字列の内容に新しい文字の値を割り当てます。|  
|[operator&#91;&#93;](../Topic/basic_string::operator.md)|文字列に指定したインデックスのある文字への参照を提供します。|  
  
## 解説  
 関数が [max\_size](../Topic/basic_string::max_size.md) の要素よりも長いシーケンスを生成するように指示された場合、関数は [length\_error](../Topic/length_error%20Class.md) 型のオブジェクトをスローして長さエラーを報告します。  
  
 被制御シーケンスの要素を指定する参照、ポインター、および反復子は、被制御シーケンスを変更する関数の呼び出しの後、または非 **const** メンバー関数への最初の呼び出しの後、無効になることがあります。  
  
## 必要条件  
 **ヘッダー:** \<string\>  
  
 **名前空間:** std  
  
## 参照  
 [\<string\>](../standard-library/string.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)