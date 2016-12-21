---
title: "basic_stringstream クラス | Microsoft Docs"
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
  - "std.basic_stringstream"
  - "basic_stringstream"
  - "std::basic_stringstream"
  - "sstream/std::basic_stringstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_stringstream クラス"
ms.assetid: 49629814-ca37-45c5-931b-4ff894e6ebd2
caps.latest.revision: 19
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# basic_stringstream クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラス [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<**Elem**, **Tr**, `Alloc`\> のストリーム バッファーを使用して、要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトを表します。  
  
## 構文  
  
```  
  
        template <  
   class Elem,   
   class Tr = char_traits<Elem>,   
   class Alloc = allocator<Elem>   
>  
   class basic_stringstream : public basic_iostream<Elem, Tr>  
```  
  
#### パラメーター  
 `Alloc`  
 アロケーター クラス。  
  
 `Elem`  
 文字列の基本要素の型。  
  
 *Tr*  
 文字列の基本要素に特化した文字の特徴。  
  
## 解説  
 このテンプレート クラスは、**Elem** 型の要素を含むクラス [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<**Elem**, **Tr**, `Alloc`\> のストリーム バッファーを使用して、要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトについて記述します。Elem 型の特性はクラス **Tr** によって決定され、その要素はクラス `Alloc` のアロケーターによって割り当てられます。  このオブジェクトは、クラス basic\_stringbuf\<**Elem**, **Tr**, `Alloc`\> のオブジェクトを格納します。  
  
### コンストラクター  
  
|||  
|-|-|  
|[basic\_stringstream](../Topic/basic_stringstream::basic_stringstream.md)|`basic_stringstream` 型のオブジェクトを構築します。|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/basic_stringstream::allocator_type.md)|この型は、テンプレート パラメーター `Alloc` のシノニムです。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[rdbuf](../Topic/basic_stringstream::rdbuf.md)|型 `pointer` の格納されたストリーム バッファーのアドレスを [basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<`Elem`, `Tr`, `Alloc`\> に返します。|  
|[str](../Topic/basic_stringstream::str.md)|文字列バッファー内のテキストを設定または取得します。書き込み位置は変更しません。|  
  
## 必要条件  
 **ヘッダー:** \<sstream\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)