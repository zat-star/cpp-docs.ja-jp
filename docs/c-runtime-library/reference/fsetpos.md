---
title: fsetpos | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 12
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 8ae2c34fb0eb62ec895b8b8e28bc6dd14f03b1fa
ms.lasthandoff: 02/24/2017

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
 正常に終了した場合、`fsetpos` は 0 を返します。 失敗した場合、関数は&0; 以外の値を返し、`errno` を以下のいずれかのマニフェスト定数 (ERRNO で定義されます) に設定します。`EBADF` の場合、ファイルがアクセスできないか、`stream` がポイントするオブジェクトが有効なファイル構造ではありません。または、`EINVAL` の場合、`stream` または `pos` の無効の値が渡されたことを意味します。 無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、これらの関数は無効なパラメーター ハンドラーを呼び出します。  
  
 リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 `fsetpos` 関数は、`stream`のファイル位置インジケーターを `pos` *、* の値に設定します。これは、`stream`* に対する `fgetpos` への前の呼び出しで取得されます。* 関数は、ファイルの終端のインジケーターをクリアし、`stream`* 上の [ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md) のすべての効果を元に戻しますにします。* `fsetpos` を呼び出した後で、`stream` 上の次の操作は、入力または出力になります。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`fsetpos`|\<stdio.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
 「[fgetpos](../../c-runtime-library/reference/fgetpos.md)」の例を参照してください。  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 [System::IO::FileStream::Position](https://msdn.microsoft.com/en-us/library/system.io.filestream.position.aspx)  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)
