---
title: "_splitpath_s、_wsplitpath_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wsplitpath_s"
  - "_splitpath_s"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wsplitpath_s"
  - "splitpath_s"
  - "_splitpath_s"
  - "wsplitpath_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_splitpath_s 関数"
  - "_wsplitpath_s 関数"
  - "パス名"
  - "パス名"
  - "splitpath_s 関数"
  - "wsplitpath_s 関数"
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
caps.latest.revision: 29
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _splitpath_s、_wsplitpath_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

パス名を構成要素に分解します。  [\_splitpath、\_wsplitpath](../Topic/_splitpath,%20_wsplitpath.md) には、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、セキュリティが強化されたバージョンがあります。  
  
## 構文  
  
```  
errno_t _splitpath_s(  
   const char * path,  
   char * drive,  
   size_t driveNumberOfElements,  
   char * dir,  
   size_t dirNumberOfElements,  
   char * fname,  
   size_t nameNumberOfElements,  
   char * ext,   
   size_t extNumberOfElements  
);  
errno_t _wsplitpath_s(  
   const wchar_t * path,  
   wchar_t * drive,  
   size_t driveNumberOfElements,  
   wchar_t *dir,  
   size_t dirNumberOfElements,  
   wchar_t * fname,  
   size_t nameNumberOfElements,  
   wchar_t * ext,  
   size_t extNumberOfElements  
);  
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>  
errno_t _splitpath_s(  
   const char *path,  
   char (&drive)[drivesize],  
   char (&dir)[dirsize],  
   char (&fname)[fnamesize],  
   char (&ext)[extsize]  
); // C++ only  
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>  
errno_t _wsplitpath_s(  
   const wchar_t *path,  
   wchar_t (&drive)[drivesize],  
   wchar_t (&dir)[dirsize],  
   wchar_t (&fname)[fnamesize],  
   wchar_t (&ext)[extsize]  
); // C++ only  
```  
  
#### パラメーター  
 \[入力\] `path`  
 完全パス。  
  
 \[出力\] `drive`  
 ドライブ文字。後ろにコロン \(`:`\) が付きます。  ドライブ文字が不要な場合は、このパラメーターに `NULL` を渡すことができます。  
  
 \[入力\] `driveNumberOfElements`  
 `drive` バッファーのサイズ \(1 バイト文字またはワイド文字の数\)。  `drive` が `NULL` の場合は、この値を 0 にする必要があります。  
  
 \[出力\] `dir`  
 ディレクトリ パスと末尾のスラッシュ。  区切り記号にはスラッシュ \(`/` \) および円記号 \(`\`\) を使用でき、両方を混在させることもできます。  ディレクトリ パスが不要な場合は、このパラメーターに `NULL` を渡すことができます。  
  
 \[入力\] `dirNumberOfElements`  
 `dir` バッファーのサイズ \(1 バイト文字またはワイド文字の数\)。  `dir` が `NULL` の場合は、この値を 0 にする必要があります。  
  
 \[出力\] `fname`  
 基本ファイル名 \(拡張子なし\)。  ファイル名が不要な場合は、このパラメーターに `NULL` を渡すことができます。  
  
 \[入力\] `nameNumberOfElements`  
 `fname` バッファーのサイズ \(1 バイト文字またはワイド文字の数\)。  `fname` が `NULL` の場合は、この値を 0 にする必要があります。  
  
 \[出力\] `ext`  
 ファイル名の拡張子。先頭にピリオド \(**.**\) が付きます。ファイル名の拡張子が不要な場合は、このパラメーターに `NULL` を渡すことができます。  
  
 \[入力\] `extNumberOfElements`  
 `ext` バッファーのサイズ \(1 バイト文字またはワイド文字の数\)。  `ext` が `NULL` の場合は、この値を 0 にする必要があります。  
  
## 戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。  
  
### エラー条件  
  
|状態|戻り値|  
|--------|---------|  
|`path` が  `NULL`|`EINVAL`|  
|`drive` が `NULL`、`driveNumberOfElements` がゼロ以外|`EINVAL`|  
|`drive` が `NULL` 以外、`driveNumberOfElements` がゼロ|`EINVAL`|  
|`dir` が `NULL`、`dirNumberOfElements` がゼロ以外|`EINVAL`|  
|`dir` が `NULL` 以外、`dirNumberOfElements` がゼロ|`EINVAL`|  
|`fname` が `NULL`、`nameNumberOfElements` がゼロ以外|`EINVAL`|  
|`fname` が `NULL` 以外、`nameNumberOfElements` がゼロ|`EINVAL`|  
|`ext` が `NULL`、`extNumberOfElements` がゼロ以外|`EINVAL`|  
|`ext` が `NULL` 以外、`extNumberOfElements` がゼロ|`EINVAL`|  
  
 上記のいずれかの条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
 バッファーが短すぎて結果を保存できない場合、この関数はすべてのバッファーを消去して空の文字列にし、`errno` を `ERANGE` に設定し、`ERANGE` を返します。  
  
## 解説  
 `_splitpath_s`  関数は、パスを 4 つの構成要素に分解します。  `_splitpath_s` は現在使用中のマルチバイト コード ページに従ってマルチバイト文字列を認識し、必要に応じてマルチバイト文字列引数を自動的に処理します。  `_wsplitpath_s`  は `_splitpath_s` のワイド文字バージョンであり、`_``wsplitpath_s` ``  の引数はワイド文字列です。  それ以外では、これらの関数の動作は同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tsplitpath_s`|`_splitpath_s`|`_splitpath_s`|`_wsplitpath_s`|  
  
 完全なパスの各構成要素は、別々のバッファーに格納されます。各ファイル構成要素に許容される最大サイズは、STDLIB.H に定義されているマニフェスト定数の `_MAX_DRIVE`、`_MAX_DIR`、`_MAX_FNAME`、および `_MAX_EXT` で指定されます。  ファイル構成要素のサイズが対応するマニフェスト定数を超えると、ヒープの破損が発生します。  
  
 マニフェスト定数の値を次の表に示します。  
  
|名前|値|  
|--------|-------|  
|\_MAX\_DRIVE|3|  
|\_MAX\_DIR|256|  
|\_MAX\_FNAME|256|  
|\_MAX\_EXT|256|  
  
 完全パスにファイル名などの構成要素が含まれていない場合、`_splitpath_s` は、対応するバッファーに空の文字列を割り当てます。  
  
 C\+\+ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
 これらの関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。  この動作を無効にするには、[\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md) を使用します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_splitpath_s`|\<stdlib.h\>|  
|`_wsplitpath_s`|\<stdlib.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 [\_makepath\_s、\_wmakepath\_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md) 関数の例を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [\_splitpath、\_wsplitpath](../Topic/_splitpath,%20_wsplitpath.md)   
 [\_fullpath、\_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_makepath、\_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)