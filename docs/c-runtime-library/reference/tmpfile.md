---
title: "tmpfile | Microsoft Docs"
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
  - "tmpfile"
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
  - "tmpfile"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "一時ファイル"
  - "tmpfile 関数"
  - "一時ファイル、作成"
ms.assetid: c4a4dc24-70da-438d-ae4e-98352d88e375
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tmpfile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

一時ファイルを作成します。  この関数は、より安全なバージョンが空いたらできません。; [tmpfile\_s](../Topic/tmpfile_s.md)を参照してください。  
  
## 構文  
  
```  
FILE *tmpfile( void );  
```  
  
## 戻り値  
 成功すると、`tmpfile` はストリーム ポインターを返します。  それ以外の場合は `NULL` のポインターを返します。  
  
## 解説  
 `tmpfile` 関数は一時ファイルを作成し、そのストリームへのポインターを返します。  一時ファイルは、ルート ディレクトリに作成されます。  ルート以外のディレクトリに一時ファイルを作成するには、[tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) または [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) を [fopen](../../c-runtime-library/reference/fopen-wfopen.md) と共に使用します。  
  
 ファイルを開くことができない場合 `tmpfile` は `NULL` のポインターを返します。  この一時ファイルは、ファイルが閉じられたとき、プログラムが正常に終了したとき、または `_rmtmp` が呼び出されたときに、自動的に削除されます。これは、現在の作業ディレクトリが変更されていないことを前提とします。  一時ファイルは `w+b` \(バイナリ読み書き両用\) モードで開かれます。  
  
 エラーが TMP\_MAX よりも STDIO.H を \(インクルード\) `tmpfile`"を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`tmpfile`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
> [!NOTE]
>  この例を Windows Vista で実行するには管理特権が必要です。  
  
```  
// crt_tmpfile.c  
// compile with: /W3  
// This program uses tmpfile to create a  
// temporary file, then deletes this file with _rmtmp.  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   int  i;  
  
   // Create temporary files.  
   for( i = 1; i <= 3; i++ )  
   {  
      if( (stream = tmpfile()) == NULL ) // C4996  
      // Note: tmpfile is deprecated; consider using tmpfile_s instead  
         perror( "Could not open new temporary file\n" );  
      else  
         printf( "Temporary file %d was created\n", i );  
   }  
  
   // Remove temporary files.  
   printf( "%d temporary files deleted\n", _rmtmp() );  
}  
```  
  
  **一時ファイルが作成された 1**  
**一時ファイルが作成された 2**  
**一時ファイルが作成された 3**  
**削除される 3 種類の一時ファイル**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [\_rmtmp](../Topic/_rmtmp.md)   
 [\_tempnam、\_wtempnam、tmpnam、\_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)