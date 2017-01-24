---
title: "gets、_getws | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_getws"
  - "gets"
apilocation: 
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_getts"
  - "gets"
  - "_getws"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getts 関数"
  - "_getws 関数"
  - "gets 関数"
  - "getts 関数"
  - "getws 関数"
  - "線, 取得"
  - "標準入力, 読み取り"
  - "ストリーム, 取得 (行を)"
ms.assetid: 1ec2dd4b-f801-48ea-97c2-892590f16024
caps.latest.revision: 32
caps.handback.revision: 32
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# gets、_getws
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`stdin` ストリームから行を取得します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[gets\_s、\_getws\_s](../c-runtime-library/reference/gets-s-getws-s.md)」を参照してください。  
  
> [!IMPORTANT]
>  これらは古い関数です。 Visual Studio 2015 以降、これらは CRT で使用できません。 これらの関数のセキュリティを強化したバージョン gets\_s および \_getws\_s は、引き続き使用できます。 これらの代替関数の詳細については、「[gets\_s、\_getws\_s](../c-runtime-library/reference/gets-s-getws-s.md)」を参照してください。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
char *gets(   
   char *buffer   
);  
wchar_t *_getws(   
   wchar_t *buffer   
);  
template <size_t size>  
char *gets(   
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_getws(   
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### パラメーター  
 `buffer`  
 入力文字列の格納場所。  
  
## 戻り値  
 正常に終了した場合はその引数を返します。 エラーが発生した場合またはファイルの終端に達した場合は、`NULL` ポインターを返します。 どちらが発生したかを確認するには、[ferror](../c-runtime-library/reference/ferror.md) または [feof](../c-runtime-library/reference/feof.md) を使用します。`buffer` が `NULL` の場合は、「[パラメーターの検証](../c-runtime-library/parameter-validation.md)」で説明されているように、これらの関数は無効パラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、これらの関数は `NULL` を返し、errno を `EINVAL` に設定します。  
  
## 解説  
 `gets` 関数は、`stdin` 標準入力ストリームから行を読み取り、`buffer` に格納します。 行は、最初の改行文字 \('\\n'\) までのすべての文字 \(改行文字を含む\) で構成されます。`gets` は、行を返す前に、改行文字を null 文字 \('\\0'\) に置き換えます。 これとは対照的に、`fgets` 関数は改行文字を保持します。 ワイド文字を扱う場合は、`_getws` ではなく `gets` を使用します。引数にはワイド文字列を指定します。また戻り値もワイド文字列です。  
  
> [!IMPORTANT]
>  gets で読み取る文字の数を制限する方法がないため、信頼できない入力によってバッファー オーバーランが発生しやすくなります。 代わりに、`fgets` を使用してください。  
  
 C\+\+ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_getts`|`gets`|`gets`|`_getws`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`gets`|\<stdio.h\>|  
|`_getws`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「[互換性](../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_gets.c // compile with: /WX /W3 #include <stdio.h> int main( void ) { char line[21]; // room for 20 chars + '\0' gets( line );  // C4996 // Danger: No way to limit input to 20 chars. // Consider using gets_s instead. printf( "The line entered was: %s\n", line ); }  
```  
  
 入力が 20 文字を超えると、行バッファーのオーバーランが発生し、ほぼ確実にプログラムがクラッシュします。  
  
```Output  
  
Hello there!入力された行は Hello there!  
```  
  
## 同等の .NET Framework 関数  
 [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## 参照  
 [ストリーム入出力](../c-runtime-library/stream-i-o.md)   
 [fgets、fgetws](../c-runtime-library/reference/fgets-fgetws.md)   
 [fputs、fputws](../Topic/fputs,%20fputws.md)   
 [puts、\_putws](../Topic/puts,%20_putws.md)