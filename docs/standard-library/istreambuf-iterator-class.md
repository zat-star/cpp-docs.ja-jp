---
title: "istreambuf_iterator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "istreambuf_iterator"
  - "std.istreambuf_iterator"
  - "std::istreambuf_iterator"
  - "streambuf/std::istreambuf_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istreambuf_iterator クラス"
ms.assetid: 39002da2-61a6-48a5-9d0c-5df8271f6038
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# istreambuf_iterator クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

istreambuf\_iterator テンプレート クラスは、入力ストリーム バッファーから文字要素を抽出する入力反復子オブジェクトを表します。これには、`basic_streambuf`\<**CharType**, **Traits**\> へのポインター型の、格納されたオブジェクトを介してアクセスします。  
  
## 構文  
  
```  
  
      template <   
   class CharType  
   class Traits = char_traits<CharType>  
>  
class istreambuf_iterator  
: public iterator<input_iterator_tag, CharType, typename Traits::off_type, CharType *, CharType&>  
```  
  
#### パラメーター  
 `CharType`  
 istreambuf\_iterator の文字型を表す型。  
  
 `Traits`  
 istreambuf\_iterator の文字型を表す型。  この引数は省略可能であり、既定値は `char_traits` \<*CharType\>* です。  
  
## 解説  
 istreambuf\_iterator クラスは入力反復子の要件を満たす必要があります。  
  
 null 以外の格納されたポインターを使用して istreambuf\_iterator クラスのオブジェクトを構築またはインクリメントすると、オブジェクトは、関連付けられている入力ストリームから **CharType** 型のオブジェクトを効果的に抽出および格納することを試行します。  ただし、抽出はオブジェクトが実際に逆参照またはコピーされるまで遅延することがあります。  抽出が失敗した場合、オブジェクトは効果的に格納されたポインターを null ポインターに置き換え、シーケンス終端のインジケーターを作成します。  
  
### コンストラクター  
  
|||  
|-|-|  
|[istreambuf\_iterator](../Topic/istreambuf_iterator::istreambuf_iterator.md)|入力ストリームから文字を読み取るために初期化される `istreambuf_iterator` を構築します。|  
  
### Typedef  
  
|||  
|-|-|  
|[char\_type](../Topic/istreambuf_iterator::char_type.md)|`ostreambuf_iterator` の文字型を提供する型。|  
|[int\_type](../Topic/istreambuf_iterator::int_type.md)|`istreambuf_iterator` の整数型を提供する型。|  
|[istream\_type](../Topic/istreambuf_iterator::istream_type.md)|`istream_iterator` のストリーム型を提供する型。|  
|[streambuf\_type](../Topic/istreambuf_iterator::streambuf_type.md)|`istreambuf_iterator` のストリーム型を提供する型。|  
|[traits\_type](../Topic/istream_iterator::traits_type.md)|`istream_iterator` の文字特性型を提供する型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[equal](../Topic/istreambuf_iterator::equal.md)|2 つ入力ストリーム バッファー反復子の等価性をテストします。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\*](../Topic/istreambuf_iterator::operator*.md)|逆参照演算子は、ストリーム内の次の文字を返します。|  
|[operator\+\+](../Topic/istreambuf_iterator::operator++.md)|入力ストリームから次の文字を返すか、オブジェクトをインクリメントする前にオブジェクトをコピーして、そのコピーを返します。|  
|[operator\-\>](../Topic/istreambuf_iterator::operator-%3E.md)|メンバーの値 \(存在する場合\) を返します。|  
  
## 必要条件  
 **ヘッダー:** \<iterator\>  
  
 **名前空間:** std  
  
## 参照  
 [iterator 構造体](../Topic/iterator%20Struct.md)   
 [\<iterator\>](../standard-library/iterator.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)