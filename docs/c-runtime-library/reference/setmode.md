---
title: "_setmode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_setmode"
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
  - "_setmode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_setmode 関数"
  - "ファイル変換 [C++], 設定 (モードを)"
  - "ファイル [C++], モード"
  - "ファイル [C++], 変換"
  - "setmode 関数"
  - "Unicode [C++], コンソール出力"
ms.assetid: 996ff7cb-11d1-43f4-9810-f6097182642a
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _setmode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルの変換モードを設定します。  
  
## 構文  
  
```  
int _setmode (    int fd,    int mode  );  
```  
  
#### パラメーター  
 `fd`  
 ファイル記述子。  
  
 `mode`  
 新しい変換モード。  
  
## 戻り値  
 成功した場合、前の変換モードを返します。  
  
 この関数に無効なパラメーターが渡されると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、この関数は \-1 を返し、`errno` を、無効なファイル記述子を示す `EBADF` または無効な `mode` 引数を示す `EINVAL` に設定します。  
  
 リターン コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `_setmode` 関数は、`fd` で指定されたファイルの変換モードを `mode` に設定します。  `mode` として `_O_TEXT` を渡すと、テキスト \(変換\) モードが設定されます。  キャリッジ リターンとライン フィード \(CR\-LF\) の組み合わせは、入力時に 1 つのライン フィード文字に変換されます。  ライン フィード文字は、出力時に CR\-LF の組み合わせに変換されます。  `_O_BINARY` を渡すと、バイナリ \(未変換\) モードが設定され、このモードではこれらの変換は抑制されます。  
  
 `_O_U16TEXT`、`_O_U8TEXT`、または \_`O_WTEXT` を渡して Unicode モードを有効にすることもできます。これについては、このドキュメントの 2 番目の例で示します。  `_setmode` は、通常は `stdin` および `stdout` の既定の変換モードを変更するために使用しますが、任意のファイルで使用できます。  `_setmode` をストリームのファイル記述子に適用する場合は、ストリームに対して入力または出力操作を実行する前に `_setmode` を呼び出します。  
  
> [!CAUTION]
>  ファイル ストリームにデータを書き込む場合は、`_setmode` を使用してモードを変更する前に、[fflush](../Topic/fflush.md) を使用して明示的にコードをフラッシュします。  コードをフラッシュしないと、予期しない動作が発生することがあります。  ストリームにデータを書き込んでいない場合は、コードをフラッシュする必要はありません。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|省略可能なヘッダー|  
|----------|------------|---------------|  
|`_setmode`|\<io.h\>|\<fcntl.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_setmode.c  
// This program uses _setmode to change  
// stdin from text mode to binary mode.  
  
#include <stdio.h>  
#include <fcntl.h>  
#include <io.h>  
  
int main( void )  
{  
   int result;  
  
   // Set "stdin" to have binary mode:  
   result = _setmode( _fileno( stdin ), _O_BINARY );  
   if( result == -1 )  
      perror( "Cannot set mode" );  
   else  
      printf( "'stdin' successfully changed to binary mode\n" );  
}  
```  
  
  **'stdin' successfully changed to binary mode**   
## 使用例  
  
```  
// crt_setmodeunicode.c  
// This program uses _setmode to change  
// stdout to Unicode. Cyrillic and Ideographic  
// characters will appear on the console (if  
// your console font supports those character sets).  
  
#include <fcntl.h>  
#include <io.h>  
#include <stdio.h>  
  
int main(void) {  
    _setmode(_fileno(stdout), _O_U16TEXT);  
    wprintf(L"\x043a\x043e\x0448\x043a\x0430 \x65e5\x672c\x56fd\n");  
    return 0;  
}  
  
```  
  
## 同等の .NET Framework 関数  
  
-   [\<caps:sentence id\="tgt28" sentenceid\="fe03c471a7a38d5378cea62467482dae" class\="tgtSentence"\>System::IO::BinaryReader Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.binaryreader.aspx)  
  
-   [\<caps:sentence id\="tgt29" sentenceid\="105e62b7505c25e3e182779c87f145eb" class\="tgtSentence"\>System::IO::TextReader Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.textreader.aspx)  
  
## 参照  
 [ファイル処理](../../c-runtime-library/file-handling.md)   
 [\_creat、\_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fopen、\_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_open、\_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_set\_fmode](../../c-runtime-library/reference/set-fmode.md)