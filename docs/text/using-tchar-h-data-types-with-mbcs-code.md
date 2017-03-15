---
title: "_MBCS コードでの TCHAR.H データ型の使用 | Microsoft Docs"
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
  - ""tchar.h""
  - "TCHAR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "汎用テキストのデータ型 [C++]"
  - "汎用テキスト マップ [C++]"
  - "マップ (汎用テキストを)"
  - "マップ [C++], TCHAR.H"
  - "MBCS [C++], 汎用テキスト マップ"
  - "TCHAR.H データ型, マップ"
ms.assetid: 298583c5-22c3-40f6-920e-9ec96d42abd8
caps.latest.revision: 7
caps.handback.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# _MBCS コードでの TCHAR.H データ型の使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

記号定数 **\_MBCS** が定義されている場合、汎用テキスト ルーチンは、次のいずれかのルーチンに割り当てられます。  
  
-   マルチバイトのバイト、文字、および文字列を適切に処理する SBCS ルーチン。  この場合、文字列引数は **char\*** 型であることが想定されます。  たとえば、`_tprintf` は `printf` に割り当てられます。`printf` の文字列引数は **char\*** 型です。  文字列の型に **\_TCHAR** 汎用テキスト データ型を使用すると、**\_TCHAR\*** が **char\*** に割り当てられるため、`printf` に対する仮引数と実引数の型が一致します。  
  
-   MBCS 固有のルーチン。  この場合、文字列引数は `unsigned` **char\*** 型であることが想定されます。  たとえば、`_tcsrev` は `_mbsrev` に割り当てられます。この関数は、引数と戻り値に `unsigned` **char\*** 型の文字列を想定します。  文字列の型に **\_TCHAR** 汎用テキスト データ型を使用すると、**\_TCHAR** は `char` 型に割り当てられるため、型の不一致が発生する可能性があります。  
  
 型の不一致を回避するための解決策として、次に 3 種類紹介します。これを無視すると、C のコンパイラでは警告が、C\+\+ のコンパイラではエラーが発生します。  
  
-   既定の動作を使用します。  Tchar.h は、次の例に示すように、ランタイム ライブラリのルーチンに対する汎用テキスト ルーチンのプロトタイプを提供します。  
  
    ```  
    char * _tcsrev(char *);  
    ```  
  
     既定の場合は、`_tcsrev` のプロトタイプが Libc.lib のサンクによって `_mbsrev` に割り当てられます。  これにより、`_mbsrev` のパラメーターと戻り値の型が、**\_TCHAR \*** \(つまり `char` **\***\) から `unsigned` `char` **\*** に変換されます。  この方法では、**\_TCHAR** を使用したときの型一致が保証されますが、関数呼び出しのオーバーヘッドのため、多少処理が遅くなってしまいます。  
  
-   コード内に次のプリプロセッサ ステートメントを組み込むことにより、関数をインライン展開します。  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     この方法では、Tchar.h に指定されているインライン関数サンクによって、汎用テキスト ルーチンが適切な MBCS ルーチンに直接割り当てられます。  Tchar.h の該当箇所を以下に示します。  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     インライン展開は、型の一致を保証するだけでなく、実行時間が増えることもないため、使用できる場合には最良の解決策です。  
  
-   コード内に次のプリプロセッサ ステートメントを組み込むことにより、ダイレクト マッピングを使用します。  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     既定の動作を使用しない場合やインライン展開を使用できない場合は、これが高速な方法となります。  汎用テキスト ルーチンは、次の Tchar.h のコード例に示すように、マクロによってそのルーチンの MBCS バージョンに直接割り当てられます。  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
     この方法を使うときには、文字列引数や文字列戻り値に対して正しいデータ型を使うように注意する必要があります。  型をキャストして一致させるか、または **\_TXCHAR** 汎用テキスト データ型を使用できます。  **\_TXCHAR** は、SBCS のコードでは `char` 型に割り当てられ、MBCS のコードでは `unsigned` `char` 型に割り当てられます。  汎用テキスト マクロの詳細については、「ランタイム ライブラリ リファレンス」の「[汎用テキスト マップ](../c-runtime-library/generic-text-mappings.md)」を参照してください。  
  
## 参照  
 [Tchar.h における汎用テキストのマッピング](../Topic/Generic-Text%20Mappings%20in%20Tchar.h.md)