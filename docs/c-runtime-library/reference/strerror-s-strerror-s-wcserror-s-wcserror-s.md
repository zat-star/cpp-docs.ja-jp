---
title: "strerror_s、_strerror_s、_wcserror_s、__wcserror_s | Microsoft Docs"
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
  - "__wcserror_s"
  - "_strerror_s"
  - "_wcserror_s"
  - "strerror_s"
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
  - "wcserror_s"
  - "__wcserror_s"
  - "_tcserror_s"
  - "_wcserror_s"
  - "tcserror_s"
  - "strerror_s"
  - "_strerror_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__wcserror_s 関数"
  - "_strerror_s 関数"
  - "_tcserror_s 関数"
  - "_wcserror_s 関数"
  - "エラー メッセージ, 取得"
  - "エラー メッセージ, 印刷"
  - "出力 (エラー メッセージを)"
  - "strerror_s 関数"
  - "tcserror_s 関数"
  - "wcserror_s 関数"
ms.assetid: 9e5b15a0-efe1-4586-b7e3-e1d7c31a03d6
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strerror_s、_strerror_s、_wcserror_s、__wcserror_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

システム エラー メッセージ \(`strerror_s`、`_wcserror_s`\) を取得します。または、ユーザーが指定したエラー メッセージ \(`_strerror_s`、`__wcserror_s`\) を出力します。  これらの関数は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[strerror、\_strerror、\_wcserror、\_\_wcserror](../../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md) のセキュリティが強化されたバージョンです。  
  
## 構文  
  
```  
errno_t strerror_s(  
   char *buffer,  
   size_t numberOfElements,  
   int errnum   
);  
errno_t _strerror_s(  
   char *buffer,  
   size_t numberOfElements,  
   const char *strErrMsg   
);  
errno_t _wcserror_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   int errnum   
);  
errno_t __wcserror_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   const wchar_t *strErrMsg   
);  
template <size_t size>  
errno_t strerror_s(  
   char (&buffer)[size],  
   int errnum   
); // C++ only  
template <size_t size>  
errno_t _strerror_s(  
   char (&buffer)[size],  
   const char *strErrMsg   
); // C++ only  
template <size_t size>  
errno_t _wcserror_s(  
   wchar_t (&buffer)[size],  
   int errnum   
); // C++ only  
template <size_t size>  
errno_t __wcserror_s(  
   wchar_t (&buffer)[size],  
   const wchar_t *strErrMsg   
); // C++ only  
```  
  
#### パラメーター  
 `buffer`  
 エラー文字列を格納するバッファー。  
  
 `numberOfElements`  
 バッファーのサイズ。  
  
 `errnum`  
 エラー番号。  
  
 `strErrMsg`  
 ユーザーが指定したメッセージ。  
  
## 戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。  
  
### エラー条件  
  
|`buffer`|`numberOfElements`|`strErrMsg`|`buffer` の内容|  
|--------------|------------------------|-----------------|------------------|  
|`NULL`|任意|任意|適用なし|  
|任意|0|任意|変更されない|  
  
## 解説  
 `strerror_s` 関数はエラー メッセージの文字列に `errnum` をマップし、その文字列を `buffer` 内に返します。  `_strerror_s` はエラー番号を受け取りません。`errno` の現在の値を使用して適切なメッセージを決定します。  `strerror_s` および `_strerror_s` の両方とも、実際にはメッセージを出力できません。メッセージの出力のためには、[fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md) などの出力関数を呼び出す必要があります。  
  
```  
if (( _access( "datafile",2 )) == -1 )  
{  
   _strerror_s(buffer, 80);  
   fprintf( stderr, buffer );  
}  
```  
  
 `strErrMsg` が `NULL` の場合、`_strerror_s` はエラーを生成した最後のライブラリの呼び出しのシステム エラー メッセージを含む文字列を `buffer` に返します。  エラー メッセージ文字列は、改行文字 \(「\\n」\) で終了します。  `strErrMsg` が `NULL` ではない場合、`_strerror_s` は、\(以下の順序どおりに\) 文字列のメッセージ、コロン、空白、エラーを生成した最後のライブラリの呼び出しのシステム エラー メッセージ、および改行文字を含む文字列を `buffer` に返します。  文字列のメッセージの長さは、最大で 94 文字です。  
  
 これらの関数は、エラー メッセージの長さが `numberOfElements` \-1 を超える場合、エラー メッセージを切り詰めます。  `buffer` の結果の文字列は、常に null で終わります。  
  
 `_strerror_s` の実際のエラー番号は、変数 [errno](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) に格納されます。  システム エラー メッセージは、エラー番号順のメッセージの配列である変数 [\_sys\_errlist](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) を使用してアクセスできます。  `_strerror_s` は、`errno` 変数の値を `_sys_errlist` 変数のインデックスとして使用して、適切なエラー メッセージにアクセスします。  変数 [\_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) の値は、`_sys_errlist` の配列の要素の最大数として定義されます。  正確な結果を生成するため、ルーチンがエラーを返した直後に `_strerror_s` を呼び出します。  そうしなければ、`strerror_s` または `_strerror_s` への後続の呼び出しが `errno` の値をオーバーライドする可能性があります。  
  
 `_wcserror_s` と `__wcserror_s`は`strerror_s`と `_strerror_s`のワイド文字バージョンであり、それぞれです。  
  
 これらの関数では、パラメーターの検証が行われます。  buffer が `NULL` である場合、またはパラメーターのサイズが 0 である場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、関数は `EINVAL` を返し、`errno` を `EINVAL` に設定します。  
  
 `_strerror_s, _wcserror_s,` と `__wcserror_s`  は、ANSI 定義の一部ではなく、ANSI 定義に対する Microsoft の拡張機能です。  移植性が必要な場合には使用しないでください。ANSI 互換のために、 `strerror_s`  を使用します。  
  
 C\+\+ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
 これらの関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。  この動作を無効にするには、[\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md) を使用します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tcserror_s`|`strerror_s`|`strerror_s`|`_wcserror_s`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`strerror_s`, `_strerror_s`|\<string.h\>|  
|`_wcserror_s`, `__wcserror_s`|\<string.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 「[perror](../../c-runtime-library/reference/perror-wperror.md)」の例を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::Exception::Message](https://msdn.microsoft.com/en-us/library/system.exception.message.aspx)  
  
## 参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror、\_wperror](../../c-runtime-library/reference/perror-wperror.md)