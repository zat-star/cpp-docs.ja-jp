---
title: "gets_s、_getws_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _getws_s
- gets_s
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
- _getws_s
- gets_s
dev_langs:
- C++
helpviewer_keywords:
- getws_s function
- _getws_s function
- lines, getting
- streams, getting lines
- buffers, avoiding overruns
- buffer overruns
- buffers, buffer overruns
- gets_s function
- standard input, reading from
ms.assetid: 5880c36f-122c-4061-a1a5-aeeced6fe58c
caps.latest.revision: 29
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
ms.openlocfilehash: 4f4a10f432c663be33fe751bcde862c4d8e57c49
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="getss-getwss"></a>gets_s、_getws_s
`stdin` ストリームから行を取得します。 これらの [gets および _getws](../../c-runtime-library/gets-getws.md) のバージョンは、「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」(CRT のセキュリティ機能) で説明されているように、セキュリティが強化されています。  
  
## <a name="syntax"></a>構文  
  
```  
char *gets_s(   
   char *buffer,  
   size_t sizeInCharacters  
);  
wchar_t *_getws_s(   
   wchar_t *buffer,  
   size_t sizeInCharacters  
);  
template <size_t size>  
char *gets_s(   
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_getws_s(   
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `buffer`  
 入力文字列の格納場所。  
  
 [入力] `sizeInCharacters`  
 バッファーのサイズ。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は `buffer` を返します。 エラーが発生した場合またはファイルの終端に達した場合は、 `NULL` ポインターを返します。 どちらが発生したかを確認するには、[ferror](../../c-runtime-library/reference/ferror.md) または [feof](../../c-runtime-library/reference/feof.md) を使用します。  
  
## <a name="remarks"></a>コメント  
 `gets_s` 関数は、`stdin` 標準入力ストリームから行を読み取り、`buffer` に格納します。 行は、最初の改行文字 ('\n') までのすべての文字 (改行文字を含む) で構成されます。 `gets_s` は、行を返す前に、改行文字を null 文字 ('\0') に置き換えます。 これとは対照的に、`fgets_s` 関数は改行文字を保持します。  
  
 最初に読み取られた文字がファイルの終端の文字である場合、null 文字が `buffer` の先頭に格納され、`NULL` が返されます。  
  
 ワイド文字を扱う場合は、`_getws` ではなく `gets_s` を使用します。引数にはワイド文字列を指定します。また戻り値もワイド文字列です。  
  
 `buffer` が `NULL` の場合、`sizeInCharacters` が 0 以下の場合、またはバッファーが小さすぎて入力行と終端の null を格納できない場合、これらの関数は「[Parameter Validation](../../c-runtime-library/parameter-validation.md)」(パラメーターの検証) で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、これらの関数は `NULL` を返し、errno を `ERANGE` に設定します。  
  
 C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_getts`|`gets_s`|`gets_s`|`_getws`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`gets_s`|\<stdio.h>|  
|`_getws`|\<stdio.h> または \<wchar.h>|  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。 コンソール (`stdin`、`stdout`、および `stderr`) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_gets_s.c  
// This program retrieves a string from the stdin and   
// prints the same string to the console.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char line[21]; // room for 20 chars + '\0'  
   gets_s( line, 20 );  
   printf( "The line entered was: %s\n", line );  
}  
```  
  
```Output  
  
Hello there!The line entered was: Hello there!  
```  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [gets、_getws](../../c-runtime-library/gets-getws.md)   
 [fgets、fgetws](../../c-runtime-library/reference/fgets-fgetws.md)   
 [fputs、fputws](../../c-runtime-library/reference/fputs-fputws.md)   
 [puts、_putws](../../c-runtime-library/reference/puts-putws.md)
