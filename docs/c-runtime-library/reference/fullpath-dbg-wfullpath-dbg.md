---
title: "_fullpath_dbg、_wfullpath_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wfullpath_dbg"
  - "_fullpath_dbg"
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
  - "wfullpath_dbg"
  - "_wfullpath_dbg"
  - "_fullpath_dbg"
  - "fullpath_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_fullpath_dbg 関数"
  - "_wfullpath_dbg 関数"
  - "絶対パス"
  - "fullpath_dbg 関数"
  - "相対ファイル パス"
  - "wfullpath_dbg 関数"
ms.assetid: 81f72f85-07da-4f5c-866a-598e0fb03f6b
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# _fullpath_dbg、_wfullpath_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

メモリの割り当てに `malloc` のデバッグ バージョンを使用する [\_fullpath、\_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md) のバージョン。  
  
## 構文  
  
```  
char *_fullpath_dbg(     char *absPath,    const char *relPath,    size_t maxLength,    int blockType,    const char *filename,    int linenumber  ); wchar_t *_wfullpath_dbg(     wchar_t *absPath,    const wchar_t *relPath,    size_t maxLength,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### パラメーター  
 `absPath`  
 絶対または完全パス名を格納するバッファーへのポインター、または `NULL`。  
  
 `relPath`  
 相対パス名。  
  
 `maxLength`  
 絶対パス名のバッファー \(`absPath`\) の最大長。  この長さは、`_fullpath` の場合はバイト単位ですが、`_wfullpath` の場合はワイド文字単位 \(`wchar_t`\) です。  
  
 `blockType`  
 要求するメモリ ブロックの種類。`_CLIENT_BLOCK` または `_NORMAL_BLOCK`。  
  
 `filename`  
 割り当て操作を要求したソース ファイル名へのポインターまたは `NULL`。  
  
 `linenumber`  
 割り当て操作が要求されたソース ファイル内の行番号または `NULL`。  
  
## 戻り値  
 各関数は、絶対パス名 \(`absPath`\) を格納するバッファーへのポインターを返します。  エラーがある場合 \(たとえば、`relPath` で渡される値に無効または見つからないドライブ文字が含まれている場合や、作成された絶対パス名 \(`absPath`\) の長さが `maxLength` よりも長い場合など\)、この関数は `NULL` を返します。  
  
## 解説  
 `_fullpath_dbg` および `_wfullpath_dbg` 関数は `_fullpath` および `_wfullpath` と同じものですが、**\_**`DEBUG`が定義されている場合に、最初のパラメーターとして NULL が渡されると、これらの関数はメモリを割り当てるために `malloc` および `_malloc_dbg` のデバッグ バージョンを使用する点が異なります。  `_malloc_dbg` のデバッグ機能の詳細については、「[\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)」を参照してください。  
  
 多くの場合、これらの関数を明示的に呼び出す必要はありません。  代わりに、`_CRTDBG_MAP_ALLOC` フラグを定義できます。  `_CRTDBG_MAP_ALLOC`が定義されている場合、`_fullpath` および `_wfullpath`の呼び出しはそれぞれ `_fullpath_dbg` および `_wfullpath_dbg` にマップし直され、`blockType` が `_NORMAL_BLOCK` に設定されます。  そのため、ヒープ ブロックを `_CLIENT_BLOCK` としてマークする場合以外は、これらの関数を明示的に呼び出す必要はありません。  詳細については、「[デバッグ ヒープ上のメモリ ブロックの型](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tfullpath_dbg`|`_fullpath_dbg`|`_fullpath_dbg`|`_wfullpath_dbg`|  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`_fullpath_dbg`|\<crtdbg.h\>|  
|`_wfullpath_dbg`|\<crtdbg.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 <xref:System.IO.File.Create%2A>  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [\_fullpath、\_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [デバッグ バージョンのヒープ割り当て関数](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md)