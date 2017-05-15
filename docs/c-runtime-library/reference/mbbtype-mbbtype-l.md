---
title: "_mbbtype、_mbbtype_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbbtype
- _mbbtype_l
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
- _mbbtype_l
- mbbtype
- mbbtype_l
- _mbbtype
dev_langs:
- C++
helpviewer_keywords:
- _mbbtype function
- _mbbtype_l function
- mbbtype function
- mbbtype_l function
ms.assetid: b8e34b40-842a-4298-aa39-0bd2d8e51c2a
caps.latest.revision: 18
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: e7b9c7aed7205e6cac428a0f627525f9484afc5a
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="mbbtype-mbbtypel"></a>_mbbtype、_mbbtype_l
前のバイトに基づいて、バイトの種類を返します。  
  
> [!IMPORTANT]
>  この API は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
int _mbbtype(  
   unsigned char c,  
   int type   
);  
int _mbbtype_l(  
   unsigned char c,  
   int type,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `c`  
 テスト対象の文字。  
  
 `type`  
 テストするバイトの種類。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 `_mbbtype` は、文字列内のバイトの種類を返します。 この判断は、テスト条件を制御する `type` の値で指定されるとおり、状況に応じて異なります。 `type` は、文字列内の前のバイトの種類です。 次の表のマニフェスト定数は、Mbctype.h で定義されています。  
  
|`type` の値|`_mbbtype` によるテスト対象|戻り値|`c`|  
|---------------------|--------------------------|------------------|---------|  
|1 以外の値|有効な 1 バイトまたは先頭バイト|`_MBC_SINGLE` (0)|1 バイト (0x20 - 0x7E、0xA1 - 0 xdf)|  
|1 以外の値|有効な 1 バイトまたは先頭バイト|`_MBC_LEAD` (1)|マルチバイト文字の先行バイト (0x81 - 0x9F、0xE0 - 0 xfc)|  
|1 以外の値|有効な 1 バイトまたは先頭バイト|`_MBC_ILLEGAL`<br /><br /> ( -1)|無効な文字 (任意以外の値 0x20 - 0x7E、0xA1 - 0 xdf、0x81 - 0x9F、0xE0 - 0 xfc|  
|1|有効な末尾バイト|`_MBC_TRAIL` (2)|マルチバイト文字の後続バイト (0x40 ~ 0x7E、0x80 ~ 0 xfc)|  
|1|有効な末尾バイト|`_MBC_ILLEGAL`<br /><br /> ( -1)|無効な文字 (任意以外の値 0x20 - 0x7E、0xA1 - 0 xdf、0x81 - 0x9F、0xE0 - 0 xfc|  
  
## <a name="remarks"></a>コメント  
 `_mbbtype` 関数は、マルチバイト文字内のバイトの種類を判断します。 `type` の値が 1 以外の場合、`_mbbtype` は、有効な 1 バイト文字、またはマルチバイト文字の先頭バイトであるかどうかをテストします。 `type` の値が 1 の場合、`_mbbtype` は、マルチバイト文字の有効な末尾バイトであるかどうかをテストします。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」をご覧ください。 この関数の `_mbbtype` バージョンは、ロケールに依存するこの動作について現在のロケールを使用します。`_mbbtype_l` バージョンは、渡されるロケール パラメーターを代わりに使用することを除いて、同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」をご覧ください。  
  
 以前のバージョンでは、`_mbbtype` は `chkctype` という名前でした。 新しいコードでは、`_mbbtype` を使用してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_mbbtype`|\<mbstring.h>|\<mbctype.h>*|  
|`_mbbtype_l`|\<mbstring.h>|\<mbctype.h>*|  
  
 \* 戻り値として使用されるマニフェスト定数の定義。  
  
 互換性について詳しくは、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [バイト分類](../../c-runtime-library/byte-classification.md)
