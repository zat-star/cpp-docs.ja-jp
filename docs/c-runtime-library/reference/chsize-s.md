---
title: _chsize_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _chsize_s
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
- chsize_s
- _chsize_s
dev_langs: C++
helpviewer_keywords:
- files [C++], changing size
- chsize_s function
- _chsize_s function
ms.assetid: d88d2e94-6e3b-42a5-8631-16ac4d82fa38
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8b00b0afdf9ba2daac8b4a64a8527d3b73e3c0cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="chsizes"></a>_chsize_s
ファイル サイズを変更します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_chsize](../../c-runtime-library/reference/chsize.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _chsize_s(   
   int fd,  
   __int64 size   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fd`  
 開いているファイルを参照するファイル記述子。  
  
 `size`  
 バイト単位のファイルの新しい長さ。  
  
## <a name="return-value"></a>戻り値  
 ファイル サイズが正常に変更された場合は、`_chsize_s` は値 0 を返します。 0 以外の戻り値はエラーを示します: 指定したファイルがアクセスに対してロックされている場合、戻り値は `EACCES` になり、指定したファイルが読み取り専用かまたは記述子が無効な場合は `EBADF`、デバイスで空いている領域が残っていない場合は `ENOSPC`、サイズが 0 未満の場合は `EINVAL` になります。 `errno` は同じ値に設定されます。  
  
 リターン コードの詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 `_chsize_s` 関数は、`fd` に関連付けられているファイルを `size` に指定された長さに拡張するか切り捨てます。 ファイルは、書き込みを許可するモードで開かれている必要があります。 ファイルが拡張される場合は、null 文字 ('\0') が追加されます。 ファイルが切り捨てられる場合、短くなったファイルの末尾からファイルの元の長さまでのすべてのデータは失われます。  
  
 `_chsize_s` は、ファイル サイズとして 64 ビットの整数を取るので、4 GB より大きいファイル サイズを処理できます。 `_chsize` は、32 ビットのファイル サイズに制限されます。  
  
 この関数は、パラメーターを検証します。 `fd` が有効なファイル記述子ではないか、サイズが 0 未満である場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_chsize_s`|\<io.h>|\<errno.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [_chsize](../../c-runtime-library/reference/chsize.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_creat、_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)