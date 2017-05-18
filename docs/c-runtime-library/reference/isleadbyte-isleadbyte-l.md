---
title: "isleadbyte、_isleadbyte_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _isleadbyte_l
- isleadbyte
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _istleadbyte
- _isleadbyte_l
- isleadbyte
dev_langs:
- C++
helpviewer_keywords:
- lead bytes
- _isleadbyte_l function
- _istleadbyte function
- istleadbyte function
- isleadbyte function
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
caps.latest.revision: 20
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 73078df22931a5533ffe912174d11b384c8de417
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="isleadbyte-isleadbytel"></a>isleadbyte、_isleadbyte_l
文字がマルチバイト文字の先行バイトかどうかを判定します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「                  [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
int isleadbyte(  
   int c   
);  
int _isleadbyte_l(  
   int c   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `c`  
 テストする整数。  
  
## <a name="return-value"></a>戻り値  
 `isleadbyte` では、引数がテスト条件を満たす場合に 0 以外の値が返され、テスト条件を満たさない場合に 0 が返されます。 "C" ロケールと 1 バイト文字セット (SBCS) のロケールでは、 `isleadbyte` は常に 0 を返します。  
  
## <a name="remarks"></a>コメント  
 `isleadbyte` のマクロは、引数がマルチバイト文字の先行バイトの場合に 0 以外の値を返します。 `isleadbyte`-1 から任意の整数引数に対して意味のある結果が生成されます (`EOF`) に`UCHAR_MAX`(0 xff) まで、包括的です。  
  
 `isleadbyte` の予想される引数の型は `int`です。符号付き文字が渡されると、コンパイラはこれを符号拡張して整数に変換し、予期しない結果が生じる場合があります。  
  
 この関数の `_l` サフィックスが付いたバージョンは、サフィックスが付いていないバージョンと同じですが、ロケールに依存する動作については、現在のロケールではなく渡されたロケールを使用する点が異なります。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istleadbyte`|常に false を返します|**_** `isleadbyte`|常に false を返します|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`isleadbyte`|\<ctype.h>|  
|`_isleadbyte_l`|\<ctype.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [バイト分類](../../c-runtime-library/byte-classification.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [_ismbb 系ルーチン](../../c-runtime-library/ismbb-routines.md)
