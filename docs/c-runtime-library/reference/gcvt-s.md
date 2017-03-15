---
title: "_gcvt_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_gcvt_s"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_gcvt_s"
  - "gcvt_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CVTBUFSIZE"
  - "_gcvt_s 関数"
  - "変換, 浮動小数点から文字列へ"
  - "CVTBUFSIZE"
  - "浮動小数点関数, 変換 (数値を文字列に)"
  - "gcvt_s 関数"
  - "数, 変換 (文字列に)"
  - "文字列 [C++], 変換 (浮動小数点型から)"
ms.assetid: 0a8d8a26-5940-4ae3-835e-0aa6ec1b0744
caps.latest.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 30
---
# _gcvt_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列に浮動小数点値を変換します。  この関数は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[\_gcvt](../../c-runtime-library/reference/gcvt.md) のセキュリティが強化されたバージョンです。  
  
## 構文  
  
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
  
#### パラメーター  
 \[出力\] `buffer`  
 変換の結果を格納するバッファー。  
  
 \[入力\] `sizeInBytes`  
 バッファーのサイズ。  
  
 \[入力\] `value`  
 変換される数値。  
  
 \[入力\] `digits`  
 格納されている有効桁数。  
  
## 戻り値  
 正常に終了した場合は 0 を返します。  エラーが無効なパラメーターで \(無効な値については、次の表を参照してください\) 場合は、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)で呼び出されます。  実行の継続が許可された場合、エラー コードが返されます。  エラー コードは、Errno.h で定義されます。  これらのエラーのリスティングの場合、[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)を参照してください。  
  
### エラー条件  
  
|`buffer`|`sizeInBytes`|`value`|`digits`|戻り値|`buffer` の値|  
|--------------|-------------------|-------------|--------------|---------|-----------------|  
|`NULL`|任意|任意|任意|`EINVAL`|変更されない。|  
|`NULL` 以外 \(有効なメモリを指し示している\)|0|任意|任意|`EINVAL`|変更されない。|  
|`NULL` 以外 \(有効なメモリを指し示している\)|任意|任意|\>\= `sizeInBytes`|`EINVAL`|変更されない。|  
  
 **セキュリティの問題**  
  
 `_gcvt_s` は `buffer` が有効なメモリを指さないし、`NULL`であるアクセス違反が発生します。  
  
## 解説  
 `_gcvt_s` 関数 \(小数点記号と可能なバイトを含む\) に浮動小数点 `value` を文字列に変換し、`buffer`で文字列を格納します。  `buffer` は 自動的に付けられた終端の null 文字に変換後の値を格納するのに十分な大きさが必要です。  `_CVTBUFSIZE` 長さのバッファーは、浮動小数点値で十分です。  `digits` のバッファー サイズが \+ 1 を使用すると、関数では、バッファーの末尾を上書きしていないため、この操作のための十分なバッファーを指定してください。  `_gcvt_s` は 10 進形式で `digits` の数字を生成しようとします。  できない場合、指数形式の `digits` の数字を生成します。  後続のゼロは変換で制約できます。  
  
 この関数を使用して、C\+\+ では、テンプレートのオーバーロードによって簡素化されます。; オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
 この関数は、1 番目のデバッグ バージョンは 0xFD をバッファーにコピーします。  この動作を無効にするには、[\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md) を使用します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|----------|------------|----------------|  
|`_gcvt_s`|\<stdlib.h\>|\<error.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
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
  
  **変換された値: 1.2**   
## 同等の .NET Framework 関数  
 <xref:System.Convert.ToString%2A>  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [atof、\_atof\_l、\_wtof、\_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt\_s](../Topic/_ecvt_s.md)   
 [\_fcvt\_s](../../c-runtime-library/reference/fcvt-s.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)