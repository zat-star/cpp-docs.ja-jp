---
title: "strerror、_strerror、_wcserror、__wcserror | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- strerror
- _strerror
- _wcserror
- __wcserror
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __sys_errlist
- wcserror
- _strerror
- __wcserror
- strerror
- __sys_nerr
- _tcserror
- _wcserror
- tcserror
dev_langs:
- C++
helpviewer_keywords:
- strerror function
- _strerror function
- __sys_errlist
- wcserror function
- error messages, printing
- __sys_nerr
- tcserror function
- printing error messages
- _wcserror function
- _tcserror function
- __wcserror function
- error messages, getting
ms.assetid: 27b72255-f627-43c0-8836-bcda8b003e14
caps.latest.revision: 21
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
ms.openlocfilehash: 3c79a2502fd9e52ff5e05e600c4d1a1e8e3761c8
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="strerror-strerror-wcserror-wcserror"></a>strerror、_strerror、_wcserror、__wcserror
システム エラー メッセージの文字列 (`strerror`、`_wcserror`) を取得します。または、ユーザーが指定したエラー メッセージの文字列 (`_strerror`、`__wcserror`) を書式設定します。 これらの関数にはセキュリティが強化されたバージョンがあります。「[strerror_s、_strerror_s、_wcserror_s、\__wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
char *strerror(  
   int errnum   
);  
char *_strerror(  
   const char *strErrMsg   
);  
wchar_t * _wcserror(  
   int errnum   
);  
wchar_t * __wcserror(  
   const wchar_t *strErrMsg   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `errnum`  
 エラー番号。  
  
 `strErrMsg`  
 ユーザーが指定したメッセージ。  
  
## <a name="return-value"></a>戻り値  
 これらの関数はすべて、エラー メッセージの文字列へのポインターを返します。 文字列は後続の呼び出しによって上書きされる可能性があります。  
  
## <a name="remarks"></a>コメント  
 `strerror` 関数は、エラー メッセージの文字列に `errnum` をマップし、その文字列へのポインターを返します。 `strerror` および `_strerror` の両方とも、実際にはメッセージを出力しません。メッセージを出力させるためには、[fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md) などの出力関数を呼び出す必要があります。  
  
```  
if (( _access( "datafile",2 )) == -1 )  
   fprintf( stderr, _strerror(NULL) );  
```  
  
 `strErrMsg` が `NULL` として渡された場合、`_strerror` は、エラーを生成した最後のライブラリの呼び出しのシステム エラー メッセージを含む文字列へのポインターを返します。 エラー メッセージ文字列は、改行文字 (「\n」) で終了します。 `strErrMsg` が `NULL` ではない場合、`_strerror` は、(以下の順序どおりに) 文字列のメッセージ、コロン、空白、エラーを生成した最後のライブラリの呼び出しのシステム エラー メッセージ、および改行文字を含む文字列へのポインターを返します。 文字列のメッセージの長さは、最大で 94 文字です。  
  
 `_strerror` の実際のエラー番号は、変数 [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) に格納されます。 正確な結果を生成するため、ルーチンがエラーを返した直後に `_strerror` を呼び出します。 そうしなければ、`strerror` または `_strerror` への後続の呼び出しが `errno` の値をオーバーライドする可能性があります。  
  
 `_wcserror`、および `__wcserror` は、それぞれ、`strerror`、および `_strerror` のワイド文字バージョンです。  
  
 `_strerror`、`_wcserror`、および `__wcserror` は、ANSI 定義の一部ではありません。これらは Microsoft 拡張機能であり、コードの移植性が必要となる場合は使用しないことをお勧めします。 ANSI 互換のために、代わりに `strerror` を使用します。  
  
 エラーの文字列を取得するには、非推奨のマクロ [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) および [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) や非推奨の内部関数 `__sys_errlist` および `__sys_nerr` ではなく、`strerror` または `_wcserror` をお勧めします。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcserror`|`strerror`|`strerror`|`_wcserror`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`strerror`|\<string.h>|  
|`_strerror`|\<string.h>|  
|`_wcserror`, `__wcserror`|\<string.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
 「[perror](../../c-runtime-library/reference/perror-wperror.md)」の例をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror、_wperror](../../c-runtime-library/reference/perror-wperror.md)
