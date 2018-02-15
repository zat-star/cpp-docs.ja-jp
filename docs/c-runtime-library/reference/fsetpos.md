---
title: fsetpos | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fsetpos
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
- fsetpos
dev_langs:
- C++
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 483cf151374c1c3a03e53e49ce67a00a148406fd
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="fsetpos"></a>fsetpos
ストリームの位置インジケーターを設定します。  
  
## <a name="syntax"></a>構文  
  
```  
int fsetpos(   
   FILE *stream,  
   const fpos_t *pos   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
 `pos`  
 位置インジケーターのストレージ。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合、`fsetpos` は 0 を返します。 失敗した場合、関数は 0 以外の値を返し、`errno` を以下のいずれかのマニフェスト定数 (ERRNO で定義されます) に設定します。`EBADF` の場合、ファイルがアクセスできないか、`stream` がポイントするオブジェクトが有効なファイル構造ではありません。または、`EINVAL` の場合、`stream` または `pos` の無効の値が渡されたことを意味します。 無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、これらの関数は無効なパラメーター ハンドラーを呼び出します。  
  
 リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `fsetpos`関数のファイル位置インジケーターを設定する`stream`の値に`pos`を呼び出す前に取得される`fgetpos`に対して`stream`です。 関数は、ファイルの終端のインジケーターをクリアし、任意の効果を元に戻します[ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md)で`stream`です。 `fsetpos` を呼び出した後で、`stream` 上の次の操作は、入力または出力になります。  
  
## <a name="requirements"></a>必要条件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`fsetpos`|\<stdio.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
 「[fgetpos](../../c-runtime-library/reference/fgetpos.md)」の例を参照してください。  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)