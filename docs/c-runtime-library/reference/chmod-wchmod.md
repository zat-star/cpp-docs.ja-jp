---
title: "_chmod、_wchmod | Microsoft Docs"
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
  - "_chmod"
  - "_wchmod"
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
  - "_chmod"
  - "_wchmod"
  - "wchmod"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_chmod 関数"
  - "_wchmod 関数"
  - "chmod 関数"
  - "ファイルのアクセス許可 [C++]"
  - "ファイル [C++], 変更 (アクセス許可を)"
  - "wchmod 関数"
ms.assetid: 92f7cb86-b3b0-4232-a599-b8c04a2f2c19
caps.latest.revision: 23
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _chmod、_wchmod
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルのアクセス許可の設定を変更します。  
  
## 構文  
  
```  
  
      int _chmod(   
   const char *filename,  
   int pmode   
);  
int _wchmod(   
   const wchar_t *filename,  
   int pmode   
);  
```  
  
#### パラメーター  
 `filename`  
 既存のファイルの名前。  
  
 `pmode`  
 ファイルのアクセス許可の設定。  
  
## 戻り値  
 これらの関数は、アクセス許可の設定が正常に変更された場合は 0 を返します。  戻り値 –1 は失敗を示します。  指定したファイルが存在する場合は、`errno` は `ENOENT`;に設定されます。パラメーターが無効な場合、`errno` は `EINVAL`に設定されます。  
  
## 解説  
 ファイルのアクセス許可の設定が `filename`で指定した `_chmod` の関数の変更*。*アクセス許可は、ファイルに対する読み取りと書き込みアクセスを制御します。  整数式 `pmode` は SYS\\Stat.h で次の記号定数 1 のいずれかまたは両方を定義しています。  
  
 `_S_IWRITE`  
 許可される書き込み。  
  
 `_S_IREAD`  
 許可される読み取り。  
  
 `_S_IREAD | _S_IWRITE`  
 許可されるの読み取りと書き込み。  
  
 定数は、両方とも提供されると、`OR` のビットごとのな演算子と結合されます。         `|` \).  記述するアクセス許可、ファイルが読み取り専用されません。  すべてのファイルを読み取り、常にです。; 書き込み専用アクセス許可を与えることはできません。  したがって、`_S_IWRITE` モードと `_S_IREAD | _S_IWRITE` は等価です。  
  
 `_wchmod` 関数は、`_chmod` 関数のワイド文字バージョンです。`_wchmod` 関数の引数 `filename` は、ワイド文字列です。  それ以外では、`_wchmod` と `_chmod` の動作は同じです。  
  
 この関数は、パラメーターを検証します。  `pmode` がマニフェスト定数の 1 種類の組み合わせで、別の一連の定数を組み込む、それらは無視されます。  `filename` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続 `errno` は `EINVAL` および関数の戻り値が \-1 に設定されます。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tchmod`|`_chmod`|`_chmod`|`_wchmod`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|----------|------------|----------------|  
|`_chmod`|\<io.h\>|\<sys\/types.h、sys\> \<\/stat.h、errno.h\> \<\>|  
|`_wchmod`|\<io.h または\> wchar.h \<\>|\<sys\/types.h、sys\> \<\/stat.h、errno.h\> \<\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_chmod.c  
// This program uses _chmod to  
// change the mode of a file to read-only.  
// It then attempts to modify the file.  
//  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
// Change the mode and report error or success   
void set_mode_and_report(char * filename, int mask)  
{  
   // Check for failure   
   if( _chmod( filename, mask ) == -1 )  
   {  
      // Determine cause of failure and report.   
      switch (errno)  
      {  
         case EINVAL:  
            fprintf( stderr, "Invalid parameter to chmod.\n");  
            break;  
         case ENOENT:  
            fprintf( stderr, "File %s not found\n", filename );  
            break;  
         default:  
            // Should never be reached   
            fprintf( stderr, "Unexpected error in chmod.\n" );  
       }  
   }  
   else  
   {  
      if (mask == _S_IREAD)  
        printf( "Mode set to read-only\n" );  
      else if (mask & _S_IWRITE)  
        printf( "Mode set to read/write\n" );  
   }  
   fflush(stderr);  
}  
  
int main( void )  
{   
  
   // Create or append to a file.   
   system( "echo /* End of file */ >> crt_chmod.c_input" );  
  
   // Set file mode to read-only:   
   set_mode_and_report("crt_chmod.c_input ", _S_IREAD );  
  
   system( "echo /* End of file */ >> crt_chmod.c_input " );  
  
   // Change back to read/write:   
   set_mode_and_report("crt_chmod.c_input ", _S_IWRITE );  
  
   system( "echo /* End of file */ >> crt_chmod.c_input " );   
}   
```  
  
  **`テキスト行。` `テキスト行。`読み取り専用に設定されるモード**  
**アクセスが拒否されました。**  
**読み取り\/書き込みに設定されるモード**   
## 同等の .NET Framework 関数  
  
-   [System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx)  
  
-   [System::Security::Permissions::FileIOPermission](https://msdn.microsoft.com/en-us/library/system.security.permissions.fileiopermission.aspx)  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [\_access、\_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [\_creat、\_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_fstat、\_fstat32、\_fstat64、\_fstati64、\_fstat32i64、\_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_open、\_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_stat、\_wstat 関数](../../c-runtime-library/reference/stat-functions.md)