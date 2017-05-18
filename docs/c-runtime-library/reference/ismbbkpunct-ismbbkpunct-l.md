---
title: "_ismbbkpunct、_ismbbkpunct_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbbkpunct_l
- _ismbbkpunct
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
- ismbbkpunct_l
- _ismbbkpunct_l
- ismbbkpunct
- _ismbbkpunct
dev_langs:
- C++
helpviewer_keywords:
- _ismbbkpunct_l function
- ismbbkpunct_l function
- ismbbkpunct function
- _ismbbkpunct function
ms.assetid: a04c59cd-5ca7-4296-bec0-2b0d7f04edd0
caps.latest.revision: 19
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: edfd9d72c2e83d83d8e31de967a9d0f183523906
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ismbbkpunct-ismbbkpunctl"></a>_ismbbkpunct、_ismbbkpunct_l
マルチバイト文字が区切り文字かどうかをチェックします。  
  
## <a name="syntax"></a>構文  
  
```  
int _ismbbkpunct(  
   unsigned int c   
);  
int _ismbbkpunct_l(  
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
 `_ismbbkpunct` は、整数 `c` が非 ASCII の区切り記号の場合に 0 以外の値を返し、それ以外の場合は 0 を返します。 たとえば、コード ページ 932 でのみ `_ismbbkpunct` は、カタカナ区切り文字をテストします。 `_ismbbkpunct` は、ロケールに依存する任意の文字設定に現在のロケールを使用します。 `_ismbbkpunct_l` は、渡されるロケールを使用することを除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」をご覧ください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_ismbbkpunct`|\<mbctype.h>|  
|`_ismbbkpunct_l`|\<mbctype.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [バイト分類](../../c-runtime-library/byte-classification.md)   
 [_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)
