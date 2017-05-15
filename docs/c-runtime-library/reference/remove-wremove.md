---
title: "remove、_wremove | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wremove
- remove
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
- remove
- _wremove
- _tremove
dev_langs:
- C++
helpviewer_keywords:
- tremove function
- _wremove function
- files [C++], deleting
- _tremove function
- files [C++], removing
- wremove function
- remove function
ms.assetid: b6345ec3-3289-4645-93a4-28b9e478cc19
caps.latest.revision: 10
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 621a1c2ed9b44afb0f47fbac37b6c8de3cccecdf
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="remove-wremove"></a>remove、_wremove
ファイルを削除します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      int remove(  
   const char *path   
);  
int _wremove(  
   const wchar_t *path   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *path*  
 削除されるファイルのパス。  
  
## <a name="return-value"></a>戻り値  
 ファイルが正常に削除された場合、これらの関数はそれぞれ 0 を返します。 それ以外の場合は -1 を返し、`errno` を `EACCES` に設定して、パスが読み取り専用のファイルを指定、またはファイルが開かれていることを示すか、**ENOENT** に設定して、ファイル名やパスが見つからなかったか、パスがディレクトリを指定することを示します。  
  
 リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 **remove** 関数は、*path* によって指定されたファイルを削除します。 `_wremove` 関数は、**_remove** 関数のワイド文字バージョンです。`_wremove` 関数の *path* 引数は、ワイド文字列です。 それ以外では、`_wremove` と **_remove** の動作は同じです。 ファイルを削除する前に、ファイルへのすべてのハンドルを閉じる必要があります。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tremove`|**remove**|**remove**|`_wremove`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|**remove**|\<stdio.h> または \<io.h>|  
|`_wremove`|\<stdio.h> または \<wchar.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
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
  
## <a name="input-crtremovetxt"></a>入力: crt_remove.txt  
  
```  
This file will be deleted.  
```  
  
## <a name="sample-output"></a>出力例  
  
```  
Deleted 'CRT_REMOVE.TXT'  
```  
  
## <a name="see-also"></a>関連項目  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [_unlink、_wunlink](../../c-runtime-library/reference/unlink-wunlink.md)
