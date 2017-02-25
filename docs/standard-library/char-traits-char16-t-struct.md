---
title: "char_traits&lt;char16_t&gt; 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::char_traits<char16_t>"
  - "std.char_traits<char16_t>"
  - "char_traits<char16_t>"
  - "string/std::char_traits<char16_t>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits<char16_t> クラス"
ms.assetid: 5daf3b62-dd6e-451f-b189-0350a04ff966
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# char_traits&lt;char16_t&gt; 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型 `char16_t`要素にテンプレートの構造体 **char\_traits\<CharType\>** の特殊化にする構造体。  
  
## 構文  
  
```  
template<> struct char_traits<char16_t>;  
```  
  
## 解説  
 クラスは、構造体が `char16_t`型のオブジェクトを操作するライブラリ関数の利用できるようになります。  
  
## 必要条件  
 **ヘッダー:** の \<文字列\>  
  
 **名前空間:** std  
  
## 参照  
 [\<string\>](../standard-library/string.md)   
 [char\_traits 構造体](../standard-library/char-traits-struct.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)