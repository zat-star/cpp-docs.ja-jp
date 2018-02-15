---
title: "_mbbtombc、_mbbtombc_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _mbbtombc_l
- _mbbtombc
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
- _mbbtombc_l
- _mbbtombc
- mbbtombc_l
- mbbtombc
dev_langs:
- C++
helpviewer_keywords:
- mbbtombc_l function
- mbbtombc function
- _mbbtombc_l function
- _mbbtombc function
ms.assetid: 78593389-b0fc-43b6-8c1f-2a6bf702d64e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17f0cfa6c4162eee1422def2343f38745183e1b4
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="mbbtombc-mbbtombcl"></a>_mbbtombc、_mbbtombc_l
1 バイトのマルチバイト文字を、対応する 2 バイトのマルチバイト文字に変換します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、次を参照してください。[ユニバーサル Windows プラットフォーム アプリでサポートされない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned int _mbbtombc(  
   unsigned int c   
);  
unsigned int _mbbtombc_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `c`  
 変換する 1 バイト文字。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 `_mbbtombc` は、`c` を正常に変換できた場合は、マルチバイト文字を返します。それ以外の場合は、`c` を返します。  
  
## <a name="remarks"></a>コメント  
 `_mbbtombc` 関数は、与えられた 1 バイトのマルチバイト文字を、対応する 2 バイトのマルチバイト文字に変換します。 文字が変換する 0 xdf の範囲 0x20-0x7E または 0xA1 - 内になければなりません。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」をご覧ください。 この関数の各バージョンは、ロケールに依存するこの動作について、`_mbbtombc` は現在のロケールを使用し、`_mbbtombc_l` は渡されるロケール パラメーターを代わりに使用する点を除いて、同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。  
  
 以前のバージョンでは、`_mbbtombc` は `hantozen` という名前でした。 新しいコードでは、`_mbbtombc` を使用してください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_mbbtombc`|\<mbstring.h>|  
|`_mbbtombc_l`|\<mbstring.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [_mbctombb、_mbctombb_l](../../c-runtime-library/reference/mbctombb-mbctombb-l.md)