---
title: "_ftell_nolock、_ftelli64_nolock | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ftelli64_nolock
- _ftell_nolock
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
- _ftelli64_nolock
- ftelli64_nolock
- ftell_nolock
- _ftell_nolock
dev_langs:
- C++
helpviewer_keywords:
- ftelli64_nolock function
- _ftelli64_nolock function
- _ftell_nolock function
- ftell_nolock function
- file pointers [C++], getting current position
ms.assetid: 84e68b0a-32f8-4c4a-90ad-3f2387685ede
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 4d0e042dc3d8bb7a5b956aeb834e51887e1b0138
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="ftellnolock-ftelli64nolock"></a>_ftell_nolock、_ftelli64_nolock
スレッドをロックせずに、ファイル ポインターの現在の位置を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
long _ftell_nolock(   
   FILE *stream   
);  
__int64 _ftelli64_nolock(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stream`  
 `FILE` 構造体をターゲットにします。  
  
## <a name="return-value"></a>戻り値  
 `ftell` および `_ftelli64` と同じです。 詳細については、「[ftell、_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)**」を参照してください。**  
  
## <a name="remarks"></a>コメント  
 これらの関数は、それぞれ `ftell` および `_ftelli64` のロックなしバージョンです。 同一`ftell`と`_ftelli64`他のスレッドによる干渉から保護されない点を除いて、します。 これらの関数では他のスレッドをロックアウトするオーバーヘッドが発生しないため、処理が速くなる場合があります。 これらの関数は、シングルスレッド アプリケーション、呼び出し元のスコープで既にスレッド分離を処理している場合などのスレッドセーフなコンテキストでのみ使用してください。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|オプション ヘッダー|  
|--------------|---------------------|---------------------|  
|`ftell_nolock`|\<stdio.h>|\<errno.h>|  
|`_ftelli64_nolock`|\<stdio.h>|\<errno.h>|  
  
 互換性について詳しくは、「はじめに」の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)   
 [fseek、_fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [_lseek、_lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [ftell、_ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)
