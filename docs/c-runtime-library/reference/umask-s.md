---
title: _umask_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _umask_s
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
- unmask_s
- _umask_s
dev_langs:
- C++
helpviewer_keywords:
- masks, file-permission-setting
- _umask_s function
- masks
- file permissions [C++]
- umask_s function
- files [C++], permission settings for
ms.assetid: 70898f61-bf2b-4d8d-8291-0ccaa6d33145
caps.latest.revision: 17
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 5c8efcdf5d3f44a6cd3bbcc39f2a98e3659c95ab
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="umasks"></a>_umask_s
既定のファイル アクセス許可マスクを設定します。 「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」 (CRT のセキュリティ機能) の説明にあるとおり、セキュリティが強化されたバージョンの [_umask](../../c-runtime-library/reference/umask.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _umask_s(  
   int mode,  
   int * pOldMode  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `mode`  
 既定のアクセス許可の設定。  
  
 [出力] `oldMode`  
 アクセス許可設定の以前の値。  
  
## <a name="return-value"></a>戻り値  
 `Mode` が有効なモードを指定していない、または `pOldMode` ポインターが `NULL` である場合、エラー コードを返します。  
  
### <a name="error-conditions"></a>エラー条件  
  
|`mode`|`pOldMode`|**戻り値**|`oldMode` **の内容**|  
|------------|----------------|----------------------|--------------------------------|  
|任意|`NULL`|`EINVAL`|変更されない|  
|無効なモード|任意|`EINVAL`|変更されない|  
  
 上記のいずれかの条件が発生すると、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラ―が呼び出されます。 実行の継続が許可された場合、`_umask_s` は `EINVAL` を返し、`errno` を `EINVAL` に設定します。  
  
## <a name="remarks"></a>コメント  
 `_umask_s`関数では、現在のプロセスのファイルのアクセス許可マスクを設定で指定されたモードに`mode`です。 ファイルのアクセス許可マスクは、`_creat`、`_open`、または `_sopen` によって新しく作成されたファイルのアクセス許可の設定を変更します。 マスクのビットが 1 の場合は、ファイルの要求されたアクセス許可値に対応するビットは 0 (許可しない) に設定されます。 マスクのビットが 0 の場合は、対応するビットは変更されません。 新しいファイルのアクセス許可の設定は、そのファイルが最初に閉じられるまで、設定されません。  
  
 `pmode` は、SYS\STAT.H で定義されている下記のマニフェスト定数のいずれか、または両方が含まれた整数式です。  
  
 `_S_IWRITE`  
 書き込みが許可されます。  
  
 `_S_IREAD`  
 読み取りが許可されます。  
  
 `_S_IREAD | _S_IWRITE`  
 読み取りと書き込みが許可されます。  
  
 両方の定数が指定されると、これらはビットごとの OR 演算子 (`|`) を使用して組み合わされます。 `mode` 引数が `_S_IREAD` である場合、読み取りが許可されていません (ファイルは書き込み専用)。 `mode` 引数が `_S_IWRITE` である場合、書き込みが許可されていません (ファイルは読み取り専用)。 たとえば、マスクに書き込みビットが設定されている場合、新しいファイルはいずれも読み取り専用となります。 MS-DOS および Windows オペレーティング システムでは、すべてのファイルは読み取り可能です。書き込み専用のアクセス許可を与えることはできません。 したがって、`_umask_s` で読み取りビットを設定しても、ファイルのモードに影響はありません。  
  
 `pmode` がマニフェスト定数のいずれかの組み合わせではない、または、別の定数セットを組み込んでいる場合、この関数は単にそれらを無視します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_umask_s`|\<io.h> と \<sys/stat.h> と \<sys/types.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_umask_s.c  
/* This program uses _umask_s to set  
 * the file-permission mask so that all future  
 * files will be created as read-only files.  
 * It also displays the old mask.  
 */  
  
#include <sys/stat.h>  
#include <sys/types.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int oldmask, err;  
  
   /* Create read-only files: */  
   err = _umask_s( _S_IWRITE, &oldmask );  
   if (err)  
   {  
      printf("Error setting the umask.\n");  
      exit(1);  
   }  
   printf( "Oldmask = 0x%.4x\n", oldmask );  
}  
```  
  
```Output  
Oldmask = 0x0000  
```  
  
## <a name="see-also"></a>関連項目  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [下位入出力](../../c-runtime-library/low-level-i-o.md)   
 [_chmod、_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_creat、_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_mkdir、_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_umask](../../c-runtime-library/reference/umask.md)
