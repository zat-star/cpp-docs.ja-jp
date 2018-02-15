---
title: _set_printf_count_output | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _set_printf_count_output
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_printf_count_output
- _set_printf_count_output
dev_langs:
- C++
helpviewer_keywords:
- '%n format'
- set_printf_count_output function
- _set_printf_count_output function
ms.assetid: d8259ec5-764e-42d0-9169-72172e95163b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 279b14f0387348d322bbe09428af24daa5fd2f69
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="setprintfcountoutput"></a>_set_printf_count_output
[printf、_printf_l、wprintf、_wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) ファミリの関数で、`%n` 形式のサポートを有効または無効にします。  
  
## <a name="syntax"></a>構文  
  
```  
int _set_printf_count_output(  
   int enable  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `enable`  
 ゼロ以外の値の場合には `%n` のサポートを有効にし、ゼロの場合には `%n` のサポートを無効にします。  
  
## <a name="property-valuereturn-value"></a>プロパティ値/戻り値  
 この関数を呼び出す前の `%n` サポートの状態は次のとおりです: `%n` サポートが有効だった場合にはゼロ以外。無効だった場合にはゼロ。  
  
## <a name="remarks"></a>コメント  
 セキュリティ上の理由で、`%n` 形式指定子のサポートは、`printf` とそのすべてのバリアントにおいて既定で無効になっています。 `printf` 形式指定に `%n` がある場合には、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、既定の動作として無効なパラメーター ハンドラーが呼び出されます。 呼び出す`_set_printf_count_output`0 以外の引数を持つにより`printf`-ファミリの関数を解釈する`%n`」の説明に従って[書式指定構文: printf 関数と wprintf 関数](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)です。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_set_printf_count_output`|\<stdio.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
  
```C  
// crt_set_printf_count_output.c  
#include <stdio.h>  
  
int main()  
{  
   int e;  
   int i;  
   e = _set_printf_count_output( 1 );  
   printf( "%%n support was %sabled.\n",  
        e ? "en" : "dis" );  
   printf( "%%n support is now %sabled.\n",  
        _get_printf_count_output() ? "en" : "dis" );  
   printf( "12345%n6789\n", &i ); // %n format should set i to 5  
   printf( "i = %d\n", i );  
}  
```  
  
```Output  
%n support was disabled.  
%n support is now enabled.  
123456789  
i = 5  
```  
  
## <a name="see-also"></a>参照  
 [_get_printf_count_output](../../c-runtime-library/reference/get-printf-count-output.md)