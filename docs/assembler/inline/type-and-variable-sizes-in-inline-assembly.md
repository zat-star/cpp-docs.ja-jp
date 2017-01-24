---
title: "インライン アセンブリでの型と変数サイズ | Microsoft Docs"
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
  - "length"
  - "Type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "インライン アセンブラー, 演算子"
  - "LENGTH 演算子"
  - "サイズ"
  - "SIZE 演算子"
  - "サイズ, インライン アセンブラー内での取得"
  - "TYPE 演算子"
  - "変数, 長さ"
  - "変数, サイズ"
  - "変数, 型"
ms.assetid: b62c2f2b-a7ad-4145-bae4-d890db86d348
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# インライン アセンブリでの型と変数サイズ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 **長さ**  に **サイズ**  と  **種類**  の演算子にはインライン アセンブリに限定的な意味を持ちます。  これらの演算子は `DUP` でまったく \(MASM ディレクティブまたは演算子を使用するデータを定義しないため\) は使用できません。  ただしC のサイズや C\+\+ の変数または型の検索に使用できます :  
  
-   **長さ**  の演算子は配列の要素数を返すことができます。  これは配列の変数の値 1 を返します。  
  
-   **サイズ**  の演算子は. または C\+\+ の変数のサイズを返すことができます。  変数のサイズは  **長さ**  と  **種類**  の積です。  
  
-   **種類**  の演算子は. のサイズや C\+\+ の型または変数返すことができます。  変数が配列の場合は **種類**  は配列の要素のサイズを返します。  
  
 たとえばプログラムに 8 要素の `int` の配列がある場合は  
  
```  
int arr[8];  
```  
  
 次の C およびアセンブリの式は `arr` および要素のサイズがあります。  
  
|\_\_asm|C|サイズ|  
|-------------|-------|---------|  
|**長さ**  の arr|`sizeof`\(arr\)\/`sizeof`\(arr \[0\]\)|8|  
|**サイズ**  の arr|`sizeof`\(arr\)|32|  
|**種類**  の arr|`sizeof`\(arr \[0\]\)|4|  
  
 **終了 Microsoft 固有の仕様→**  
  
## 参照  
 [\_\_asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)