---
title: "regex_traits &lt; char &gt; クラス | Microsoft Docs"
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
  - "std::tr1::regex_traits<char>"
  - "regex_traits<char>"
  - "std.tr1.regex_traits<char>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex_traits < char > クラス [TR1]"
ms.assetid: ce95ebcd-3687-4ad5-bf1d-b89fdc633675
caps.latest.revision: 17
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# regex_traits &lt; char &gt; クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

regex\_traits を char 用に特化したクラスです。  
  
## 構文  
  
```  
template <>  
    class regex_traits<char>  
```  
  
## 解説  
 テンプレート クラスの明示的な特殊化は、クラスは [regex\_traits クラス](../standard-library/regex-traits-class.md) 型の要素に対して `char` \(ようにこの型のオブジェクトを操作するライブラリ関数の利点がかかることができます\)。  
  
## 必要条件  
 **ヘッダー:** \<regex\>  
  
 **名前空間:** std  
  
## 参照  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_traits クラス](../standard-library/regex-traits-class.md)