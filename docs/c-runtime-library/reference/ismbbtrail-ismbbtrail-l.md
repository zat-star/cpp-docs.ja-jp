---
title: "_ismbbtrail、_ismbbtrail_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbbtrail
- _ismbbtrail_l
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
- _ismbbtrail
- ismbbtrail
- _ismbbtrail_l
- ismbbtrail_l
dev_langs:
- C++
helpviewer_keywords:
- ismbbtrail_l function
- _ismbbtrail function
- _ismbbtrail_l function
- ismbbtrail function
ms.assetid: dfdd0292-960b-4c1d-bf11-146e0fc80247
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 125b35ecc01c58808fab939649f9b71f5c4ca85f
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="ismbbtrail-ismbbtraill"></a>_ismbbtrail、_ismbbtrail_l
バイトがマルチバイト文字の後続バイトかどうかを判定します。  
  
## <a name="syntax"></a>構文  
  
```  
int _ismbbtrail(  
   unsigned int c   
);  
int _ismbbtrail_l(  
   unsigned int c,  
   _locale_t locale   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `c`  
 テストする整数。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 整数 `c` がマルチバイト文字の 2 番目のバイトの場合、`_ismbbtrail` は 0 以外の値を返します。 たとえば、コード ページ 932 でのみ、有効な範囲は 0x40 – 0x7E、0x80 – 0xFC です。  
  
## <a name="remarks"></a>コメント  
 `_ismbbtrail` は、ロケールに依存する動作に現在のロケールを使用します。 `_ismbbtrail_l` は、代わりに渡されるロケールを使用する点を除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」をご覧ください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_ismbbtrail`|\<mbctype.h> または \<mbstring.h>|\<ctype.h>、* \<limits.h>、\<stdlib.h>|  
|`_ismbbtrail_l`|\<mbctype.h> または \<mbstring.h>|\<ctype.h>、* \<limits.h>、\<stdlib.h>|  
  
 \* テスト条件のマニフェスト定数の場合。  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [バイト分類](../../c-runtime-library/byte-classification.md)   
 [_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)
