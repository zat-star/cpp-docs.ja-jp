---
title: "strerror、_strerror、_wcserror、__wcserror | Microsoft Docs"
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
  - "strerror"
  - "_strerror"
  - "_wcserror"
  - "__wcserror"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__sys_errlist"
  - "wcserror"
  - "_strerror"
  - "__wcserror"
  - "strerror"
  - "__sys_nerr"
  - "_tcserror"
  - "_wcserror"
  - "tcserror"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__sys_errlist"
  - "__sys_nerr"
  - "__wcserror 関数"
  - "_strerror 関数"
  - "_tcserror 関数"
  - "_wcserror 関数"
  - "エラー メッセージ, 取得"
  - "エラー メッセージ, 印刷"
  - "出力 (エラー メッセージを)"
  - "strerror 関数"
  - "tcserror 関数"
  - "wcserror 関数"
ms.assetid: 27b72255-f627-43c0-8836-bcda8b003e14
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strerror、_strerror、_wcserror、__wcserror
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

システム エラー メッセージの文字列 \(`strerror`、`_wcserror`\) を取得します。または、ユーザーが指定したエラー メッセージの文字列 \(`_strerror`、`__wcserror`\) を書式設定します。  これらの関数のセキュリティを強化したバージョンについては、「[strerror\_s、\_strerror\_s、\_wcserror\_s、\_\_wcserror\_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)」を参照してください。  
  
## 構文  
  
```  
char *strerror(    int errnum  ); char *_strerror(    const char *strErrMsg  ); wchar_t * _wcserror(    int errnum  ); wchar_t * __wcserror(    const wchar_t *strErrMsg  );  
```  
  
#### パラメーター  
 `errnum`  
 エラー番号。  
  
 `strErrMsg`  
 ユーザーが指定したメッセージ。  
  
## 戻り値  
 これらの関数はすべて、エラー メッセージの文字列へのポインターを返します。  文字列は後続の呼び出しによって上書きされる可能性があります。  
  
## 解説  
 `strerror` 関数は、エラー メッセージの文字列に `errnum` をマップし、その文字列へのポインターを返します。  `strerror` および `_strerror` の両方とも、実際にはメッセージを出力しません。メッセージの出力のためには、[fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md) などの出力関数を呼び出す必要があります。  
  
```  
if (( _access( "datafile",2 )) == -1 )  
   fprintf( stderr, _strerror(NULL) );  
```  
  
 `strErrMsg` が `NULL` として渡された場合、`_strerror` は、エラーを生成した最後のライブラリの呼び出しのシステム エラー メッセージを含む文字列へのポインターを返します。  エラー メッセージ文字列は、改行文字 \(「\\n」\) で終了します。  `strErrMsg` が `NULL` ではない場合、`_strerror` は、\(以下の順序どおりに\) 文字列のメッセージ、コロン、空白、エラーを生成した最後のライブラリの呼び出しのシステム エラー メッセージ、および改行文字を含む文字列へのポインターを返します。  文字列のメッセージの長さは、最大で 94 文字です。  
  
 `_strerror` の実際のエラー番号は、変数 [errno](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) に格納されます。  正確な結果を生成するため、ルーチンがエラーを返した直後に `_strerror` を呼び出します。  そうしなければ、`strerror` または `_strerror` への後続の呼び出しが `errno` の値をオーバーライドする可能性があります。  
  
 `_wcserror`、および `__wcserror` は、それぞれ、`strerror`、および `_strerror` のワイド文字バージョンです。  
  
 `_strerror`、`_wcserror`、および `__wcserror` は、ANSI 定義の一部ではありません。これらは Microsoft 拡張機能であり、コードの移植性が必要となる場合は使用しないことをお勧めします。  ANSI 互換のために、代わりに `strerror` を使用します。  
  
 エラーの文字列を取得するには、非推奨のマクロ [\_sys\_errlist](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) および [\_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) や非推奨の内部関数 `__sys_errlist` および `__sys_nerr` ではなく、`strerror` または `_wcserror` をお勧めします。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tcserror`|`strerror`|`strerror`|`_wcserror`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`strerror`|\<string.h\>|  
|`_strerror`|\<string.h\>|  
|`_wcserror`, `__wcserror`|\<string.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 「[perror](../../c-runtime-library/reference/perror-wperror.md)」の例を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::Exception::Message](https://msdn.microsoft.com/en-us/library/system.exception.message.aspx)  
  
## 参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror、\_wperror](../../c-runtime-library/reference/perror-wperror.md)