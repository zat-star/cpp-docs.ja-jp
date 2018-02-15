---
title: fwrite | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fwrite
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
- fwrite
dev_langs:
- C++
helpviewer_keywords:
- streams, writing data to
- fwrite function
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 73b5328ce6851ceb61ad3260760e95cd329ee064
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="fwrite"></a>fwrite
ストリームにデータを書き込みます。  
  
## <a name="syntax"></a>構文  
  
```  
size_t fwrite(  
   const void *buffer,  
   size_t size,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `buffer`  
 書き込むデータへのポインター。  
  
 `size`  
 項目サイズ (バイト単位)。  
  
 `count`  
 書き込む項目の最大数。  
  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## <a name="return-value"></a>戻り値  
 `fwrite` は、実際に書き込まれる全項目の数を返します。エラーが発生した場合は、`count` 未満になる場合があります。 また、エラーが発生した場合は、ファイル位置インジケーターを決定できません。 `stream` または `buffer` が null ポインターの場合、または奇数バイトの書き込みが Unicode モードで指定された場合、この関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、0 を返します。  
  
## <a name="remarks"></a>コメント  
 `fwrite` 関数は、それぞれが `count` の長さの、最大で `size` 個の項目を、`buffer` から出力 `stream` に書き込みます。 `stream` に関連付けられるファイル ポインター (存在する場合) は、実際に書き込まれたバイト数でインクリメントされます。 場合`stream`が開かれているテキスト モードでは、各ライン フィードはキャリッジ リターン、ライン フィードのペアに置き換えられます。 この置き換えは、戻り値には影響しません。  
  
 `stream` が Unicode 変換モードで開かれた場合 (たとえば、`stream` を呼び出して `fopen`、`ccs=UNICODE`、または `ccs=UTF-16LE` を含むモード パラメーターを使用することで `ccs=UTF-8` が開かれた場合や、`_setmode` と `_O_WTEXT`、`_O_U16TEXT`、または `_O_U8TEXT` を含むモード パラメーターを使用してモードが Unicode 変換モードに変更された場合など)、`buffer` は UTF-16 データを含む `wchar_t` の配列へのポインターとして解釈されます。 このモードで奇数バイトの書き込みを試みると、パラメーター検証エラーが発生します。  
  
 この関数は呼び出し元スレッドをロックするため、スレッド セーフです。 ロックしないバージョンについては、「`_fwrite_nolock`」を参照してください。  
  
## <a name="requirements"></a>必要条件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`fwrite`|\<stdio.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
 「[fread](../../c-runtime-library/reference/fread.md)」の例を参照してください。  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)   
 [fread](../../c-runtime-library/reference/fread.md)   
 [_fwrite_nolock](../../c-runtime-library/reference/fwrite-nolock.md)   
 [_write](../../c-runtime-library/reference/write.md)