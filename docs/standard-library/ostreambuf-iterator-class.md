---
title: "ostreambuf_iterator クラス | Microsoft Docs"
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
  - "std.ostreambuf_iterator"
  - "streambuf/std::ostreambuf_iterator"
  - "ostreambuf_iterator"
  - "std::ostreambuf_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ostreambuf_iterator クラス"
ms.assetid: dad1e624-2f45-4e94-8887-a885e95f9071
caps.latest.revision: 16
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ostreambuf_iterator クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

テンプレート クラス ostreambuf\_iterator は、抽出 **operator\>\>** を使用して連続する文字要素を出力ストリームに書き込む出力反復子オブジェクトを表します。  `ostreambuf_iterator` は、出力ストリームに挿入されるオブジェクトの型がジェネリック型ではなく文字である点が、[ostream\_iterator クラス](../standard-library/ostream-iterator-class.md)のオブジェクトとは異なります。  
  
## 構文  
  
```  
  
      template <   
   class CharType = char  
   class Traits = char_traits<CharType>  
>  
```  
  
#### パラメーター  
 `CharType`  
 ostreambuf\_iterator の文字型を表す型。  この引数は省略可能であり、既定値は `char` です。  
  
 `Traits`  
 ostreambuf\_iterator の文字型を表す型。  この引数は省略可能であり、既定値は `char_traits` \<*CharType\>* です。  
  
## 解説  
 ostreambuf\_iterator クラスは出力反復子の要件を満たす必要があります。  アルゴリズムは `ostreambuf_iterator` を使用して出力ストリームに直接書き込むことができます。  このクラスは、生の \(フォーマットされていない\) I\/O ストリームに文字の形式でアクセスできる低レベルのストリームの反復子を提供し、高レベルのストリーム反復子に関連付けられたバッファリングや文字変換をバイパスすることができます。  
  
### コンストラクター  
  
|||  
|-|-|  
|[ostreambuf\_iterator](../Topic/ostreambuf_iterator::ostreambuf_iterator.md)|出力ストリームに文字を書き込むために初期化された `ostreambuf_iterator` を構築します。|  
  
### Typedef  
  
|||  
|-|-|  
|[char\_type](../Topic/ostreambuf_iterator::char_type.md)|`ostreambuf_iterator` の文字型を提供する型。|  
|[ostream\_type](../Topic/ostreambuf_iterator::ostream_type.md)|`ostream_iterator` のストリーム型を提供する型。|  
|[streambuf\_type](../Topic/ostreambuf_iterator::streambuf_type.md)|`ostreambuf_iterator` のストリーム型を提供する型。|  
|[traits\_type](../Topic/ostreambuf_iterator::traits_type.md)|`ostream_iterator` の文字特性型を提供する型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[failed](../Topic/ostreambuf_iterator::failed.md)|出力ストリーム バッファーへの挿入の失敗をテストします。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\*](../Topic/ostreambuf_iterator::operator*.md)|出力反復子式 \*`i` \= `x` を実装するために使用される逆参照演算子。|  
|[operator\+\+](../Topic/ostreambuf_iterator::operator++.md)|操作が呼び出される前に示したものと同じオブジェクトに `ostreambuf_iterator` を返す、実質的な機能を持たないインクリメント演算子。|  
|[operator\=](../Topic/ostreambuf_iterator::operator=.md)|この演算子は、関連付けられているストリーム バッファーに文字を挿入します。|  
  
## 必要条件  
 **ヘッダー:** \<iterator\>  
  
 **名前空間:** std  
  
## 参照  
 [\<iterator\>](../standard-library/iterator.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)