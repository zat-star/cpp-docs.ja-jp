---
title: "_ismbbtrail、_ismbbtrail_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
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
dev_langs: C++
helpviewer_keywords:
- ismbbtrail_l function
- _ismbbtrail function
- _ismbbtrail_l function
- ismbbtrail function
ms.assetid: dfdd0292-960b-4c1d-bf11-146e0fc80247
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1e5c20e436e7b51b1c4e5463fb56165ae24c264d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
 `_ismbbtrail` は、ロケールに依存する動作に現在のロケールを使用します。 `_ismbbtrail_l` は、代わりに渡されるロケールを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_ismbbtrail`|\<mbctype.h> または \<mbstring.h>|\<ctype.h>、* \<limits.h>、\<stdlib.h>|  
|`_ismbbtrail_l`|\<mbctype.h> または \<mbstring.h>|\<ctype.h>、* \<limits.h>、\<stdlib.h>|  
  
 \* テスト条件のマニフェスト定数の場合。  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [バイト分類](../../c-runtime-library/byte-classification.md)   
 [_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)