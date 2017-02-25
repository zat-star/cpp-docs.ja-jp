---
title: "basic_istringstream クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::basic_istringstream"
  - "sstream/std::basic_istringstream"
  - "basic_istringstream"
  - "std.basic_istringstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_istringstream クラス"
ms.assetid: 1d5bb4b5-793d-4833-98e5-14676c451915
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# basic_istringstream クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラス [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<**Elem**, **Tr**, `Alloc`\> のストリーム バッファーからの、要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを記述します。  
  
## 構文  
  
```  
  
        template <  
   class Elem,   
   class Tr = char_traits<Elem>,   
   class Alloc = allocator<Elem>   
>  
   class basic_istringstream : public basic_istream<Elem, Tr>  
```  
  
#### パラメーター  
 `Alloc`  
 アロケーター クラス。  
  
 `Elem`  
 文字列の基本要素の型。  
  
 *Tr*  
 文字列の基本要素に特化した文字の特徴。  
  
## 解説  
 このテンプレート クラスは、**Elem** 型の要素を含む [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<**Elem**, **Tr**, `Alloc`\> クラスのストリーム バッファーから要素とエンコードされたオブジェクトを抽出する際の、抽出を制御するオブジェクトを記述します。Elem 型の文字特性は **Tr** クラスによって決められ、その要素は `Alloc` クラスのアロケーターによって割り当てられます。  このオブジェクトは、クラス basic\_stringbuf\<**Elem**, **Tr**, `Alloc`\> のオブジェクトを格納します。  
  
### コンストラクター  
  
|||  
|-|-|  
|[basic\_istringstream](../Topic/basic_istringstream::basic_istringstream.md)|`basic_istringstream` 型のオブジェクトを構築します。|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/basic_istringstream::allocator_type.md)|この型は、テンプレート パラメーター `Alloc` のシノニムです。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[rdbuf](../Topic/basic_istringstream::rdbuf.md)|型 `pointer` の格納されたストリーム バッファーのアドレスを [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<`Elem`, `Tr`, `Alloc`\> に返します。|  
|[str](../Topic/basic_istringstream::str.md)|文字列バッファー内のテキストを設定または取得します。書き込み位置は変更しません。|  
|[swap](../Topic/basic_istringstream::swap.md)|この `basic_istringstream` オブジェクト内の値を、提供されるオブジェクトの値と交換します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \=](../Topic/basic_istringstream::operator=.md)|オブジェクト パラメーターの値をこの `basic_istringstream` オブジェクトに代入します。|  
  
## 必要条件  
 **ヘッダー:** \<sstream\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)