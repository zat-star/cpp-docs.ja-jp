---
title: _commit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _commit
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
- _commit
- commit
dev_langs:
- C++
helpviewer_keywords:
- files [C++], flushing
- flushing files to disk
- commit function
- _commit function
- committing files to disk
ms.assetid: d0c74d3a-4f2d-4fb0-b140-2d687db3d233
caps.latest.revision: 14
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 40d0fdf7d64dca941c952921d1c3107baa910a74
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="commit"></a>_commit
ファイルを直接ディスクにフラッシュします。  
  
## <a name="syntax"></a>構文  
  
```  
int _commit(   
   int fd   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fd`  
 開いているファイルを参照するファイル記述子。  
  
## <a name="return-value"></a>戻り値  
 ファイルがディスクに正常にフラッシュされた場合、`_commit` は 0 を返します。 戻り値-1 はエラーを示します。  
  
## <a name="remarks"></a>コメント  
 `_commit` 関数は、オペレーティング システムに対して、`fd` に関連付けられたファイルをディスクに書き込む処理を強制します。 この関数を呼び出すと、オペレーティング システムのタイミングではなく、即時に指定したファイルがフラッシュされます。  
  
 `fd` が無効なファイル記述子である場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は -1 を返し、`errno` は `EBADF` に設定されます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|省略可能なヘッダー|  
|-------------|---------------------|----------------------|  
|`_commit`|\<io.h>|\<errno.h>|  
  
 互換性について詳しくは、「はじめに」の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [下位入出力](../../c-runtime-library/low-level-i-o.md)   
 [_creat、_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_read](../../c-runtime-library/reference/read.md)   
 [_write](../../c-runtime-library/reference/write.md)
