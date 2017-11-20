---
title: "fclose、_fcloseall | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fclose
- _fcloseall
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
- fclose
- _fcloseall
dev_langs: C++
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d0cb985b4e2ddeea853ccd40668a3e378834e68a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="fclose-fcloseall"></a>fclose、_fcloseall
ストリームを閉じるか (`fclose`)、またはすべての開いているストリームを閉じます (`_fcloseall`)。  
  
## <a name="syntax"></a>構文  
  
```  
int fclose(   
   FILE *stream   
);  
int _fcloseall( void );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## <a name="return-value"></a>戻り値  
 ストリームが正常に閉じられた場合、`fclose` は 0 を返します。 `_fcloseall` は、閉じられたストリームの総数を返します。 どちらの関数もエラーを示す `EOF` を返します。  
  
## <a name="remarks"></a>コメント  
 `fclose` 関数は、`stream` を閉じます。 `stream` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、`fclose` は `errno` を `EINVAL` に設定し、`EOF` を返します。 この関数を呼び出す前に必ず、`stream` ポインターをチェックすることをお勧めします。  
  
 エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
 `_fcloseall` 関数は、`stdin`、`stdout`、および `stderr` (MS-DOS では、`_stdaux` と`_stdprn` も) を除くすべての開いているストリームを閉じます。 また、`tmpfile` によって作成された一時ファイルも閉じて削除します。 両方の関数では、終了する前に、ストリームに関連付けられているすべてのバッファーがフラッシュされます。 システムによって割り当てられたバッファーについては、ストリームを閉じる際に解放します。 `setbuf` と `setvbuf` を使用してユーザーが割り当てたバッファーは、自動的に解放されません。  
  
 **注:** これらの関数を使用してストリームを閉じる場合は、ストリームだけでなく基になるファイル記述子と OS ファイル ハンドル (またはソケット) も閉じられます。 したがって、ファイル ハンドルまたはファイル記述子として元々開いていたファイルが `fclose` によって閉じられる場合は、ファイル記述子を閉じるための `_close` の呼び出し、ファイル ハンドルを閉じるための Win32 関数 `CloseHandle` の呼び出しを行わないでください。  
  
 `fclose` と `_fcloseall` には、他のスレッドからの干渉に対処するコードが含まれています。 `_fclose_nolock` のロックしないバージョンについては、「`fclose`」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`fclose`|\<stdio.h>|  
|`_fcloseall`|\<stdio.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
 「[fopen](../../c-runtime-library/reference/fopen-wfopen.md)」の例を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_fdopen、_wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen、_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen、_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)