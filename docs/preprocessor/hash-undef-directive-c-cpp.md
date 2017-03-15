---
title: "#undef ディレクティブ (C/C++) | Microsoft Docs"
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
  - "#undef"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#undef ディレクティブ"
  - "プリプロセッサ, ディレクティブ"
  - "undef ディレクティブ (#undef)"
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #undef ディレクティブ (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`#define` で作成された名前を削除 \(定義解除\) します。  
  
## 構文  
  
```  
  
#undef   
identifier  
  
```  
  
## 解説  
 `#undef` ディレクティブは、*identifier* の現在の定義を削除します。  その結果、後続の *identifier* がプリプロセッサによって無視されます。  `#undef` を使用してマクロ定義を削除するには、パラメーター リストを指定せずに、マクロの *identifier*  のみを指定します。  
  
 `#undef` ディレクティブは事前の定義を持たない識別子にも適用できます。  これにより、その識別子が未定義であることが保証されます。  `#undef` ステートメント内では、マクロ置換は実行されません。  
  
 `#undef` ディレクティブ、通常は `#define` ディレクティブと対で使用され、識別子が特別な意味を持つ領域をソース プログラム内に作成します。  たとえば、ソース プログラムの特定の関数でマニフェスト定数を使用すると、プログラムの残り部分に影響を与えない環境固有の値を定義できます。  また `#undef` ディレクティブは、`#if` ディレクティブをソース プログラムの条件付きコンパイルを制御します。  詳細については、「[\#if、\#elif、\#else、および \#endif ディレクティブ](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)」を参照してください。  
  
 次の例は、`#undef` ディレクティブを使用して、シンボリック定数およびマクロの定義を削除しています。  マクロの識別子のみが指定されていることに注意してください。  
  
```  
#define WIDTH 80  
#define ADD( X, Y ) ((X) + (Y))  
.  
.  
.  
#undef WIDTH  
#undef ADD  
```  
  
 **Microsoft 固有の仕様 →**  
  
 マクロは、コマンド ラインで \/U オプションを使用し、その後ろに定義解除する識別子を指定して定義を解除できます。  このコマンドを実行すると、ファイルの先頭に `#undef` *macro\-name* ステートメントのシーケンスを追加した場合と同じ効果が得られます。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)