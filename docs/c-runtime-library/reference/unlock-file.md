---
title: _unlock_file | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _unlock_file
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
- _unlock_file
- unlock_file
dev_langs:
- C++
helpviewer_keywords:
- files [C++], unlocking
- unlock_file function
- _unlock_file function
- unlocking files
ms.assetid: cf380a51-6d3a-4f38-bd64-2d4fb57b4369
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
ms.openlocfilehash: bc676e9912264009e0af263ec88fb142fbb4d1fe
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="unlockfile"></a>_unlock_file
他のプロセスがアクセスできるようにファイルのロックを解除します。  
  
## <a name="syntax"></a>構文  
  
```  
void _unlock_file(  
   FILE* file  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `file`  
 ファイル ハンドルです。  
  
## <a name="remarks"></a>コメント  
 `_unlock_file` 関数は、`file` で指定されたファイルのロックを解除します。 ファイルのロックを解除すると、他のプロセスがそのファイルにアクセスできるようになります。 以前に `file` ポインターに対して `_lock_file` を呼び出していない限り、この関数は呼び出さないでください。 ロックされていないファイルに対して `_unlock_file` を呼び出すと、デッドロックの発生する可能性があります。 例については、「[_lock_file](../../c-runtime-library/reference/lock-file.md)」をご覧ください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_unlock_file`|\<stdio.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [_creat、_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_lock_file](../../c-runtime-library/reference/lock-file.md)
