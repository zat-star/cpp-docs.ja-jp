---
title: "_strdec、_wcsdec、_mbsdec、_mbsdec_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcsdec
- _strdec
- _mbsdec
- _mbsdec_l
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
- _strdec
- mbsdec_l
- strdec
- _mbsdec
- _mbsdec_l
- mbsdec
- wcsdec
- _wcsdec
dev_langs:
- C++
helpviewer_keywords:
- mbsdec_l function
- mbsdec function
- tcsdec function
- _tcsdec function
- _strdec function
- _wcsdec function
- _mbsdec_l function
- strdec function
- wcsdec function
- _mbsdec function
ms.assetid: ae37c223-800f-48a9-ae8e-38c8d20af2dd
caps.latest.revision: 24
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 08ab806a3f2852109dda05d40e7264dbd8571298
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="strdec-wcsdec-mbsdec-mbsdecl"></a>_strdec、_wcsdec、_mbsdec、_mbsdec_l
文字列ポインターを 1 文字前へ移動します。  
  
> [!IMPORTANT]
>  `mbsdec` と `mbsdec_l` は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] で実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned char *_strdec(  
   const unsigned char *start,  
   const unsigned char *current   
);  
unsigned wchar_t *_wcsdec(  
   const unsigned wchar_t *start,  
   const unsigned wchar_t *current   
);  
unsigned char *_mbsdec(  
   const unsigned char *start,  
   const unsigned char *current   
);  
unsigned char *_mbsdec_l(  
   const unsigned char *start,  
   const unsigned char *current,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `start`  
 任意の文字へのポインター (または`_mbsdec`と`_mbsdec_l`、任意のマルチバイト文字の最初のバイト) 元の文字列です。`start`前に指定する必要があります`current`元の文字列。  
  
 `current`  
 任意の文字へのポインター (または`_mbsdec`と`_mbsdec_l`、任意のマルチバイト文字の最初のバイト) 元の文字列です。`current`従う必要があります`start`元の文字列。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 `_mbsdec`、 `_mbsdec_l`、 `_strdec`、および`_wcsdec`直前にある文字へのポインターを返す各`current`です。`_mbsdec`返します`NULL`場合の値`start`以上のものには、`current`です。 `_tcsdec` は、これらの関数の 1 つに割り当てられます。戻り値は割り当てによって異なります。  
  
## <a name="remarks"></a>コメント  
 `_mbsdec` 関数と `_mbsdec_l` 関数は、`current` を含む文字列の `start` に先行するマルチバイト文字の最初のバイトへのポインターを返します。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」を参照してください。  `_mbsdec` は、現在使用中のロケールに従ってマルチバイト文字シーケンスを認識します。`_mbsdec_l` は、渡されたロケール パラメーターを代わりに使用することを除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 `start` または `current` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は `EINVAL` を返し、`errno` を `EINVAL` に設定します。  
  
> [!IMPORTANT]
>  これらの関数は、バッファー オーバーランの脅威に対して脆弱な場合があります。 バッファー オーバーランは、認められていない特権の昇格の原因となるため、システムの攻撃に使用される可能性があります。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcsdec`|`_strdec`|`_mbsdec`|`_wcsdec`|  
  
 `_strdec` と `_wcsdec` はそれぞれ、`_mbsdec` と `_mbsdec_l` の 1 バイト文字バージョンとワイド文字バージョンです。 `_strdec` と `_wcsdec` はこの割り当てにのみ使用し、それ以外には使用しないでください。  
  
 詳細については、「[汎用テキスト マップの使用](../../c-runtime-library/using-generic-text-mappings.md)」および「[汎用テキスト マップ](../../c-runtime-library/generic-text-mappings.md)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|-------------|---------------------|---------------------|  
|`_mbsdec`|\<mbstring.h>|\<mbctype.h>|  
|`_mbsdec_l`|\<mbstring.h>|\<mbctype.h>|  
|`_strdec`|\<tchar.h>||  
|`_wcsdec`|\<tchar.h>||  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
 `_tcsdec` を使用する例を次に示します。  
  
```  
  
      #include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main()  
{  
   const TCHAR *str = _T("12345");  
   cout << "str: " << str << endl;  
  
   const TCHAR *str2;  
   str2 = str + 2;  
   cout << "str2: " << str2 << endl;  
  
   TCHAR *answer;  
   answer = _tcsdec( str, str2 );  
   cout << "answer: " << answer << endl;  
  
   return (0);   
}  
  
```  
  
 `_mbsdec` を使用する例を次に示します。  
  
```  
#include <iostream>  
#include <mbstring.h>  
using namespace std;  
  
int main()   
{   
   char *str = "12345";  
   cout << "str: " << str << endl;  
  
   char *str2;  
   str2 = str + 2;   
   cout << "str2: " << str2 << endl;  
  
   unsigned char *answer;  
   answer = _mbsdec( reinterpret_cast<unsigned char *>( str ), reinterpret_cast<unsigned char *>( str2 ));  
  
   cout << "answer: " << answer << endl;  
  
   return (0);   
}  
  
```  
  
## <a name="see-also"></a>関連項目  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [_strinc、_wcsinc、_mbsinc、_mbsinc_l](../../c-runtime-library/reference/strinc-wcsinc-mbsinc-mbsinc-l.md)   
 [_strnextc、_wcsnextc、_mbsnextc、_mbsnextc_l](../../c-runtime-library/reference/strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)   
 [_strninc、_wcsninc、_mbsninc、_mbsninc_l](../../c-runtime-library/reference/strninc-wcsninc-mbsninc-mbsninc-l.md)
