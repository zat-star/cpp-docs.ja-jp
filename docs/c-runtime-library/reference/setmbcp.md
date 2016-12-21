---
title: "_setmbcp | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_setmbcp"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_setmbcp"
  - "setmbcp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_setmbcp 関数"
  - "マルチバイト コード ページ"
  - "setmbcp 関数"
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _setmbcp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

新しいマルチバイト コード ページを設定します。  
  
## 構文  
  
```  
int _setmbcp(  
   int codepage   
);  
```  
  
#### パラメーター  
 `codepage`  
 ロケールに依存しないマルチバイト ルーチンの新しいコード ページの設定。  
  
## 戻り値  
 コード ページが正常に設定されている場合は 0 を返します。  無効なコード ページ値が `codepage`に指定されている場合、戻り–1 とコード ページの設定は変更されません。  メモリ割り当てのエラーが発生 `EINVAL` に `errno` を設定します。  
  
## 解説  
 `_setmbcp` 関数は新しいマルチバイト コード ページを指定します。  既定ではシステムの既定の ANSI コード ページに、ランタイム システムが自動的に、マルチバイトのコード ページを設定します。  マルチバイトのコード ページの設定は、ロケールに依存しないすべてのマルチバイト ルーチンに影響します。  ただし、定義された現在のロケールのコード ページを使用するように `_setmbcp` に指示する可能性があります \(マニフェスト定数および関連の結果を次の一覧を参照してください。  マルチバイトのコード ページではなくロケールのコード ページに依存するマルチバイト ルーチンの一覧については、[マルチバイト文字列の解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)を参照してください。  
  
 マルチバイトのコード ページは、次のランタイム ライブラリ ルーチンによって文字処理に影響します:  
  
||||  
|-|-|-|  
|[\_exec 関数](../../c-runtime-library/exec-wexec-functions.md)|[\_mktemp](../../c-runtime-library/reference/mktemp-wmktemp.md)|[\_stat](../../c-runtime-library/reference/stat-functions.md)|  
|[\_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[\_spawn 関数](../Topic/_spawn,%20_wspawn%20Functions.md)|[\_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[\_makepath](../../c-runtime-library/reference/makepath-wmakepath.md)|[\_splitpath](../Topic/_splitpath,%20_wsplitpath.md)|[tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
  
 さらに、パラメーターがマルチバイト コード ページに従ってマルチバイト文字 \(`_exec` と `_spawn` ファミリなど\) の文字列を処理するため、マルチバイト文字 `argv` または `envp` プログラム引数を受け取るすべてのランタイム ライブラリ ルーチン。  したがって、これらのルーチンは、マルチバイトのコード ページを変更する `_setmbcp` の呼び出しに影響されます。  
  
 `codepage` の引数は次の値のいずれかに設定できます。:  
  
-   `_MB_CP_ANSI` オペレーティング システムから取得したプログラム起動時に ANSI コード ページを使用します。  
  
-   `_MB_CP_LOCALE` 前の呼び出しから取得された現在のロケールのコード ページを使用します。[setlocale](../Topic/setlocale,%20_wsetlocale.md).  
  
-   `_MB_CP_OEM` オペレーティング システムから取得したプログラム起動時に OEM のコード ページを使用します。  
  
-   `_MB_CP_SBCS` 前のコード ページを使用します。  コード ページが `_MB_CP_SBCS`に設定すると、[\_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md) などのルーチンは、常に FALSE を返します。  
  
-   値が ANSI、OEM、またはそのオペレーション システム サポートされているコード ページであるかどうかをそのほかの有効なコード ページ値に関係なく、\(サポートされていない UTF\-8、UTF\-7 は含まれません。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_setmbcp`|\<mbctype.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 参照  
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)