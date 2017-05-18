---
title: "_mbctombb、_mbctombb_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbctombb_l
- _mbctombb
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
- _mbctombb_l
- _mbctombb
- mbctombb_l
- mbctombb
dev_langs:
- C++
helpviewer_keywords:
- _mbctombb function
- mbctombb_l function
- mbctombb function
- _mbctombb_l function
ms.assetid: d90970b8-71ff-4586-b6a2-f9ceb811f776
caps.latest.revision: 17
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
ms.openlocfilehash: c659b24b2d8364af4303c0667841224560914cd6
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="mbctombb-mbctombbl"></a>_mbctombb、_mbctombb_l
2 バイト マルチバイト文字を、対応する 1 バイト マルチバイト文字に変換します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned int _mbctombb(  
   unsigned int c   
);  
unsigned int _mbctombb_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `c`  
 変換するマルチバイト文字。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、`_mbctombb`と`_mbctombb_l`に対応する 1 バイト文字を返します`c`; 返します`c`です。  
  
## <a name="remarks"></a>コメント  
 `_mbctombb`と`_mbctombb_l`関数では、特定のマルチバイト文字を対応する 1 バイト マルチバイト文字に変換します。 文字は、変換する 0 xdf 範囲 0x20-0x7E または 0xA1 - 1 バイト文字に対応する必要があります。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定に影響されます。詳細については、「[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」を参照してください。 `_l` サフィックスが付いていないこの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」をご覧ください。  
  
 以前のバージョンでは、`_mbctombb` は `zentohan` と呼ばれていました。 代わりに、 `_mbctombb` を使用してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_mbctombb`|\<mbstring.h>|  
|`_mbctombb_l`|\<mbstring.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [_mbbtombc、_mbbtombc_l](../../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)   
 [_mbcjistojms、_mbcjistojms_l、_mbcjmstojis、_mbcjmstojis_l](../../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)   
 [_mbctohira、_mbctohira_l、_mbctokata、_mbctokata_l](../../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)   
 [_mbctolower、_mbctolower_l、_mbctoupper、_mbctoupper_l](../../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)
