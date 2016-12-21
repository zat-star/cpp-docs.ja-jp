---
title: "ostream_iterator クラス | Microsoft Docs"
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
  - "ostream_iterator"
  - "std.ostream_iterator"
  - "std::ostream_iterator"
  - "iterator/std::ostream_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ostream_iterator クラス"
ms.assetid: 24d842d3-9f45-4bf6-a697-62f5968f5a03
caps.latest.revision: 17
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ostream_iterator クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

テンプレート クラス ostream\_iterator は、抽出**演算子 \<\<** を使用して連続する要素を出力ストリームに書き込む出力反復子オブジェクトを表します。  
  
## 構文  
  
```  
  
      template <  
   class Type   
   class CharType = char  
   class Traits = char_traits<CharType>  
>  
class ostream_iterator  
```  
  
#### パラメーター  
 *Type*  
 出力ストリームに挿入されるオブジェクトの型。  
  
 `CharType`  
 `ostream_iterator` の文字型を表す型。  この引数は省略可能であり、既定値は `char` です。  
  
 `Traits`  
 `ostream_iterator` の文字型を表す型。  この引数は省略可能であり、既定値は `char_traits` \<*CharType\>* です。  
  
 ostream\_iterator クラスは出力反復子の要件を満たす必要があります。  アルゴリズムは `ostream_iterator` を使用して出力ストリームに直接書き込むことができます。  
  
### コンストラクター  
  
|||  
|-|-|  
|[ostream\_iterator](../Topic/ostream_iterator::ostream_iterator.md)|出力ストリームに書き込むために初期化され、区切られた `ostream_iterator` を構築します。|  
  
### Typedef  
  
|||  
|-|-|  
|[char\_type](../Topic/ostream_iterator::char_type.md)|`ostream_iterator` の文字型を提供する型。|  
|[ostream\_type](../Topic/ostream_iterator::ostream_type.md)|`ostream_iterator` のストリーム型を提供する型。|  
|[traits\_type](../Topic/ostream_iterator::traits_type.md)|`ostream_iterator` の文字特性型を提供する型。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\*](../Topic/ostream_iterator::operator*.md)|出力反復子式 \*`i` \= `x` を実装するために使用される逆参照演算子。|  
|[operator\+\+](../Topic/ostream_iterator::operator++.md)|操作が呼び出される前に示したものと同じオブジェクトに `ostream_iterator` を返す、実質的な機能を持たないインクリメント演算子。|  
|[operator\=](../Topic/ostream_iterator::operator=.md)|出力ストリームに書き込むための出力反復子式 \*`i` \= `x` を実装するために使用される代入演算子。|  
  
## 必要条件  
 **ヘッダー:** \<iterator\>  
  
 **名前空間:** std  
  
## 参照  
 [\<iterator\>](../standard-library/iterator.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)