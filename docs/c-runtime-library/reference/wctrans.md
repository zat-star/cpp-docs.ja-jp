---
title: wctrans | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wctrans
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords: wctrans
dev_langs: C++
helpviewer_keywords:
- character codes, wctrans
- characters, codes
- characters, converting
- wctrans function
ms.assetid: 215404bf-6d60-489c-9ae9-880e6b586162
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: babda33f03b29e2b8ccaa9967038c3299c4bc6ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="wctrans"></a>wctrans
文字コードの 1 つのセットから別のセットへのマッピングを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
wctrans_t wctrans(  
   const char *property   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `property`  
 有効な変換のいずれかを指定する文字列。  
  
## <a name="return-value"></a>戻り値  
 現在のロケールの `LC_CTYPE` カテゴリが、名前がプロパティ文字列 `property` に一致するマッピングを定義しない場合、この関数は 0 を返します。 それ以外の場合、[towctrans](../../c-runtime-library/reference/towctrans.md) への後続の呼び出しに対する 2 番目の引数として使用するのに適した 0 以外の値を返します。  
  
## <a name="remarks"></a>コメント  
 この関数では、文字コードの 1 つのセットから別のセットへのマッピングを指定します。  
  
 次の呼び出しのペアの動作はすべてのロケールで同じですが、"C" ロケールであっても追加のマッピングを定義できます。  
  
|関数|同等なもの|  
|--------------|-------------|  
|`tolower(`  `c`  `)`|`towctrans(`  `c` `, wctrans("towlower" ) )`|  
|`towupper(`  `c`  `)`|`towctrans(`  `c` `, wctrans( "toupper" ) )`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`wctrans`|\<wctype.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_wctrans.cpp  
// compile with: /EHsc  
// This example determines a mapping from one set of character  
// codes to another.   
  
#include <wchar.h>  
#include <wctype.h>  
#include <stdio.h>  
#include <iostream>  
  
int main()   
{  
    wint_t c = 'a';  
    printf_s("%d\n",c);  
  
    wctrans_t i = wctrans("toupper");  
    printf_s("%d\n",i);  
  
    wctrans_t ii = wctrans("towlower");  
    printf_s("%d\n",ii);  
  
    wchar_t wc = towctrans(c, i);  
    printf_s("%d\n",wc);  
}  
```  
  
```Output  
97  
1  
0  
65  
```  
  
## <a name="see-also"></a>参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)