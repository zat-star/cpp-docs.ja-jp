---
title: "char_traits 構造体 | Microsoft Docs"
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
  - "std::char_traits"
  - "std.char_traits"
  - "iosfwd/std::char_traits"
  - "char_traits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits クラス"
  - "char_traits 構造体"
ms.assetid: 568e59f0-4521-4207-9223-9dcf6a16d620
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# char_traits 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

char\_traits 構造体は文字に関連付けられた属性を記述します。  
  
## 構文  
  
```  
template <  
   class CharType  
> struct char_traits;  
```  
  
#### パラメーター  
 `CharType`  
 要素のデータ型。  
  
## 解説  
 テンプレートの構造体は **CharType** 型のさまざまな文字特性を記述します。  このテンプレート クラス [basic\_string](../standard-library/basic-string-class.md) は、[basic\_ios](../Topic/basic_ios%20Class.md) などのいくつかの iostream テンプレート クラスと同様、この情報を使用して **CharType** 型の要素を操作します。  このような要素型では、明示的な構築や破棄を要求できません。  既定のコンストラクター、コピー コンストラクター、および代入演算子を、必要なセマンティクスと共に指定する必要があります。  ビットごとのコピーは、代入と同じ効果を持つ必要があります。  char\_traits 構造体のメンバー関数は、いずれも例外をスローしません。  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/char_traits::char_type.md)|文字の型。|  
|[int\_type](../Topic/char_traits::int_type.md)|`char_type` 型の文字、またはファイルの終端 \(EOF\) 文字を表すことができる整数型。|  
|[off\_type](../Topic/char_traits::off_type.md)|ストリーム内の位置間のオフセットを表すことのできる整数型。|  
|[pos\_type](../Topic/char_traits::pos_type.md)|ストリーム内の位置を表すことのできる整数型。|  
|[state\_type](../Topic/char_traits::state_type.md)|ストリーム内のマルチバイト文字の変換状態を表す型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[assign](../Topic/char_traits::assign.md)|1 つの文字の値を別の文字に割り当てます。|  
|[compare](../Topic/char_traits::compare.md)|指定した文字数まで 2 つの文字列を比較します。|  
|[copy](../Topic/char_traits::copy.md)|1 つの文字列から別の文字列に指定した数の文字をコピーします。  使用しないでください。  代わりに [char\_traits::\_Copy\_s](../Topic/char_traits::_Copy_s.md) を使用してください。|  
|[\_Copy\_s](../Topic/char_traits::_Copy_s.md)|1 つの文字列から別の文字列に指定した数の文字をコピーします。|  
|[eof](../Topic/char_traits::eof.md)|ファイルの終端 \(EOF\) 文字を返します。|  
|[eq](../Topic/char_traits::eq.md)|2 つの `char_type` 文字が等しいかどうかをテストします。|  
|[eq\_int\_type](../Topic/char_traits::eq_int_type.md)|`int_type` として表される 2 つの文字が等しいかどうかをテストします。|  
|[find](../Topic/char_traits::find.md)|文字の範囲内で指定した文字が最初に出現する位置を検索します。|  
|[length](../Topic/char_traits::length.md)|文字列の長さを返します。|  
|[lt](../Topic/char_traits::lt.md)|1 つの文字が別の文字よりも小さいかどうかをテストします。|  
|[move](../Topic/char_traits::move.md)|シーケンス内の文字を、指定された文字数だけ、重複が生じる可能性のある別のシーケンスにコピーします。  使用しないでください。  代わりに [char\_traits::\_Move\_s](../Topic/char_traits::_Move_s.md) を使用してください。|  
|[\_Move\_s](../Topic/char_traits::_Move_s.md)|シーケンス内の文字を、指定された文字数だけ、重複が生じる可能性のある別のシーケンスにコピーします。|  
|[not\_eof](../Topic/char_traits::not_eof.md)|文字がファイルの終端 \(EOF\) 文字であるかどうかをテストします。|  
|[to\_char\_type](../Topic/char_traits::to_char_type.md)|`int_type` の文字を `char_type` の対応する文字に変換し、その結果を返します。|  
|[to\_int\_type](../Topic/char_traits::to_int_type.md)|`char_type` の文字を `int_type` の対応する文字に変換し、その結果を返します。|  
  
## 必要条件  
 **ヘッダー:** \<string\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)