---
title: "basic_ostringstream クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "basic_ostringstream"
  - "std.basic_ostringstream"
  - "sstream/std::basic_ostringstream"
  - "std::basic_ostringstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ostringstream クラス"
ms.assetid: aea699f7-350f-432a-acca-adbae7b483fb
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# basic_ostringstream クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

要素とエンコードされたオブジェクトを [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<**Elem**, **Tr**, `Alloc`\> クラスのストリーム バッファーに挿入する操作を制御するオブジェクトを記述します。  
  
## 構文  
  
```  
  
        template <  
   class Elem,   
   class Tr = char_traits<Elem>,   
   class Alloc = allocator<Elem>   
>  
   class basic_ostringstream : public basic_ostream<Elem, Tr>  
```  
  
#### パラメーター  
 `Alloc`  
 アロケーター クラス。  
  
 `Elem`  
 文字列の基本要素の型。  
  
 *Tr*  
 文字列の基本要素に特化した文字の特徴。  
  
## 解説  
 このクラスは、要素とエンコードされたオブジェクトを、ストリーム バッファーに挿入する操作を制御するオブジェクトを記述します。要素は **Elem** 型で、文字特性は **Tr** クラスによって決められ、要素は `Alloc` クラスのアロケーターによって割り当てられます。  このオブジェクトは、クラス basic\_stringbuf\<**Elem**, **Tr**, `Alloc`\> のオブジェクトを格納します。  
  
### コンストラクター  
  
|||  
|-|-|  
|[basic\_ostringstream](../Topic/basic_ostringstream::basic_ostringstream.md)|`basic_ostringstream` 型のオブジェクトを構築します。|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/basic_ostringstream::allocator_type.md)|この型は、テンプレート パラメーター `Alloc` のシノニムです。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[rdbuf](../Topic/basic_ostringstream::rdbuf.md)|型 `pointer` の格納されたストリーム バッファーのアドレスを [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<`Elem`, `Tr`, `Alloc`\> に返します。|  
|[str](../Topic/basic_ostringstream::str.md)|文字列バッファー内のテキストを設定または取得します。書き込み位置は変更しません。|  
  
## 必要条件  
 **ヘッダー:** \<sstream\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)