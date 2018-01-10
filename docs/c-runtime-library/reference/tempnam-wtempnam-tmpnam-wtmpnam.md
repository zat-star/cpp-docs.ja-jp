---
title: "_tempnam、_wtempnam、tmpnam、_wtmpnam | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wtempnam
- _wtmpnam
- tmpnam
- _tempnam
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
- wtempnam
- _wtmpnam
- wtmpnam
- tmpnam
- _wtempnam
- _tempnam
dev_langs: C++
helpviewer_keywords:
- wtempnam function
- file names [C++], creating temporary
- _tempnam function
- ttmpnam function
- tmpnam function
- tempnam function
- wtmpnam function
- temporary files, creating
- file names [C++], temporary
- _ttmpnam function
- _wtmpnam function
- _wtempnam function
ms.assetid: 3ce75f0f-5e30-42a6-9791-8d7cbfe70fca
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9708c23fc76095a591a2eceafcb875ce173383ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="tempnam-wtempnam-tmpnam-wtmpnam"></a>_tempnam、_wtempnam、tmpnam、_wtmpnam
一時ファイルの作成に使用できる名前を生成します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[tmpnam_s、_wtmpnam_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
char *_tempnam(  
   const char *dir,  
   const char *prefix   
);  
wchar_t *_wtempnam(  
   const wchar_t *dir,  
   const wchar_t *prefix   
);  
char *tmpnam(  
   char *str   
);  
wchar_t *_wtmpnam(  
   wchar_t *str   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `prefix`  
 `_tempnam` によって返された名前の前に付けられる文字列。  
  
 `dir`  
 TMP 環境変数がない場合、または TMP が有効なディレクトリではない場合にファイル名で使用されるパス。  
  
 `str`  
 生成された名前を保持し、関数によって返される名前と同じになるポインター。 これは、生成された名前を保存する便利な方法です。  
  
## <a name="return-value"></a>戻り値  
 各関数は、生成された名前へのポインター、または失敗した場合は `NULL` を返します。 しようとすると、エラーが発生する可能性が複数の`TMP_MAX`(STDIO を参照してください。H) を使用した呼び出し`tmpnam`を使用する場合または`_tempnam`TMP 環境変数で指定された無効なディレクトリ名があると、`dir`パラメーター。  
  
> [!NOTE]
>  `tmpnam` と `_wtmpnam` によって返されるポインターは、内部の静的バッファーを指します。 これらのポインターの割り当てを解除するために [free](../../c-runtime-library/reference/free.md) を呼び出さないでください。 `_tempnam` および `_wtempnam` によって割り当てられたポインターに対して、`free` を呼び出す必要があります。  
  
## <a name="remarks"></a>コメント  
 これらの各関数は、現在存在しないファイルの名前を返します。 `tmpnam` は現在の作業ディレクトリ内で一意の名前を返し、`_tempnam` を使用して、現在のディレクトリではないディレクトリで一意の名前を生成することができます。 ファイル名の前に円記号が付いていてパス情報がない場合 (\fname21 など)、その名前は現在の作業ディレクトリに対して有効なので注意してください。  
  
 `tmpnam` については、この生成されたファイル名を `str` に格納することができます。 `str` が `NULL` の場合、`tmpnam` は内部の静的バッファーに結果を残します。 したがって後続の呼び出しは、この値を破棄します。 `tmpnam` によって生成された名前を構成しているのは、プログラムで生成されたファイル名と、`tmpnam` への最初の呼び出しの後は base 32 で連番のファイル拡張子 (STDIO.H 内の `TMP_MAX` が 32,767 の場合、.1-.vvu) です。  
  
 `_tempnam` は、次の規則によって選択されたディレクトリに対して一意のファイル名を生成します。  
  
-   TMP 環境変数が定義され、有効なディレクトリ名に設定された場合は、TMP で指定したディレクトリに対して一意のファイル名が生成されます。  
  
-   TMP 環境変数が定義されていない場合、または存在しないディレクトリの名前に設定されている場合、`_tempnam` は一意の名前を生成するパスとして `dir` パラメーターを使用します。  
  
-   TMP 環境変数が定義されていない場合、または存在しないディレクトリの名前に設定されており、`dir` が `NULL` であるか、存在しないディレクトリの名前に設定されている場合、`_tempnam` は現在の作業ディレクトリを使用して一意の名前を生成します。 現時点では、TMP と `dir` の両方で存在しないディレクトリの名前を指定すると、`_tempnam` 関数の呼び出しは失敗します。  
  
 `_tempnam` によって返される名前は、`prefix` とシーケンシャル番号の連結であり、指定したディレクトリに対して一意のファイル名を作成するために組み合わされます。 `_tempnam` は、拡張機能を持たないファイル名を生成します。 `_tempnam` は、[malloc](../../c-runtime-library/reference/malloc.md) 使用してファイル名に領域を割り当てます。プログラムは、この領域が不要になったときにこの領域を解放する必要があります。  
  
 `_tempnam` および `tmpnam` は、オペレーティング システムから取得した OEM コード ページに従ってマルチバイト文字シーケンスを認識し、マルチバイト文字列の引数を適切な方法で自動的に処理します。 ワイド文字を扱う場合は、`_tempnam` ではなく `_wtempnam` を使用します。`_wtempnam` の場合、引数にはワイド文字列を指定します。また戻り値もワイド文字列です。 `_wtempnam` がマルチバイト文字列を処理しない点を除き、`_wtempnam` と `_tempnam` の動作は同じです。 ワイド文字を扱う場合は、`_wtmpnam` ではなく `tmpnam` を使用します。`_wtmpnam` の場合、引数にはワイド文字列を指定します。また戻り値もワイド文字列です。 `_wtmpnam` がマルチバイト文字列を処理しない点を除き、`_wtmpnam` と `tmpnam` の動作は同じです。  
  
 `_DEBUG` と `_CRTDBG_MAP_ALLOC` が定義されている場合、`_tempnam` と `_wtempnam` は [_tempnam_dbg と _wtempnam_dbg](../../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md) の呼び出しによって置き換えられます。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ttmpnam`|`tmpnam`|`tmpnam`|`_wtmpnam`|  
|`_ttempnam`|`_tempnam`|`_tempnam`|`_wtempnam`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_tempnam`|\<stdio.h>|  
|`_wtempnam`, `_wtmpnam`|\<stdio.h> または \<wchar.h>|  
|`tmpnam`|\<stdio.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_tempnam.c  
// compile with: /W3  
// This program uses tmpnam to create a unique filename in the  
// current working directory, then uses _tempnam to create   
// a unique filename with a prefix of stq.   
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{     
   char* name1 = NULL;  
   char* name2 = NULL;  
  
   // Create a temporary filename for the current working directory:   
   if( ( name1 = tmpnam( NULL ) ) != NULL ) // C4996  
   // Note: tmpnam is deprecated; consider using tmpnam_s instead  
      printf( "%s is safe to use as a temporary file.\n", name1 );  
   else  
      printf( "Cannot create a unique filename\n" );  
  
   // Create a temporary filename in temporary directory with the  
   // prefix "stq". The actual destination directory may vary  
   // depending on the state of the TMP environment variable and  
   // the global variable P_tmpdir.     
  
   if( ( name2 = _tempnam( "c:\\tmp", "stq" ) ) != NULL )  
      printf( "%s is safe to use as a temporary file.\n", name2 );   
   else  
      printf( "Cannot create a unique filename\n" );  
  
   // When name2 is no longer needed :     
   if(name2)  
     free(name2);  
  
}  
```  
  
```Output  
\s1gk. is safe to use as a temporary file.  
C:\DOCUME~1\user\LOCALS~1\Temp\2\stq2 is safe to use as a temporary file.  
```  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)   
 [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)