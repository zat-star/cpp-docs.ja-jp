---
title: "_access_s、_waccess_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_access_s"
  - "_waccess_s"
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
  - "waccess_s"
  - "access_s"
  - "_waccess_s"
  - "_access_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_access_s 関数"
  - "_taccess_s 関数"
  - "_waccess_s 関数"
  - "access_s 関数"
  - "taccess_s 関数"
  - "waccess_s 関数"
ms.assetid: fb3004fc-dcd3-4569-8b27-d817546e947e
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# _access_s、_waccess_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

読み取り\/書き込みファイル アクセス許可が決まります。  この関数は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[\_access、\_waccess](../../c-runtime-library/reference/access-waccess.md) のセキュリティが強化されたバージョンです。  
  
## 構文  
  
```  
errno_t _access_s(   
   const char *path,   
   int mode   
);  
errno_t _waccess_s(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### パラメーター  
 `path`  
 ファイルまたはディレクトリ パス。  
  
 `mode`  
 アクセス許可の設定。  
  
## 戻り値  
 ファイルに特定のモードに応じて、各関数は 0。  名前付きなファイルが特定のモードであり、アクセス可能である関数の戻り値はエラー コードを返します。  この場合、関数の戻り値は次のように、また同じ値に設定 `errno` のエラー コードを設定します。  
  
 `EACCES`  
 アクセスの拒否。  ファイルのアクセス許可は指定されたアクセスができません。  
  
 `ENOENT`  
 ファイル名またはパスが見つかりません。  
  
 `EINVAL`  
 無効なパラメーター。  
  
 詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 ファイルを使用すると、`_access_s` 関数は指定されたファイルがあり、`mode`の値で指定されたようにアクセスできるかどうかを判定します。  ディレクトリを使用すると、`_access_s` は、指定したディレクトリが存在するかどうかを決定します。  [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] 以降のオペレーティング システムでは、すべてのディレクトリが読み取りおよび書き込みアクセス。  
  
|モード値|チェックはのファイル。|  
|----------|-----------------|  
|00|プロシージャだけです。|  
|02|アクセス許可を記述します。|  
|04|読み取りアクセス許可。|  
|06|アクセス許可の読み取りと書き込み。|  
  
 ファイルの読み取りまたは書き込みアクセス許可はファイルを開くには、機能を確認するだけでは不十分です。  たとえば、ファイルが別のプロセスによってロックされている場合は、0 を返します `_access_s` がアクセスできないことがあります。  
  
 `_waccess_s` は `_waccess_s` への `path` の引数はワイド文字列の `_access_s`のワイド文字バージョンです。  それ以外では、`_waccess_s` と `_access_s` の動作は同じです。  
  
 これらの関数では、パラメーターの検証が行われます。  `path` が `NULL` である場合は `mode` が有効なモードを指定しない場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_taccess_s`|`_access_s`|`_access_s`|`_waccess_s`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|----------|------------|----------------|  
|`_access_s`|\<io.h\>|\<errno.h\>|  
|`_waccess_s`|\<wchar.h または\> io.h \<\>|\<errno.h\>|  
  
## 使用例  
 この例が存在するかどうか、および書き込みが許可されているかどうか crt\_access\_s.c という名前のファイルをチェック アウトするために `_access_s` を使用します。  
  
```  
// crt_access_s.c  
  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    errno_t err = 0;  
  
    // Check for existence.   
    if ((err = _access_s( "crt_access_s.c", 0 )) == 0 )  
    {  
        printf_s( "File crt_access_s.c exists.\n" );  
  
        // Check for write permission.   
        if ((err = _access_s( "crt_access_s.c", 2 )) == 0 )  
        {  
            printf_s( "File crt_access_s.c does have "  
                      "write permission.\n" );  
        }  
        else  
        {  
            printf_s( "File crt_access_s.c does not have "  
                      "write permission.\n" );  
        }  
    }  
    else  
    {  
        printf_s( "File crt_access_s.c does not exist.\n" );  
    }  
}  
```  
  
  **ファイル crt\_access\_s.c です。**  
**ファイル crt\_access\_s.c はアクセス許可を記述することはありません。**   
## 同等の .NET Framework 関数  
 <xref:System.IO.FileAccess?displayProperty=fullName>  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [\_access、\_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [\_chmod、\_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_fstat、\_fstat32、\_fstat64、\_fstati64、\_fstat32i64、\_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_open、\_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_stat、\_wstat 関数](../../c-runtime-library/reference/stat-functions.md)