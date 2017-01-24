---
title: "TCHAR.H データ型の _MBCS 定義下での使用 | Microsoft Docs"
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
  - "_mbcs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_MBCS データ型"
  - "MBCS データ型"
  - "TCHAR.H データ型"
ms.assetid: 48f471e7-9d2b-4a39-b841-16a0e15c0a18
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# TCHAR.H データ型の _MBCS 定義下での使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 汎用テキスト ルーチンのマップのテーブル \([汎用テキストのマッピング](../c-runtime-library/generic-text-mappings.md)を参照してください\) ように `_MBCS` マニフェスト定数を定義すると、汎用テキスト ルーチンは、次の種類の 1 かのルーチンにマップ:  
  
-   マルチバイトのバイト、文字、および文字列を適切に処理する SBCS ルーチン。  この場合、文字列引数は `char*`型であると想定されます。  たとえば、`printf`への `_tprintf` マップ; `printf` の文字列引数は `char*`型です。  文字列の型に `_TCHAR` の汎用テキスト データ型を使用すると、`printf` の正式な、実際のパラメーターの型は `_TCHAR*` が `char*`にマッピングされるため、一致します。  
  
-   MBCS 固有のルーチン。  この場合、文字列引数は `unsigned char*`型であると想定されます。  たとえば、`_tcsrev`は `_mbsrev`にマップします `unsigned char*`型の文字列を想定し、返します。  再度 `char`を入力するに `_TCHAR`が割り当てられている可能性のある型の競合がある場合は、文字列の型に `_TCHAR`の汎用テキスト データ型を使用する場合。  
  
 型の不一致を回避するための解決策として、次に 3 種類紹介します。これを無視すると、C のコンパイラでは警告が、C\+\+ のコンパイラではエラーが発生します。  
  
-   既定の動作を使用します。  TCHAR.H は次の例のようにランタイム ライブラリのルーチンに対する汎用テキスト ルーチンのプロトタイプを提供します。  
  
    ```  
    char *_tcsrev(char *);  
    ```  
  
     `_tcsrev` の既定の設定では、プロトタイプは LIBC.LIB のサンクによって `_mbsrev` に割り当てられます。  これは `_TCHAR *` から `unsigned char *`に `_mbsrev` 入力パラメーターと戻り値の型 \(`char *`など\) を変更します。  このメソッドは `_TCHAR`を使用しますが、関数呼び出しのオーバーヘッドに比較的低速ですと一致する型になります。  
  
-   コード内に次のプリプロセッサ ステートメントを組み込むことにより、関数をインライン展開します。  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     このメソッドにより適切な MBCS ルーチンに対する汎用テキスト ルーチンを直接割り当てられます。インライン関数サンクは、TCHAR.H で。  TCHAR.H の次のコード例の例はこれがどのようにする方法の例を示します。  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     インライン展開は、型の一致を保証するだけでなく、実行時間が増えることもないため、使用できる場合には最良の解決策です。  
  
-   コード内に次のプリプロセッサ ステートメントを組み込むことにより「ダイレクト マッピング」。  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     既定の動作を使用しない場合やインライン展開を使用できない場合は、これが高速な方法となります。  これは汎用テキスト ルーチンを TCHAR.H.の次の例のように MBCS ルーチンのバージョンにマクロによって直接割り当てられます。  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
 この方法を使うと、適切なデータ型を文字列引数に使用され、戻り値を指す\) ようにするためです。  適切な型の不一致には、`_TXCHAR` の汎用テキスト データ型を使用できるようにするために型キャストを使用できます。  `_TXCHAR` は MBCS コードの `unsigned char` を入力する SBCS のコード マップの `char` を入力するようにマップします。  汎用テキスト マクロに関する詳細については、「[汎用テキストのマッピング](../c-runtime-library/generic-text-mappings.md)」を参照してください。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [国際化](../c-runtime-library/internationalization.md)   
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)