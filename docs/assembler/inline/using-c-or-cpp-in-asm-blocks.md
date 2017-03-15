---
title: "__asm ブロックでの C または C++ の使用 | Microsoft Docs"
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
helpviewer_keywords: 
  - "__asm キーワード [C++], C/C++ の要素"
  - "コメント, __asm ブロック内"
  - "定数, __asm ブロック内"
  - "インライン アセンブラー, 混在命令 (C/C++ のステートメント)"
  - "マクロ, __asm ブロック"
  - "プリプロセス ディレクティブ"
  - "プリプロセス ディレクティブ, __asm ブロックでの使用"
  - "プリプロセッサ, ディレクティブ"
  - "シンボル, __asm ブロック内"
  - "型名, __asm ブロックでの使用"
  - "typedef 名, __asm ブロックでの使用"
ms.assetid: ae8b2b52-6b75-42e3-ac0c-ad02d922ed97
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __asm ブロックでの C または C++ の使用
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 インライン アセンブリ命令が C または C\+\+ のステートメントと混合できるためC または C\+\+ の変数を名前でとそれらの言語の他の多くの要素を使用することはできます。  
  
 `__asm` ブロックは次の言語要素を使用して :  
  
-   ラベルを含むシンボルおよび変数と関数名  
  
-   `enum` の記号定数とメンバーを含む定数  
  
-   マクロとプリプロセッサ ディレクティブ  
  
-   コメント \(\/\*\*\/ と **\/\/** 両方\)  
  
-   MASM \(の種類を有効な場所で型名\)  
  
-   一般に **PTR** と  **種類**  などの演算子を使用した `typedef` の名前または構造体または共用体のメンバーを指定します。  
  
 `__asm` ブロック内ではC 表記またはアセンブラー小数点表記を持つ整数定数を指定できます \(0x100 と 100h たとえばはと等価です。  これは `#define`\(15\) を使用して C の定数を定義しC または C\+\+ の両方でプログラムのアセンブリの一部を使用できるようになります。  または 8 進数で 0 とそれらに付けて定数を指定できます。  たとえば0777 は 8 進定数を指定します。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [\_\_asm のブロックで演算子を使用する](../../assembler/inline/using-operators-in-asm-blocks.md)  
  
-   [C または C\+\+ の Symbols\_in \_\_asm のを使用してブロック](../Topic/Using%20C%20or%20C++%20Symbols%20in%20__asm%20Blocks.md)  
  
-   [\_\_asm ブロックの C または C\+\+ のデータにアクセス](../Topic/Accessing%20C%20or%20C++%20Data%20in%20__asm%20Blocks.md)  
  
-   [インライン アセンブリを使用するための関数](../../assembler/inline/writing-functions-with-inline-assembly.md)  
  
 **終了 Microsoft 固有の仕様→**  
  
## 参照  
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)