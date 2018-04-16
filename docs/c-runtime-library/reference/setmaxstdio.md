---
title: _setmaxstdio | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _setmaxstdio
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
- setmaxstdio
- _setmaxstdio
dev_langs:
- C++
helpviewer_keywords:
- maximum open files
- _setmaxstdio function
- setmaxstdio function
- open files, maximum
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5317437202cef423759ac850aab2360892521746
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="setmaxstdio"></a>_setmaxstdio
`stdio` のレベルで同時に開かれるファイル数の最大値を設定します。  
  
## <a name="syntax"></a>構文  
  
```  
int _setmaxstdio(  
   int newmax   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `newmax`  
 `stdio` のレベルで同時に開かれるファイル数の新しい最大値。  
  
## <a name="return-value"></a>戻り値  
 返します`newmax`正常終了した場合は-1 をそれ以外の場合。  
  
 `newmax` が `_IOB_ENTRIES` より小さいか、オペレーティング システムで使用できるハンドルの最大数より大きい場合には、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は -1 を返し、`errno` を `EINVAL` に設定します。  
  
 これらと他のエラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 `_setmaxstdio` 関数は、`stdio` のレベルで同時に開かれるファイル数の最大値を変更します。  
  
 C ランタイム I/O では、Win32 プラットフォームで、以前のバージョンよりも多くの開いているファイルをサポートするようになりました。 [lowio レベル](../../c-runtime-library/low-level-i-o.md) (つまり、`_open`、`_read`、`_write` などの I/O 関数ファミリを使って、開かれ、アクセスされる) では、最大 2,048 までのファイルを同時に開くことができます。 [stdio レベル](../../c-runtime-library/stream-i-o.md) (つまり、`fopen`、`fgetc`、`fputc` などの関数ファミリを使って、開かれ、アクセスされる) では、最大 512 までのファイルを同時に開くことができます。 `stdio` レベルでの 512 の開いているファイルの制限は、`_setmaxstdio` 関数を使うことで、2,048 の最大値へ引き上げることができます。  
  
 `fopen` などの `stdio` レベルの関数は `lowio` 関数の上に構築されているため、2,048 という最大値は、C ランタイム ライブラリによってアクセスされる同時に開いているファイルの数の固定された上限です。  
  
> [!NOTE]
>  この上限は、特定の Win32 プラットフォームと構成でサポートされる上限を超える可能性があります。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_setmaxstdio`|\<stdio.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
 `_setmaxstdio` の使用例については、「[_getmaxstdio](../../c-runtime-library/reference/getmaxstdio.md)」をご覧ください。  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)