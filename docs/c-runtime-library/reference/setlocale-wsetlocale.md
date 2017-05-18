---
title: "setlocale、_wsetlocale | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wsetlocale
- setlocale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wsetlocale
- _tsetlocale
- setlocale
dev_langs:
- C++
helpviewer_keywords:
- wsetlocale function
- setlocale function
- tsetlocale function
- locales, defining
- _tsetlocale function
- defining locales
- _wsetlocale function
ms.assetid: 3ffb684e-5990-4202-9553-b5339af9520d
caps.latest.revision: 31
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 5a83ef5640a72dcd2ff8f7f35c587789dff35d61
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="setlocale-wsetlocale"></a>setlocale、_wsetlocale
実行時ロケールを設定または取得します。  
  
## <a name="syntax"></a>構文  
  
```  
char *setlocale(  
   int category,  
   const char *locale   
);  
wchar_t *_wsetlocale(  
   int category,  
   const wchar_t *locale   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `category`  
 ロケールに影響されるカテゴリ。  
  
 `locale`  
 ロケールの指定子。  
  
## <a name="return-value"></a>戻り値  
 有効な `locale` と `category` が指定された場合は、指定された `locale` と `category` に関連付けられている文字列へのポインターを返します。 `locale` または `category` が無効な場合、null ポインターを返します。プログラムの現在のロケール設定は変更されません。  
  
 たとえば、  
  
 `setlocale( LC_ALL, "en-US" );`  
  
 を呼び出すと、すべてのカテゴリを設定し、文字列だけを返します  
  
 `en-US`  
  
 `setlocale` によって返された文字列をコピーして、プログラムのロケール情報のその部分を復元できます。 `setlocale` によって返された文字列に対しては、グローバルまたはスレッド ローカル ストレージが使用されます。 その後 `setlocale` を呼び出すと文字列が上書きされ、前の呼び出しで返された文字列のポインターは無効になります。  
  
## <a name="remarks"></a>コメント  
 `setlocale` および `locale` で指定されている現在のプログラムのロケール情報の一部またはすべてを設定、変更、または照会するには、`category` 関数を使用します。 `locale` とは、地域性、つまり国や地域、言語に関する情報であり、この情報に基づいてプログラムのさまざまな側面をカスタマイズできます。 ロケールに依存するカテゴリとしては、日付の形式や通貨値の表示形式などがあります。 `locale` を、コンピューターでサポートされているさまざまな形式を持つ言語の既定の文字列に設定した場合は、`setlocale` 戻り値をチェックして、有効な言語を確認する必要があます。 たとえば、`locale` を "chinese" に設定した場合、戻り値は "chinese-simplified" または "chinese-traditional" のいずれかです。  
  
 ワイド文字を扱う場合は、`_wsetlocale` ではなく `setlocale` を使用します。`locale` の場合、`_wsetlocale` 引数にはワイド文字列を指定します。また戻り値もワイド文字列です。 それ以外では、`_wsetlocale` と `setlocale` の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsetlocale`|`setlocale`|`setlocale`|`_wsetlocale`|  
  
 `category` 引数は、影響を受けるプログラムのロケール情報の部分を指定します。 `category` に使用するマクロ、および影響されるプログラムの一部は次のとおりです。  
  
 `LC_ALL`  
 次の一覧のすべてのカテゴリ。  
  
 `LC_COLLATE`  
 `strcoll`、`_stricoll`、`wcscoll`、`_wcsicoll`、`strxfrm`、`_strncoll`、`_strnicoll`、`_wcsncoll`、`_wcsnicoll`、および `wcsxfrm` の各関数。  
  
 `LC_CTYPE`  
 文字処理関数の (影響を受けない `isdigit`、`isxdigit`、`mbstowcs`、および `mbtowc` を除く)。  
  
 `LC_MONETARY`  
 `localeconv` 関数が返す通貨形式情報。  
  
 `LC_NUMERIC`  
 `printf` などの書式化出力ルーチン、データ変換ルーチン、および `localeconv` が返す通貨形式以外の形式情報で使用される小数点文字。 小数点文字に加え、`LC_NUMERIC` は、桁区切り記号、および [localeconv](../../c-runtime-library/reference/localeconv.md) によって返されるグループ化コントロールの文字列も設定します。  
  
 `LC_TIME`  
 `strftime` および `wcsftime` 関数。  
  
 この関数は、カテゴリ パラメーターを検証します。 カテゴリ パラメーターが前の表に示されている値のいずれでもない場合は、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`NULL` を返します。  
  
 The `locale` 引数は、ロケールを指定する文字列へのポインターです。 `locale` 引数の形式については、「[ロケール名、言語、および国/地域識別文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)」をご覧ください。 `locale` が空の文字列をポイントしている場合は、実装定義のネイティブ環境になります。 `C` の値は、C 翻訳のための ANSI に準拠した最小環境を指定します。 `C` ロケールは、すべての `char` データ型が 1 バイトであり、それらの値は常に 256 未満であると推定します。  
  
 プログラムの開始時に、次のステートメントの等価性の確認が実行されます。  
  
 `setlocale( LC_ALL, "C" );`  
  
 `locale` 引数には、ロケール名、言語識別文字列、言語識別文字列と国/地域コード、コード ページ、または言語識別文字列、国/地域コード、コード ページを指定できます。 使用できるロケール名、言語、国/地域コード、およびコード ページのセットには、1 文字に 2 バイトを超えるデータを必要とする (UTF-7、UTF-8 など) コード ページを除き、Windows の NLS API でサポートされるすべてが含まれています。 UTF-7 または UTF-8 のコード ページ値を指定すると、`setlocale` は失敗し、NULL を返します。 `setlocale` でサポートされているロケール名のセットについては、「[ロケール名、言語、および国/地域識別文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)」に記載されています。 `setlocale` でサポートされる言語識別文字列と国/地域識別文字列は、「[言語識別文字列](../../c-runtime-library/language-strings.md)」および「[国/地域識別文字列](../../c-runtime-library/country-region-strings.md)」に記載されています。 パフォーマンス上の理由と、コードに埋め込まれた、またはストレージに対してシリアル化されたロケール文字列の保守容易性の理由により、ロケール名形式を使用することをお勧めします。 オペレーティング システムの更新によってロケール名の文字列が変更される可能性は、言語および国/地域名の形式よりも低くなっています。  
  
 `locale` 引数として null ポインターを渡すことは、`setlocale` が国際的な環境を設定するのではなく、照会することを意味します。 `locale` 引数が null ポインターの場合、プログラムの現在のロケール設定は変更されません。 代わりに、`setlocale` は、スレッドの現在のロケールの `category` に対応する文字列へのポインターを返します。 `category` 引数が `LC_ALL` の場合、関数は各カテゴリの現在の設定を表すセミコロンで区切られた文字列を返します。 たとえば、呼び出しのシーケンス   
  
 `// Set all categories and return "en-US"`  
  
 `setlocale(LC_ALL, "en-US");`  
  
 `// Set only the LC_MONETARY category and return "fr-FR"`  
  
 `setlocale(LC_MONETARY, "fr-FR");`  
  
 `printf("%s\n", setlocale(LC_ALL, NULL));`  
  
 の場合、  
  
 `LC_COLLATE=en-US;LC_CTYPE=en-US;LC_MONETARY=fr-FR;LC_NUMERIC=en-US;LC_TIME=en-US`  
  
 は、`LC_ALL` カテゴリに対応する文字列です。  
  
 次の例は `LC_ALL` のカテゴリに関連するものです。 文字列 ".OCP" および ".ACP" のどちらかをコード ページ番号の代わりに使用して、それぞれの文字列で、ユーザー既定の OEM コード ページおよびユーザー既定の ANSI コード ページを使用することを指定できます。  
  
 `setlocale( LC_ALL, "" );`  
 ロケールを既定に設定します。これはオペレーティング システムから取得したユーザー既定の ANSI コード ページです。  
  
 `setlocale( LC_ALL, ".OCP" );`  
 ロケールに、オペレーティング システムから取得した現在の OEM コード ページを明示的に設定します。  
  
 `setlocale( LC_ALL, ".ACP" );`  
 ロケールに、オペレーティング システムから取得した ANSI コード ページを設定します。  
  
 `setlocale( LC_ALL, "<localename>" );`  
 ロケールに、*\<localename>* で表されるロケール名を設定します。  
  
 `setlocale( LC_ALL, "<language>_<country>" );`  
 ロケールに、*\<language>* と *\<country>* で表される言語と国/地域、およびホスト オペレーティング システムから取得した既定のコード ページを設定します。  
  
 `setlocale( LC_ALL, "<language>_<country>.<code_page>" );`  
 ロケールに、*\<language>*、*\<country>*、および *<code_page>* 文字列によって表される言語、国/地域、コード ページを設定します。 言語、国/地域、およびコード ページはさまざまに組み合わせて使用できます。 たとえば、次の呼び出しは、ロケールに、カナダ フランス語、およびコード ページ 1252 を設定します。  
  
 `setlocale( LC_ALL, "French_Canada.1252" );`  
  
 次の呼び出しは、ロケールに、カナダ フランス語、および既定の ANSI コード ページを設定します。  
  
 `setlocale( LC_ALL, "French_Canada.ACP" );`  
  
 次の呼び出しは、ロケールに、カナダ フランス語、および既定の OEM コード ページを設定します。  
  
 `setlocale( LC_ALL, "French_Canada.OCP" );`  
  
 `setlocale( LC_ALL, "<language>" );`  
 ロケールに *\<language>* で表される言語を設定し、指定した言語の既定の国/地域と、その国/地域のユーザー既定の ANSI コード ページをホスト オペレーティング システムから取得して使用します。 たとえば、次の `setlocale` の呼び出しは同等です。  
  
 `setlocale( LC_ALL, "en-US" );`  
  
 `setlocale( LC_ALL, "English" );`  
  
 `setlocale( LC_ALL, "English_United States.1252" );`  
  
 パフォーマンスと保守性の理由から、最初の形式を使用することをお勧めします。  
  
 `setlocale( LC_ALL, ".<code_page>" );`  
 コード ページに、*<code_page>* で表される値、および指定したコード ページの既定の国/地域と言語 (ホスト オペレーティング システムによって定義) を設定します。  
  
 カテゴリは、コード ページの変更に影響する `LC_ALL` または `LC_CTYPE` である必要があります。 たとえば、ホスト オペレーティング システムの既定の国/地域と言語が "United States" と "English" の場合、次の `setlocale` の 2 種類の呼び出しは機能的に同じです。  
  
 `setlocale( LC_ALL, ".1252" );`  
  
 `setlocale( LC_ALL, "English_United States.1252");`  
  
 詳細については、「[C/C++ プリプロセッサ リファレンス](../../preprocessor/c-cpp-preprocessor-reference.md)」の [setlocale](../../preprocessor/setlocale.md) pragma ディレクティブをご覧ください。  
  
 `setlocale` がプログラムのすべてのスレッドのロケールに影響するか、または呼び出しスレッドのロケールだけに影響するかを制御するには、関数 [_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md) を使用します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`setlocale`|\<locale.h>|  
