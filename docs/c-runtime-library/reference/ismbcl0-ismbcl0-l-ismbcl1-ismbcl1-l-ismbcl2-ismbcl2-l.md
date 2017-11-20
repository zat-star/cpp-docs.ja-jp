---
title: "_ismbcl0、_ismbcl0_l、_ismbcl1、_ismbcl1_l、_ismbcl2、_ismbcl2_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbcl2
- _ismbcl1
- _ismbcl0
- _ismbcl2_l
- _ismbcl1_l
- _ismbcl0_l
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
- ismbcl0
- _ismbcl1_l
- _ismbcl0
- ismbcl1
- ismbcl0_l
- _ismbcl2_l
- ismbcl2
- ismbcl1_l
- _ismbcl1
- _ismbcl0_l
- _ismbcl2
- ismbcl2_l
dev_langs: C++
helpviewer_keywords:
- _ismbcl0_l function
- _ismbcl2 function
- _ismbcl1_l function
- ismbcl2 function
- _ismbcl1 function
- ismbcl0_l function
- ismbcl2_l function
- ismbcl1_l function
- ismbcl0 function
- ismbcl1 function
- _ismbcl2_l function
- _ismbcl0 function
ms.assetid: ee15ebd1-462c-4a43-95f3-6735836d626a
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 25472150345de54898e21bb63e869a74e22e905b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ismbcl0-ismbcl0l-ismbcl1-ismbcl1l-ismbcl2-ismbcl2l"></a>_ismbcl0、_ismbcl0_l、_ismbcl1、_ismbcl1_l、_ismbcl2、_ismbcl2_l
現在のロケールまたは指定された LC_CTYPE 変換状態カテゴリを使用する、**コード ページ 932 固有の関数**。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
int _ismbcl0(  
   unsigned int c   
);  
int _ismbcl0_l(  
   unsigned int c,  
   _locale_t locale  
);  
int _ismbcl1(  
   unsigned int c   
);  
int _ismbcl1_l(  
   unsigned int c ,  
   _locale_t locale  
);  
int _ismbcl2(  
   unsigned int c   
);  
int _ismbcl2_l(  
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
 これらの各ルーチンでは、文字がテスト条件を満たす場合に 0 以外の値が返され、テスト条件を満たさない場合に 0 が返されます。 `c` <= 255 で、対応する `_ismbb` ルーチンがある (たとえば、`_ismbcalnum` は `_ismbbalnum` に対応します) 場合、結果は、対応する `_ismbb` ルーチンの戻り値になります。  
  
## <a name="remarks"></a>コメント  
 これらの各関数は特定の条件で特定のマルチバイト文字をテストします。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」を参照してください。 `_l` サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
|ルーチン|テスト条件 (コード ページ 932 のみ)|  
|-------------|-------------------------------------------|  
|`_ismbcl0`|JIS の非漢字: 0x8140<=`c`<=0x889E。|  
|`_ismbcl0_l`|JIS の非漢字: 0x8140<=`c`<=0x889E。|  
|`_ismbcl1`|JIS のレベル 1: 0x889F<=`c`<=0x9872。|  
|`_ismbcl1_l`|JIS のレベル 1: 0x889F<=`c`<=0x9872。|  
|`_ismbcl2`|JIS のレベル 2: 0x989F<=`c`<=0xEAA4。|  
|`_ismbcl2_l`|JIS のレベル 2: 0x989F<=`c`<=0xEAA4。|  
  
 関数は、指定された値 `c` が、上の表に記載のテスト条件に一致するかどうかをチェックしますが、`c` が有効なマルチバイト文字かどうかはチェックしません。 下位バイトが範囲 0x00 - 0x3F、0x7F、または 0xFD - 0xFF にある場合、これらの関数は 0 以外の値を返し、文字がテスト条件を満たすことを示します。 マルチバイト文字が定義されているかどうかをテストするために [_ismbbtrail](../../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md) を使用します。  
  
 **コード ページ 932 固有情報終了**  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_ismbcl0`|\<mbstring.h>|  
|`_ismbcl0_l`|\<mbstring.h>|  
|`_ismbcl1`|\<mbstring.h>|  
|`_ismbcl1_l`|\<mbstring.h>|  
|`_ismbcl2`|\<mbstring.h>|  
|`_ismbcl2_l`|\<mbstring.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [文字分類](../../c-runtime-library/character-classification.md)   
 [_ismbc 系ルーチン](../../c-runtime-library/ismbc-routines.md)   
 [is、isw 系ルーチン](../../c-runtime-library/is-isw-routines.md)