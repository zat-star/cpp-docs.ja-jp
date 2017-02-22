---
title: "_tempnam_dbg、_wtempnam_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wtempnam_dbg"
  - "_tempnam_dbg"
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
  - "wtempnam_dbg"
  - "tempnam_dbg"
  - "_tempnam_dbg"
  - "_wtempnam_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tempnam_dbg 関数"
  - "_wtempnam_dbg 関数"
  - "ファイル名 [C++], 作成 (一時)"
  - "ファイル名 [C++], 一時"
  - "tempnam_dbg 関数"
  - "一時ファイル, 作成"
  - "wtempnam_dbg 関数"
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# _tempnam_dbg、_wtempnam_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`malloc, _malloc_dbg` のデバッグ バージョンを使用する [\_tempnam、\_wtempnam、tmpnam、\_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) の関数バージョン。  
  
## 構文  
  
```  
char *_tempnam_dbg(    const char *dir,    const char *prefix,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wtempnam_dbg(    const wchar_t *dir,    const wchar_t *prefix,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### パラメーター  
 `dir`  
 TMP 環境変数がない場合、または TMP が有効なディレクトリではない場合にファイル名で使用されるパス。  
  
 `prefix`  
 `_tempnam` によって返された名前の前に付けられる文字列。  
  
 `blockType`  
 要求するメモリ ブロックの種類。`_CLIENT_BLOCK`または `_NORMAL_BLOCK`。  
  
 `filename`  
 割り当て操作を要求したソース ファイル名へのポインターまたは `NULL`。  
  
 `linenumber`  
 割り当て操作が要求されたソース ファイル内の行番号または `NULL`。  
  
## 戻り値  
 各関数は、生成された名前へのポインター、または失敗した場合は `NULL` を返します。  TMP 環境変数および `dir` パラメーターに無効なディレクトリ名が指定されている場合は、失敗する可能性があります。  
  
> [!NOTE]
>  `_tempnam_dbg` および `_wtempnam_dbg` によって割り当てられたポインターに対して、`free` \(または `free_dbg`\) を呼び出す必要があります。  
  
## 解説  
 `_tempnam_dbg` および `_wtempnam_dbg`関数は `_tempnam`および `_wtempnam`と同じものですが、`_DEBUG`が定義されている場合に、最初のパラメーターとして `NULL` が渡されると、これらの関数はメモリを割り当てるために `malloc` および `_malloc_dbg` のデバッグ バージョンを使用する点が異なります。  詳細については、「[\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)」を参照してください。  
  
 多くの場合、これらの関数を明示的に呼び出す必要はありません。  代わりに、フラグ `_CRTDBG_MAP_ALLOC` を定義することができます。  `_CRTDBG_MAP_ALLOC` が定義されている場合、`_tempnam` および `_wtempnam` の呼び出しはそれぞれ  `_tempnam_dbg` および `_wtempnam_dbg` にマップし直され、`blockType` が `_NORMAL_BLOCK` に設定されます。  そのため、ヒープ ブロックを `_CLIENT_BLOCK` としてマークする場合以外は、これらの関数を明示的に呼び出す必要はありません。  詳細については、「[デバッグ ヒープ上のメモリ ブロックの型](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_ttempnam_dbg`|`_tempnam_dbg`|`_tempnam_dbg`|`_wtempnam_dbg`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_tempnam_dbg`, `_wtempnam_dbg`|\<crtdbg.h\>|  
  
 互換性の詳細については、ランタイム ライブラリ リファレンスの「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 該当なし。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [\_tempnam、\_wtempnam、tmpnam、\_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [デバッグ バージョンのヒープ割り当て関数](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)