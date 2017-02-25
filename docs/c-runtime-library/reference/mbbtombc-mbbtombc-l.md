---
title: "_mbbtombc、_mbbtombc_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbbtombc_l"
  - "_mbbtombc"
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
  - "_mbbtombc_l"
  - "_mbbtombc"
  - "mbbtombc_l"
  - "mbbtombc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbbtombc 関数"
  - "_mbbtombc_l 関数"
  - "mbbtombc 関数"
  - "mbbtombc_l 関数"
ms.assetid: 78593389-b0fc-43b6-8c1f-2a6bf702d64e
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _mbbtombc、_mbbtombc_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

1 バイトのマルチバイト文字を、対応する 2 バイトのマルチバイト文字に変換します。  
  
> [!IMPORTANT]
>  この API は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
unsigned int _mbbtombc(  
   unsigned int c   
);  
unsigned int _mbbtombc_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `c`  
 変換する 1 バイト文字。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 `_mbbtombc` は、`c` を正常に変換できた場合は、マルチバイト文字を返します。それ以外の場合は、`c` を返します。  
  
## 解説  
 `_mbbtombc` 関数は、与えられた 1 バイトのマルチバイト文字を、対応する 2 バイトのマルチバイト文字に変換します。  変換する文字は、0x20 ～ 0x7E または 0xA1 ～ 0xDF の範囲である必要があります。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  この関数の各バージョンは、ロケールに依存するこの動作について、`_mbbtombc` は現在のロケールを使用し、`_mbbtombc_l` は渡されるロケール パラメーターを代わりに使用する点を除いて、同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 以前のバージョンでは、`_mbbtombc` は `hantozen` という名前でした。  新しいコードでは、`_mbbtombc` を使用してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_mbbtombc`|\<mbstring.h\>|  
|`_mbbtombc_l`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 該当なし。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [\_mbctombb、\_mbctombb\_l](../../c-runtime-library/reference/mbctombb-mbctombb-l.md)