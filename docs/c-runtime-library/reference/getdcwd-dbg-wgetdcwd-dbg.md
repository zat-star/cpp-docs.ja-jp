---
title: "_getdcwd_dbg、_wgetdcwd_dbg | Microsoft Docs"
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
  - "_getdcwd_dbg"
  - "_wgetdcwd_dbg"
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
  - "_getdcwd_dbg"
  - "getdcwd_dbg"
  - "_wgetdcwd_dbg"
  - "wgetdcwd_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getdcwd_dbg 関数"
  - "_wgetdcwd_dbg 関数"
  - "現在の作業ディレクトリ"
  - "ディレクトリ [C++], 現在の作業"
  - "getdcwd_dbg 関数"
  - "wgetdcwd_dbg 関数"
  - "作業ディレクトリ"
ms.assetid: 266bf6f0-0417-497f-963d-2e0f306d9385
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _getdcwd_dbg、_wgetdcwd_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\_getdcwd、\_wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md) 関数のデバッグ バージョン \(デバッグ中のみ使用可能\)。  
  
## 構文  
  
```  
char *_getdcwd_dbg(    int drive,    char *buffer,    int maxlen,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wgetdcwd_dbg(    int drive,    wchar_t *buffer,    int maxlen,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### パラメーター  
 `drive`  
 ディスク ドライブの名前。  
  
 `buffer`  
 パスの格納場所。  
  
 `maxlen`  
 文字数でのパスの最大長: `_getdcwd_dbg`の場合は `char`、および `_wgetdcwd_dbg` の場合は `wchar_t`。  
  
 `blockType`  
 要求するメモリ ブロックの種類: `_CLIENT_BLOCK`または `_NORMAL_BLOCK`。  
  
 `filename`  
 割り当て操作を要求したソース ファイル名へのポインターまたは `NULL`。  
  
 `linenumber`  
 割り当て操作が要求されたソース ファイル内の行番号または `NULL`。  
  
## 戻り値  
 `buffer` へのポインターを返します。  `NULL` 戻り値はエラーを示し、`errno` は、`ENOMEM` に設定され、`maxlen` バイトを割り当てるのにメモリが不足している \(`NULL` の引数が `buffer` として指定されている場合\) ことを示すか、または `ERANGE` に設定され、パスが `maxlen` 文字より長いことを示します。  詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `_getdcwd_dbg` および `_wgetdcwd_dbg` 関数は `_getdcwd` および `_wgetdcwd` と同じものですが、`_DEBUG` が定義されている場合に、`buffer` パラメーターとして `NULL` が渡されると、これらの関数はメモリを割り当てるために `malloc` および `_malloc_dbg` のデバッグ バージョンを使用する点が異なります。  詳細については、「[\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)」を参照してください。  
  
 多くの場合、これらの関数を明示的に呼び出す必要はありません。  代わりに、`_CRTDBG_MAP_ALLOC` フラグを定義できます。  `_CRTDBG_MAP_ALLOC` が定義されている場合、`_getdcwd` および `_wgetdcwd` の呼び出しはそれぞれ `_getdcwd_dbg` および `_wgetdcwd_dbg` にマップし直され、`blockType` が `_NORMAL_BLOCK` に設定されます。  そのため、ヒープ ブロックを `_CLIENT_BLOCK` としてマークする場合以外は、これらの関数を明示的に呼び出す必要はありません。  詳細については、「[デバッグ ヒープ上のメモリ ブロックの型](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tgetdcwd_dbg`|`_getdcwd_dbg`|`_getdcwd_dbg`|`_wgetdcwd_dbg`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_getdcwd_dbg`|\<crtdbg.h\>|  
|`_wgetdcwd_dbg`|\<crtdbg.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 <xref:System.Environment.CurrentDirectory%2A?displayProperty=fullName>  
  
## 参照  
 [\_getdcwd、\_wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)   
 [ディレクトリ制御](../../c-runtime-library/directory-control.md)   
 [デバッグ バージョンのヒープ割り当て関数](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)