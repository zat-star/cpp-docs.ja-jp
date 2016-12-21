---
title: "_mbcjistojms、_mbcjistojms_l、_mbcjmstojis、_mbcjmstojis_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbcjistojms"
  - "_mbcjmstojis"
  - "_mbcjistojms_l"
  - "_mbcjmstojis_l"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "mbcjistojms"
  - "_mbcjistojms"
  - "_mbcjistojms_l"
  - "_mbcjmstojis_l"
  - "_mbcjmstojis"
  - "mbcjmstojis_l"
  - "mbcjistojms_l"
  - "mbcjmstojis"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbcjistojms 関数"
  - "_mbcjistojms_l 関数"
  - "_mbcjmstojis 関数"
  - "_mbcjmstojis_l 関数"
  - "mbcjistojms 関数"
  - "mbcjistojms_l 関数"
  - "mbcjmstojis 関数"
  - "mbcjmstojis_l 関数"
ms.assetid: dece5127-b337-40a4-aa10-53320a2c9432
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbcjistojms、_mbcjistojms_l、_mbcjmstojis、_mbcjmstojis_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

日本工業標準 \(JIS: Japan Industry Standard\) 文字と Japan Microsoft \(JMS\) 文字の間を変換します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
unsigned int _mbcjistojms(  
   unsigned int c   
);  
unsigned int _mbcjistojms_l(  
   unsigned int c,  
   _locale_t locale  
);  
unsigned int _mbcjmstojis(  
   unsigned int c   
);  
unsigned int _mbcjmstojis_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `c`  
 変換する文字。  
  
 `local`  
 使用するロケール。  
  
## 戻り値  
 日本語のロケールで、これらの関数は変換された文字を返すか、または変換可能でない場合は 0 を返します。  日本語以外のロケールで、これらの関数は、渡された文字を返します。  
  
## 解説  
 `_mbcjistojms` 関数は、日本工業標準 \(JIS\) の文字を Microsoft の漢字 \(Shift JIS\) 文字に変換します。  先行バイトと後続バイトが範囲 0x21 – 0x7E にある場合にのみ、文字が変換されます。  先行バイトまたは後続バイトがこの範囲外にある場合は、`errno` は `EILSEQ` に設定されます。  エラー コードの詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
 `_mbcjmstojis` 関数は JIS の文字に Shift JIS 文字を変換します。  先行バイトが 0x81 – 0x9F または 0xE0 – 0xFC の範囲にあり、後続バイトが 0x40 – 0x7E または 0x80 – 0xFC の範囲にある場合にのみ、文字が変換されます。  その範囲の一部のコード ポイントには割り当てられた文字がないため、変換できないことに注意してください。  
  
 値 `c` は上位 8 のビットが変換される文字の先行バイトを表し、下位の 8 ビットが後続バイトを表す、16 ビットの値です。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  `_l` サフィックスが付いていないこの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 以前のバージョンでは、`_mbcjistojms` と `_mbcjmstojis` は、`jistojms` と `jmstojis`、それぞれに呼び出されます。  `_mbcjistojms`、`_mbcjistojms_l`、`_mbcjmstojis` と `_mbcjmstojis_l` を代わりに使用する必要があります。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_mbcjistojms`|\<mbstring.h\>|  
|`_mbcjistojms_l`|\<mbstring.h\>|  
|`_mbcjmstojis`|\<mbstring.h\>|  
|`_mbcjmstojis_l`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [\_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)