---
title: "_fcvt_s | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fcvt_s
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
- fcvt_s
- _fcvt_s
dev_langs:
- C++
helpviewer_keywords:
- fcvt_s function
- converting floating point, to strings
- floating-point functions, converting number to string
- _fcvt_s function
ms.assetid: 48671197-1d29-4c2b-a5d8-d2368f5f68a1
caps.latest.revision: 27
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
ms.openlocfilehash: 9c282757ae79367cdc2ee72b3f3ce8d0e50983fa
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="fcvts"></a>_fcvt_s
浮動小数点数を文字列に変換します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_fcvt](../../c-runtime-library/reference/fcvt.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _fcvt_s(   
   char* buffer,  
   size_t sizeInBytes,  
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
template <size_t size>  
errno_t _fcvt_s(   
   char (&buffer)[size],  
   double value,  
   int count,  
   int *dec,  
   int *sign   
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `buffer`  
 変換の結果を保持する指定されたバッファー。  
  
 [入力] `sizeInBytes`  
 バッファーのサイズ (バイト単位)。  
  
 [入力] `value`  
 変換される数値。  
  
 [入力] `count`  
 小数点以下の桁数。  
  
 [出力] `dec`  
 格納された小数点位置を指すポインター。  
  
 [出力] `sign`  
 格納された符号インジケーターを指すポインター。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0 を返します。 障害が発生した場合、戻り値はエラー コードを示します。 エラー コードは、Errno.h で定義されています。 これらのエラーの一覧については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
 パラメーターが次の表の無効な値の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、この関数は無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
### <a name="error-conditions"></a>エラー条件  
  
|`buffer`|`sizeInBytes`|値|count|dec|sign|Return|`buffer` の値|  
|--------------|-------------------|-----------|-----------|---------|----------|------------|-----------------------|  
|`NULL`|任意|任意|任意|任意|任意|`EINVAL`|変更されません。|  
|`NULL` ではありません (有効なメモリを指します)|<=0|任意|任意|任意|任意|`EINVAL`|変更されません。|  
|任意|任意|任意|任意|`NULL`|任意|`EINVAL`|変更されません。|  
|任意|任意|任意|任意|任意|`NULL`|`EINVAL`|変更されません。|  
  
 **セキュリティ上の問題**  
  
 `buffer` が有効なメモリを指しておらず、`NULL` ではない場合、`_fcvt_s` はアクセス違反を生成する可能性があります。  
  
## <a name="remarks"></a>コメント  
 `_fcvt_s` 関数は、浮動小数点数の値を null で終わる文字列に変換します。 `value` パラメーターは変換する浮動小数点数です。 `_fcvt_s` は、`value` の桁数を文字列として格納し、null 文字 ("\0") を追加します。 `count` パラメーターは、小数点より後の格納する桁数を指定します。 余分な桁は、`count` 桁まで丸められます。 この桁数が `count` の有効桁数より少ない場合は、文字列に 0 が埋め込まれます。  
  
 文字列には数字だけが格納されます。 `value` の小数点位置と符号は、呼び出しの後で `dec` と `sign` から取得できます。 `dec` パラメーターは、整数値を指します。この整数値は、小数点が文字列の先頭から何文字目にあるのかを示します。 0 または負の整数値は、小数点が文字列の先頭より左にあることを示します。 `sign` パラメーターは、`value` の符号を示す整数を指します。 `value` が正の場合、整数は 0 に設定され、`value` が負の場合は負の値に設定されます。  
  
 長さ `_CVTBUFSIZE` のバッファーは、浮動小数点値には十分です。  
  
 `_ecvt_s` と `_fcvt_s` の違いは、`count` パラメーターの解釈にあります。 `_ecvt_s`解釈`count`として出力文字列に数字の合計数と`_fcvt_s`解釈`count`桁数、小数点後として。  
  
 C++ では、テンプレートのオーバーロードによってこの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
 この関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。 この動作を無効にするには、[_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).を使用します。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|オプション ヘッダー|  
|--------------|---------------------|---------------------|  
|`_fcvt_s`|\<stdlib.h>|\<errno.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
 **ライブラリ:** [CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)のすべてのバージョンです。  
  
## <a name="example"></a>例  
  
```  
// fcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char * buf = 0;  
  int decimal;  
  int sign;  
  int err;  
  
  buf = (char*) malloc(_CVTBUFSIZE);  
  err = _fcvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);  
  
  if (err != 0)  
  {  
     printf("_fcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
```Output  
Converted value: 120000  
```  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [atof、_atof_l、_wtof、_wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt_s](../../c-runtime-library/reference/ecvt-s.md)   
 [_gcvt_s](../../c-runtime-library/reference/gcvt-s.md)   
 [_fcvt](../../c-runtime-library/reference/fcvt.md)
