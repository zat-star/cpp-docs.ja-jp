---
title: "単純変数の宣言 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "宣言 (変数を), 単純な"
  - "型指定されていない変数"
ms.assetid: b07adf9d-9e79-4b64-8a34-e6fe1c7eccec
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 単純変数の宣言
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

直接宣言の最も単純な形式である単純変数の宣言は、変数名と型を指定します。  また、変数のストレージ クラスとデータ型を指定します。  
  
 ストレージ クラス、型、またはこの両方が変数宣言に必要です。  型指定されていない変数 \(`var;` など\) は警告を生成します。  
  
## 構文  
 `declarator`:  
 *pointer*  opt  
  
 *direct\-declarator*  
  
 *direct\-declarator*:  
 *identifier*  
  
 *identifier*:  
 *nondigit*  
  
 *identifier nondigit*  
  
 *identifier digit*  
  
 演算型、構造体型、共用体型、列挙型、void 型、および `typedef` の名前によって表される型については、型指定子がすべての型情報を提供するため、単純な宣言子を宣言で使用できます。  ポインター型、配列型、および関数型では、より複雑な宣言子が必要です。  
  
 同じ宣言で複数の変数を指定するために、コンマ \(**,**\) で区切られた識別子のリストを使用できます。  宣言で定義されているすべての変数に、同じ基本型があります。  次に例を示します。  
  
```  
int x, y;        /* Declares two simple variables of type int */  
int const z = 1; /* Declares a constant value of type int */  
```  
  
 変数 `x` および `y` は、特定の実装の `int` 型で定義されるセットに任意の値を保持できます。  簡単なオブジェクト `z` は値 1 に初期化され、変更できません。  
  
 `z` の宣言の対象が初期化されていない静的変数であるか、宣言がファイル スコープで行われた場合、初期値 0 を受け取り、その値は変更できません。  
  
```  
unsigned long reply, flag; /* Declares two variables  
                              named reply and flag     */  
```  
  
 この例では、両方の変数 \(`reply` と `flag`\) は `unsigned long` 型を持ち、符号なし整数値を保持します。  
  
## 参照  
 [宣言子と変数宣言](../c-language/declarators-and-variable-declarations.md)