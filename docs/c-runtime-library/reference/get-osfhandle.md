---
title: _get_osfhandle | Microsoft Docs
ms.custom: 
ms.date: 12/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_osfhandle
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
- get_osfhandle
- _get_osfhandle
dev_langs: C++
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2b810edac60b08ccc31d6767cb11b7176fb981b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="getosfhandle"></a>_get_osfhandle

指定されたファイル記述子に関連付けられている、オペレーティング システム ファイル ハンドルを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
intptr_t _get_osfhandle(   
   int fd   
);  
```  
  
### <a name="parameters"></a>パラメーター

*fd*  
既存のファイル記述子。  
  
## <a name="return-value"></a>戻り値

場合は、オペレーティング システム ファイル ハンドルを返します*fd*は無効です。 それ以外の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行は継続許可されたかどうか、この関数を返します`INVALID_HANDLE_VALUE`(-1) を設定および`errno`に`EBADF`、無効なファイル ハンドルを示すです。  
  
## <a name="remarks"></a>コメント

オペレーティング システム (OS) のファイル ハンドルが取得されたファイルを閉じる`_get_osfhandle`、呼び出す[\_閉じる](../../c-runtime-library/reference/close.md)ファイル記述子に*fd*です。 呼び出す必要はありません`CloseHandle`この関数の戻り値にします。 基になる OS ファイル ハンドルが所有、 *fd*ファイル記述子、および閉じるときに`_close`で呼び出される*fd*です。 ファイル記述子がによって所有されている場合、`FILE *`ストリーム、呼び出すことで、 [fclose](../../c-runtime-library/reference/fclose-fcloseall.md)を`FILE *`ストリームがファイル記述子と基になる OS ファイル ハンドルの両方を閉じます。 この場合、呼び出さない`_close`ファイル記述子。
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_get_osfhandle`|\<io.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>参照

[ファイル処理](../../c-runtime-library/file-handling.md)   
[_close](../../c-runtime-library/reference/close.md)   
[_creat、_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
[_dup、_dup2](../../c-runtime-library/reference/dup-dup2.md)   
[_open、_wopen](../../c-runtime-library/reference/open-wopen.md)
