---
title: "_strdate_s、_wstrdate_s | Microsoft Docs"
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
  - "_strdate_s"
  - "_wstrdate_s"
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
  - "api-ms-win-crt-time-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_strdate_s"
  - "wstrdate_s"
  - "_wstrdate_s"
  - "strdate_s"
  - "_tstrdate_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "日付、コピー"
  - "tstrdate_s 関数"
  - "wstrdate_s 関数"
  - "_tstrdate_s 関数"
  - "strdate_s 関数"
  - "コピー (日付を)"
  - "_strdate_s 関数"
  - "_wstrdate_s 関数"
ms.assetid: d41d8ea9-e5ce-40d4-864e-1ac29b455991
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _strdate_s、_wstrdate_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在のシステム日付をバッファーにコピーします。  これらの関数は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[\_strdate、\_wstrdate](../../c-runtime-library/reference/strdate-wstrdate.md) のセキュリティが強化されたバージョンです。  
  
## 構文  
  
```  
errno_t _strdate_s(  
   char *buffer,  
   size_t numberOfElements  
);  
errno_t _wstrdate_s(  
   wchar_t *buffer,  
   size_t numberOfElements  
);  
template <size_t size>  
errno_t _strdate_s(  
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
errno_t _wstrdate_s(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### パラメーター  
 \[出力\] `buffer`  
 書式設定された日付文字列が格納されるバッファーへのポインター。  
  
 \[入力\] `numberOfElements`  
 バッファーのサイズ。  
  
## 戻り値  
 正常に終了した場合は 0 を返します。  エラーが発生した場合の戻り値はエラー コードです。  エラー コードは ERRNO.H で定義されています。この関数によって生じるエラーの正確な情報については以下の表を参照してください。  エラー コードの詳細については、「[errno 定数](../../c-runtime-library/errno-constants.md)」を参照してください。  
  
## エラー条件  
  
|`buffer`|`numberOfElements`|戻り値|`buffer` の内容|  
|--------------|------------------------|---------|------------------|  
|`NULL`|\(任意\)|`EINVAL`|変更されない|  
|`NULL` 以外 \(有効なバッファーを指し示している\)|0|`EINVAL`|変更されない|  
|`NULL` 以外 \(有効なバッファーを指し示している\)|0 \< `numberOfElements` \< 9|`EINVAL`|空の文字列|  
|`NULL` 以外 \(有効なバッファーを指し示している\)|`numberOfElements` \>\= 9|0|「解説」で説明しているように形式が設定された現在の日付|  
  
## セキュリティの問題  
 `numberOfElements` パラメーターが 9 を超える場合に、バッファーに無効な `NULL` 以外の値を渡すと、アクセス違反が生じる結果となります。  
  
 実際の `buffer` のサイズを超えるサイズ値を渡すと、バッファー オーバーランが発生する結果となります。  
  
## 解説  
 これらの関数は、`_strdate` 関数と `_wstrdate` 関数のセキュリティが強化されたバージョンです。  `_strdate_s` 関数は、`buffer` が指すバッファーに現在のシステム日付をコピーします。この日付の形式は `mm`\/`dd`\/`yy` で、`mm` は月を表す 2 桁の数値、`dd` は日を表す 2 桁の数値、および `yy` は年を表す 2 桁の数値です。  たとえば、文字列 `12/05/99` は 1999 年 12 月 5 日を表します。  バッファーの長さは 9 文字以上である必要があります。  
  
 ワイド文字を扱う場合は、`_strdate_s` ではなく `_wstrdate_s` を使用します。`_wstrdate_s` の場合、引数にはワイド文字列を指定します。また戻り値もワイド文字列です。  それ以外では、これらの関数の動作は同じです。  
  
 `buffer` が `NULL` ポインターの場合、または `numberOfElements` が 9 文字未満の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  buffer が `NULL` の場合または`numberOfElements` が 0 以下の場合に実行の継続が許可されると、これらの関数は \-1 を返し、`errno` を `EINVAL` に設定します。`numberOfElements` が 9 未満の場合は、`errno` を `ERANGE` に設定します。  
  
 C\+\+ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる \(サイズの引数を指定する必要がなくなる\) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tstrdate_s`|`_strdate_s`|`_strdate_s`|`_wstrdate_s`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_strdate`|\<time.h\>|  
|`_wstrdate`|\<time.h または\> wchar.h \<\>|  
|`_strdate_s`|\<time.h\>|  
  
## 使用例  
 「[time](../Topic/time,%20_time32,%20_time64.md)」の例を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::DateTime::Parse](https://msdn.microsoft.com/en-us/library/system.datetime.parse.aspx)  
  
## 参照  
 [時間管理](../../c-runtime-library/time-management.md)   
 [asctime\_s、\_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [ctime\_s、\_ctime32\_s、\_ctime64\_s、\_wctime\_s、\_wctime32\_s、\_wctime64\_s](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [gmtime\_s、\_gmtime32\_s、\_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s、\_localtime32\_s、\_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [mktime、\_mktime32、\_mktime64](../Topic/mktime,%20_mktime32,%20_mktime64.md)   
 [time、\_time32、\_time64](../Topic/time,%20_time32,%20_time64.md)   
 [\_tzset](../Topic/_tzset.md)