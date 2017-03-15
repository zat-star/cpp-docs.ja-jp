---
title: "remove、_wremove | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wremove"
  - "remove"
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
  - "remove"
  - "_wremove"
  - "_tremove"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tremove 関数"
  - "_wremove 関数"
  - "ファイル [C++], 削除"
  - "ファイル [C++], 削除"
  - "remove 関数"
  - "tremove 関数"
  - "wremove 関数"
ms.assetid: b6345ec3-3289-4645-93a4-28b9e478cc19
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# remove、_wremove
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルを削除します。  
  
## 構文  
  
```  
  
      int remove(  
   const char *path   
);  
int _wremove(  
   const wchar_t *path   
);  
```  
  
#### パラメーター  
 *path*  
 削除するファイルのパス。  
  
## 戻り値  
 これらの関数は、ファイルが正常に削除された場合は 0 を返します。  それ以外の場合は、ファイルが開いている指定またはファイル名またはパスが見つからない場合、またはパスがディレクトリを指定することを示します **ENOENT** と \-1 を返し、パスが読み取り専用ファイルを設定するときに `errno` を `EACCES` にいずれか。  
  
 リターン コードの詳細については、「[\_doserrno, errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 *パス*で指定された **削除** 関数はファイルを削除します。`_wremove` は **\_remove**のワイド文字バージョンであり、; `_wremove` への *パスの* 引数はワイド文字列です。  `_wremove` と **\_remove** は別の方法で同様に動作します。  ファイルに対するすべてのハンドルは、削除する前に閉じる必要があります。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tremove`|**remove**|**remove**|`_wremove`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|**remove**|\<stdio.h または\> io.h \<\>|  
|`_wremove`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
  
```  
// crt_remove.c  
/* This program uses remove to delete crt_remove.txt */  
  
#include <stdio.h>  
  
int main( void )  
{  
   if( remove( "crt_remove.txt" ) == -1 )  
      perror( "Could not delete 'CRT_REMOVE.TXT'" );  
   else  
      printf( "Deleted 'CRT_REMOVE.TXT'\n" );  
}  
```  
  
## 入力: crt\_remove.txt  
  
```  
This file will be deleted.  
```  
  
## 出力例  
  
```  
Deleted 'CRT_REMOVE.TXT'  
```  
  
## 同等の .NET Framework 関数  
 [System::IO::File::Delete](https://msdn.microsoft.com/en-us/library/system.io.file.delete.aspx)  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [\_unlink、\_wunlink](../Topic/_unlink,%20_wunlink.md)