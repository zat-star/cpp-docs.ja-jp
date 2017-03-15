---
title: "char_traits&lt;char&gt; 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "string/std::char_traits<char>"
  - "std::char_traits<char >"
  - "char_traits<char >"
  - "std.char_traits<char >"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits<char> クラス"
ms.assetid: abd9373a-77db-4031-bf4b-f8ac15087581
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# char_traits&lt;char&gt; 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型 `char`要素にテンプレートの構造体 **char\_traits\<CharType\>** の特殊化にする構造体。  
  
## 構文  
  
```  
template<> struct char_traits<char>;  
```  
  
## 解説  
 クラスまたは構造体がこの `char`型のオブジェクトを操作するライブラリ関数の利用できるようになります。  
  
## 使用例  
 型 `char`要素を示した例のテンプレート クラス [char\_traits クラス](../standard-library/char-traits-struct.md)\<**CharType**\> の typedef およびメンバー関数を参照してください。  
  
## 必要条件  
 **ヘッダー:** の \<文字列\>  
  
 **名前空間:** std