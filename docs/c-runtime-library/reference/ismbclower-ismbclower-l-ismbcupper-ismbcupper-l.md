---
title: "_ismbclower、_ismbclower_l、_ismbcupper、_ismbcupper_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbclower
- _ismbclower_l
- _ismbcupper_l
- _ismbcupper
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
- _ismbcupper
- _ismbclower
dev_langs:
- C++
helpviewer_keywords:
- _ismbcupper function
- ismbclower function
- _ismbclower_l function
- ismbcupper_l function
- _ismbclower function
- ismbcupper function
- ismbclower_l function
- _ismbcupper_l function
ms.assetid: 17d89587-65bc-477c-ba8f-a84e63cf59e7
caps.latest.revision: 19
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
ms.openlocfilehash: 2d62b6859490047796d66cc2b56090a130ffd5f9
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="ismbclower-ismbclowerl-ismbcupper-ismbcupperl"></a>_ismbclower、_ismbclower_l、_ismbcupper、_ismbcupper_l
マルチバイト文字が小文字または大文字であるかどうかをチェックします。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
int _ismbclower(  
   unsigned int c   
);  
int _ismbclower_l(  
   unsigned int c,  
   _locale_t locale   
);  
int _ismbcupper(  
   unsigned int c   
);  
int _ismbcupper_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `c`  
 テストする文字。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 これらの各ルーチンでは、文字がテスト条件を満たす場合に 0 以外の値が返され、テスト条件を満たさない場合に 0 が返されます。 `c`<= 255 で、対応する `_ismbb` ルーチンがある (たとえば、`_ismbcalnum` は `_ismbbalnum` に対応します) 場合、結果は、対応する `_ismbb` ルーチンの戻り値になります。  
  
## <a name="remarks"></a>コメント  
 これらの各関数は特定の条件で特定のマルチバイト文字をテストします。  
  
 これらの関数のうち `_l` サフィックスが付けられたバージョンは同じですが、ロケールに依存する動作に現在のロケールではなく渡されたロケールを使用するという点で異なります。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」をご覧ください。  
  
|ルーチン|テスト条件|コード ページ 932 の例|  
|-------------|--------------------|---------------------------|  
|`_ismbclower`|小文字の英字|`c` が ASCII 小文字の英字 (0x61<=`c`<=0x7A) の 1 バイト表現である場合に限り、0 以外の値を返します。|  
|`_ismbclower_l`|小文字の英字|`c` が ASCII 小文字の英字 (0x61<=`c`<=0x7A) の 1 バイト表現である場合に限り、0 以外の値を返します。|  
|`_ismbcupper`|大文字の英字|`c` が ASCII 大文字の英字 (0x41<=`c`<=0x5A) の 1 バイト表現である場合に限り、0 以外の値を返します。|  
|`_ismbcupper_l`|大文字の英字|`c` が ASCII 大文字の英字 (0x41<=`c`<=0x5A) の 1 バイト表現である場合に限り、0 以外の値を返します。|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_ismbclower`|\<mbstring.h>|  
|`_ismbclower_l`|\<mbstring.h>|  
|`_ismbcupper`|\<mbstring.h>|  
|`_ismbcupper_l`|\<mbstring.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [文字分類](../../c-runtime-library/character-classification.md)   
 [_ismbc 系ルーチン](../../c-runtime-library/ismbc-routines.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)   
 [_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)
