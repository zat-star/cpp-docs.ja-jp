---
title: "_CrtIsMemoryBlock | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_CrtIsMemoryBlock"
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
apitype: "DLLExport"
f1_keywords: 
  - "CrtlsMemoryBlock"
  - "_CrtIsMemoryBlock"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CrtIsMemoryBlock 関数"
  - "CrtIsMemoryBlock 関数"
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _CrtIsMemoryBlock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定されたメモリ ブロックがローカル ヒープ内にあり、有効なデバッグ ヒープ ブロック型識別子が設定されていることを検査します \(デバッグ バージョンだけ\)。  
  
## 構文  
  
```  
int _CrtIsMemoryBlock(   
   const void *userData,  
   unsigned int size,  
   long *requestNumber,  
   char **filename,  
   int *linenumber   
);  
```  
  
#### パラメーター  
 \[入力\] `userData`  
 検査するメモリ ブロックの先頭へのポインター。  
  
 \[入力\] `size`  
 指定されたブロックのサイズ \(バイト\)。  
  
 \[出力\] `requestNumber`  
 ブロックの割り当て番号へのポインター、または `NULL`。  
  
 \[出力\] `filename`  
 ブロックを要求したソース ファイル名へのポインター、または `NULL`。  
  
 \[出力\] `linenumber`  
 ソース ファイル内の行番号へのポインター、または `NULL`。  
  
## 戻り値  
 `_CrtIsMemoryBlock` は、指定されたメモリ ブロックがローカル ヒープにあり、有効なデバッグ ヒープ ブロック型識別子が設定されていれば、`TRUE` を返します。それ以外の場合は、`FALSE` を返します。  
  
## 解説  
 `_CrtIsMemoryBlock` 関数は、指定されたメモリ ブロックがアプリケーションのローカル ヒープ内にあり、有効なブロック型識別子が設定されていることを検査します。  また、この関数を使用すると、オブジェクト割り当て順序番号と、メモリ ブロックの割り当て要求を行ったソース ファイル名および行番号を取得できます。  `requestNumber`、`filename`、`linenumber` の各パラメーターとして NULL 以外の値を渡すと、`_CrtIsMemoryBlock` は、ローカル ヒープ内にメモリ ブロックが見つかった場合、これらのパラメーターにそのメモリ ブロックのデバッグ ヘッダーの値を設定します。  [\_DEBUG](../Topic/_DEBUG.md) が未定義の場合、`_CrtIsMemoryBlock` の呼び出しはプリプロセスで削除されます。  
  
 `_CrtIsMemoryBlock` は、失敗すると `FALSE` を返し、出力パラメーターを既定値に初期化します。この場合、`requestNumber` および `lineNumber` は 0 に設定され、`filename` は `NULL` に設定されます。  
  
 この関数は `TRUE` または `FALSE` を返すため、[\_ASSERT](../Topic/_ASSERT,%20_ASSERTE,%20_ASSERT_EXPR%20Macros.md) 系マクロに渡すことによって、デバッグ用の単純なエラー処理機構を作成できます。  指定されたアドレスがローカル ヒープ内にない場合に、アサーションの失敗を発生させるには、次のように記述します。  
  
```  
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,   
&filename, &linenumber ) );  
```  
  
 `_CrtIsMemoryBlock` を他のデバッグ関数およびマクロと共に使用する方法の詳細については、「[レポート用マクロの使用](../Topic/Macros%20for%20Reporting.md)」を参照してください。  デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法の詳細については、「[CRT デバッグ ヒープ](../Topic/CRT%20Debug%20Heap%20Details.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_CrtIsMemoryBlock`|\<crtdbg.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。  
  
## 使用例  
 「[\_CrtIsValidHeapPointer](../../c-runtime-library/reference/crtisvalidheappointer.md)」のトピックの例を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [デバッグ ルーチン](../../c-runtime-library/debug-routines.md)