---
title: "_mbsbtype、_mbsbtype_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsbtype_l
- _mbsbtype
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
- mbsbtype
- mbsbtype_l
- _mbsbtype_l
- _mbsbtype
dev_langs:
- C++
helpviewer_keywords:
- _mbsbtype function
- mbsbtype function
- _mbsbtype_l function
- mbsbtype_l function
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: a20ff8b10229714a434dc0f77748f37f9c15064a
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="mbsbtype-mbsbtypel"></a>_mbsbtype、_mbsbtype_l
文字列内のバイトの種類を返します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
int _mbsbtype(  
   const unsigned char *mbstr,  
   size_t count   
);  
int _mbsbtype_l(  
   const unsigned char *mbstr,  
   size_t count,  
   _locale_t locale   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `mbstr`  
 マルチバイト文字のシーケンスのアドレス。  
  
 `count`  
 文字列の先頭からのバイト オフセット。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 `_mbsbtype`および`_mbsbtype_l`指定したバイトのテストの結果を示す整数値を返します。 次の表のマニフェスト定数は、Mbctype.h で定義されています。  
  
|戻り値|バイトの種類|  
|------------------|---------------|  
|`_MBC_SINGLE` (0)|1 バイト文字。 たとえば、コード ページ 932 で`_mbsbtype`指定したバイト範囲は、0x20-0x7E または 0xA1 - 0 xdf 場合 0 を返します。|  
|`_MBC_LEAD` (1)|マルチバイト文字の先行バイト。 たとえば、コード ページ 932 で`_mbsbtype`指定したバイト範囲は、0x81 から 0x9F または 0xE0 - - 0 xfc 場合 1 を返します。|  
|`_MBC_TRAIL` (2)|マルチバイト文字の後続バイト。 たとえば、コード ページ 932 で`_mbsbtype`指定したバイト範囲は、0x40 ~ 0x7E または 0x80 ~ 0 xfc 2 を返します。|  
|`_MBC_ILLEGAL` (-1)|`NULL` のオフセット `NULL` の位置にあるバイトの前に見つかった、`count` 文字列、無効な文字、または `mbstr` バイト。|  
  
## <a name="remarks"></a>コメント  
 `_mbsbtype` 関数は、マルチバイト文字列のバイトの種類を判断します。 この関数は、`count` のオフセット `mbstr` の位置にあるバイトだけを調べます。指定されたバイトの前にある無効な文字は無視します。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」をご覧ください。 `_l` サフィックスが付いていないこの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」をご覧ください。  
  
 入力文字列が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、`errno` が `EINVAL` に設定され、関数から `_MBC_ILLEGAL` が返されます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_mbsbtype`|\<mbstring.h>|\<mbctype.h>*|  
|`_mbsbtype_l`|\<mbstring.h>|\<mbctype.h>*|  
  
 \* 戻り値として使用されるマニフェスト定数の場合。  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [バイト分類](../../c-runtime-library/byte-classification.md)
