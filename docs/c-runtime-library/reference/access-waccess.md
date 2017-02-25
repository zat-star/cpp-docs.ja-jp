---
title: "_access、_waccess | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_access"
  - "_waccess"
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
  - "_waccess"
  - "_access"
  - "taccess"
  - "waccess"
  - "_taccess"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_access 関数"
  - "_taccess 関数"
  - "_waccess 関数"
  - "access 関数"
  - "taccess 関数"
  - "waccess 関数"
ms.assetid: ba34f745-85c3-49e5-a7d4-3590bd249dd3
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# _access、_waccess
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルが読み取り専用かがないかどうかを判定します。  セキュリティが強化されたバージョンを使用できるようになりました。「[\_access\_s、\_waccess\_s](../../c-runtime-library/reference/access-s-waccess-s.md)」を参照してください。  
  
## 構文  
  
```  
int _access(   
   const char *path,   
   int mode   
);  
int _waccess(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### パラメーター  
 `path`  
 ファイルまたはディレクトリ パス。  
  
 `mode`  
 読み取り\/書き込み属性。  
  
## 戻り値  
 ファイルに特定のモードに応じて、各関数は 0。  名前付きなファイルが存在せず、特定のモードがある関数の戻り値–1; この場合、`errno` を次の表に示すように設定されます。  
  
 `EACCES`  
 拒否されたアクセス: ファイルのアクセス許可は指定されたアクセスができません。  
  
 `ENOENT`  
 ファイル名またはパスが見つかりません。  
  
 `EINVAL`  
 無効なパラメーター。  
  
 リターン コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 ファイルを使用すると、`_access` 関数は指定されたファイルまたはディレクトリが存在し、`mode`の値で指定された属性がかどうかです。  ディレクトリを使用すると、`_access` は、指定したディレクトリが存在するかどうかだけを; [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] 以降のオペレーティング システムでは、すべてのディレクトリが読み取りおよび書き込みアクセス。  
  
|`mode` の値|チェックはのファイル。|  
|---------------|-----------------|  
|00|プロシージャだけ|  
|02|書き込み専用|  
|04|読み取り専用|  
|06|読み取りと書き込みを行います。|  
  
 この関数は、ファイルとディレクトリが読み取り専用かどうかはチェックされません。ファイル システム セキュリティ設定を確認します。  それぞれのアクセス トークンが必要です。  ファイルシステムのセキュリティの詳細については、「[トークンにアクセスします。](http://msdn.microsoft.com/library/windows/desktop/aa374909)」を参照してください。  ATL クラスはこの機能を提供するために存在; [CAccessToken クラス](../Topic/CAccessToken%20Class.md)を参照してください。  
  
 `_waccess` 関数は、`_access` 関数のワイド文字バージョンです。`_waccess` 関数の引数 `path` は、ワイド文字列です。  それ以外では、`_waccess` と `_access` の動作は同じです。  
  
 この関数は、パラメーターを検証します。  `path` が `NULL` である場合は `mode` が有効なモードを指定しない場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続 `EINVAL` と戻りに関数を設定 `errno` \-1。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_taccess`|`_access`|`_access`|`_waccess`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|省略可能なヘッダー|  
|----------|------------|---------------|  
|`_access`|\<io.h\>|\<errno.h\>|  
|`_waccess`|\<wchar.h または\> io.h \<\>|\<errno.h\>|  
  
## 使用例  
 次の例では、かどうか、および書き込みが許可されているかどうか crt\_ACCESS.C という名前のファイルをチェック アウトするために `_access` を使用します。  
  
```  
// crt_access.c  
// compile with: /W1  
// This example uses _access to check the file named  
// crt_ACCESS.C to see if it exists and if writing is allowed.  
  
#include  <io.h>  
#include  <stdio.h>  
#include  <stdlib.h>  
  
int main( void )  
{  
    // Check for existence.  
    if( (_access( "crt_ACCESS.C", 0 )) != -1 )  
    {  
        printf_s( "File crt_ACCESS.C exists.\n" );  
  
        // Check for write permission.  
        // Assume file is read-only.  
        if( (_access( "crt_ACCESS.C", 2 )) == -1 )  
            printf_s( "File crt_ACCESS.C does not have write permission.\n" );  
    }  
}  
```  
  
  **ファイル crt\_ACCESS.C です。**  
**ファイル crt\_ACCESS.C はアクセス許可を記述することはありません。**   
## 同等の .NET Framework 関数  
 <xref:System.IO.FileAccess?displayProperty=fullName>  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [\_chmod、\_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_fstat、\_fstat32、\_fstat64、\_fstati64、\_fstat32i64、\_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_open、\_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_stat、\_wstat 関数](../../c-runtime-library/reference/stat-functions.md)