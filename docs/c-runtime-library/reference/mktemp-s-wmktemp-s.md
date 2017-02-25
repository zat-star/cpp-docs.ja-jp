---
title: "_mktemp_s、_wmktemp_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mktemp_s"
  - "_wmktemp_s"
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
apitype: "DLLExport"
f1_keywords: 
  - "wmktemp_s"
  - "mktemp_s"
  - "_mktemp_s"
  - "_wmktemp_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mktemp_s 関数"
  - "_tmktemp_s 関数"
  - "_wmktemp_s 関数"
  - "ファイル [C++], 一時"
  - "mktemp_s 関数"
  - "一時ファイル [C++]"
  - "tmktemp_s 関数"
  - "wmktemp_s 関数"
ms.assetid: 92a7e269-7f3d-4c71-bad6-14bc827a451d
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _mktemp_s、_wmktemp_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

一意のファイル名を作成します。  これらの関数は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[\_mktemp、\_wmktemp](../../c-runtime-library/reference/mktemp-wmktemp.md) のセキュリティが強化されたバージョンです。  
  
## 構文  
  
```  
errno_t _mktemp_s(  
   char *template,  
   size_t sizeInChars  
);  
errno_t _wmktemp_s(  
   wchar_t *template,  
   size_t sizeInChars  
);  
template <size_t size>  
errno_t _mktemp_s(  
   char (&template)[size]  
); // C++ only  
template <size_t size>  
errno_t _wmktemp_s(  
   wchar_t (&template)[size]  
); // C++ only  
```  
  
#### パラメーター  
 `template`  
 ファイル名のパターン。  
  
 `sizeInChars`  
 終端の null を含めたバッファーのサイズ。`_mktemp_s` では 1 バイト文字単位、`_wmktemp_s` ではワイド文字単位。  
  
## 戻り値  
 これらの関数は両方とも、正常終了した場合は 0 を返し、失敗した場合はエラー コードを返します。  
  
### エラー条件  
  
|`template`|`sizeInChars`|**戻り値**|**テンプレート内の新しい値**|  
|----------------|-------------------|-------------|----------------------|  
|`NULL`|任意|`EINVAL`|`NULL`|  
|誤った形式 \(正しい形式については、「`Remarks`」を参照\)|任意|`EINVAL`|空の文字列|  
|任意|\<X \= 数|`EINVAL`|空の文字列|  
  
 上記のいずれかのエラー条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、`errno` が `EINVAL` に設定され、関数から `EINVAL` が返されます。  
  
## 解説  
 `_mktemp_s` 関数は、引数 `template` を変更することで一意のファイル名を作成し、呼び出し後に `template` ポインターが新しいファイル名を含む文字列を指すようにします。  `_mktemp_s` 関数は、ランタイム システムで現在使用されているマルチバイト コード ページに従ってマルチバイト文字シーケンスを認識し、マルチバイト文字列の引数を適切な方法で自動的に処理します。  `_wmktemp_s` 関数は `_mktemp_s` 関数のワイド文字バージョンで、`_wmktemp_s` 関数の引数はワイド文字列です。  `_wmktemp_s` 関数と `_mktemp_s` 関数の動作は、`_wmktemp_s` 関数がマルチバイト文字列を扱わない点を除いて同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tmktemp_s`|`_mktemp_s`|`_mktemp_s`|`_wmktemp_s`|  
  
 `template` 引数の形式は `baseXXXXXX` です。ここで、`base` は指定した新しいファイル名の一部で、X は `_mktemp_s` で指定された文字のプレースホルダーです。  `template` の各プレースホルダー文字には、大文字の X を指定する必要があります。  `_mktemp_s` は `base` を保持し、後に続く X のうち先頭の X を英字に置き換えます。  さらに、`_mktemp_s` は残りの X を 5 桁の値に置き換えます。この値は、呼び出し元プロセス \(マルチスレッド プログラムの場合は呼び出し元スレッド\) を識別する一意の数字です。  
  
 `_mktemp_s` の呼び出しが成功するたびに、`template` が変更されます。  同じ `template` 引数を使用して同じプロセスまたはスレッドから呼び出されると、`_mktemp_s` は、前の呼び出しで `_mktemp_s` から返された名前と一致するファイル名を調べます。  指定した名前のファイルが存在しない場合、`_mktemp_s` はその名前を返します。  以前返されたすべての名前のファイルが存在する場合、`_mktemp_s` は、その名前の英字部分をアルファベット順の次の小文字に置き換えて、新しい名前を作成します。  たとえば、`base` が次のような場合があります。  
  
```  
fn  
```  
  
 さらに、`_mktemp_s` で指定した 5 桁の値が 12345 の場合、最初に次の名前が返されます。  
  
```  
fna12345  
```  
  
 この名前が FNA12345 ファイルの作成に使用され、そのファイルがまだ存在する場合、`template` に同じ `base` を指定して同じプロセスまたはスレッドを呼び出すと、次の名前が返されます。  
  
```  
fnb12345  
```  
  
 FNA12345 が存在しない場合は、次の名前がもう一度返されます。  
  
```  
fna12345  
```  
  
 `_mktemp_s` は、base 値と template 値をどのように組み合わせても、最大で 26 個の一意のファイル名を作成できます。  したがって、この例で使用されている `base` 値と `template` 値に対して `_mktemp_s` が作成できる最後の一意のファイル名は FNZ12345 になります。  
  
 C\+\+ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる \(サイズの引数を指定する必要がなくなる\) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_mktemp_s`|\<io.h\>|  
|`_wmktemp_s`|\<io.h または\> wchar.h \<\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_mktemp_s.cpp  
/* The program uses _mktemp to create  
 * five unique filenames. It opens each filename  
 * to ensure that the next name is unique.  
 */  
  
#include <io.h>  
#include <string.h>  
#include <stdio.h>  
  
char *fnTemplate = "fnXXXXXX";  
char names[5][9];  
  
int main()  
{  
   int i, err, sizeInChars;  
   FILE *fp;  
  
   for( i = 0; i < 5; i++ )  
   {  
      strcpy_s( names[i], sizeof(names[i]), fnTemplate );  
      /* Get the size of the string and add one for the null terminator.*/  
      sizeInChars = strnlen(names[i], 9) + 1;  
      /* Attempt to find a unique filename: */  
      err = _mktemp_s( names[i], sizeInChars );  
      if( err != 0 )  
         printf( "Problem creating the template" );  
      else  
      {  
         if( fopen_s( &fp, names[i], "w" ) == 0 )  
            printf( "Unique filename is %s\n", names[i] );  
         else  
            printf( "Cannot open %s\n", names[i] );  
         fclose( fp );  
      }  
   }  
  
   return 0;  
}  
```  
  
## 出力例  
  
```  
Unique filename is fna03188  
Unique filename is fnb03188  
Unique filename is fnc03188  
Unique filename is fnd03188  
Unique filename is fne03188  
```  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [fopen、\_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_getpid](../Topic/_getpid.md)   
 [\_open、\_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [\_tempnam、\_wtempnam、tmpnam、\_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [tmpfile\_s](../Topic/tmpfile_s.md)