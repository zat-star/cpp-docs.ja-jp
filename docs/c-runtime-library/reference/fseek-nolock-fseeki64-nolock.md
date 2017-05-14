---
title: "_fseek_nolock、_fseeki64_nolock | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fseek_nolock
- _fseeki64_nolock
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
apitype: DLLExport
f1_keywords:
- _fseek_nolock
- _fseeki64_nolock
- fseek_nolock
- fseeki64_nolock
dev_langs:
- C++
helpviewer_keywords:
- _fseek_nolock function
- fseeki64_nolock function
- file pointers [C++], moving
- fseek_nolock function
- _fseeki64_nolock function
- seek file pointers
ms.assetid: 2dd4022e-b715-462b-b935-837561605a02
caps.latest.revision: 13
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
ms.openlocfilehash: 256ea0d3f0c1eabf917ea914bc6194744fb38d5c
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="fseeknolock-fseeki64nolock"></a>_fseek_nolock、_fseeki64_nolock
指定した場所にファイル ポインターを移動します。  
  
## <a name="syntax"></a>構文  
  
```  
int _fseek_nolock(   
   FILE *stream,  
   long offset,  
   int origin   
);  
int _fseeki64_nolock(   
   FILE *stream,  
   __int64 offset,  
   int origin   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
 `offset`  
 `origin.` から読み取られたバイト数。  
  
 `origin`  
 最初の位置。  
  
## <a name="return-value"></a>戻り値  
 それぞれ [fseek、_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md) と同じです。  
  
## <a name="remarks"></a>コメント  
 これらの関数はそれぞれ `fseek` および `_fseeki64` のロックなしバージョンです。他のスレッドによる干渉から保護されないことを除き、それぞれ、`fseek` および `_fseeki64` と同じです。 これらの関数では他のスレッドをロックアウトするオーバーヘッドが発生しないため、処理が速くなる場合があります。 これらの関数は、シングルスレッド アプリケーション、呼び出し元のスコープで既にスレッド分離を処理している場合などのスレッドセーフなコンテキストでのみ使用してください。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`fseek`|\<stdio.h>|  
|`_fseeki64`|\<stdio.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [ftell、_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)   
 [_lseek、_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [rewind](../../c-runtime-library/reference/rewind.md)
