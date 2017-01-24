---
title: "char_traits&lt;wchar_t&gt; 構造体 | Microsoft Docs"
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
  - "std.char_traits<wchar_t>"
  - "char_traits<wchar_t>"
  - "string/std::char_traits<wchar_t>"
  - "std::char_traits<wchar_t>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits<wchar_t> クラス"
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# char_traits&lt;wchar_t&gt; 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型 `wchar_t`要素にテンプレートの構造体 **char\_traits\<CharType\>** から特化したクラスである。  
  
## 構文  
  
```  
template<> struct char_traits<wchar_t>;  
```  
  
## 解説  
 クラスまたは構造体がこの `wchar_t`型のオブジェクトを操作するライブラリ関数の利用できるようになります。  
  
## 必要条件  
 **ヘッダー:** の \<文字列\>  
  
 **名前空間:** std  
  
## 参照  
 [char\_traits 構造体](../standard-library/char-traits-struct.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)