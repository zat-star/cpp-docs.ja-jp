---
title: _umask | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _umask
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
f1_keywords: _umask
dev_langs: C++
helpviewer_keywords:
- masks, file-permission-setting
- _umask function
- masks
- umask function
- file permissions [C++]
- files [C++], permission settings for
ms.assetid: 5e9a13ba-5321-4536-8721-6afb6f4c8483
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d8651fd1aa1400b366c6db369eff7bfde8751507
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="umask"></a>_umask
既定のファイル アクセス許可マスクを設定します。 この関数のセキュリティが強化されたバージョンについては、「[_umask_s](../../c-runtime-library/reference/umask-s.md)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
int _umask(  
   int pmode   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pmode`  
 既定のアクセス許可の設定。  
  
## <a name="return-value"></a>戻り値  
 `_umask` は `pmode` の以前の値を返します。 エラーの戻り値はありません。  
  
## <a name="remarks"></a>コメント  
 `_umask`関数では、現在のプロセスのファイルのアクセス許可マスクを設定で指定されたモードに`pmode`です。 ファイルのアクセス許可マスクは、`_creat`、`_open`、または `_sopen` によって新しく作成されたファイルのアクセス許可の設定を変更します。 マスクのビットが 1 の場合は、ファイルの要求されたアクセス許可値に対応するビットは 0 (許可しない) に設定されます。 マスクのビットが 0 の場合は、対応するビットは変更されません。 新しいファイルのアクセス許可の設定は、そのファイルが最初に閉じられるまで、設定されません。  
  
 `pmode` は、SYS\STAT.H で定義されている下記のマニフェスト定数のいずれか、または両方が含まれた整数式です。  
  
 `_S_IWRITE`  
 書き込みが許可されます。  
  
 `_S_IREAD`  
 読み取りが許可されます。  
  
 `_S_IREAD | _S_IWRITE`  
 読み取りと書き込みが許可されます。  
  
 両方の定数が指定されると、これらはビットごとの OR 演算子 (`|`) を使用して組み合わされます。 `pmode` 引数が `_S_IREAD` である場合、読み取りが許可されていません (ファイルは書き込み専用)。 `pmode` 引数が `_S_IWRITE` である場合、書き込みが許可されていません (ファイルは読み取り専用)。 たとえば、マスクに書き込みビットが設定されている場合、新しいファイルはいずれも読み取り専用となります。 MS-DOS および Windows オペレーティング システムでは、すべてのファイルは読み取り可能です。書き込み専用のアクセス許可を与えることはできません。 したがって、`_umask` で読み取りビットを設定しても、ファイルのモードに影響はありません。  
  
 `pmode` がマニフェスト定数のいずれかの組み合わせではない、または、別の定数セットを組み込んでいる場合、この関数は単にそれらを無視します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_umask`|\<io.h>、\<sys/stat.h>、\<sys/types.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_umask.c  
// compile with: /W3  
// This program uses _umask to set  
// the file-permission mask so that all future  
// files will be created as read-only files.  
// It also displays the old mask.  
#include <sys/stat.h>  
#include <sys/types.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int oldmask;  
  
   /* Create read-only files: */  
   oldmask = _umask( _S_IWRITE ); // C4996  
   // Note: _umask is deprecated; consider using _umask_s instead  
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