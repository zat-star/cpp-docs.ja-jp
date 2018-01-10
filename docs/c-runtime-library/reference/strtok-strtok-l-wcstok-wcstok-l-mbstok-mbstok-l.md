---
title: "strtok、_strtok_l、wcstok、_wcstok_l、_mbstok、_mbstok_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbstok_l
- _mbstok
- wcstok
- _mbstok
- strtok
- _wcstok_l
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbstok
- strtok
- _tcstok
- wcstok
dev_langs: C++
helpviewer_keywords:
- mbstok_l function
- strings [C++], searching
- tcstok function
- _tcstok function
- _strtok_l function
- strtok function
- mbstok function
- wcstok_l function
- _mbstok function
- tcstok_l function
- tokens, finding in strings
- _mbstok_l function
- wcstok function
- _wcstok_l function
- _tcstok_l function
- strtok_l function
ms.assetid: 904cb734-f0d7-4d77-ba81-4791ddf461ae
caps.latest.revision: "34"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aa20ca680481ffce009a362bf0f4b21923ef572d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="strtok-strtokl-wcstok-wcstokl-mbstok-mbstokl"></a>strtok、_strtok_l、wcstok、_wcstok_l、_mbstok、_mbstok_l
現在のロケールまたは渡された指定のロケールを使用して、文字列内の次のトークンを検索します。 これらの関数にはセキュリティが強化されたバージョンがあります。「[strtok_s、_strtok_s_l、wcstok_s、_wcstok_s_l、_mbstok_s、_mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md)」を参照してください。  
  
> [!IMPORTANT]
>  `_mbstok` および `_mbstok_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
char *strtok(  
   char *strToken,  
   const char *strDelimit   
);  
wchar_t *wcstok(  
   wchar_t *strToken,  
   const wchar_t *strDelimit   
);  
unsigned char *_mbstok(  
   unsigned char*strToken,  
   const unsigned char *strDelimit   
);  
unsigned char *_mbstok(  
   unsigned char*strToken,  
   const unsigned char *strDelimit,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `strToken`  
 トークンを含む文字列。  
  
 `strDelimit`  
 区切り記号文字のセット。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 `strToken` で見つかった次のトークンへのポインターを返します。 これ以上トークンがない場合、これらは `NULL` を返します。 各呼び出しは、返されたトークンの後に発生する最初の区切り記号を `strToken` 文字に置き換えることで `NULL` を変更します。  
  
## <a name="remarks"></a>コメント  
 `strtok` 関数は `strToken` の次のトークンを検索します。 `strDelimit` の文字セットは、現在の呼び出しの `strToken` で検索されたトークンの使用可能な区切り記号を指定します。 `wcstok` 関数と `_mbstok` 関数は、`strtok` 関数のワイド文字バージョンとマルチバイト文字バージョンです。 `wcstok` 関数の引数と戻り値はワイド文字列で、`_mbstok` 関数の引数と戻り値はマルチバイト文字列です。 それ以外では、これらの関数の動作は同じです。  
  
> [!IMPORTANT]
>  これらの関数は、バッファー オーバーランが原因で発生する可能性のある問題の影響を受けます。 バッファー オーバーランは、システムを攻撃するときによく使用される方法であり、その結果、認められていない権限が昇格されます。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。  
  
 `strtok` への最初の呼び出しで、関数は先行する区切り記号をスキップし、`strToken` の最初のトークンへのポインターを返して null 文字を含むトークンを終了します。 `strToken` への一連の呼び出しにより、より多くのトークンを `strtok` の残りから作成できます。 各呼び出し`strtok`変更`strToken`後に null 文字を挿入することで、`token`その呼び出しによって返されます。 `strToken` から次のトークンを読み込むには、`strtok` を `NULL` 引数に `strToken` 値を使用して呼び出します。 `NULL` `strToken` 引数により、`strtok` は変更された `strToken` で次のトークンを検索します。 `strDelimit` 引数は、ある呼び出しから次の呼び出しへ任意の値を取ることができるため、区切り記号のセットが異なる場合があります。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定に影響されます。詳細については、「[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」を参照してください。 `_l` サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。  
  
> [!NOTE]
>  各関数は、文字列をトークンに解析する際にスレッド ローカルの静的変数を使用します。 したがって、複数のスレッドが望ましくない影響を受けずに同時にこれらの関数を呼び出すことができます。 ただし、1 つのスレッド内でこれらの関数のいずれかの呼び出しをインターリーブすると、データの破損や正確でない結果が生成される可能性が非常に高くなります。 さまざまな文字列を解析する際、1 つの文字列の解析を完了してから、次の解析を開始します。 また、別の関数が呼び出されているループから、これらの関数の 1 つを呼び出す場合の危険性にも注意してください。 他の関数が最終的にこれらの関数の 1 つを使用した場合、インターリーブされた呼び出しのシーケンスにより、データの破損を招くことがあります。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcstok`|`strtok`|`_mbstok`|`wcstok`|  
|`_tcstok`|`_strtok_l`|`_mbstok_l`|`_wcstok_l`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`strtok`|\<string.h>|  
|`wcstok`|\<string.h> または \<wchar.h>|  
|`_mbstok`, `_mbstok_l`|\<mbstring.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_strtok.c  
// compile with: /W3  
// In this program, a loop uses strtok  
// to print all the tokens (separated by commas  
// or blanks) in the string named "string".  
//  
#include <string.h>  
#include <stdio.h>  
  
char string[] = "A string\tof ,,tokens\nand some  more tokens";  
char seps[]   = " ,\t\n";  
char *token;  
  
int main( void )  
{  
   printf( "Tokens:\n" );  
  
   // Establish string and get the first token:  
   token = strtok( string, seps ); // C4996  
   // Note: strtok is deprecated; consider using strtok_s instead  
   while( token != NULL )  
   {  
      // While there are tokens in "string"  
      printf( " %s\n", token );  
  
      // Get next token:   
      token = strtok( NULL, seps ); // C4996  
   }  
}  
```  
  
```Output  
Tokens:  
 A  
 string  
 of  
 tokens  
 and  
 some  
 more  
 tokens  
```  
  
## <a name="see-also"></a>参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn、wcscspn、_mbscspn、_mbscspn_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strspn、wcsspn、_mbsspn、_mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)