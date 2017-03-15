---
title: "_ltoa_s、_ltow_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ltoa_s"
  - "_ltow_s"
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
  - "_ltow_s"
  - "_ltoa_s"
  - "ltoa_s"
  - "ltow_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ltoa_s 関数"
  - "_ltow_s 関数"
  - "変換 (整数を)"
  - "変換 (数値の), 文字列への"
  - "長整数型の変換 (文字列に)"
  - "ltoa_s 関数"
  - "ltow_s 関数"
ms.assetid: d7dc61ea-1ccd-412d-b262-555a58647386
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _ltoa_s、_ltow_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列に長整数を変換します。  これらの関数は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[\_ltoa、\_ltow](../Topic/_ltoa,%20_ltow.md) のセキュリティが強化されたバージョンです。  
  
## 構文  
  
```  
errno_t _ltoa_s(  
    long value,  
    char *str,  
    size_t sizeOfstr,  
    int radix   
);  
errno_t _ltow_s(  
    long value,  
    wchar_t *str,  
    size_t sizeOfstr,  
    int radix   
);  
template <size_t size>  
errno_t _ltoa_s(  
    long value,  
    char (&str)[size],  
    int radix   
); // C++ only  
template <size_t size>  
errno_t _ltow_s(  
    long value,  
    wchar_t (&str)[size],  
    int radix   
); // C++ only  
```  
  
#### パラメーター  
 `value`  
 変換される数値。  
  
 `str`  
 結果文字列のバッファー。  
  
 `sizeOfstr`  
 `_ltoa_s` のバイトまたは `_ltow_s`の単語の `str` のサイズ。  
  
 `radix`  
 `value` の基数。  
  
## 戻り値  
 この関数が正常終了した場合は 0、失敗した場合はエラー コードを返します。  
  
## 解説  
 `_ltoa_s` 関数は、`value` の数字を null で終わる文字列に変換し、その結果 \(最大 33 バイト\) を `str` に格納します。  `radix` 引数は、`value` の基数を 2 ～ 36 の範囲で指定します。  `radix` を 10 に設定し、`value` が負の場合、格納される文字列の最初の文字はプラス記号 \(–\) です。  `_ltow_s` は `_ltoa_s`のワイド文字バージョンであり、; `_ltow_s` の 2 番目の引数はワイド文字列です。  
  
 `str` が `NULL` ポインターである場合、または `sizeOfstr` がゼロ以下の場合、これらの関数は [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、これらの関数は長整数の範囲の `value` または `str` が、これらの関数はを返し、`ERANGE`に `errno` を設定した場合は \-1 を返し、`EINVAL`に `errno` を設定します。  
  
 C\+\+ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる \(サイズの引数を指定する必要がなくなる\) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_ltot_s`|`_ltoa_s`|`_ltoa_s`|`_ltow_s`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_ltoa_s`|\<stdlib.h\>|  
|`_ltow_s`|\<stdlib.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 同等の .NET Framework 関数  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [\_itoa、\_i64toa、\_ui64toa、\_itow、\_i64tow、\_ui64tow](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)   
 [\_ultoa、\_ultow](../../c-runtime-library/reference/ultoa-ultow.md)   
 [\_ultoa\_s、\_ultow\_s](../Topic/_ultoa_s,%20_ultow_s.md)