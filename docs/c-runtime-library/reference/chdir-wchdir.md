---
title: _chdir, _wchdir | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wchdir
- _chdir
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- tchdir
- _chdir
- _wchdir
- _tchdir
- wchdir
dev_langs:
- C++
helpviewer_keywords:
- _tchdir function
- _chdir function
- _wchdir function
- tchdir function
- wchdir function
- chdir function
- directories [C++], changing
ms.assetid: 85e9393b-62ac-45d5-ab2a-fa2217f6152e
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 75896dcec6e73b153473dd52c17b4dc95e425535
ms.lasthandoff: 02/24/2017

---
# <a name="chdir-wchdir"></a>_chdir、_wchdir
現在の作業ディレクトリを変更します。  
  
## <a name="syntax"></a>構文  
  
```  
int _chdir(   
   const char *dirname   
);  
int _wchdir(   
   const wchar_t *dirname   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dirname`  
 新しい作業ディレクトリのパス。  
  
## <a name="return-value"></a>戻り値  
 これらの関数は、成功した場合、値 0 を返します。 戻り値 –1 は失敗を示します。 指定したパスが見つからない場合、 `errno` は `ENOENT`に設定されます。 `dirname` が NULL の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、 `errno` が `EINVAL` に設定され、関数から -1 が返されます。  
  
## <a name="remarks"></a>コメント  
 `_chdir` 関数は、現在の作業ディレクトリを `dirname`で指定されたディレクトリに変更します。 `dirname` パラメーターは、既存のディレクトリを示す必要があります。 この関数は、任意のドライブの現在の作業ディレクトリを変更できます。 新しいドライブ文字が `dirname`で指定されている場合、既定のドライブ文字も同様に変更されます。 たとえば、A が既定のドライブ文字で、\BIN が現在の作業ディレクトリの場合、次の呼び出しにより、ドライブ C の現在の作業ディレクトリが変更され、C が新しい既定のドライブとして設定されます。  
  
```  
_chdir("c:\\temp");  
```  
  
 パスに省略可能な円記号 (`\`) を使用すると、C の文字列リテラルでは&1; つの円記号 (`\\`) を表すのに&2; つの円記号 (`\`) を使用する必要があります。  
  
 `_wchdir` 関数は、`_chdir` 関数のワイド文字バージョンです。`_wchdir` 関数の `dirname` 引数は、ワイド文字列 `. _wchdir` で、それ以外は `_chdir` の動作は同じです。  
  
### <a name="generic-text-routine-mapping"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tchdir`|`_chdir`|`_chdir`|`_wchdir`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_chdir`|\<direct.h>|\<errno.h>|  
|`_wchdir`|\<direct.h> または \<wchar.h>|\<errno.h>|  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_chdir.c  
// arguments: C:\WINDOWS  
  
/* This program uses the _chdir function to verify  
   that a given directory exists. */  
  
#include <direct.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main( int argc, char *argv[] )  
{  
  
   if(_chdir( argv[1] ) )  
   {  
      switch (errno)  
      {  
      case ENOENT:  
         printf( "Unable to locate the directory: %s\n", argv[1] );  
         break;  
      case EINVAL:  
         printf( "Invalid buffer.\n");  
         break;  
      default:  
         printf( "Unknown error.\n");  
      }  
   }  
   else  
      system( "dir *.exe");  
}  
```  
  
```Output  
Volume in drive C has no label.  
 Volume Serial Number is 2018-08A1  
  
 Directory of c:\windows  
  
08/29/2002  04:00 AM         1,004,032 explorer.exe  
12/17/2002  04:43 PM            10,752 hh.exe  
03/03/2003  09:24 AM            33,792 ieuninst.exe  
10/29/1998  04:45 PM           306,688 IsUninst.exe  
08/29/2002  04:00 AM            66,048 NOTEPAD.EXE  
03/03/2003  09:24 AM            33,792 Q330994.exe  
08/29/2002  04:00 AM           134,144 regedit.exe  
02/28/2003  06:26 PM            46,352 setdebug.exe  
08/29/2002  04:00 AM            15,360 TASKMAN.EXE  
08/29/2002  04:00 AM            49,680 twunk_16.exe  
08/29/2002  04:00 AM            25,600 twunk_32.exe  
08/29/2002  04:00 AM           256,192 winhelp.exe  
08/29/2002  04:00 AM           266,752 winhlp32.exe  
              13 File(s)      2,249,184 bytes  
               0 Dir(s)  67,326,029,824 bytes free  
```  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 [System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)  
  
## <a name="see-also"></a>関連項目  
 [ディレクトリ制御](../../c-runtime-library/directory-control.md)   
 [_mkdir、_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir、_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)   
 [system、_wsystem](../../c-runtime-library/reference/system-wsystem.md)
