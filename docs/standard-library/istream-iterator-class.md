---
title: "istream_iterator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "iterator/std::istream_iterator"
  - "std.istream_iterator"
  - "std::istream_iterator"
  - "istream_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istream_iterator クラス"
ms.assetid: fb52a8cd-7f71-48d1-b73e-4b064e2a8d16
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# istream_iterator クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

入力反復子オブジェクトを表します。  このクラスは、入力ストリームから `Type` クラスのオブジェクトを抽出します。これには、格納している、`basic_istream`\<`CharType`, `Traits`\> への `pointer` 型のオブジェクトを介してアクセスします。  
  
## 構文  
  
```  
template<class Type,  
    class CharType = char,  
    class Traits = char_traits<CharType>,  
    class Distance = ptrdiff_t,  
> class istream_iterator  
 : public iterator<  
        input_iterator_tag,  
        Type,   
        Distance,   
        const Type *,  
        const Type&  
    >;  
```  
  
#### パラメーター  
 `Type`  
 入力ストリームから抽出されるオブジェクトの型。  
  
 `CharType`  
 `istream_iterator` の文字型を表す型。  この引数は省略可能であり、既定値は `char` です。  
  
 `Traits`  
 `istream_iterator` の文字型を表す型。  この引数は省略可能であり、既定値は `char_traits`\<`CharType`\> です。  
  
 `Distance`  
 `istream_iterator` の相違点の種類を表す符号付き整数型。  この引数は省略可能であり、既定値は `ptrdiff_t` です。  
  
 null 以外の格納されたポインターを使用して istream\_iterator クラスのオブジェクトを構築またはインクリメントすると、オブジェクトは、関連付けられている入力ストリームから `Type` 型のオブジェクトを抽出および格納することを試行します。  抽出が失敗した場合、オブジェクトは効果的に格納されたポインターを null ポインターに置き換え、シーケンス終端のインジケーターを作成します。  
  
### コンストラクター  
  
|||  
|-|-|  
|[istream\_iterator](../Topic/istream_iterator::istream_iterator.md)|既定の `istream_iterator` または読み取り元の反復子のストリーム型に初期化される `istream_iterator` として、ストリームの終わり反復子を構築します。|  
  
### Typedef  
  
|||  
|-|-|  
|[char\_type](../Topic/istream_iterator::char_type.md)|`istream_iterator` の文字型を提供する型。|  
|[istream\_type](../Topic/istream_iterator::istream_type.md)|`istream_iterator` のストリーム型を提供する型。|  
|[traits\_type](../Topic/istream_iterator::traits_type.md)|`istream_iterator` の文字特性型を提供する型。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\*](../Topic/istream_iterator::operator*.md)|逆参照演算子は、`istream_iterator` で指定された `Type` 型の格納されたオブジェクトを返します。|  
|[operator\-\>](../Topic/istream_iterator::operator-%3E.md)|メンバーの値 \(存在する場合\) を返します。|  
|[operator\+\+](../Topic/istream_iterator::operator++.md)|入力ストリームからインクリメントされたオブジェクトを抽出するか、オブジェクトをインクリメントする前にオブジェクトをコピーして、そのコピーを返します。|  
  
## 必要条件  
 **ヘッダー:**\<iterator\>  
  
 **名前空間:** std  
  
## 参照  
 [input\_iterator\_tag 構造体](../standard-library/input-iterator-tag-struct.md)   
 [iterator 構造体](../Topic/iterator%20Struct.md)   
 [\<iterator\>](../standard-library/iterator.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)