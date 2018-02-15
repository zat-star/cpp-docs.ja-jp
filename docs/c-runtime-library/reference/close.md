---
title: _close | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _close
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
- _close
dev_langs:
- C++
helpviewer_keywords:
- _close function
- close function
- files [C++], closing
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9532d8fb98786f35dfa888b5bf8bef5e3e8b2583
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="close"></a>_close
ファイルを閉じます。  
  
## <a name="syntax"></a>構文  
  
```  
int _close(   
   int fd   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fd`  
 開いているファイルを参照するファイル記述子。  
  
## <a name="return-value"></a>戻り値  
 ファイルが正常に閉じられた場合、`_close` は 0 を返します。 戻り値-1 はエラーを示します。  
  
## <a name="remarks"></a>コメント  
 `_close` 関数は、`fd` に関連付けられているファイルを閉じます。  
  
 ファイル記述子と基になる OS ファイル ハンドルは閉じられます。 したがって、ファイルが最初に Win32 関数 `CreateFile` を使用して開かれ、`_open_osfhandle` を使用してファイル記述子に変換された場合、`CloseHandle` を呼び出す必要はありません。  
  
 この関数は、パラメーターを検証します。 `fd` が正しくないファイル記述子である場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は -1 を返し、`errno` は `EBADF` に設定されます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_close`|\<io.h>|\<errno.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
 [_open](../../c-runtime-library/reference/open-wopen.md) の例を参照してください。  
  
## <a name="see-also"></a>参照  
 [下位入出力](../../c-runtime-library/low-level-i-o.md)   
 [_chsize](../../c-runtime-library/reference/chsize.md)   
 [_creat、_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_dup、_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_unlink、_wunlink](../../c-runtime-library/reference/unlink-wunlink.md)