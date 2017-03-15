---
title: "_getdcwd、_wgetdcwd | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_getdcwd"
  - "_wgetdcwd"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wgetdcwd"
  - "getdcwd"
  - "_getdcwd"
  - "tgetdcwd"
  - "_wgetdcwd"
  - "_tgetdcwd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wgetdcwd 関数"
  - "作業ディレクトリ"
  - "getdcwd 関数"
  - "_getdcwd 関数"
  - "_wgetdcwd 関数"
  - "現在の作業ディレクトリ"
  - "ディレクトリ [C++] 現在の作業"
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _getdcwd、_wgetdcwd
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定されたドライブの現在の作業ディレクトリの完全なパスを取得します。  
  
## 構文  
  
```  
char *_getdcwd(   
   int drive,  
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetdcwd(   
   int drive,  
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### パラメーター  
 `drive`  
 ドライブを指定する負でない整数 \(0 \= 既定のドライブ、1 \= A、2 \= B など\)。  
  
 指定されたドライブが使用できない場合、またはドライブの種類 \(たとえば、リムーバブル ドライブ、固定ドライブ、CD\-ROM ドライブ、RAM ディスク ドライブ、ネットワーク ドライブ\) を特定できない場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、正しくないパラメーター ハンドラーが呼び出されます。  
  
 `buffer`  
 パスが、記憶域の場所または **NULL**します。  
  
 場合 **NULL** を指定すると、この関数は、少なくとものバッファーを割り当てます `maxlen` を使用してサイズ **malloc**, 、および戻り値の `_getdcwd` 、割り当てられたバッファーへのポインターです。 バッファーは、`free` を呼び出し、ポインターに渡すことによって解放できます。  
  
 `maxlen`  
 文字数でパスの最大長を指定する 0 以外の正の整数。`char` では `_getdcwd`、`wchar_t` では `_wgetdcwd`。  
  
 `maxlen` が 0 以下の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されている正しくないパラメーター ハンドラーが呼び出されます。  
  
## 戻り値  
 指定されたドライブの現在の作業ディレクトリの完全なパスを表す文字列へのポインター、またはエラーを示す `NULL`。  
  
 `buffer` を `NULL` に指定し、`maxlen` 文字を割り当てるためのメモリが不足している場合は、エラーが発生し、`errno` は `ENOMEM` に設定されます。 終端の null 文字を含むパスの長さが `maxlen` を超える場合、エラーが発生し、`errno` が `ERANGE` に設定されます。 これらのエラー コードについて詳しくは、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」をご覧ください。  
  
## 解説  
 `_getdcwd` 関数は、指定されたドライブの現在の作業ディレクトリの完全なパスを取得し、それを `buffer` に格納します。 現在の作業ディレクトリがルートに設定されている場合、文字列は円記号 \(\\\) で終わります。 現在の作業ディレクトリがルート以外のディレクトリに設定されている場合、文字列は、円記号ではなく、ディレクトリの名前で終わります。  
  
 `_wgetdcwd` は、`_getdcwd` のワイド文字バージョンで、その `buffer` パラメーターと戻り値はワイド文字列になります。 それ以外では、`_wgetdcwd` と `_getdcwd` の動作は同じです。  
  
 依存している場合でも、この関数はスレッド セーフである **GetFullPathName**, 、これはスレッド セーフではありません。 マルチ スレッド アプリケーションがこの両方の関数を呼び出す場合、スレッド セーフを侵害するただし、および **GetFullPathName**します。 詳細についてを参照してください [MSDN ライブラリ](http://go.microsoft.com/fwlink/?LinkID=150542) 検索して **GetFullPathName**します。  
  
 `_nolock` サフィックスが付いているこの関数のバージョンは、スレッドセーフではなく、他のスレッドによる干渉から保護されないという点を除いて、この関数とまったく同じように動作します。 詳細については、「[\_getdcwd\_nolock、\_wgetdcwd\_nolock](../../c-runtime-library/reference/getdcwd-nolock-wgetdcwd-nolock.md)」を参照してください。  
  
 `_DEBUG` と `_CRTDBG_MAP_ALLOC` が定義されている場合、`_getdcwd` と `_wgetdcwd` への呼び出しは `_getdcwd_dbg` と `_wgetdcwd_dbg` への呼び出しに置き換えられるので、メモリ割り当てをデバッグできます。 詳しくは [\_getdcwd\_dbg、\_wgetdcwd\_dbg](../../c-runtime-library/reference/getdcwd-dbg-wgetdcwd-dbg.md) をご覧ください。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tgetdcwd`|`_getdcwd`|`_getdcwd`|`_wgetdcwd`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_getdcwd`|\<direct.h\>|  
|`_wgetdcwd`|\<direct.h\> または \<wchar.h\>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## 使用例  
 [\_getdrive](../../c-runtime-library/reference/getdrive.md) の例をご覧ください。  
  
## 同等の .NET Framework 関数  
 [System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)  
  
## 参照  
 [ディレクトリ制御](../../c-runtime-library/directory-control.md)   
 [\_chdir、\_wchdir](../Topic/_chdir,%20_wchdir.md)   
 [\_getcwd、\_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [\_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [\_mkdir、\_wmkdir](../Topic/_mkdir,%20_wmkdir.md)   
 [\_rmdir、\_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)