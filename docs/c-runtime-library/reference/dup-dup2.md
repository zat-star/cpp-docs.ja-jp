---
title: "_dup、_dup2 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _dup
- _dup2
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _dup2
- _dup
dev_langs:
- C++
helpviewer_keywords:
- _dup2 function
- dup function
- file handles [C++], duplicating
- file handles [C++], reassigning
- dup2 function
- _dup function
ms.assetid: 4d07e92c-0d76-4832-a770-dfec0e7a0cfa
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: a85a26fbe7ab8417ea9ecd3c43745789117ac856
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="dup-dup2"></a>_dup、_dup2
開いているファイルの 2 つ目のファイル記述子 (`_dup`) を作成するか、ファイル記述子 (`_dup2`) を再割り当てします。  
  
## <a name="syntax"></a>構文  
  
```  
int _dup(   
   int fd   
);  
int _dup2(   
   int fd1,  
   int fd2   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fd`, `fd1`  
 開いているファイルを参照するファイル記述子。  
  
 `fd2`  
 任意のファイル記述子。  
  
## <a name="return-value"></a>戻り値  
 `_dup` は新しいファイル記述子を返します。 `_dup2` は成功したことを示すために 0 を返します。 エラーが発生した場合、各関数は-1 を返しセット`errno`に`EBADF`ファイル記述子が有効でない場合または`EMFILE`ファイル記述子をこれ以上使用可能な場合です。 ファイル記述子が無効な場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、関数によって無効なパラメーター ハンドラーも開始されます。  
  
 リターン コードについて詳しくは、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `_dup` 関数と `_dup2` 関数は、2 つ目のファイル記述子を現在開いているファイルに関連付けます。 これらの関数は、`stdout` のような定義済みファイル記述子を別のファイルに関連付けるために使用できます。 ファイル操作はいずれかのファイル記述子を使用して実行できます。 新しい記述子の作成によって、ファイルに対するアクセス権の種類が影響を受けることはありません。 `_dup` は、指定されたファイルに対して次に使用できるファイル記述子を返します。 `_dup2` は `fd2` に `fd1` と同じファイルを参照するよう強制します。 呼び出し時に `fd2` が開いているファイルに関連付けられている場合は、そのファイルが閉じられます。  
  
 `_dup` と `_dup2` はいずれもファイル記述子をパラメーターとして受け取ります。 これらの関数のいずれかに `(FILE *)` ストリームを渡すには、[_fileno](../../c-runtime-library/reference/fileno.md) を使います。 `fileno` ルーチンは、指定したストリームに現在関連付けられているファイル記述子を返します。 次の例は、`stderr` (Stdio.h で `FILE` `*` として定義) をファイル記述子に関連付ける方法です。  
  
```  
int cstderr = _dup( _fileno( stderr ));  
```  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_dup`|\<io.h>|  
|`_dup2`|\<io.h>|  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。 コンソール (`stdin`、`stdout`、および `stderr`) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_dup.c  
// This program uses the variable old to save  
// the original stdout. It then opens a new file named  
// DataFile and forces stdout to refer to it. Finally, it  
// restores stdout to its original state.  
//  
  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int old;  
   FILE *DataFile;  
  
   old = _dup( 1 );   // "old" now refers to "stdout"   
                      // Note:  file descriptor 1 == "stdout"   
   if( old == -1 )  
   {  
      perror( "_dup( 1 ) failure" );  
      exit( 1 );  
   }  
   _write( old, "This goes to stdout first\n", 26 );  
   if( fopen_s( &DataFile, "data", "w" ) != 0 )  
   {  
      puts( "Can't open file 'data'\n" );  
      exit( 1 );  
   }  
  
   // stdout now refers to file "data"   
   if( -1 == _dup2( _fileno( DataFile ), 1 ) )  
   {  
      perror( "Can't _dup2 stdout" );  
      exit( 1 );  
   }  
   puts( "This goes to file 'data'\n" );  
  
   // Flush stdout stream buffer so it goes to correct file   
   fflush( stdout );  
   fclose( DataFile );  
  
   // Restore original stdout   
   _dup2( old, 1 );  
   puts( "This goes to stdout\n" );  
   puts( "The file 'data' contains:" );  
   _flushall();  
   system( "type data" );  
}  
```  
  
```Output  
This goes to stdout first  
This goes to stdout  
  
The file 'data' contains:  
This goes to file 'data'  
```  
  
## <a name="see-also"></a>関連項目  
 [下位入出力](../../c-runtime-library/low-level-i-o.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_creat、_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)
