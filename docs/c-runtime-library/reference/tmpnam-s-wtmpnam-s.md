---
title: "tmpnam_s、_wtmpnam_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- tmpnam_s
- _wtmpnam_s
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
- tmpnam_s
- _wtmpnam_s
- L_tmpnam_s
dev_langs: C++
helpviewer_keywords:
- tmpnam_s function
- file names [C++], creating temporary
- _wtmpnam_s function
- L_tmpnam_s constant
- temporary files, creating
- file names [C++], temporary
- wtmpnam_s function
ms.assetid: e70d76dc-49f5-4aee-bfa2-f1baa2bcd29f
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e7846d9169db45f4176ad97dfc3c0b9d5a3c346c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="tmpnams-wtmpnams"></a>tmpnam_s、_wtmpnam_s
一時ファイルの作成に使用できる名前を生成します。 これらは、「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」 (CRT のセキュリティ機能) の説明にあるとおり、セキュリティが強化されたバージョンの [tmpnam および _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t tmpnam_s(  
   char * str,  
   size_t sizeInChars   
);  
errno_t _wtmpnam_s(  
   wchar_t *str,  
   size_t sizeInChars   
);  
template <size_t size>  
errno_t tmpnam_s(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _wtmpnam_s(  
   wchar_t (&str)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `str`  
 生成された名前を保持するポインター。  
  
 [入力] `sizeInChars`  
 バッファーのサイズ (文字単位)。  
  
## <a name="return-value"></a>戻り値  
 これらの関数はどちらも、正常終了の場合は 0、エラーの場合はエラー番号を返します。  
  
### <a name="error-conditions"></a>エラー条件  
  
|||||  
|-|-|-|-|  
|`str`|`sizeInChars`|**戻り値**|`str` **の内容**|  
|`NULL`|任意|`EINVAL`|変更されない|  
|`NULL` ではない (有効なメモリを指す)|短すぎる|`ERANGE`|変更されない|  
  
 `str` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
## <a name="remarks"></a>コメント  
 これらの各関数は、現在存在しないファイルの名前を返します。 `tmpnam_s` は、現在の作業ディレクトリ内で一意である名前を返します。 ファイル名の前に円記号が付いていてパス情報がない場合 (\fname21 など)、その名前は現在の作業ディレクトリに対して有効なので注意してください。  
  
 `tmpnam_s` については、この生成されたファイル名を `str` で格納することができます。 `tmpnam_s` によって返される文字列の最大長は、STDIO.H に定義されているとおり `L_tmpnam_s` です。 `str` が `NULL` の場合、`tmpnam_s` は内部の静的バッファーに結果を残します。 したがって後続の呼び出しは、この値を破棄します。 `tmpnam_s` によって生成された名前を構成しているのは、プログラムで生成されたファイル名と、`tmpnam_s` への最初の呼び出しの後は base 32 で連番のファイル拡張子 (STDIO.H 内の `TMP_MAX_S` が INT_MAX の場合、.1-.1vvvvvu) です。  
  
 `tmpnam_s` は、オペレーティング システムから取得した OEM コード ページに従ってマルチバイト文字シーケンスを認識し、マルチバイト文字列の引数を適切な方法で自動的に処理します。 ワイド文字を扱う場合は、`_wtmpnam_s` ではなく `tmpnam_s` を使用します。`_wtmpnam_s` の場合、引数にはワイド文字列を指定します。また戻り値もワイド文字列です。 `_wtmpnam_s` がマルチバイト文字列を処理しない点を除き、`_wtmpnam_s` と `tmpnam_s` の動作は同じです。  
  
 C++ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ttmpnam_s`|`tmpnam_s`|`tmpnam_s`|`_wtmpnam_s`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`tmpnam_s`|\<stdio.h>|  
|`_wtmpnam_s`|\<stdio.h> または \<wchar.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_tmpnam_s.c  
// This program uses tmpnam_s to create a unique filename in the  
// current working directory.   
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{     
   char name1[L_tmpnam_s];  
   errno_t err;  
   int i;  
  
   for (i = 0; i < 15; i++)  
   {  
      err = tmpnam_s( name1, L_tmpnam_s );  
      if (err)  
      {  
         printf("Error occurred creating unique filename.\n");  
         exit(1);  
      }  
      else  
      {  
         printf( "%s is safe to use as a temporary file.\n", name1 );  
      }  
   }    
}  
```  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)