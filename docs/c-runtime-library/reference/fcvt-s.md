---
title: "_fcvt_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fcvt_s"
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
  - "fcvt_s"
  - "_fcvt_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fcvt_s 関数"
  - "変換 (浮動小数点型を), 文字列への"
  - "fcvt_s 関数"
  - "浮動小数点関数, 変換 (数値を文字列に)"
ms.assetid: 48671197-1d29-4c2b-a5d8-d2368f5f68a1
caps.latest.revision: 27
caps.handback.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fcvt_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列に浮動小数点数に変換します。  この関数は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[\_fcvt](../Topic/_fcvt.md) のセキュリティが強化されたバージョンです。  
  
## 構文  
  
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
  
#### パラメーター  
 \[出力\] `buffer`  
 変換の結果を格納する指定されたバッファー。  
  
 \[入力\] `sizeInBytes`  
 バッファーのサイズ \(バイト数\)  
  
 \[入力\] `value`  
 変換される数値。  
  
 \[入力\] `count`  
 小数点以下の桁数を指定します。  
  
 \[出力\] `dec`  
 保存された小数点位置へのポインター。  
  
 \[出力\] `sign`  
 保存された署名のインジケーターへのポインター。  
  
## 戻り値  
 正常に終了した場合は 0 を返します。  エラーが発生した場合の戻り値はエラー コードです。  エラー コードは、Errno.h で定義されます。  これらのエラーのリスティングの場合、[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)を参照してください。  
  
 無効なパラメーターの場合は、次の表に示すように、この関数は [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
### エラー条件  
  
|`buffer`|`sizeInBytes`|値|count|12 年|sign|戻り値|`buffer` の値|  
|--------------|-------------------|-------|-----------|----------|----------|---------|-----------------|  
|`NULL`|任意|任意|任意|任意|任意|`EINVAL`|変更されない。|  
|`NULL` 以外 \(有効なメモリを指し示している\)|\<\=0|任意|任意|任意|任意|`EINVAL`|変更されない。|  
|任意|任意|任意|任意|`NULL`|任意|`EINVAL`|変更されない。|  
|任意|任意|任意|任意|任意|`NULL`|`EINVAL`|変更されない。|  
  
 **セキュリティの問題**  
  
 `_fcvt_s` は `buffer` が有効なメモリを指さないし、`NULL`であるアクセス違反が発生することがあります。  
  
## 解説  
 `_fcvt_s` 関数は null で終わるな文字列に浮動小数点数に変換します。  `value` パラメーターは、変換する浮動小数点数です。  `_fcvt_s` は 文字列として `value` の数値を格納し、null 文字 \(「\\0」\) を付けます。  `count` パラメーターは 10 進数の後に格納される桁数を指定します。  余分な数字が `count` の場所に丸められます。  精度の `count` の数値より少なくがある場合は、文字列をゼロで埋められます。  
  
 数値を文字列に保存されます。  小数点の位置と `value` の符号は呼び出しの後に `dec` と `sign` から取得できます。  整数値への `dec` パラメーター point; この整数値は文字列の先頭に関して小数点の位置を示します。  ゼロまたは負の整数値は整数部の桁目の左側にあることを示します。  パラメーター `sign` は `value`の符号を表す整数を指定します。  整数を 0 に `value` が負の場合 `value` が正の値である設定され、0 以外のな数値に設定されます。  
  
 `_CVTBUFSIZE` 長さのバッファーは、浮動小数点値で十分です。  
  
 `_ecvt_s` と `_fcvt_s` の違いは `count` パラメーターの解釈にあります。  `_ecvt_s` は 出力文字列の桁数として `count` を解釈し、`_fcvt_s` は小数点以下の桁数として`ount` c を復号化します。  
  
 この関数を使用して、C\+\+ では、テンプレートのオーバーロードによって簡素化されます。; オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
 この関数は、1 番目のデバッグ バージョンは 0xFD をバッファーにコピーします。  この動作を無効にするには、[\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md) を使用します。  
  
## 必要条件  
  
|関数|必須ヘッダー|オプション ヘッダー|  
|--------|------------|----------------|  
|`_fcvt_s`|\<stdlib.h\>|\<errno.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
 **ライブラリ:** [CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md) のすべてのバージョン。  
  
## 使用例  
  
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
  
  **変換された値: 120000**   
## 同等の .NET Framework 関数  
 <xref:System.Convert.ToString%2A>  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [atof、\_atof\_l、\_wtof、\_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt\_s](../Topic/_ecvt_s.md)   
 [\_gcvt\_s](../../c-runtime-library/reference/gcvt-s.md)   
 [\_fcvt](../Topic/_fcvt.md)