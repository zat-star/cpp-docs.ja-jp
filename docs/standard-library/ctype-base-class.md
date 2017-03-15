---
title: "ctype_base クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "locale/std::ctype_base"
  - "std.ctype_base"
  - "ctype_base"
  - "std::ctype_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ctype_base クラス"
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# ctype_base クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラスは、テンプレート クラス [ctype](../standard-library/ctype-class.md)のファセットの基本クラスとして機能します。  各またはすべての範囲内にある文字列を設定するか、またはテストするために使用される列挙型を定義するために使用する ctype クラスの基本クラスです。  
  
## 構文  
  
```  
struct ctype_base : public locale::facet  
{  
    enum  
    {  
        alnum, alpha, cntrl, digit, graph,  
        lower, print, punct, space, upper,  
        xdigit  
    };  
    typedef short mask;  
    ctype_base(  
        size_t _Refs = 0  
    );  
    ~ctype_base();  
};  
```  
  
## 解説  
 これは列挙体マスクを定義します。  各列挙体の定数は、ヘッダー \<ctype.h で宣言する同様の名前の関数で定義されている文字、分類するさまざまな方法の特徴を付けます。\>  定数は、次の操作:  
  
-   **Space** \(関数 [isspace](../Topic/isspace.md)\)  
  
-   **印刷** \(関数 [isprint](../Topic/isprint.md)\)  
  
-   **cntrl** \(関数 [iscntrl](../Topic/iscntrl.md)\)  
  
-   **上部** \(関数 [isupper](../Topic/isupper.md)\)  
  
-   **下段** \(関数 [islower](../Topic/islower.md)\)  
  
-   **数字** \(関数 [isdigit](../Topic/isdigit.md)\)  
  
-   **punct** \(関数 [ispunct](../Topic/ispunct.md)\)  
  
-   **xdigit** \(関数 [isxdigit](../Topic/isxdigit.md)\)  
  
-   **アルファ** \(関数 [isalpha](../Topic/isalpha.md)\)  
  
-   **alnum** \(関数 [isalnum](../Topic/isalnum.md)\)  
  
-   **グラフ** \(関数 [isgraph](../Topic/isgraph.md)\)  
  
 O リングによってこれらの定数分類の組み合わせの特徴を付けることができます。  特に、true と **alnum** \=\= \(**アルファ**常になります。  ``&#124; **数字**\) と **グラフ** \=\= \(**alnum**``&#124; **punct**\)。  
  
## 必要条件  
 **ヘッダー:** の \<ロケール\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)