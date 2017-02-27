---
title: _get_output_format |Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_output_format
apilocation:
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- get_output_format
- _get_output_format
dev_langs:
- C++
helpviewer_keywords:
- output formatting
- get_output_format function
- _get_output_format function
ms.assetid: 0ce42f3b-3479-41c4-bcbf-1d21f7ee37e7
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: e923c8f4dcfbf2a2392c6b70fee2c5dc423c34c6

---
# <a name="getoutputformat"></a>_get_output_format
出力形式フラグの現在の値を取得します。  
  
> [!IMPORTANT]
>  これは古い関数です。 Visual Studio 2015 以降、CRT で使用できません。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned int _get_output_format();  
```  
  
## <a name="return-value"></a>戻り値  
 出力形式フラグの現在の値。  
  
## <a name="remarks"></a>コメント  
 出力形式フラグは、書式付き I/O の機能を制御します。 現在、このフラグに指定できるのは 0 と `_TWO_DIGIT_EXPONENT`という 2 つの値です。 `_TWO_DIGIT_EXPONENT` に設定すると、指数部の大きさによって&3; 桁目が必要になる場合を除いて、浮動小数点数の指数部は&2; 桁のみで出力されます。 このフラグを&0; に設定すると、浮動小数点数の指数部は&3; 桁で出力され、必要な場合は&0; を埋め込んで&3; 桁にされます。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_get_output_format`|\<stdio.h>|  
  
 互換性について詳しくは、概要の「[互換性](../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [printf、_printf_l、wprintf、_wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [printf_s、_printf_s_l、wprintf_s、_wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [printf 関数の型フィールド文字](../c-runtime-library/printf-type-field-characters.md)   
 [_set_output_format](../c-runtime-library/set-output-format.md)


<!--HONumber=Feb17_HO4-->


