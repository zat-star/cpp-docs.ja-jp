---
title: _ecvt_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ecvt_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- ecvt_s
- _ecvt_s
dev_langs:
- C++
helpviewer_keywords:
- _ecvt_s function
- ecvt_s function
- numbers, converting
- converting double numbers
ms.assetid: d52fb0a6-cb91-423f-80b3-952a8955d914
caps.latest.revision: 25
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
ms.openlocfilehash: 81bcb9fe1306f5affa49672269890d6f5888a3ac
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="ecvts"></a>_ecvt_s
`double` の値を文字列に変換します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_ecvt](../../c-runtime-library/reference/ecvt.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _ecvt_s(   
   char * _Buffer,  
   size_t _SizeInBytes,  
   double _Value,  
   int _Count,  
   int *_Dec,  
   int *_Sign  
);  
template <size_t size>  
errno_t _ecvt_s(   
   char (&_Buffer)[size],  
   double _Value,  
   int _Count,  
   int *_Dec,  
   int *_Sign  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `_Buffer`  
 変換の結果である数字の文字列へのポインターが格納されます。  
  
 [入力] `_SizeInBytes`  
 バッファーのサイズ (バイト単位)。  
  
 [入力] `_Value`  
 変換される数値。  
  
 [入力] `_Count`  
 格納する桁数。  
  
 [出力] `_Dec`  
 格納された小数点位置。  
  
 [出力] `_Sign`  
 変換後の数値の符号。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0 を返します。 障害が発生した場合、戻り値はエラー コードを示します。 エラー コードは、Errno.h で定義されています。 詳しくは、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
 パラメーターが次の表の無効な値の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、この関数は無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
### <a name="error-conditions"></a>エラー条件  
  
|`_Buffer`|`_SizeInBytes`|_Value|_Count|_Dec|_Sign|戻り値|`buffer` の値|  
|---------------|--------------------|-------------|-------------|-----------|------------|------------------|-----------------------|  
|`NULL`|任意|任意|任意|任意|任意|`EINVAL`|変更されません。|  
|`NULL` ではありません (有効なメモリを指します)|<=0|任意|任意|任意|任意|`EINVAL`|変更されません。|  
|任意|任意|任意|任意|`NULL`|任意|`EINVAL`|変更されません。|  
|任意|任意|任意|任意|任意|`NULL`|`EINVAL`|変更されません。|  
  
 **セキュリティ上の問題**  
  
 `buffer` が有効なメモリを指しておらず、`NULL` ではない場合、`_ecvt_s` はアクセス違反を生成する可能性があります。  
  
## <a name="remarks"></a>コメント  
 `_ecvt_s` 関数は、浮動小数点数の値を文字列に変換します。 `_Value` パラメーターは変換する浮動小数点数です。 この関数は、`_Value` の最大 `count` 桁を文字列として格納し、null 文字 ("\0") を追加します。 `_Value` の桁数が `_Count` を超える場合、下位の桁は丸められます。 `count` 桁より少ない場合は、文字列が 0 で埋められます。  
  
 文字列には数字だけが格納されます。 `_Value` の小数点位置と符号は、呼び出しの後で `_Dec` と `_Sign` から取得できます。 `_Dec` パラメーターは、文字列の先頭に対する小数点位置を示す整数値をポイントします。 0 または負の整数値は、最初の桁の左側に小数点があることを示します。 `_Sign` パラメーターは、変換後の数値の符号を示す整数をポイントします。 整数値が 0 の場合、数値は正の値です。 それ以外の場合、数値は負の値です。  
  
 長さ `_CVTBUFSIZE` のバッファーは、浮動小数点値には十分です。  
  
 `_ecvt_s` と `_fcvt_s` の違いは、`_Count` パラメーターの解釈です。 `_ecvt_s` が `_Count` を出力文字列全体の桁数として解釈するのに対し、`_fcvt_s` は `_Count` を小数点より後の桁数と解釈します。  
  
 C++ では、テンプレートのオーバーロードによってこの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
 この関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。 この動作を無効にするには、[_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).を使用します。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|オプション ヘッダー|  
|--------------|---------------------|---------------------|  
|`_ecvt_s`|\<stdlib.h>|\<errno.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// ecvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main( )  
{  
  char * buf = 0;  
  int decimal;  
  int sign;  
  int err;  
  
  buf = (char*) malloc(_CVTBUFSIZE);  
  err = _ecvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);  
  
  if (err != 0)  
  {  
     printf("_ecvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
```Output  
Converted value: 12000  
```  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [atof、_atof_l、_wtof、_wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [_fcvt_s](../../c-runtime-library/reference/fcvt-s.md)   
 [_gcvt_s](../../c-runtime-library/reference/gcvt-s.md)
