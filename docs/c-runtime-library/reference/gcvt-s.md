---
title: _gcvt_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _gcvt_s
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
- _gcvt_s
- gcvt_s
dev_langs:
- C++
helpviewer_keywords:
- _gcvt_s function
- _CVTBUFSIZE
- floating-point functions, converting number to string
- gcvt_s function
- numbers, converting to strings
- conversions, floating point to strings
- strings [C++], converting from floating point
- CVTBUFSIZE
ms.assetid: 0a8d8a26-5940-4ae3-835e-0aa6ec1b0744
caps.latest.revision: 30
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
ms.openlocfilehash: cc1f34eae067f0d2cc0781c9001af550b291006f
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="gcvts"></a>_gcvt_s
浮動小数点値を文字列に変換します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_gcvt](../../c-runtime-library/reference/gcvt.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _gcvt_s(   
   char *buffer,  
   size_t sizeInBytes,  
   double value,  
   int digits   
);  
template <size_t cchStr>  
errno_t _gcvt_s(   
   char (&buffer)[cchStr],  
   double value,  
   int digits   
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `buffer`  
 変換の結果を格納するバッファー。  
  
 [入力] `sizeInBytes`  
 バッファーのサイズ。  
  
 [入力] `value`  
 変換する値。  
  
 [入力] `digits`  
 格納される有効桁数。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0 を返します。 無効なパラメーターのためにエラーが発生した場合 (無効な値については次の表を参照)、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明するように、無効なパラメーター ハンドラーが呼び出されます。 実行を継続できる場合は、エラー コードが返されます。 エラー コードは、Errno.h で定義されています。 これらのエラーの一覧については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
### <a name="error-conditions"></a>エラー条件  
  
|`buffer`|`sizeInBytes`|`value`|`digits`|リターン|`buffer` の値|  
|--------------|-------------------|-------------|--------------|------------|-----------------------|  
|`NULL`|任意|任意|任意|`EINVAL`|変更されません。|  
|`NULL` ではない (有効なメモリを指す)|ゼロ|任意|任意|`EINVAL`|変更されません。|  
|`NULL` ではない (有効なメモリを指す)|任意|任意|>= `sizeInBytes`|`EINVAL`|変更されません。|  
  
 **セキュリティ上の問題**  
  
 `buffer` が有効なメモリを指しておらず、`NULL` ではない場合、`_gcvt_s` はアクセス違反を生成する可能性があります。  
  
## <a name="remarks"></a>コメント  
 `_gcvt_s` 関数は、浮動小数点 `value` を (小数点、符号バイトを含む) 文字列に変換し、この文字列を `buffer` に格納します。 `buffer` は、変換された値に、自動的に追加される終端の nulll 文字を加えたものを格納するのに十分な大きさである必要があります。 長さ `_CVTBUFSIZE` のバッファーは、浮動小数点値には十分です。 バッファー サイズ `digits` + 1 を使用する場合、関数はバッファーの末尾を上書きしないようにして、この操作のために十分なバッファーを供給します。 `_gcvt_s` は、10 進数形式で `digits` 桁を生成しようとします。 生成できない場合、指数形式で `digits` 桁を生成します。 後続のゼロは、変換時に非表示にできます。  
  
 C++ では、テンプレートのオーバーロードによってこの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
 この関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。 この動作を無効にするには、[_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).を使用します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_gcvt_s`|\<stdlib.h>|\<error.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_gcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char buf[_CVTBUFSIZE];  
  int decimal;  
  int sign;  
  int err;  
  
  err = _gcvt_s(buf, _CVTBUFSIZE, 1.2, 5);  
  
  if (err != 0)  
  {  
     printf("_gcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
```Output  
Converted value: 1.2  
```  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [atof、_atof_l、_wtof、_wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt_s](../../c-runtime-library/reference/ecvt-s.md)   
 [_fcvt_s](../../c-runtime-library/reference/fcvt-s.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)
