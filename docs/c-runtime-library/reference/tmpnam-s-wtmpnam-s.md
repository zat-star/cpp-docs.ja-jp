---
title: "tmpnam_s、_wtmpnam_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "tmpnam_s"
  - "_wtmpnam_s"
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
  - "tmpnam_s"
  - "_wtmpnam_s"
  - "L_tmpnam_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_wtmpnam_s 関数"
  - "ファイル名 [C++], 作成 (一時)"
  - "ファイル名 [C++], 一時"
  - "L_tmpnam_s 定数"
  - "一時ファイル, 作成"
  - "tmpnam_s 関数"
  - "wtmpnam_s 関数"
ms.assetid: e70d76dc-49f5-4aee-bfa2-f1baa2bcd29f
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# tmpnam_s、_wtmpnam_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

一時ファイルを作成するために使用できる名前を生成します。  これらは [CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)"に説明されているように、セキュリティが強化された [tmpnam と\_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) のバージョンです。  
  
## 構文  
  
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
  
#### パラメーター  
 \[出力\] `str`  
 生成された名前を保持するポインター。  
  
 \[入力\] `sizeInChars`  
 文字の buffer のサイズ。  
  
## 戻り値  
 これらの関数はエラーの数が正常終了した場合は 0 を返します。  
  
### エラー条件  
  
|||||  
|-|-|-|-|  
|`str`|`sizeInChars`|**戻り値**|**目次**  `str`|  
|`NULL`|任意|`EINVAL`|変更されない|  
|存在しない `NULL` \(有効なメモリへのポインター\)|非常に短い|`ERANGE`|変更されない|  
  
 `str` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
## 解説  
 これらの関数は、現在存在しないファイルの名前を返します。  `tmpnam_s` は 現在の作業ディレクトリに一意の名前を返します。  ファイル名が円記号とパス情報と、\\fname21 など、このメモ アタッチされていない場合、名前は現在の作業ディレクトリに対して有効であることを示します。  
  
 `tmpnam_s`では、`str`で生成されたファイル名を保存できます。  `tmpnam_s` から返された文字列の最大長は、STDIO.H.で定義されている `L_tmpnam_s`です。  `str` が `NULL`場合、`tmpnam_s` は静的な内部バッファーに結果が保存されます。  したがって、後続の呼び出しは、この値を破棄します。  `tmpnam_s` によって生成された名前は、`tmpnam_s`への最初の呼び出しの後に、基数 32 \(.1\-.1vvvvvu の連続する番号のプログラムで生成されたファイル名と、ファイル拡張子でインクルードの `TMP_MAX_S` が INT\_MAX 時\) で構成されます。  
  
 `tmpnam_s` は 適切な方法で自動的にマルチバイト文字列の引数を処理しま、マルチバイト文字のシーケンスをオペレーティング システムから取得した OEM のコード ページに従ってマルチバイト文字列を認識します。  ワイド文字を扱う場合は、`tmpnam_s` ではなく `_wtmpnam_s` を使用します。`_wtmpnam_s` の場合、引数にはワイド文字列を指定します。また戻り値もワイド文字列です。  `_wtmpnam_s` と `tmpnam_s` の動作は、`_wtmpnam_s` がマルチバイト文字列を扱わない点を除いて同じです。  
  
 C\+\+ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_ttmpnam_s`|`tmpnam_s`|`tmpnam_s`|`_wtmpnam_s`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`tmpnam_s`|\<stdio.h\>|  
|`_wtmpnam_s`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
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
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile\_s](../Topic/tmpfile_s.md)