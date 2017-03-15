---
title: "/CLRHEADER | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/CLRHEADER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRHEADER dumpbin オプション"
  - "CLRHEADER dumpbin オプション"
  - "-CLRHEADER dumpbin オプション"
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /CLRHEADER
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/CLRHEADER file  
```  
  
## 解説  
 それぞれの文字について以下に説明します。  
  
 `file`  
 [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) でビルドされるイメージ ファイル。  
  
## 解説  
 このオプションは、マネージ プログラムで使われる .NET ヘッダーについての情報を表示します。  .NET ヘッダーの場所とサイズ \(バイト単位\)、およびヘッダー内のセクションが出力されます。  
  
 [\/GL](../../build/reference/gl-whole-program-optimization.md) コンパイラ オプションで生成したファイルで使用できるのは、[\/HEADERS](../../build/reference/headers.md) DUMPBIN オプションだけです。  
  
 \/clr を指定してコンパイルしたファイルで \/CLRHEADER が使用される場合、dumpbin 出力に **clr Header:** セクションができます。**flags** の値は、どんな \/clr オプションが使用されているかを示します。  
  
-   0  \-\- \/clr \(イメージにはネイティブ コードが含まれている可能性があります\)。  
  
-   1 \-\- \/clr:safe \(イメージは MSIL のみで、任意の CLR プラットフォームで実行でき、場合によっては検証可能です\)。  
  
-   3 \-\- \/clr:pure \(イメージは MSIL のみですが、x86 プラットフォームでのみ実行できます\)。  
  
 また、プログラムを使用して、共通言語ランタイム用にイメージをビルドしたかどうかを確認する方法もあります。詳細については、「[方法: イメージがネイティブであるか CLR であるかを確認する](../Topic/How%20to:%20Determine%20if%20an%20Image%20is%20Native%20or%20CLR.md)」を参照してください。  
  
## 参照  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)