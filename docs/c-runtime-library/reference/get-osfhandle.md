---
title: _get_osfhandle | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_osfhandle
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
dev_langs:
- C++
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 314f57a38cdabb4257624550f6686075a5b61697
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="getosfhandle"></a>_get_osfhandle
指定されたファイル記述子に関連付けられている、オペレーティング システム ファイル ハンドルを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
intptr_t _get_osfhandle(   
   int fd   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fd`  
 既存のファイル記述子。  
  
## <a name="return-value"></a>戻り値  
 `fd` が有効な場合、オペレーティング システムのファイル ハンドルです。 それ以外の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行は継続許可されたかどうか、この関数を返します`INVALID_HANDLE_VALUE`(-1) を設定および`errno`に`EBADF`、無効なファイル ハンドルを示すです。  
  
## <a name="remarks"></a>コメント  
 `_get_osfhandle` で開いたファイルを閉じるには、`_close` を呼び出します。 `_close` を呼び出すことによって元のハンドルも閉じるため、元のハンドルで Win32 関数 `CloseHandle` を呼び出す必要はありません。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_get_osfhandle`|\<io.h>|  
  
 互換性について詳しくは、「はじめに」の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_creat、_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_dup、_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)
