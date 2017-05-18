---
title: "_mbcjistojms、_mbcjistojms_l、_mbcjmstojis、_mbcjmstojis_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbcjistojms
- _mbcjmstojis
- _mbcjistojms_l
- _mbcjmstojis_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbcjistojms
- _mbcjistojms
- _mbcjistojms_l
- _mbcjmstojis_l
- _mbcjmstojis
- mbcjmstojis_l
- mbcjistojms_l
- mbcjmstojis
dev_langs:
- C++
helpviewer_keywords:
- _mbcjmstojis_l function
- _mbcjistojms function
- mbcjmstojis function
- _mbcjistojms_l function
- _mbcjmstojis function
- mbcjistojms function
- mbcjmstojis_l function
- mbcjistojms_l function
ms.assetid: dece5127-b337-40a4-aa10-53320a2c9432
caps.latest.revision: 20
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
ms.openlocfilehash: 514e00148ec34a14a7b229d5b7e226d8be66636d
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="mbcjistojms-mbcjistojmsl-mbcjmstojis-mbcjmstojisl"></a>_mbcjistojms、_mbcjistojms_l、_mbcjmstojis、_mbcjmstojis_l
日本工業標準 (JIS: Japan Industry Standard) 文字と Japan Microsoft (JMS) 文字の間を変換します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
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
  
#### <a name="parameters"></a>パラメーター  
 `c`  
 変換する文字。  
  
 `local`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 日本語のロケールで、これらの関数は変換された文字を返すか、または変換可能でない場合は 0 を返します。 日本語以外のロケールで、これらの関数は、渡された文字を返します。  
  
## <a name="remarks"></a>コメント  
 `_mbcjistojms` 関数は、日本工業標準 (JIS) の文字を Microsoft の漢字 (Shift JIS) 文字に変換します。 潜在顧客と後続バイトが範囲 0x21 - 0x7E 内にある場合にのみ、文字が変換されます。 先行バイトまたは後続バイトがこの範囲外にある場合は、`errno` は `EILSEQ` に設定されます。 このエラー コードと他のエラーコードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
 `_mbcjmstojis`関数 Shift JIS の文字を JIS 文字に変換します。 範囲 0x81 から 0x9F または 0xE0 - - 0 xfc が先行バイトと後続バイトが範囲内に、0x40 ~ 0x7E または 0x80 ~ 0 xfc 場合にのみ、文字が変換されます。 その範囲の一部のコード ポイントには割り当てられた文字がないため、変換できないことに注意してください。  
  
 値 `c` は上位 8 のビットが変換される文字の先行バイトを表し、下位の 8 ビットが後続バイトを表す、16 ビットの値です。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」を参照してください。 `_l` サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。  
  
 以前のバージョンで`_mbcjistojms`と`_mbcjmstojis`呼び出された`jistojms`と`jmstojis`、それぞれします。 `_mbcjistojms`、 `_mbcjistojms_l`、`_mbcjmstojis`と`_mbcjmstojis_l`代わりに使用する必要があります。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_mbcjistojms`|\<mbstring.h>|  
|`_mbcjistojms_l`|\<mbstring.h>|  
|`_mbcjmstojis`|\<mbstring.h>|  
|`_mbcjmstojis_l`|\<mbstring.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)