|`_wsetlocale`|\<locale.h> または \<wchar.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```C  
// crt_setlocale.c  
//   
// This program demonstrates the use of setlocale when  
// using two independent threads.  
//  
  
#include <locale.h>  
#include <process.h>  
#include <windows.h>  
#include <stdio.h>  
#include <time.h>  
  
#define BUFF_SIZE 100  
  
// Retrieve the date in the current  
// locale's format.  
int get_date(unsigned char* str)  
{  
    __time64_t ltime;  
    struct tm  thetime;  
  
    // Retrieve the current time  
    _time64(&ltime);  
    _gmtime64_s(&thetime, &ltime);  
  
    // Format the current time structure into a string  
    // "%#x" is the long date representation in the  
    // current locale  
    if (!strftime((char *)str, BUFF_SIZE, "%#x",   
                  (const struct tm *)&thetime))  
    {  
        printf("strftime failed!\n");  
        return -1;  
    }  
    return 0;  
}  
  
// This thread sets its locale to the argument  
// and prints the date.  
uintptr_t __stdcall SecondThreadFunc( void* pArguments )  
{  
    unsigned char str[BUFF_SIZE];  
    char * locale = (char *)pArguments;  
  
    // Set the thread locale  
    printf("The thread locale is now set to %s.\n",  
           setlocale(LC_ALL, locale));  
  
    // Retrieve the date string from the helper function  
    if (get_date(str) == 0)  
    {  
        printf("The date in %s locale is: '%s'\n", locale, str);  
    }  
  
    _endthreadex( 0 );  
    return 0;  
}   
  
// The main thread sets the locale to English   
// and then spawns a second thread (above) and prints the date.  
int main()  
{   
    HANDLE          hThread;  
    unsigned        threadID;  
    unsigned char   str[BUFF_SIZE];  
  
    // Configure per-thread locale to cause all subsequently created   
    // threads to have their own locale.  
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);  
  
    // Set the locale of the main thread to US English.  
    printf("The thread locale is now set to %s.\n",  
           setlocale(LC_ALL, "en-US"));  
  
    // Create the second thread with a German locale.  
    // Our thread function takes an argument of the locale to use.  
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,  
                                      "de-DE", 0, &threadID );  
  
    if (get_date(str) == 0)  
    {  
        // Retrieve the date string from the helper function  
        printf("The date in en-US locale is: '%s'\n\n", str);  
    }  
  
    // Wait for the created thread to finish.  
    WaitForSingleObject( hThread, INFINITE );  
  
    // Destroy the thread object.  
    CloseHandle( hThread );  
}  
```  
  
```Output  
The thread locale is now set to en-US.  
The time in en-US locale is: 'Wednesday, May 12, 2004'  
  
The thread locale is now set to de-DE.  
The time in de-DE locale is: 'Mittwoch, 12. Mai 2004'  
```  
  
## <a name="see-also"></a>関連項目  
 [ロケール名、言語、および国/地域識別文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md)   
 [_create_locale、_wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [_mbclen、mblen、_mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [strlen、wcslen、_mbslen、_mbslen_l、_mbstrlen、_mbstrlen_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)   
 [mbstowcs、_mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc、_mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [strcoll 系関数](../../c-runtime-library/strcoll-functions.md)   
 [strftime、wcsftime、_strftime_l、_wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [wcstombs、_wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb、_wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)
