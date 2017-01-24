---
title: "_tempnam、_wtempnam、tmpnam、_wtmpnam | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wtempnam"
  - "_wtmpnam"
  - "tmpnam"
  - "_tempnam"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wtempnam"
  - "_wtmpnam"
  - "wtmpnam"
  - "tmpnam"
  - "_wtempnam"
  - "_tempnam"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tempnam 関数"
  - "_ttmpnam 関数"
  - "_wtempnam 関数"
  - "_wtmpnam 関数"
  - "ファイル名 [C++], 作成 (一時)"
  - "ファイル名 [C++], 一時"
  - "tempnam 関数"
  - "一時ファイル, 作成"
  - "tmpnam 関数"
  - "ttmpnam 関数"
  - "wtempnam 関数"
  - "wtmpnam 関数"
ms.assetid: 3ce75f0f-5e30-42a6-9791-8d7cbfe70fca
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _tempnam、_wtempnam、tmpnam、_wtmpnam
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

一時ファイルを作成するために使用できる名前を生成します。  これらの関数のセキュリティを強化したバージョンについては、「[tmpnam\_s、\_wtmpnam\_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md)」を参照してください。  
  
## 構文  
  
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
  
#### パラメーター  
 `prefix`  
 名前にアタッチされた文字列が `_tempnam`によって返されます。  
  
 `dir`  
 TMP 環境変数がないか、TMP が有効なディレクトリにあるファイル名で使用されているパス。  
  
 `str`  
 生成された名前を保持し、関数から返された名前と同じポインター。  これは生成された名前を保存するのに便利です。  
  
## 戻り値  
 これらの関数は、生成される名前または `NULL` にエラーが発生した場合は、ポインターを返します。  エラーが `TMP_MAX` よりも STDIO.H を \(インクルード\) `tmpnam` "を参照してください `_tempnam`またはを使用する場合、TMP 環境変数と `dir` パラメーターで指定された無効なディレクトリ名です。  
  
> [!NOTE]
>  ポインターは、静的なバッファーに `tmpnam` と `_wtmpnam` ポイントによって返されます。  [フリー](../../c-runtime-library/reference/free.md) は これらのポインターを解放するために呼び出す必要があります。  `free` は `_tempnam` と `_wtempnam`に割り当てられたポインターを呼び出す必要があります。  
  
## 解説  
 これらの関数は、現在存在しないファイルの名前を返します。  `tmpnam` は 現在の作業ディレクトリに一意の名前を返します `_tempnam` は現在のディレクトリ以外の一意の名前を付けることができます。  ファイル名が円記号とパス情報と、\\fname21 など、このメモ アタッチされていない場合、名前は現在の作業ディレクトリに対して有効であることを示します。  
  
 `tmpnam`では、`str`で生成されたファイル名を保存できます。  `str` が `NULL`場合、`tmpnam` は静的な内部バッファーに結果が保存されます。  したがって、後続の呼び出しは、この値を破棄します。  `tmpnam` によって生成された名前は、`tmpnam`への最初の呼び出しの後に、基数 32 \(.1\-.vvu の連続する番号のプログラムで生成されたファイル名と、ファイル拡張子でインクルードの `TMP_MAX` が 32,767 の場合\) で構成されます。  
  
 `_tempnam` は 次の規則によって、選択したディレクトリの一意のファイル名を生成する:  
  
-   TMP 環境変数が有効なディレクトリ名に定義され、設定された、一意のファイル名は TMP で指定されたディレクトリに生成されます。  
  
-   TMP 環境変数が定義されていない場合は、ディレクトリの名前に設定すると、`_tempnam` は一意の名前を生成するパスとして `dir` パラメーターを使用します。  
  
-   TMP 環境変数が定義されていない場合は、次のない、`dir` がないディレクトリの名前に `NULL` または設定でディレクトリの名前に設定すると、`_tempnam` は一意の名前を生成するには、現在の作業ディレクトリを使用します。  現在 TMP および `dir` の両方が、ディレクトリの名前を指定すると、`_tempnam` 関数呼び出しは失敗します。  
  
 `_tempnam` によって返される名前が指定されたディレクトリに固有の名前を作成するために使用する `prefix`、および連続する番号を連結したものです。  `_tempnam` は 拡張子がないファイル名を生成します。  `_tempnam` は filename の領域を割り当てるに [malloc](../../c-runtime-library/reference/malloc.md) ;を プログラムは、不要になったときに、この領域を解放する必要があります。  
  
 `_tempnam` と `tmpnam` は適切な方法で自動的にマルチバイト文字列の引数を処理しま、マルチバイト文字のシーケンスをオペレーティング システムから取得した OEM のコード ページに従ってマルチバイト文字列を認識します。  `_wtempnam` は `_tempnam`のワイド文字バージョンであり、; `_wtempnam` の引数と戻り値はワイド文字列です。  `_wtempnam` と `_tempnam` の動作は、`_wtempnam` がマルチバイト文字列を扱わない点を除いて同じです。  ワイド文字を扱う場合は、`tmpnam` ではなく `_wtmpnam` を使用します。`_wtmpnam` の場合、引数にはワイド文字列を指定します。また戻り値もワイド文字列です。  `_wtmpnam` と `tmpnam` の動作は、`_wtmpnam` がマルチバイト文字列を扱わない点を除いて同じです。  
  
 `_DEBUG` と `_CRTDBG_MAP_ALLOC` が定義されている場合、`_tempnam` と `_wtempnam` は [\_tempnam\_dbg と\_wtempnam\_dbg](../../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md)への呼び出しに置き換えられます。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_ttmpnam`|`tmpnam`|`tmpnam`|`_wtmpnam`|  
|`_ttempnam`|`_tempnam`|`_tempnam`|`_wtempnam`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_tempnam`|\<stdio.h\>|  
|`_wtempnam`, `_wtmpnam`|\<stdio.h\> または \<wchar.h\>|  
|`tmpnam`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
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
  
  **\\s1gk. 一時ファイルとして使用することは安全です。**  
**C:\\DOCUME~1\\user\\LOCALS~1\\Temp\\2\\stq2 は 一時ファイルとして使用しても安全です。**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)   
 [tmpfile\_s](../Topic/tmpfile_s.md)